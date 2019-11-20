---
title: '<Javascript> data fliter 와 foreach 로 다루기 '
summary: ':rocket:' 
author: JohnJung
date: '2019-11-20'
slug: data-fliter-foreach
categories:
  - Javascript Post
tags: []
image:
  caption: ''
  focal_point: ''
---



## salesTeam 안에 있는 data  fliter 와 foreach 로 다루기 

```js
var salesTeam = [
  {
    "name": {
      "first": "Bruce",
      "last": "Wayne"
    },
    "age": 10,
    "sales": "$2314"
  },
  {
    "name": {
      "first": "Alvaro",
      "last": "Angelos"
    },
    "age": 55,
    "sales": "$1668"
  },
  {
    "name": {
      "first": "Alvaro",
      "last": "Angelos"
    },
    "age": 15,
    "sales": "$1668"
  }
];


// age 가 20 아래인 것만 teenager 에 담기 
// filter 사용

let teenager = salesTeam.filter(function(ele){
    return ele.age < 20;
  });

// 뽑은거 안에서 fullNmae 가져오기
// foreach 사용

  let result = [];
  teenager.forEach(function(ele){
    result.push(`${ele.name.first} ${ele.name.last}`); // 
  });




```
