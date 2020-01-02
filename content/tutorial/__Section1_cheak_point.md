---
  title: __Cheak_Point 
date: 2019-04-29
draft: true
menu:
  tutorial:
  parent: "_section1"
weight: 1
toc: yes
type: docs
---



## Check_Point_1 Scope

   * 8번에 result인 x 가 10인 이유는 이해가 되는데 

**10번에 함수밖에있는 result 인  x 가 어떻게 outer(),inner()함수에 변수 x 를 가져왔는지** 이해가 잘안되어 질문을 드립니다..  제가 이해하기로는 단순히 var 이 함수안에서 다시 선언되지 않아서 인가요?

부탁드립니다.  




### 8번문제 

```js

var x = 10;

function outer () {
  var x = 20;
  function inner () {
    x = x + 10;
    return x;
  }
  inner();
}

outer();

var result = x;  // 10


```

### 10번 문제 

```js
var x = 10;

function outer () {
  x = 20;
  function inner () {
    x = x + 20;
  }
  inner();
}

outer();

var result = x; // 40


```

### 해답




> 8 번 문제 함수안에 변수가 let var const 선언되면 함수범위(스코프 범위)를 벗어나서 변수를 쓸수가 없다 


> 10번 문제  함수 안에 변수가 선언되지 않고 전역에 선언되었기 때문에 함수안에 x는 전역에 있는 것을 할당 하게 되어 가져온후 그것을 어니서나 쓸수 있는 변수가 되어버린것이다. 



## check_point 2 _Closure
 

  * 클로저를 정의한다면 
  
    * 함수안에 또다른 함수를 실행 외부함수가 실행 `종료된 뒤에도` 여전히 내부함수가 계속 외부함수였던 스코프에 접근할수 있다. 



#### Qeustion

```js
var add = function(x) {
   function sum (y) {
      return x + y;
  }
  return sum;
}

var foo = add(1) // 이렇게 하면 x는 1로 저장된다. 

foo(2) // 1 + 2 되어서 3 

var total1 = foo(10) // 1 + 10 = 11
var total2 = foo(11) // 1 + 11 = 12

var total3 = foo(12) // 1 + 12 = 13
var total4 = foo(13) // 1 + 13 = 14

var total5 = foo(14) // 1 + 14 = 15
var total6 = foo(15) // 1 + 15 = 16

var total7 = foo(16) // 1 + 16 = 17
var total8 = foo(17) // 1 + 17 = 18

```





