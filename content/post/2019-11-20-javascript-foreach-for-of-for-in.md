---
title: forEach, for of, for in 의 차이
summary: 'Javascript:rocket:' 
author: JohnJung
date: '2019-11-20'
slug: javascript-foreach-for-of-for-in
categories:
  - Javascript Post
tags: []
image:
  caption: ''
  focal_point: ''
---



> basic for문과 for in은 반복변수에 index를 리턴하지만

> forEach 와 for of 는 해당 값을 리턴하기 때문이죠.




```js

const array = ['가','나','다','라'];

// for
for(let i=0; i<array.length; i++){
  console.log(array[i]);
}

// 가 나 다 라 


 
//forEach
array.forEach(function(j){
  console.log(array[j]);
});
 
// console.log(array[j]) 
// undefined
 
// console.log(j) 
// 가 나 다 라
 
 
 
 
// for of 
for (let k of array){
  console.log(array[k]);
}
 
// console.log(array[k]) 
// undefined
 
// console.log(k) 
// 가 나 다 라
 
 
 
 
 // for in
for (let z in array){
  console.log(array[z]);
}

// 가 나 다 라



```
