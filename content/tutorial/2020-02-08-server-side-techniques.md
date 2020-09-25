---
title: __Asynchronous
date: '2020-01-15'
draft: true
menu:
  tutorial:
    parent: "CodeStates"
    weight: 7
toc: yes
type: docs
---



## Callback

> Callback Function이란, 그 함수 자체가 다른 함수의 인자(argument)로 넘겨져서 주어진 시점에 실행될 수 있도록 하는 함수입니다. 주어진 시점은 동기적일 수도 있고, 아닐 수도(비동기적) 있습니다. 


* Async JS Callback

> 예제

```js
const printString = (string, callback) => { // 1
    	setTimeout(
    		() => {
    			console.log(string)
    			callback()
    		},
    		Math.floor(Math.random() * 100) + 1
    	)
    }
    
    const printAll = () => { // 2
    	printString("A", () => { // 4
    		printString("B", () => { // 5
    			printString("C", () => {}) // 6
    		})
    	})
    }
    
    printAll() // 3


```



1. `printString` 함수 표현식: 이제 printString 함수를 호출할 수 있습니다.
2. `printAll` 함수 표현식: 이제 printAll 함수를 호출할 수 있습니다.
3. (가장 마지막 줄의) `printAll` 호출
4. `**printString(A, callback)**` 호출

    1) `setTimeout()` 호출 ⇒ (`setTimeout()`의) 첫 번째 인자는 Web or C/C++ API로 가버렸!

    2) Callback Queue에서 기다리던 첫 번째 인자들이 드디어 호출

    3) 첫번째 인자 익명함수 내부의 `console.log()` 호출

    4) `callback()` 호출

5. `printString(A, **printString(B, callback)**)` 호출

    1) `setTimeout()` 호출 ⇒ 첫번째 인자는 Web or C/C++ API로 가버렸!

    2) Callback Queue에서 기다리던 첫번째 인자들이 드디어 호출

    3) 첫번째 인자 익명함수 내부의 `console.log()` 호출

    4) `callback()` 호출

6. `printString(A, printString(B, **printString(C, callback)**))` 호출

    1) `setTimeout()` 호출 ⇒ 첫번째 인자는 Web or C/C++ API로 가버렸!

    2) Callback Queue에서 기다리던 첫번째 인자들이 드디어 호출

    3) 첫번째 인자 익명함수 내부의 `console.log()` 호출

    4) `callback()` 호출
    
    

### Promise

- `Promise`란 비동기 작업을 처리하기 위해 사용되는 객체입니다.
- Callback 방식이 있음에도, Promise가 등장한 이유는 무엇일까요?
    - 바로 콜백 함수를 여러 개 중첩하여 사용했을 때 발생하는 **Callback Hell** 때문입니다. Callback Hell이 발생하면 가독성도 떨어지고, 에러에 대한 처리도 어려워집니다.
    - Callback에 대한 대안으로서, 그간 라이브러리 형식으로 제공되었던 Promise가 ES6에서 공식적으로 도입이 되었습니다. 🎉


### Using Promises


* EX)

```js
let reliable = true
    
    const promiseKept = new Promise(function(resolve, reject){ 
    	if(reliable){
        resolve('약속을 지켰습니다😸')  
    	} else {
        reject('약속을 지키지 않았습니다🙀')  
    	}
    })


```

- 먼저 `new Promise(실행 함수)`를 통해 프로미스 객체를 생성해야 합니다. `Promise` 생성자는 실행 함수를 받는데요. 이 실행 함수를 통해 `resolve`, `reject` 함수를 전달합니다.
- 어떤 비동기 작업이 성공적으로 끝나면, 실행 함수는 `resolve()`를 호출하여 결과를 반환합니다.
- 반대로 오류가 발생하면 `reject()`가 호출되어 프로미스가 거부됩니다. 통상적으로 `reject()`의 인자로는 오류의 원인이 전달되고요.
- Promise에는 **3가지 상태**가 있습니다.
    1. **Pending**: 프로미스가 이행되거나 거부되기 전, 즉 대기 상태.
    2. **Resolved**: 비동기 처리가 성공적으로 완료된 상태
    3. **Rejected**: 비동기 처리가 거부된 상태
- Promise가 성공적으로 이행이 되면, 실행함수의 `resolve` 를 통해 전달한 값을 `then()`으로 받을 수 있습니다. 반대로 거부되면, `reject`를 통해 전달한 오류의 원인을 `catch()` 메서드를 통해 받을 수 있습니다.

    → Promise의 세 가지 상태와 `then` 및 `catch` 메서드를 통해, 비동기 작업의 결과에 따른 분기 처리를 할 수 있습니다.
    
    
```js

let fetchCatData = new Promise((resolve, reject) => {
        request.get('http://www.cat-holic.com/cats',
         (error, response) => {
          if(response){ 
    					resolve(response);
    	      } else {
    	        reject(error);
    	      }                  
    			})
    	});
    
    fetchCatData.then(res=>console.log(res.body))
    		.catch(error=>console.error(error));


```

## Promise Chaining

- `then()`과 `catch()` 메서드는 **프로미스 객체**를 반환합니다. 때문에 프로미스를 연결해서 사용하는 **Promise chaining**이 가능합니다.
- 즉, 어떤 비동기 작업의 결과를 바탕으로 또 다른 비동기 작업을 수행해야 하는 경우, `프로미스_객체.then().then() ...` 과 같은 형식으로 연결하여 처리할 수 있습니다. 이와 같은 패턴 덕분에, Callback을 중첩해서 쓰는 Callback hell에 빠지지 않을 수 있는 것이지요.

![](/tutorial/2020-02-08-server-side-techniques_files/Screen Shot 2020-04-21 at 7.22.15 PM.png)


## Promise.all

* Promise.all 은 무엇일까요?

```js

let promise1 = new Promise((resolve, reject)=>{
      setTimeout(resolve, 5000, 'a');
    })
    
    let promise2 = Promise.resolve('b')
    
    
    Promise.all([promise1, promise2])
    	.then(results=>console.log(results)) // Array['a', 'b']

```

- `Promise.all`은 순회 가능한 객체, 즉 배열을 인자로 받습니다. 이 배열은 프로미스로 이루어져 있는데, 배열에 속한 모든 프로미스가 처리되고 난 뒤, 그 처리 결과를 `resolve`합니다.

- 만약 배열의 프로미스가 하나라도 실패하면, 가장 먼저 실패한 프로미스의 `reject()`가 전달 받은 오류를 `catch()` 메서드로 넘겨주게 됩니다.



## as#ync/await


- **Async function 선언**은 **AsyncFunction** 객체를 반환하는 비동기 함수를 정의합니다. 반환된 AsyncFunction 객체는 호출 시 **Promise**를 반환합니다. **즉, 동기적이던 함수를 비동기적인 함수로 바꿔주는 역할**을 합니다.
- **await** 연산자는 Async function 내부에서만 사용할 수 있습니다. await는 (보통은 강제로)비동기화 된 함수에서, 일부 비동기 작업을 동기적으로 실행될 수 있게 합니다. 즉, 비동기적인 함수 실행 순서를 일부 동기적으로 하게 합니다, 더 쉽게 말하면, **비동기 함수의 작업이 끝날 때까지 기다려줍니다.**


* .then 문법을 

```js

- 아래와 같이 작성된 `.then` 문법을

        function getProcessedData(url) {
          return downloadData(url) // returns a promise
            .catch(e => {
              return downloadFallbackData(url) // returns a promise
            })
            .then(v => {
              return processDataInWorker(v); // returns a promise
            });
        }
```
async / await으로 변경 가능합니다! 🎉


```js


        async function getProcessedData(url) {
          let v;
          try {
            v = await downloadData(url); 
          } catch (e) {
            v = await downloadFallbackData(url);
          }
          return processDataInWorker(v);
        }

```

### Why Do We ❤️async/await

- 위의 예제 코드에서 await가 없었다면 `downloadData`, `downloadFallbackData`, `processDataInWorker` 함수가 모두 동시에, 비동기적으로 실행되어 각자의 역할에 충실할 수 없었을 것입니다.
    1. `downloadData` 함수를 통한 데이터 다운로드가 수행되지 못하여 `v`에 값이 제대로 할당되지 못했을 것이고, 
    2. 에러 핸들링을 위한 함수 `downloadFallbackData`가 같이 실행되어 불필요한 리소스를 사용하고, 잘못된 값을 할당할 것이고
    3. 실제 작업( `processDataInWorker`) 또한 잘못된 인자 `v`를 받아 실행에 문제가 생길 것입니다.
    


## fs #module

### Waht is fs module ?

![](/tutorial/2020-02-08-server-side-techniques_files/Screen Shot 2020-04-21 at 7.27.08 PM.png) What is fs module?

- node.js의 fs module은 OS(Windows, Linux, Unix(macOS))의 file system과 상호작용을 합니다. fs module을 사용하여 서버의 local storage에 접근하고 특정 파일의 생성, 읽기, 갱신, 삭제 (CRUD)가 가능합니다.

![](/tutorial/2020-02-08-server-side-techniques_files/Screen Shot 2020-04-21 at 7.28.23 PM.png)


- 다른 node.js 모듈처럼, fs 모듈의 메서드에서도 보통 첫번째 인자로 에러 객체를 받습니다. 에러가 생기는 경우, 에러 객체 자리에 `null`이나 `undefined`가 아닌 에러 객체가 들어가도록 node.js가 동작합니다. 에러가 없는 경우, 나머지 인자들을 기반으로 원하는 작업을 수행할 수 있습니다.

- 아래의 코드는 각각의 비동기 fs module 메소드를 실행시키기 때문에, **순서대로 작동을 하지 않을 가능성**이 높습니다. (순서대로 실행이 될 수도 있습니다만, 권장되지 않습니다.)

```js
     
        fs.rename('/tmp/hello', '/tmp/world', (err) => {
          if (err) throw err;
          console.log('renamed complete');
        });
        fs.stat('/tmp/world', (err, stats) => {
          if (err) throw err;
          console.log(`stats: ${JSON.stringify(stats)}`);
        }); // I'm out of order...

```
- 우리가 의도한 순서대로 메서드가 작동하도록 하려면 **Callback**, **Promise API**, **Async/Await**을 사용해야 합니다.

```js

        fs.rename('/tmp/hello', '/tmp/world', (err) => {
          if (err) throw err;
          fs.stat('/tmp/world', (err, stats) => {
            if (err) throw err;
            console.log(`stats: ${JSON.stringify(stats)}`);
          });
        }); // now I'm in order !
```


## Request

> The request module is by far the most popular (non-standard) Node package for making HTTP requests. Actually, `it is really just a wrapper around Node's built in http module`, so you can achieve all of the same functionality on your own with http, but request just makes it a whole lot easier.


## HTTP VS HTTPS?

- **HTTP(Hypertext transfer protocol)**는 클라이언트-서버 간에 어떤 문서를 전송하고 받기 위한 통신 규약입니다. 그러나 HTTP에서 이루어지는 통신은 암호화되지 않았으므로 누구나 엿볼 수 있고, 또 통신을 요청하는 상대방에 대한 확인이 없기 때문에 보안에 결함이 있었습니다.

- 이러한 결함을 보완하여 등장한 것이 HTTPS(Hypertext transfer protocol over secure socket layer)입니다.


[I'm an inline-style link](https://www.geeksforgeeks.org/difference-between-http-and-https)


