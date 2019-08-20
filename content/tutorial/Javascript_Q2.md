---
title: Crucial_Points
date: 2019-6
draft: true
menu:
  tutorial:
    parent: "Javascript"
    weight: 11
toc: true
type: docs
---

![](/tutorial/Javascript_Dictionary_files/javascriptt-light_870x220.png)

---
## Scope 
---

**스코프란?**

>자바스크립트에서 스코프란 어떤 변수들에 접근할 수 있는지를 정의합니다.

>스코프엔 두 가지 종류가 있습니다. 전역 스코프와 지역 스코프로 나뉩니다.


**전역_스코프**

```js
let greeting = 'Hello John' // 박에서 변수가 선언됨

function marcusHello () {
  console.log(greeting)
}

console.log(greeting) // 'Hello John!' 

sayHello() // 'Hello John!' 

```

**지역_스코프**

```js

function marcusHello () {
  
  let greeting = 'Hello John!' // 안에서 변수가 선언됨
  console.log(greeting)
}

marcusHello() // 'Hello John!!'

console.log(x) // Error, hello is not defined

```



---
## Closure
---

* description

> 클로저는 독립적인 (자유) 변수를 가리키는 함수이다. 또는, 클로저 안에 정의된 함수는 만들어진 환경을 ‘기억한다’.

> 내부함수는 외부함수의 지역변수에 접근 할 수 있는데 외부함수의 실행이 끝나서 외부함수가 소멸된 이후에도 내부함수가 외부함수의 변수에 접근 할 수 있다. 이러한 메커니즘을 클로저라고 한다.


* 일반적인 함수

```js

let addTo = function (passed) {

	let inner = 2;
	return passed + inner; 3 + 2 

};

console.log( addTo(3) ) //  5

```

* 이것이 클로저

```js

let passed = 3;  // 함수 밖에 변수를 선언한다 

let addTo = function () { //  parameter 를 외부에서가져온다. 

	let inner = 2;
	return passed + inner; 3 + 2  // 

};

console.log( addTo() ) //  5



```
---
##커링 (currying)
---

> 호출된 함수의 매개변수로 동적으로 새로운 함수를 생성하여 반환하는 패턴을 커링이라 한다.

>호출하는 함수의 인자값이 비슷하다면 커링을 사용하는 것이 효율적이다.

> 클로저를 이용해 함수의 인자를 미리 등록해두는 것

```js

function func(a) {
    return function(b) { // 내부 함수, 즉 클로저인 익명 함수 반환
        return a + b;
    }
}
var currying = func(5);
var result = currying(5); 
console.log(result);
// 또는 아래처럼 호출
var result2 = func(5)(7); 
console.log(result2);

https://mylife365.tistory.com/320 

```






