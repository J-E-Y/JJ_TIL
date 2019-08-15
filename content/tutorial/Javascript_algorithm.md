---
title: JS algorithm
date: 2019-45
draft: true
menu:
  tutorial:
    parent: "Javascript"
    weight: 12
toc: true
type: docs
---




## isOdd

>Write a function called isOdd. ("isOdd" 함수를 작성하세요.)

>Given an integer, isOdd returns whether the integer is odd or not. (숫자가 주어졌을때, "isOdd" 함수는 주어진 숫자가 홀수 인지 아닌지를 반환합니다.)

* My_Soultion



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

**sum**

>Summation to n: Let's implement the function sum that takes a single parameter n, and computes the sum of all integers up to n starting from 0, e.g.:

>(n까지의 총 합: n을 매개변수로 받아 0 부터 n 까지 모든 수의 총 합을 반환하는 함수를 작성하세요.)

* My_Soultion



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
## onlyEvenElements


>Given an array of numbers, onlyEvenElements returns a new array of just the even numbers. (숫자로 이루어진 배열이 주어졌을때, "onlyEvenElements" 함수는 주어진 배열에 있는 짝수로만으로 이루어진 새로운 배열을 반환해야 합니다.)

* My_Soultion


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

## removeOddValues

>Write a function removeOddValues that takes an object as an argument and returns an object with all key/value pairs removed for which the value holds an odd number. ("removeOddValues" 함수를 작성하세요. 객체가 주어졌을때, "removeOddValues" 함수는 주어진 객체의 key/value 페어 중 value 가 홀수 숫자인 페어가 제거된 객체를 반환하세요.)

>You'll need to use the "typeof" operator to first check that the values are numbers: (value가 숫자인지 확인하기 위하서는 "typeof" 연산자를 먼저 사용해야 합니다.)

* My_Soultion

> first 

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


> Sceond 


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



> third

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


## firstCharacter

> In this exercise, a string is passed to a method and a new string has to be returned with the first character of each word in the string (문자열이 주어졌을때, "firstCharacter" 함수는 문자열의 각 단어 첫글자들로 이루어진 문자열을 반환하여야 합니다.)


> Attention! In test case 5 userinput is one space input char as ' ', please do not get confused with '', empty string (주의사항! 테스트 케이스 5 에서 주는 입력값은 띄어쓰기 한개(' ') 입니다. 빈 문자열('') 과 혼동하지 마세요.)


* My_Soultion


```js

unction firstCharacter (string) {
 // Your code here
 
 
 // for문 이용
 
 let output = [];
 let temp_arr = [];

 // 1. split으로 단어로 나눠서 배열 만들기
 
 temp_arr = string.split(' ');
 // 2. 각 인덱스의 첫번째 문자를 배열 output 에 담기
 for(let i=0;i<temp_arr.length;i++){
   output.push(temp_arr[i][0]);
 }
 
 // 4. 출력
 return output.join('');
 
 
 
 ////////////////////////////////////////////////////////////////////////
 
 // 2. Reduce 이용
 return string.split(' ').reduce(function(acc,cur){
   return acc+cur[0];
 
 },'');
 
 // 3. Reduce이용 2
 return string.split(' ').reduce( (acc,cur)=>acc+cur[0] ,'');
}


```





## longestWord


> sing the JavaScript language, have the function LongestWord take the sen parameter being passed and return the largest word in the string. (문장이 주어졌을때, 'LongestWord' 함수는 주어진 문장에서 가장 긴 단어를 반환합니다.)

>If there are two or more words that are the same length, return the first word from the string with that length. Assume sen will not be empty. (만약 가장 긴 단어가 두개 이상이라면, 첫번째로 등장하는 가장 긴 단어를 반환하세요. 문장은 빈 문자열이 아닙니다.)


* My_Soultion


```

// It's used by sort() 

function longestWord(string) {

 // 1. 주어진 문장을 배열로 만들기(split)
 let tmp = string.split(' ');
 //let sorted_tmp =[];
 // ['I','love','codestates'];
 // 2. sort() 사용 => 성능 떨어짐
 let x = function(a,b){
   return b.length-a.length;
 };
 // 3. 0번째 요소 출력
 return tmp.sort(x)[0];
}

////////////////////////////////////////////////////////

// It's used by reudce(1)

function longestWord(string) {
 
 let tmp = string.split(' ');
 let max = tmp[0];
 for(let i =1;i<tmp.length;i++){
   if(tmp[i].length>max.length){
     max = tmp[i];
   }
 }
 return max;
}


/////////////////////////////////////////////////////////

// It's used by reudce(2) 화살표

function longestWord(string) {

return string.split(' ').reduce((acc,cur)=> acc.length<cur.length? cur:acc);
}

```


## convertArrayToObject1

* Question

>Write a function 'transformFirstAndLast' that takes in an array, and returns an object with: (배열을 입력으로 받고 다음 조건에 만족하는 객체를 반환하는 함수 'transformFirstAndLast' 함수를 작성하세요.)

>the first element of the array as the object's key, and (1. 배열의 첫번째 요소를 객체의 키로 가집니다.)
the last element of the array as that key's value. (2. 배열의 마지막 요소를 해당 키의 값으로 가집니다.)




* My_Soultion


```js

function transformFirstAndLast(array) {
  // your code here

  // 1. 마지막으로 출력할 객체를 만든다.
  // 2. 배열의 첫번째 요소를 가져와 변수에 담는다.
  // 3. 배열의 마지막 요소를 가져와 변수에 담는다.
  // 4. 객체안에 첫번째 요소를 키로 설정한다.
  // 5. 객체안에 마지막 요소를 prop 설정한다. 

  let ret = {};
  ret[array[0]] = array[array.length -1 ];
  return ret;
}



```


## convertObjectToArray1

* Question


>Write a function called "getAllKeys" which returns an array of all the input object's keys. (객체를 입력으로 받고 해당 객체의 키들을 배열로 반환하는 "getAllKeys" 함수를 작성하세요.)



* My_Soultion


```js


function getAllKeys(obj) {
// your code here

// 1. 마지막에 출력할 새로운 배열을 만든다
// 2. for in key 값을 가져온다. 
// 3. 가져온 값을 새로 만든 배열에 넣는다.
let arr = [];
for ( key in obj ) {
  arr.push(key);
}
return arr;
}


```

## convertArrayToObject2


* Question 


> Write a function 'fromListToObject' which takes in an array of arrays, and returns an object with each pair of elements in the array as a key-value pair. (2차원 배열을 입력으로 받고 배열안에 있는 배열의 요소 페어를 키-값 페어로 가지는 객체를 반환하는 함수 'fromListToObject' 함수를 작성하세요.)



* My_Soultion


```js
function fromListToObject(array) {
  // your code here
  
  //  1. output 할 빈객체를 생성한다.  
  //  2. for 문으로 배열 안에 있는 배열을 조사한다.
  //  3. 배열안에 있는 배열의 0번째 를 키값 1번째를 prop 에 넣는다.
 
  
  let obj = {};

  for ( let i = 0; i < array.length; i = i + 1 ) {
    obj[array[i][0]] = array[i][1];
    }
    return obj
}



```


## convertObjectToArray2


* Questoin

>Write a function called "listAllValues" which returns an array of all the input object's values. (객체를 입력으로 받고 해당 객체의 값들을 배열로 반환하는 "listAllValues" 함수를 작성하세요.)


* My_Soultion


```js
function listAllValues(obj) {
  // your code here
  
  // 1. output 할 빈 배열을 생셩
  // 2. for in prop 값을 조사
  // 3. prop 값을 빈배열에 넣는다. 
  // 4. output 출력한다. 
  
  let arr = [];
  for ( prop in obj ) {
    arr.push(obj[prop]);
  } 
  return arr;
}




```
