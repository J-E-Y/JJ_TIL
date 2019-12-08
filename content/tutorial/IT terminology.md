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


## CPU 

#### 중앙 처리 장치 또는 CPU (central processing unit) 

> CPU 처리하는 용도 데이터를 읽고  처리하고  다시쓰는  동작을 합니다. 


> 컴퓨터 시스템을 통제하고 프로그램의 연산을 실행하는 가장 핵심적인 컴퓨터의 제어 장치, 혹은 그 기능을 내장한 칩을 말한다. 컴퓨터 안의 중앙 처리 장치(CPU)는 외부에서 정보를 입력 받고, 기억하고, 컴퓨터 프로그램의 명령어를 해석하여 연산하고, 외부로 출력하는 역할을 한다. 따라서 중앙 처리 장치(CPU)는 컴퓨터 부품과 정보를 교환하면서 컴퓨터 시스템 전체를 제어하는 장치로, 모든 컴퓨터의 작동과정이 중앙 처리 장치(CPU)의 제어를 받기 때문에 컴퓨터의 두뇌에 해당한다고 할 수 있다. 

> 실제의 CPU 칩엔 실행 부분뿐만 아니라 캐시 등의 부가 장치가 통합된 경우가 많다.
CPU에는 MCU(Micro Control Unit)와 주변 장치(외부 확장 장체에 관한 IC)가 다 들어있는 Soc(System On Chip)가 있다. 주변 IC가 따로 달려 있을 경우, 그것은 MCU라고 할 수 있다


## SSL


#### SSL (Secure Sockets Layer)  보안 소켓 계층

>월드 와이드 웹 브라우저와 웹 서버 간에 데이터를 안전하게 주고받기 위한 업계 표준 프로토콜. 미국 넷스케이프 커뮤니케이션스사가 개발했고, 마이크로소프트사 등 주요 웹 제품 업체가 채택하고 있다. SSL은 웹 제품뿐만 아니라 파일 전송 규약(FTP) 등 다른 TCP/IP 애플리케이션에 적용할 수 있으며, 인증 암호화 기능이 있다. 

> 인증은 웹 브라우저와 웹 서버 간에 서로 상대의 신원을 확인하는 기능이다. 예를 들면, 웹 브라우저를 사용하는 웹 서버를 사용한 가상 점포의 진위(眞僞) 여부를 조사할 수 있다. 암호화 기능을 사용하면 주고받는 데이터가 인터넷상에서 도청되는 위험성을 줄일 수 있다.




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
// 

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






