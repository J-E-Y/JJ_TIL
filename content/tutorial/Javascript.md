---
title: Javascript
date: 2019-04-29
draft: true
menu:
  tutorial:
    name: Javascript
    weight: 4
toc: true
type: docs
---

---
## **1. showing data in browser**
---


```javascript

<!DOCTYPE html>
<html>
<body>
    <h2>Javascript_note</h2>
    <p id="demo">what time is it now ?</p>

</body>
</html>

```

```javascript

var p = document.getElementById('demo');
var demo = document.getElementById('demo');
demo.innerHTML = Date();

```

```javascript

demo.style.color = "red";
demo.style.background = "black";

```

```javascript

var demo = document.getElementById('demo');
var size = 10;
function big() {
    demo.style.fontSize = size + "px";
    size = size + 1;            
}
var tid = setInterval(big, 100);

```


---
## **2. data type**
---


##### 자료형이란?

> 어떤 종류의 데이터를 사용하는 것이지 컴퓨터에게 알려주는 것
자료형마다 사용 가능한 연산자(Operator)를 따로 가지고 있습니다!
자료형이 같아야 연산을 할 수 있습니다!

##### 자료형의 종류

- Number :숫자
- String :문자
- Boolean :true and False
- Null : 값이 비어있다
- Undefined :값이 정의되지 않았다
- Object :



##### Number type


* ex)
```
var firstNum = 10;     // 소수점을 사용하지 않은 표현
var secondNum = 10.00; // 소수점을 사용한 표현
var thirdNum = 10e6;   // 10000000
var fourthNum = 10e-6; // 0.00001
```



##### String (문자열)

```
"I am String";
"Hello " + "world";
```

##### Boolean (불리언)

```
true;
false;
5 > 3;
5 == 5;
5 > 5;
```

##### The typeof Operator: 데이터유형을 알려주는 중요한 연산자!

```
typeof 10;        // number 타입
typeof "문자열";  // string 타입
typeof true;      // boolean 타입
typeof undefined; // undefined 타입
typeof null;      // object 타입

```

##### symbol (심볼)

* 심볼 타입은 ECMAScript 6부터 새롭게 추가된 타입이다.
심볼은 유일하고 변경할 수 없는 타입으로, 객체의 프로퍼티를 위한 식별자로 사용할 수 있다.

* ex) 

```
var sym = Symbol("javascript");  // symbol 타입
var symObj = Object(sym);        // object 타입
```

##### object (객체)

* 자바스크립트의 기본 타입은 객체(object)이다. 객체(object)란 실생활에서 우리가 인식할 수 있는 사물로 이해할 수 있다. 객체는 여러 프로퍼티(property)나 메소드(method)를 같은 이름으로 묶어놓은 일종의 집합체이다.

* ex)

```
var dog = { name: "해피", age: 3 }; // 객체의 생성
// 객체의 프로퍼티 참조
document.getElementById("result").innerHTML =
    "강아지의 이름은 " + dog.name + "이고, 나이는 " + dog.age + "살 이다.";
```



---
## **3. Variable**
---

> JavaScript variables are containers for storing data values.

>변수 이름 잘 짓기 변수의 이름은 매우 중요합니다. 일반적으로 소문자로 시작, 영어, 숫자, _를 주로 사용합니다. 카멜 케이스나 스네이크 케이스 


* How to crate Variablie there are two ways we tend to use 

```
1. camelCase

>>>numPeople

2. PascalCase

>>>num_people
```




---
## **operator**
---


##### Logical operator (논리연산자)


* &&	>>>논리식이 모두 참이면 참을 반환함. (논리 AND 연산)
* ||	>>>논리식 중에서 하나라도 참이면 참을 반환함. (논리 OR 연산)
* !	  >>>논리식의 결과가 참이면 거짓을, 거짓이면 참을 반환함. (논리 NOT 연산)

```
&& 는 and 

|| 는 or

! 는 Not
```

##### increment/decrement operator (증감연산자)

* 증감 연산자는 피연산자를 1씩 증가 혹은 감소시킬 때 사용하는 연산자이다.이 연산자는 피연산자가 단 하나뿐인 단항 연산자이다.

* ex)
```
var a;
a++;
a = 0;
a++;
a--;
```

##### comparison operator (비교 연산자)

```
==	왼쪽 피연산자와 오른쪽 피연산자의 값이 같으면 참을 반환함.
===	왼쪽 피연산자와 오른쪽 피연산자의 값이 같고, 같은 타입이면 참을 반환함.
!=	왼쪽 피연산자와 오른쪽 피연산자의 값이 같지 않으면 참을 반환함.
!==	왼쪽 피연산자와 오른쪽 피연산자의 값이 같지 않거나, 타입이 다르면 참을 반환함.
>	왼쪽 피연산자의 값이 오른쪽 피연산자의 값보다 크면 참을 반환함.
>=	왼쪽 피연산자의 값이 오른쪽 피연산자의 값보다 크거나 같으면 참을 반환함.
<	왼쪽 피연산자의 값이 오른쪽 피연산자의 값보다 작으면 참을 반환함.
<=	왼쪽 피연산자의 값이 오른쪽 피연산자의 값보다 작거나 같으면 참을 반환함.
```



---
## **4. length,contral string,slice alert,prompt**
---

##### 문자열의 길이 구하기

```
var a = "hello"
a.length;
. 연산자는 객체의 속성을 가져올 때 사용하는 연산자. 나중에 다시 설명할 예정입니다.
```



##### 문자열 간단히 조작하기

```
var a = "KheLLo"
a[0];
a[1] = "H"; //안 됨


a.slice(1,4);
a.toUpperCase();
a.toLowerCase();

```

##### console.log()

* 개발자 콘솔에 뭔가를 찍어주는 메서드입니다.

```
var a = 1;
var b = "더하기";
var c = 2;
console.log(a + " " + b + " " + c + " = " + a + c);
```


##### alert() 과 prompt() 사용해 보기

```
var ans = prompt("How are you?");
alert(ans);
```

 
 