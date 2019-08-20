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

![](/tutorial/Javascript_Dictionary_files/javascriptt-light_870x220.png)

---
## **1.data type**
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
- symbol(new in ECMAScript 6)
and Object :


#####  1. Number type (숫자)


* ex)
```
var firstNum = 10;     // 소수점을 사용하지 않은 표현
var secondNum = 10.00; // 소수점을 사용한 표현
var thirdNum = 10e6;   // 10000000
var fourthNum = 10e-6; // 0.00001
```

* length

```
var a = "hello"
a.length;
```



* slice :자르기 

```
var a = "KheLLo"
a[0];
a[1] = "H"; //안 됨


a.slice(1,4);
a.toUpperCase(); : 대문자로 바뀐
a.toLowerCase(); : 소문자로 바뀐다

```


##### 2. String (문자열)

```
"I am String";
"Hello " + "world";
```

##### 3. Boolean (불리언)

```
true;
false;
5 > 3;
5 === 5;
5 > 5;
```

##### 4. The typeof Operator: 데이터유형을 알려주는 중요한 연산자!

```
typeof 10;        // number 타입
typeof "문자열";  // string 타입
typeof true;      // boolean 타입
typeof undefined; // undefined 타입
typeof null;      // object 타입

```

##### 5. symbol (심볼)

* 심볼 타입은 ECMAScript 6부터 새롭게 추가된 타입이다.
심볼은 유일하고 변경할 수 없는 타입으로, 객체의 프로퍼티를 위한 식별자로 사용할 수 있다.

* ex) 

```
var sym = Symbol("javascript");  // symbol 타입
var symObj = Object(sym);        // object 타입
```

##### 6. object (객체)

* 자바스크립트의 기본 타입은 객체(object)이다. 객체(object)란 실생활에서 우리가 인식할 수 있는 사물로 이해할 수 있다. 객체는 여러 프로퍼티(property)나 메소드(method)를 같은 이름으로 묶어놓은 일종의 집합체이다.

* ex)

```
var dog = { name: "해피", age: 3 }; // 객체의 생성
// 객체의 프로퍼티 참조
document.getElementById("result").innerHTML =
    "강아지의 이름은 " + dog.name + "이고, 나이는 " + dog.age + "살 이다.";
```

---
## **2.Variable**
---

##### Using Variables

```
var x = 10;

x + 5 ; // => 15

x ; // => 10

once we have created our variables,
we can use their name as a substitute for their value elsewhere in our program.


```


##### Declaring a variable without a Vaue


```

Creating a variable in JavaScript is called "declaring" a variable.

1.var carName;
After the declaration, the variable has no value (technically it has the value of undefined).


To assign a value to the variable, use the equal sign:

2. carName = "Volvo";   // carName 를 Volvo 로 변경할때 var 없이 만든다 cos 먼저 선언을 했기 때문이다. 

2. var carName = "Volvo";


```


##### Changing a Variable’s value 


```

var pokemon = charmander

pokemon = heelo


Notice that When you change the value of a variable, "you don’t need to use the var keyword"The var keyword is only needed for creating new variables.


```

##### variable scope 변수의 유효 범위


* local variable 지역 변수

>Variables declared inside a function body are in the Local scope.

>지역 변수(local variable)란 함수 내에서 선언된 변수를 가리킨다.
이러한 지역 변수는 변수가 선언된 함수 내에서만 유효하며, 함수가 종료되면 메모리에서 사라진다.함수의 매개변수 또한 함수 내에서 정의되는 지역 변수처럼 동작한다.


* ex 1-1

```
var greeting = "Hello";

function greetSomeone() {
	var firstName = "john"
	return greeting + " " + firstName;
}

greetSomeone
firstName; // = > Error


Function(greetSomeone) is working but "firstName"" is Error Because we declared our name variable inside the scope of our greetSomeone function.


```





* global variable  전역 변수



>Variables declared outside a function body are in the global scope.


>전역 변수(global variable)란 함수의 외부에서 선언된 변수를 가리킨다.
이러한 전역 변수는 프로그램의 어느 영역에서나 접근할 수 있으며, 웹 페이지가 닫혀야만 메모리에서 사라진다.



* ex 1-2

```

"But!!!!!!! if you do this it works well"!!

var greeting = "Hello";
var firstName = "john"

function greetSomeone() {
	firstName = "JJ"
	return greeting + " "+ firstName;
}


firstNmae // = > JJ

Because you changed a variable the was defined in an outer scope

```




---
## **3.Operator**
---


##### arithmetic operator (산술 연산자)


```
+	왼쪽 피연산자의 값에 오른쪽 피연산자의 값을 더함.
-	왼쪽 피연산자의 값에서 오른쪽 피연산자의 값을 뺌.
*	왼쪽 피연산자의 값에 오른쪽 피연산자의 값을 곱함.
/	왼쪽 피연산자의 값을 오른쪽 피연산자의 값으로 나눔.
%	왼쪽 피연산자의 값을 오른쪽 피연산자의 값으로 나눈 후, 그 나머지를 반환함

```
* ex

```
var x = 10, y = 4;
document.write(x + y + "<br>"); // 14
document.write(x - y + "<br>"); // 6
document.write(x * y + "<br>"); // 40
document.write(x / y + "<br>"); // 2.5
document.write(x % y);          // 2

```

#####  assignment operator (대입 연산자)


```
=	왼쪽 피연산자에 오른쪽 피연산자의 값을 대입함.
+=	왼쪽 피연산자의 값에 오른쪽 피연산자의 값을 더한 후, 그 결과 값을 왼쪽 피연산자에 대입함.
-=	왼쪽 피연산자의 값에서 오른쪽 피연산자의 값을 뺀 후, 그 결과 값을 왼쪽 피연산자에 대입함.
*=	왼쪽 피연산자의 값에 오른쪽 피연산자의 값을 곱한 후, 그 결과 값을 왼쪽 피연산자에 대입함.
/=	왼쪽 피연산자의 값을 오른쪽 피연산자의 값으로 나눈 후, 그 결과 값을 왼쪽 피연산자에 대입함.
%=	왼쪽 피연산자의 값을 오른쪽 피연산자의 값으로 나눈 후, 그 나머지를 왼쪽
피연산자에 대입함.

```
* ex


```
var x = 10, y = 10, z = 10;
x = x - 5;
y -= 5; // y = y - 5 와 같은 표현임.
z =- 5; // z = -5 와 같은 표현임.

```
##### increment and decrement operator ( 증감 연산자 )

```
++x	먼저 피연산자의 값을 1 증가시킨 후에 해당 연산을 진행함.
x++	먼저 해당 연산을 수행하고 나서, 피연산자의 값을 1 증가시킴.
--x	먼저 피연산자의 값을 1 감소시킨 후에 해당 연산을 진행함.
x--	먼저 해당 연산을 수행하고 나서, 피연산자의 값을 1 감소시킴.

```

* ex

```
var x = 10, y = 10;
document.write((++x - 3) + "<br>"); // x의 값을 우선 1 증가시킨 후에 3을 뺌.
document.write(x + "<br>");         // 11
document.write((y++ - 3) + "<br>"); // 먼저 y에서 3을 뺀 후에 y의 값을 1 증가시킴.
document.write(y);                  // 11
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

* ex

```

var x = 3, y = 5;
var a = "abc", b = "bcd";
document.write((x > y) + "<br>");  // y의 값이 x의 값보다 크므로 false
document.write((a <= b) + "<br>"); // 알파벳 순서상 'a'가 'b'보다 먼저 나오므로 'a'가 'b'보다 작음.
document.write(x < a);             // x의 값은 숫자이고 a의 값은 문자열이므로 비교할 수 없음.

```

##### Logical operator (논리연산자)


```
&& 는 and 

|| 는 or

! 는 Not
```


##### bitwise operator (비트 연산자)


```

&	대응되는 비트가 모두 1이면 1을 반환함. (비트 AND 연산)
|	대응되는 비트 중에서 하나라도 1이면 1을 반환함. (비트 OR 연산)
^	대응되는 비트가 서로 다르면 1을 반환함. (비트 XOR 연산)
~	비트를 1이면 0으로, 0이면 1로 반전시킴. (비트 NOT 연산)
<<	지정한 수만큼 비트를 전부 왼쪽으로 이동시킴. (left shift 연산)
>>	부호를 유지하면서 지정한 수만큼 비트를 전부 오른쪽으로 이동시킴. (right shift 연산)
>>>	지정한 수만큼 비트를 전부 오른쪽으로 이동시키며, 새로운 비트는 전부 0이 됨.

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




##### typeof 연산자

> typeof 연산자는 피연산자의 타입을 반환한다.

```
숫자, NaN	"number"
문자열	"string"
true, false	"boolean"
null	"object"
undefined	"undefined"
함수	"function"
함수가 아닌 객체	"object"
```

* ex 

```
typeof "문자열"   // string
typeof 10         // number
typeof NaN        // number
typeof false      // boolean
typeof undefined  // undefined
typeof new Date() // object
typeof null       // object
```

##### ternary operator (삼항 연산자)

>삼항 연산자는 유일하게 피연산자를 세 개나 가지는 조건 연산자이다.

* ex

```
var x = 3, y = 5;
var result = (x > y) ? x : y   // x가 더 크면 x를, 그렇지 않으면 y를 반환함.
document.write("둘 중에 더 큰 수는 " + result + "이다.");

삼항 연산자는 짧은 if / else 문 대신 사용할 수 있으며, 코드를 간결하게 만들어 준다.
```


##### delete 연산자

>delete 연산자는 피연산자인 객체, 객체의 프로퍼티(property) 또는 배열의 요소(element) 등을 삭제해 준다.

피연산자가 성공적으로 삭제되었을 경우에는 참(true)을 반환하고, 삭제하지 못했을 경우에는 거짓(false)을 반환한다.
이 연산자는 피연산자가 단 하나뿐인 단항 연산자이며, 피연산자의 결합 방향은 오른쪽에서 왼쪽이다.



##### 쉼표 연산자

>쉼표 연산자를 for 문에서 사용하면, 루프마다 여러 변수를 동시에 갱신할 수 있다.


> 루프마다 i의 값은 1씩 증가하고, 동시에 j의 값은 1씩 감소함. 

```
for (var i = 0, j = 9; i <= j; i++, j--) {
    document.write("i의 값은 " + i + "이고, j의 값은 " + j + "이다.<br>");
}
```


* ex

```

var arr = [1, 2, 3];          // 배열 생성
delete arr[2];                // 배열의 원소 중 인덱스가 2인 요소를 삭제함.
document.write(arr + "<br>"); // [1, 2, ]
// 배열에 빈자리가 생긴 것으로 undefined 값으로 직접 설정된 것은 아님.
document.write(arr[2] + "<br>");
// 배열의 요소를 삭제하는 것이지 배열의 길이까지 줄이는 것은 아님.
document.write(arr.length);

```



##### instanceof 연산자

>instanceof 연산자는 피연산자인 객체가 특정 객체의 인스턴스인지 아닌지를 확인해 준다.
피연산자가 특정 객체의 인스턴스이면 참(true)을 반환하고, 특정 객체의 인스턴스가 아니면 거짓(false)을 반환한다.
이 연산자는 두 개의 피연산자를 가지는 이항 연산자이며, 피연산자들의 결합 방향은 왼쪽에서 오른쪽이다.

* ex

```
var str = new String("이것은 문자열이다.");
 
str instanceof Object;  // true
str instanceof String;  // true
str instanceof Array;   // false
str instanceof Number;  // false
str instanceof Boolean; // false

```

##### void 연산자

>void 연산자는 피연산자로 어떤 타입의 값이 오던지 상관없이 언제나 undefined 값만을 반환한다.
이 연산자는 피연산자가 단 하나뿐인 단항 연산자이며, 피연산자의 결합 방향은 오른쪽에서 왼쪽이다.

* ex

```
<a href="javascript:void(0)">이 링크는 동작하지 않는다.</a>
 
<a href="javascript:void(document.body.style.backgroundColor='yellow')">
    이 링크도 동작하지 않지만, HTML 문서의 배경색을 바꿔준다.
</a>

```

---
## **4.Conditional**
---

```

if 문
if / else 문
if / else if / else 문
switch 문

```
 
##### if 문

```
if (표현식) {
    표현식의 결과가 참일 때 실행하고자 하는 실행문;
}
```

* ex

```
var x = 10, y = 20;
if (x == y) {
    document.write("x와 y는 같다.");
}
if (x < y) {
    document.write("x가 y보다 작다.");
}
if (x > y) // 실행될 실행문이 한 줄뿐이라면 중괄호({})를 생략할 수 있음.
    document.write("x가 y보다 크다.");
```



##### else 문

```

if (표현식) {
    표현식의 결과가 참일 때 실행하고자 하는 실행문;
} else {
    표현식의 결과가 거짓일 때 실행하고자 하는 실행문;
}
else 문을 사용하면 앞의 예제를 좀 더 직관적으로 표현할 수 있다.

```


* ex

```
var x = 10, y = 20;
if (x == y) {
    document.write("x와 y는 같다.");
} else {
    if (x < y)
        document.write("x가 y보다 작다.");
    else // 실행될 실행문이 한 줄뿐이라면 중괄호({})를 생략할 수 있음.
        document.write("x가 y보다 크다.");
}


```

##### else if 문

```

if (표현식1) {
    표현식1의 결과가 참일 때 실행하고자 하는 실행문;
} else if (표현식2) {
    표현식2의 결과가 참일 때 실행하고자 하는 실행문;
} else {
    표현식1의 결과도 거짓이고, 표현식2의 결과도 거짓일 때 실행하고자 하는 실행문;
}

```

* ex

```
var x = 10, y = 20;
if (x == y) {
    document.write("x와 y는 같다.");
} else if (x < y) {
    document.write("x가 y보다 작다.");
} else { // x > y인 경우
    document.write("x가 y보다 크다.");
}

```




* switch-case

> if 와 else if를 반복적으로 써야 하는 상황을 피하게 해 줍니다.


```
var value;
switch(value) {
    case 값1:
    //value == 값1일 경우 실행할 코드
    break;
    case 값2:
    //value == 값2일 경우 실행할 코드
    break;
    //...
    default:
    //위쪽에 해당되지 않는 경우 실행할 코드
}

```

>점수가 10점이면 A, 9점이면 B, 그 외에는 C를 출력하는 코드를 작성하세요.

```
if로 구현
var score = prompt('점수를 입력하세요');
if (score === 10) {
    console.log('A');
} else if (score == 9) {
    console.log('B');
} else {
    console.log('C');
}

```


```

switch-case 로 구현
var score = prompt('점수를 입력하세요');
switch (score) {
    case 10:
    console.log('A);
    break;
    case 9:
    console.log('B');
    break;
    default:
    console.log('C');
}

```










---
## **5.Loops**
---

```

while 문
do / while 문
for 문
for / in 문
for / of 문

```

##### while

```
while (표현식) {
    표현식의 결과가 참인 동안 반복적으로 실행하고자 하는 실행문;
}
```

* note

> while 문 만들때는 변수를 미리 만들어 줘야 한다. 

```
var n ;
var n = 0;
var n = 1;

```

* ex 1-1

```
var n = 1;
while(n <= 100) {    
    console.log("Hi " + n);
    n++;
}

```


* ex 1-2


```
while 문을 사용해서 1에서 100까지의 합을 구해 봅시다.
자주 사용하는 패턴
var i = 0; // 1 변수 초기화
while (i <= 100) { // 2 변수 검사
  console.log(i); // 3 코드 다하고나서 
  i++; //  4 하나씩 증가
}

그래서 for가 등장함
위의 while 코드와 완전히 똑같음
for (var i = 0; i <= 100; i++) {
  console.log(i);
}
```

* ex gugudan with while

```

    <script>
       
        var strN = Number(prompt("input which gugudan"));
        var i = 1;
        document.write("gugudan" + strN + "<br>");
        while (i < 10) {
            document.write(strN + " * " + i + " = " + strN * i + " <br> " );
            i++;
        }
   
    </script>

```


##### for 문


```
for (초기식; 표현식; 증감식) {
    표현식의 결과가 참인 동안 반복적으로 실행하고자 하는 실행문;
}
 
```

* ex 1-1

```

for (var i = 1; i < 10; i++) {
    document.write(i + "<br>");
}

```

* ex 1-2 gugudan with for

```
    <script>
    
       var strN = Number(prompt("input which dan?"));
       document.write("gugudan" + strN + "<br>");
       for (var i = 1; i < 10; i++) {
           document.write(strN + " * " + i + " = " + strN * i + "<br>");
       }
    
    </script>

```

* ex 1-3 gugudan with button


```

    <P>사용자가 2 이상, 9 이하가 아닌 값을 입력하는 경우 "2이상, 9이하의 값만      입력할 수 있습니다."라는 메시지를 출력한다.</P>
    <script>
        
        var strN;
        while (true){
            strN = Number(prompt("input which dan from 2 dan to 9 dan"))
            if (strN < 2 || strN > 9){
                console.log("this is not available");
            } else {
                document.write("gugudan" + strN + "<br>"); 
                break;
            }
        }
        for (i = 1; i < 10; i ++){
            document.write(strN + " + " + i + " = " + strN + i + "<br>");
        }
        
    </script>

```


---
## **6.Array**
---

##### 배열이란?

> 자바스크립트에서 배열(array)은 이름과 인덱스로 참조되는 정렬된 값의 집합으로 정의된다. 배열을 구성하는 각각의 값을 배열 요소(element)라고 하며, 배열에서의 위치를 가리키는 숫자를 인덱스(index)라고 한다.

##### 특징

>배열 요소의 타입이 고정되어 있지 않으므로, 같은 배열에 있는 배열 요소끼리의 타입이 서로 다를 수도 있다. 배열 요소의 인덱스가 연속적이지 않아도 되며, 따라서 특정 배열 요소가 비어 있을 수도 있다.자바스크립트에서 배열은 Array 객체로 다뤄진다.


##### 배열 만들기 1

```
var scores = [50, 60, 70];
console.log(scores);
console.log(scores.length);

```

##### 인덱스를 이용해서 배열의 원소 읽기

```
scores[0];
scores[3];
```

##### 배열에 값 쓰기

```
scores[0] = 100;
scores[9] = 50;

```

##### 배열의 타입 알아보기

```
typeof scores
typeof scores[0]

```
##### 배열 만들기 2

```
var a = [];
a[0] = 2;
a[1] = 4;

```

##### 배열의 길이 구하기

```
scores.length;

```
##### 배열의 마지막 원소를 읽어 오려면?

```
scores[scores.length - 1];
문자열과 배열
	•	문자열과 배열은 비슷한 성질을 많이 가지고 있습니다.
	•	문자열: Immutable
	•	배열: Mutable
	•	배열의 속성과 메소드를 문자열에도 테스트해보세요.

```


##### 배열의 메소드들 1


* push() 뒤어 붙이기 

```
var arr = [1,2,3,4,];
arr.push(1);

arr; // = > [1,2,3,4,1]
```

* pop() 뒤에 있는거 빼기 

```
var arr = [1,2,3,4,];
arr.pop();

arr; // = > [1,2,3]
```


* unshift()	 앞에 붙이기

```
var arr = [1,2,3,4];

arr.unshift(1);

arr; // = > [1,1,2,3,4,];

```


* shift()  앞에 있는거 빼기

```
var arr = [1,2,3,4];

arr.shift();

arr; // = > [2,3,4,]

```

* concat() 더하기 

```
var arr = [1,2,3,4,5];

arr.concat(6); 

>>arr 
[1,2,3,4,5,6]  
기존에 있는 것은 변하지 않는다.
변하게 하기위해서는 변수를 새로 만들기 !


var arr = [1,2,3,4,5];

arr.concat([6,7,8,9,10]);

>>arr
[1,2,3,4,5,6,7,8,9,10] 
여러게를 더할수 있다.

```


* join() 문자열로 바꾸기 



```
var arr = [1,2,3,4,5,6]

arr.join() ;

>>arr
["1","2","3","4","5","6"]
문자열로 바꿔준다. 

arr.join("");

>>arr
["123456"];
문자열 다 붙인다.

```
* indaxtOf() ()<<원소를 입력하면부터 앞에서 부터 찾아서 index번호 알려준다. 
* lastIndaxtOf() ()<<원소를 입력하면부터 뒤에서 부터 찾아서 index번호 알려준다. 

```


var arr = [1,2,3,4,5];
arr.indexOf[1];

>>arr
2

arr.indexOf[100];
>>arr
-1
없는 경우 -1를 호출한다. 

EX) 
var arr = [1,2,3,4,5,6]
if (arr.indexOf(100) === -1 ) {
만약 100이라는 원소가 arr 에 없으면 
}

```
* slice()
```
var arr = [1, 2, 3, 4, 5];
a.slice(0, 3);
>>a;
123
원소는 변하지 않는다

```

* splice()


```
var arr = [1, 2, 3, 4, 5];
a.splice(0, 3);
>>a;
123
원소 값이 변한다. 
```


* split()

>문자열을 문자의 배열로 나누고 싶을 때 사용하는 메소드입니다.


```
var s = "hello, world this is jj";
s.split("");


"h", "e", "l", "l", "o", ",", " ", "w", "o", "r", "l", "d", " ", "t", "h", "i", "s", " ", "i", "s", " ", "j", "j"
```

```

var s = "hello, world this is jj";
s.split(",");
"hello", " world this is jj"
콤마가 생겼다. 콤마의 기준으로 갈라진다.
```

```
var s = "hello world t-h-i-s-i-s-j-j"
s.split("-");

"hello  world t", "h", "i", "s", "i", "s", "j", "j"
- 기준으로 갈라진다. 
```

---
## **7.Function**
---


##### 함수 만들기

```
function convertHeight(feet, inches) {
  return (feet * 12 + inches) * 2.54
}
convertHeight(5, 10);
 //= >>177.8

(feet , inches) ==>> parameter ( 매개 변수) 
(5,10)  ==>> argument ( 전달인자	)

```

##### 변수에 담아서 함수 사용하기

```
var ret = function convertHeight(feet, inches) {
  return (feet * 12 + inches) * 2.54
}
ret(5, 10);
177.8

```


##### 리턴값 없는 변수를 변수에 담으면 “undefind” 출력된다 .

* ex 1-1 (console.log)

```
var foo = function () {
	console.log(“I’m a foo”);
}
>>undefined
```

* ex 1-2 (return)

```
var foo = function () {
	return(“I’m a foo”);
}

>> I’m a foo
```

##### return 을 break 로 사용하기 (return 으로 함수를 종료하는데 사용할 수 있다.)

> (Option) 2중 루프를 한 번에 빠져 나가기
- `break` 명령은 한 번에 한 루프만 빠져나갑니다.
- 함수의 `return` 을 이용하면 2중 루프를 한 번에 종료할 수 있습니다. 


* 종료하기 
```
var test1 = function (text) {
            if (text === "exit") {
                return;
            }
            console.log("실행");
        }

test1("exit") // => undefined
```

* 실행 하기 

```
var test1 = function (text) {
            if (text === "exit") {
                return;
            }
            console.log("실행");
        }
test1("oh""); // = > 실행 

```

##### 이중 loop 빠져 나가기 

* ex (하나만 빠져 나가기 )

```
for (var i = 0; i < 10; i ++)  {
	for (var j = 0; j < 10; j++) {
		console.log(i , j );
		if (j === 3 ) {
		    break;

		}
	}
}


```

* ex (이중 loop 빠져나간다 with function)


```
        var foo = function() {
            for (var i = 0; i < 10; i ++)  {
                for (var j = 0; j < 10; j++) {
                    console.log(i , j );
                    if (j === 3 ) {
                        return;

                    }
                }
            }
         };
         
         foo();
```


##### 배열을 이용한 while 문 , for 문

```
// while loop
    
    
    function sum (nums) {
    var total = 0;
    var i = 0;
    while (i < nums.length) {
        total = total + nums[i];
        i++;
    }
    return total;
}
sum([2,3,5,1]);

>> 11

    
```


```
// for loop
  
  
  function sum (nums) {
  	var total = 0 ;
  	for (var i = 0 ; i < nums.length ; i = i + i ) {
  	total = total + nums[i]
  }
	return total;
}

sum([2,3,5,1,]);

>>11

```


---
## **8.Objects**
---


##### making objects 

```  
1.
  var dog = {};

  dog.name = "jj"
  dog.color = "red"
  dog.kind = "똥깨"
  // >>> dog = {name = "jj", color ="red" , kind = "똥깨 "}


2. 
 var dog = {
    name : "jj",
    color : "red",
    kind : "똥깨"
}

  // >>> dog = {name = "jj", color ="red" , kind = "똥깨 "}

```

##### using objcets in Javascript 

```
var dog = {
    name = "jj"
    color = "red"
    
};

we have two systems .

1. 
dog.name;
dog["name"];

결과갑 똑같다.
>>>jj

```


##### changing objects 


```
1. it is changed

dog.name = "john"

2. it is added

dog.food = "Banana"


```
##### 메소드

* 객체에 속한 함수

```

dog.eat = function(food) {
    console.log(this.name + " ate delicious " + food +"...");
};

p1.eat("Beef");

>> jj ate delicious Beef ...

```

#### this

```

메소드 안에서 사용시 함수를 소유한 객체를 가르킨다.

var p2 = {};
p2.name = "jj";
p2.weight = 80;
p2.say = function(word) {
    console.log(this.name + " says, " + word);
};

```




