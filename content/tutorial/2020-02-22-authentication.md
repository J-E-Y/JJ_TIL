---
title: __Authentication
date: '2020-01-15'
draft: true
menu:
  tutorial:
    parent: "CodeStates"
    weight: 9
toc: yes
type: docs
---



## Cookie & Session

- HTTP의 stateless하고 connectionless한 특성 때문에, 서버와 클라이언트는 연속적으로 통신을 할 수 없습니다. 때문에 같은 유저가 여러 번 요청을 보내더라도, 서버는 그 유저와의 통신이 이전에도 있었던지 알 길이 없습니다.
- 만약 쿠키와 세션이 없는 가운데 권한 부여(authorization)을 구현하려 한다면, 새로운 요청이 있을 때마다 매번 인증(authentication) 작업을 해 주어야 할 것입니다. 이에 대한 보완책이 바로 쿠키(cookie)와 세션(session)입니다.

> 세션과 쿠키는 별개의 개념이 아닙니다! 세션 또한 쿠키를 기반으로 합니다. 서버에서 세션 id가 생성이 되면, 응답 시 쿠키에 세션 id를 실어 클라이언트에 전달합니다.




## Cookie 


- 서버가 사용자 브라우저 위치에 어떤 정보를 저장하고 불러오는 수단입니다.
- 특정 호스트에서 생성된 쿠키는 이후 모든 요청마다 서버로 전송됩니다.
- 이름, 값, 만료 날짜, 경로 정보 등으로 구성되어 있습니다.
- 필요할 때 참조나 재사용이 가능합니다.
- 4KB 이하 저장 가능


## Session

- 일정 시간 동안 같은 사용자로부터 오는 요구를 하나의 상태로 보고, 그 상태를 일정하게 유지시키는 수단.
- 여기서 일정 시간이란 방문자가 웹 브라우저를 통해 웹 서버에 접속한 시점으로부터 웹 브라우저를 종료하여 연결을 끝내는 시점을 말합니다.
- 웹 서버는 각각의 요청에 대하여 고유한 식별자인 session ID를 부여하여 클라이언트를 구별합니다.
- 웹 서버의 세션 스토리지에 세션 정보가 저장됩니다.
- 데이터 저장 제한 X
- 통신에만 발동되는 쿠키, 세션 쿠키 라고도 합니다.


## Token

![](/tutorial/2020-02-22-authentication_files/Screen Shot 2020-04-22 at 6.43.29 PM.png)

[reference](https://medium.com/@peterchang_82818/difference-session-cookie-token-vs-token-authentication-based-traditional-store-a177e8474ee3)


- 인증을 위해 사용되는 암호화 된 문자열입니다.
- 토큰 인증에서, 서버는 JWT(JSON Web Token)을 생성하여 클라이언트에 보냅니다.
- 클라이언트는 JWT를 로컬 스토리지 또는 쿠키에 저장하고, 세션과 마찬가지로 사용자가 보내는 모든 요청에 포함됩니다.
- 세션 인증에서 서버가 세션 정보를 관리했던 것과 달리, 서버는 JWT를 저장하지 않습니다! 다만 토큰이 유효한지 여부만을 확인할 뿐입니다.
- JWT를 추가적으로 저장할 공간이 필요 없기 때문에, 서비스가 커진다고 하여 서버에 추가적인 부하가 발생하지 않습니다. 더 효율적입니다!




## Crypto?

- node.js의 내장 모듈로서 암호화와 관련된 일을 처리합니다.
- crypto 모듈을 사용하여 해싱과 솔팅을 구현하는 방법을 다뤄 보도록 하겠습니다.

## Hashing?

- 하나의 문자열을 다른 값이나 키로 변환하는 **단방향 암호화** 기법입니다.
- 데이터 변환은 해시 함수를 통해서 일어납니다. 해시 함수는 임의의 길이의 데이터를 고정된 길이의 데이터로 매핑하는데, 알고리즘마다 매핑된 값의 길이가 다릅니다. 예를 들어 `SHA256`은 64, `SHA512`는 128입니다.
- 앞에서 해시 자료구조를 배웠을 때 다뤘던 것처럼, 해시 함수는 **같은 값을 넣으면 늘 같은 값을 반환**해야 합니다. 때문에 여러 암호를 모은 데이터베이스를 기반으로, 암호를 유추해 낼 위험이 있습니다.
- 또한 `SHA256`, `MD5`등 알고리즘 자체는 이미 널리 공개가 되어 있습니다. 때문에 이미 보안이 뚫린 알고리즘(MD5, SHA1 등)도 있습니다.
- 해싱의 한계를 극복하기 위해, 우리는 해시 함수를 여러 번 반복하여 적용하거나 솔트(salt)를 활용할 수 있습니다.
- Crypto로 해싱을 구현해 보겠습니다.

```js

    const crypto = require('crypto');
    
    const hashClass = crypto.createHash('sha512');
    // sha512 알고리즘을 사용하는 해시 class를 만든다.
    const hashedValue = hashClass.update('get coding').digest('base64');
    // 'get coding' 이라는 문자열을 해싱하겠다는 의미. 
    // 해싱한 문자열을 base64로 인코딩하여 다이제스트를 반환한다. 
    // 다이제스트란 해시를 통해 얻어낸 암호화된 값을 뜻한다.

```


양방향 암호화도 있습니다! 이 또한 crypto로 구현할 수 있으니 관심이 있다면 `cipher`에 대해 알아봅시다. 

## Salting?

- 솔팅(salting)이란 **암호화해야 하는 값에 어떤 별도의 값(salt)을 추가해서 결과를 변형**하는 것을 뜻합니다.
- crypto 모듈에서는 pbkd2(Password-Based Key Derivation Function 2)라는 비동기 메서드를 통해 솔트를 적용할 수 있습니다

```js

    const crypto = require('crypto')
    // password, salt, iteration, 바이트 길이, 알고리즘, 콜백을 인자로 받는다.
    crypto.pbkdf2('생선구이', '소금', 123456, 64, 'sha512', (err, derivedKey)=>{ 
    	if(err) throw err; 
    	console.log(derivedKey.toString('hex')) // hex로 인코딩한다.
    })
    
```

- 만약 솔트 값이 고정되어 있다면, 솔트 값이 유출되기 쉽겠죠? 따라서 암호화를 할 때마다 랜덤한 솔트 문자열을 생성한다면 좋을 것입니다. 이와 관련하여 crypto에서 사용할 수 있는 메서드가 바로 `randomBytes` 입니다.

```js

        // 랜덤한 솔트를 64바이트 길이로 생성한다. 버퍼 형식으로 반환된다.
        crypto.randomBytes(64, (err, buf)=>{ 
        // 랜덤하게 생성된 버퍼를 base64를 통해 인코딩한다.
        	const randomlyGeneratedSalt = buf.toString('base64') 
        	crypto.pbkdf2('꽁치구이', randomlyGeneratedSalt, 123456, 64, 'sha512', (err, derivedKey)=>{
        	 if(err) throw err; 
        		console.log(derivedKey.toString('hex')) })
        })
```
- 랜덤으로 생성된 솔트는 해싱된 값(derivedKey)와 반드시 함께 저장해야 한다는 점을 명심해 주세요.

솔티드 해시 외에도 HMAC이라는 방법을 사용하여 보안을 강화할 수도 있습니다. 크립토의 `createHMA` 메서드와 함께 알아보세요.



