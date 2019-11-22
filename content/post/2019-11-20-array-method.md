---
title: forEach(), map(), fliter()
summary: 'Javascript:rocket:' 
author: JohnJung
date: '2019-11-20'
slug: array-method
categories:
  - Javascript Post
tags: []
image:
  caption: ''
  focal_point: ''
---



### 1. forEach()

> array.forEach (callback(callbackFunction(element, index, array)   

* 배열 혹은 함수를 반복할때  사용 

* 리턴값 없다  



#### ex) 

* forEach 로 배열의 합 구하기 

```js

function test(){
    var testArray = [1,2,3,4,5];
    var sum = 0;
    function getSum(value){
        sum =  sum + value;
    }
    testArray.forEach(getSum); // forEach(getSum) that's all  
    console.log(sum);
  }

test()  // 15 

```



### 2.map()

> array.map(callbackFunction(element, index, array)    

* `immutable`

* `새로운 배열`을 만들때 사용

* 리턴값 있다. 


#### ex)

* for 문으로 name 값 가져오기 

```js
let users = [
  
  {name:"john",age : 20 },
  {name:"tim",age :40 },
  {name:"esther",age : 60 },
  
];


let userName = [];


for (let i = 0; i < users.length; i ++ ) {
	userName.push(users[i].name);
 }
 
 userName // ["john", "tim", "esther"]

```


* map() 으로 name 값 가져오기 


```js

let users = [
  
  {name:"john",age : 20 },
  {name:"tim",age :40 },
  {name:"esther",age : 60 },
  
];


function getName (user){
  return user.name; //  리턴값 필요하다. 

}

users.map(getName); // ["john", "tim", "esther"]





```






### 3.fliter()

> array.fliter(callbackFunction(element, index, array) 

* `조건`에 해당한 것을 새로운 배열의 형태로 출력 한다.

* 리턴값 있다. 


* map 함수는 filter함수와 같이 오브젝트도 컨트롤 할 수도 있습니다.


#### 예제 

* filter 로 30 살 보다 많은 사람 사람을 찾는다

```js

let users = [
  
  {name:"john",age : 20 },
  {name:"tim",age :40 },
  {name:"esther",age : 60 },
  
];

function getOldName(user){
	return user.age > 30; // 리턴 필요하다. 
}
// 그리고 filter 에 함수를 넣는다. 
users.filter(getOldName) // [{name:"tim",age :40 },{name:"esther",age : 60 }];
```

* filter 로 이름에 s 가 있는 사람을 가져오고 싶다.?



```js

let users = [
  
  {name:"john",age : 20 },
  {name:"tim",age :40 },
  {name:"esther",age : 60 },
  
];


function userIncludeS (user){
	return user.name.indexOf("s") !== -1; // 조건문 

 }
 
 
users.filter(userIncludeS) // [{name:"esther",age : 60 }];

```



