---
title: every() 와 some()
summary: 'Javascript:rocket:' 
author: JohnJung
date: '2019-11-22'
slug: every-some
categories:
  - Javascript Post
tags: []

image:
  caption: ''
  focal_point: ''
---




## 1.every()

> array.every(callbackFunction(currentValue, index, array), thisArg)

* every 함수는 배열의 모든 요소가 callbackFunction 에서 true를 리턴해야 true를 리턴, 하나라도 false가 떨어지면 false를 리턴합니다.

* every나 some 함수의 경우 배열내 값이 존재하는지 확인할때나 조건에 맞는(혹은 맞지 않는) 값이 있는지 확인 할 때 등 활용이 가능합니다.



## 2.some()

> array.some(callbackFunction(currentValue, index, array), thisArg)


* some 함수는 배열의 요소 중 하나라도 callbackFunction에서 true를 리턴하면 true를 리턴 합니다.

* every나 some 함수의 경우 배열내 값이 존재하는지 확인할때나 조건에 맞는(혹은 맞지 않는) 값이 있는지 확인 할 때 등 활용이 가능합니다.





* every 와 some 의 차이점




> every 와 some 메서드는 배열을 순회하면서 특정 조건을 배열의 값들이 만족시키는지 검사하는 메서드로서 호출한 배열이 결론적으로 조건을 만족시키는지(true), 만족시키지 못하는지(false)를 알려준다. every 와 some 의 차이는 every 가 배열의 모든 값이 조건을 만족해야, some 은 일부만 만족해도 true 를 return 한다
