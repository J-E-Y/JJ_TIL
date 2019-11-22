---
title: reduce()
summary: 'Javascript:rocket:' 
author: JohnJung
date: '2019-11-22'
slug: javascript-reduce
categories:
  - Javascript Post
tags: []
image:
  caption: ''
  focal_point: ''
---


### reduce()

#### Definiton & Syntax

> arr.reduce(callback(accumulator, currentValue[, index[, array]])[, initialValue])

* accumulator — the accumulator accumulates all of the callbacks returned values.

* val — the current value being processed

* index — the current index of the value being processed

* arr — the original array

> The reduce() method is used to apply a function to each element in the array to reduce the array to a single value.


> 여러게의 값이 담긴 배열이 줄여서(reduce) `최종적으로 하나의 값으로 만드는 과정` 

* 리턴값이 반듯이 필요 

* 누적값 : 배열의 요소를 하나하나 줄여가면서 생기는 중간 과정(결과)
* 현재값 : 리듀서가 배열을 지나갈 떄 만나는 배열의 요소
* 초기값 : 배열의 요소를 줄이기 전 누적값의 `초기` 상태 



#### ex)

* Reduce vs. For Loop

* To use for Loop

```js

let arr = [1, 2, 3, 4];
let sum = 0;
for(var i = 0; i < arr.length; i++) {
    sum += arr[i];
}
// sum = 10


```

* To use the reduce() function


```js
let arr = [1,2,3,4];

let sum = arr.reduce((acc, val) => {
  return acc + val;
});

// sum = 10

```


* 배열에서 문자열로

* 이름 함쳐서 문자열로 출력 시키기 

```js

let users = [
  
  {name:"john",age : 20 },
  {name:"tim",age :40 },
  {name:"esther",age : 60 },
  
];

// "john, tim, esther" 이렇게 만들것이다. 

function sumName(retName , cuur ) {
	// 1. " " + "john" + ","
	// 2. "john," + "tim" + ","
	// 3. "john, time," + "esther" + ","
	retName = retName + cuur.name + ","; 
	return retName ; // 리턴을 꼭 해줘야 한다.
 }
 
 
users.reduce(sumName, ""); // 두번째 인자값에 초기값인  "" 넣어준다.

// "john,tim,esther,"




```


* 배열에서 객체로

* 첫번째 글자를 따서 전화번호부 만들기 


```js

// 원본
let users = [
  
  {name:"john",age : 20 },
  {name:"tim",age :40 },
  {name:"esther",age : 60 },
  
];

// 결과 출력 

let addressBook = {
	j : [
		{name:"john",age : 20 }
      ],
	t : [
		{name:"tim",age :40 }
      ],
	e : [
		{name:"esther",age : 60 }
 	  ]
};





//1. makeAddressBook < callback 함수를 미리 만든다. 

function makeAddressBook (addressBook, user) {
  // 첫번째 글자를 먼저 변수에 저장한다. 
  let firstLetter = user.name[0];
  
  // addressBook { };
  
  
  if (firstLetter in addressBook) {
	  // 만약 키가 있으면 해당 배열에 사람을 추가한다. 
    addressBook[firstLetter].push(user);
	} else {
	  // 만약 키가 없다면 해당 배열을 만들고
	  addressBook[firstLetter] = [];
	  // 사람을 추가한다. 
  	addressBook[firstLetter].push(user);
  }
	return addressBook; // 객체를 리턴한다. 
}

users.reduce(makeAddressBook, {} ); 
// {j: Array(1), t: Array(1), e: Array(1)}

/* 결과값 
{
	j : [
		{name:"john",age : 20 }
      ],
	t : [
		{name:"tim",age :40 }
      ],
	e : [
		{name:"esther",age : 60 }
 	  ]
};
*/

```





