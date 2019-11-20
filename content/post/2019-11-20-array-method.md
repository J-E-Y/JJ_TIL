---
title: Array_method
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




## 1. forEach

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
## 2.fliter

> array.fliter(callbackFunction(element, index, array) 

> 조건문을 통과하 것을 새로운 배열로 만드는 역활
리턴값 있다. 

> map 함수는 filter함수와 같이 오브젝트도 컨트롤 할 수도 있습니다.

```js

var testArray = [1,2,3,4,5];
var returnArray = testArray.map(function(currentValue, index, array){
        return currentValue * 2;
     })


```

## 3.map

> array.map(callbackFunction(element, index, array)    

> 콜백 함수의 실행 결과를 가지고 새로운 배열을 만들때 사용
> 리턴값 있다. 

## 4.every

> array.every(callbackFunction(currentValue, index, array), thisArg)

> every 함수는 배열의 모든 요소가 callbackFunction 에서 true를 리턴해야 true를 리턴, 하나라도 false가 떨어지면 false를 리턴합니다.

> every나 some 함수의 경우 배열내 값이 존재하는지 확인할때나 조건에 맞는(혹은 맞지 않는) 값이 있는지 확인 할 때 등 활용이 가능합니다.



## 4.some

> array.some(callbackFunction(currentValue, index, array), thisArg)


> some 함수는 배열의 요소 중 하나라도 callbackFunction에서 true를 리턴하면 true를 리턴 합니다.

> every나 some 함수의 경우 배열내 값이 존재하는지 확인할때나 조건에 맞는(혹은 맞지 않는) 값이 있는지 확인 할 때 등 활용이 가능합니다.





