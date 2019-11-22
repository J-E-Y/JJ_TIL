---
title: <Javascript> forEach(), map(), fliter()
summary: ':rocket:' 
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



## 1. forEach()

> array.forEach (callback(callbackFunction(element, index, array)   


> 리턴값 없다  


* forEach 로 배열의 합 구하기 

```

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



## 2.map()

> array.map(callbackFunction(element, index, array)    

* `immutable`

* 새로운 배열을 만들때 사용

* 리턴값 있다. 



## 3.fliter()

> array.fliter(callbackFunction(element, index, array) 

* 조건문을 통과하 것을 새로운 배열로 만드는 역활
리턴값 있다. 

* map 함수는 filter함수와 같이 오브젝트도 컨트롤 할 수도 있습니다.

```js

var testArray = [1,2,3,4,5];
var returnArray = testArray.map(function(currentValue, index, array){
        return currentValue * 2;
     })


```


