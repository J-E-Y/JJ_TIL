---
title: Technical terms
author: JohnJung
date: '2019-11-14'
categories: []
tags: ['Technical terms']
menu:
  tutorial:
    name: 1.Technical terms
    weight: 1
toc: yes
type: docs
summary: 'write here:rocket:' 
---


## 메소드란?


#### 객체안에 함수가 들어있는것이 메소드

```js

// 객체 만든다 
// obj 의 키는 foo
// foo 의 값은 function()
// obj.foo() 메소드 호출한것이다. 
obj = {
    foo: function () {
        return “hello world”
    }
  }

obj.foo() // “hello world” 



```

## ASCII(아키스) 



#### 아키스 코드란 무엇인가?

* ASCII (American Standard Code for Information Interchange, 미국 정보 교환 표준 부호)

* 영문 알파벳을 사용하는 대표적인 문자 코딩

* 컴퓨터는 0과 1 숫자 밖에 모르기 때문에 문자도 숫자로 기억합니다. 이때, 어떤 숫자와 어떤 문자를 대응시키는가에 따라 여러 가지 인코딩 방식이 있는데 통상 아스키 코드 방식을 많이 사용합니다.

* 아스키 코드(ASCII Table)는 0번부터 127번까지만 사용합니다. 127번 이후 코드를 사용했던 적도 있었는데 이는 표준이 아니며 운영체제마다 다른 코드(문자)를 배치했기 때문에 호환이 되지 않습니다. 윈도우즈 운영체제는 현재 128번부터 255번 사이에 포함된 문자를 출력하려는 시도에 대해 물음표(?)를 출력해서 사용하면 안된다는 것을 알려줍니다. 128번과 255번 문자는 물음표는 아니지만 사용할 수 없는 문자입니다.


#### ASCII Table (아스키 코드표 )

![](/tutorial/IT terminology_files/ASCII Table.png)



#### ex)

* alphabetPosition 함수 만들기

> In this exercise, you are required to, given a string, replace every letter with its position in the alphabet. (문자열이 주어졌을때, 각각의 문자를 알파벳의 몇번째 인지 숫자로 바꾸는 함수를 작성하세요.) If anything in the text isn't a letter, ignore it and don't return it. a being 1, b being 2, etc. (만약 문자가 알파벳이 아니라면, 무시하고 결과값에 포함하지 마세요. a 는 1, b 는 2, 등등 으로 변환됩니다.)


* output

```js
alphabetPosition("The sunset sets at twelve o' clock."); 
// "20 8 5 19 21 14 19 5 20 19 5 20 19 1 20 20 23 5 12 22 5 15 3 12 15 3 11"

```


```js

var alphabetPosition = function (str) {
 // Your code here
 let output = [];
 // 1. 배열로 바꾼다
 let temp = str.toUpperCase();
 // 2. THE SUNSET SETS AT....
 for(let i=0;i<temp.length;i++){
   if(typeof(temp[i]) ==='string'){
     if(temp[i].charCodeAt(0) - 64 > 0)
       output.push(temp[i].charCodeAt(0) - 64);
   }
 }
 return output.join(' ');
}



```






