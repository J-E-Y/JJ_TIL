---
title: JS Basic 2
date: 2019-6
draft: true
menu:
  tutorial:
    parent: "Javascript"
    weight: 11
toc: true
type: docs
---

---
## Week 1-1  : isOdd
---


>Write a function called isOdd. ("isOdd" 함수를 작성하세요.)

>Given an integer, isOdd returns whether the integer is odd or not. (숫자가 주어졌을때, "isOdd" 함수는 주어진 숫자가 홀수 인지 아닌지를 반환합니다.)



```
function isOdd(num) {
  // your code here
  // 파라미터를 2로 나누었을때의 나머지를 판별별
  // 나머지가 1인경우, true를 리턴
  // 나머지가 0인경우, false를 리턴
  if (num % 2 === 1 ) {
    return true;
  } else {
    return false;
  }
}

```


---
## Week 1-2 : sum
---


>Summation to n: Let's implement the function sum that takes a single parameter n, and computes the sum of all integers up to n starting from 0, e.g.:

>(n까지의 총 합: n을 매개변수로 받아 0 부터 n 까지 모든 수의 총 합을 반환하는 함수를 작성하세요.)


```
function sum(n) {
  let result = 0;
  //반복문을 이용하여 0부터 n까지의 숫자를 더하여 출력
  for (let i = 0; i <= n; i++) {
    result = result + i;
  }
  return result;
  
  // your code here
}
sum(3);
sum(4);

```

---
## Week 1-3 : onlyEvenElements
---

>Given an array of numbers, onlyEvenElements returns a new array of just the even numbers. (숫자로 이루어진 배열이 주어졌을때, "onlyEvenElements" 함수는 주어진 배열에 있는 짝수로만으로 이루어진 새로운 배열을 반환해야 합니다.)



```

function onlyEvenElements(arr) {
  //짝수값을 입력받을 빈배열을 선언한다.
  let result = [];
  //입력받은 배열안에 있는는 값을 판별하기위해 불러온다.
  for (let i = 0; i < arr.length; i++) {
    //값이 짝수인지를 if 문을 써서 판별한다. 
    if (arr[i] % 2 === 0) {
      //값이이 짝수인경우 빈배열에 집어넣는다.
      result.push(arr[i]);
    }
  }
  return result;
  // your code here
}


```

---
## Week 1-4 : removeOddValues
---


>Write a function removeOddValues that takes an object as an argument and returns an object with all key/value pairs removed for which the value holds an odd number. ("removeOddValues" 함수를 작성하세요. 객체가 주어졌을때, "removeOddValues" 함수는 주어진 객체의 key/value 페어 중 value 가 홀수 숫자인 페어가 제거된 객체를 반환하세요.)

>You'll need to use the "typeof" operator to first check that the values are numbers: (value가 숫자인지 확인하기 위하서는 "typeof" 연산자를 먼저 사용해야 합니다.)


```

* note

typeof "Hello" // => ?
typeof 3 // => ?
removeOddValues({ a: 1, b: 2, c: 3, d: 'hello' }); // => { b: 2, d: 'hello' }
removeOddValues({ a: 1, b: 2, c: '3' }); 

```



* first 

```
function removeOddValues(object) {
  // 1.홀수숫자인 페어가가 아닌 값들을 입력받을을 빈 객체를를 만든다.
  let object2 = {};
  // 2. value 값들을 판별하기 위해 키값을 반복시킨다.
  for (let k in object) {
  // 3. value 값이 숫자이고 짝수이면 빈객체에 대입한다. 
    if (typeof(object[k]) === 'number' && object[k] % 2 === 0) {
      object2[k] = object[k];
  //4. value 값이 문자형이면 객체에 대입한다. 
    } else if ( typeof(object[k]) === "string" ) {
      object2[k] = object[k];
    } 
  }
  return object2;
  // your code here
}

```


* Sceond 


```

function removeOddValues(input) {
	
// 1. 결과를 담을 객체를 만듭니다. 
	
  	let result = {};

// 2. input 으로 받은 object 안에 key 를 모두 반복합니다. 
  
  for (let key in input) {
	  let value = input[key];
	  let isNumber = typeof value === 'number';

	  if (isNumber ) {
	 
// key의 해당 하는 value가 짝수인지 확인합니다.
	 
    let isEven = value % 2 === 0;
    if (isEven) {
	 
// 만든 객체에 key, value를 추가합니다.
	 
    result[key] = value;
	    }
   }
// 숫자가 아니면
	
    else {
	
//만든 객체에 key, value 를 추가합니다.

  	result[key] = value;	
    }
  }
  return result;
}

removeOddValues({ a: 1, b: 2, c: 3, d: 'hello' })


```





```

function removeOddValues(object) {
  //1. value 값을 판별하기 위해 key 값을 반복한다.
  for (let k in object) {
  //2. value 값이 숫자이고 홀수이면 삭제한다. 
    if (typeof(object[k]) === 'number' && object[k] % 2 === 1) {
    delete object[k];
     }
  }
  return object;
  }



```

