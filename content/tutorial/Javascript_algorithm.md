---
title: xCoding_level_2
date: 2019-45
draft: true
menu:
  tutorial:
    parent: "3.Javascript"
    weight: 0
toc: true
type: docs
tags:
- Javascript
summary: 'write here:rocket:' 
---

![](/tutorial/Javascript_Dictionary_files/javascriptt-light_870x220.png)


---------------------------------------------------------------------------

### Question

>convert nested (2-dimensional) array to flatten array! (2차원 배열을 1차원 배열로 전환하세요.)

```js
flatten([1,2,[3],[4]]); // [1,2,3,4]

```

### My_Soultion

```js
function flatten (array){
  //your solution here
  
  // 1. 재귀함수 사용 
  let ret = []; // 새로운 배열은 만든다. 

   // 재귀함수
    function filtered(array) {
      // (1).array 의 각각의 요소에 접근한다.  [1,2,[11,25,21,34],[4]]
      // (5). array 의 각각의 요소에 접근한다. [11,25,21,34]
      for(let i = 0 ; i < array.length; i ++ ) {
        // (2)만약 요소가 array 안에 array 가아니면  [1,2]
        // (6)만약 요소가 array 안에 array 가 아니면 [11,25,21,34]
        if (!Array.isArray(array[i])){
          // (3)새로만든 배열안에 합친다. ret = [1,2]
          // (7)새로만든 배열안에 합친다. ret = [1,2,11,25,21,34]
          ret = ret.concat(array[i]);
          // (4)만약 array 안에 array 가 발견되면
          // array는 array안에 있는 array로 담기고
          // filtered(array) 가 실행된다.  
        } else {
          filtered(array[i]);
        }
      }
    }
    filtered(array);
  return ret;
  }
  
  // reduece 사용해서 풀기
   
   return array.reduce(function(accu,curr){
     return accu.concat(curr)
   },[]);
  }
  



```

### Question 


## bugInApple

> Find out "B"(Bug) in a lot of "A"(Apple). (수많은 "A"(Apple) 사이에서 "B"(Bug)를 찾으세요.)

>There will always be one bug in apple, not need to consider the situation that without bug or more than one bugs. (사과(apple) 사이에는 언제나 항상 한개의 벌레(bug)가 있으므로 벌레가 없는 경우나 한개 이상인 경우는 고려하지 않으셔도 됩니다.)

```js

//Note: 2-dimesional Array will be input. (노트: 2차원 배열이 매개변수로 주어집니다.)

input:

[["A","A","A","A","A"],["A","B","A","A","A"],["A","A","A","A","A"],["A","A","A","A","A"],["A","A","A","A","A"]]

output:
[1,1]

```

### My_Soultion

```js

let bugInApple = function(array) {
 var location = [];
  for ( var i = 0; i < array.length ; i++) {
    for ( var j = 0; j < array[i].length ; j++) {
      if (array[i][j] === "B") {
        location.push(i);
        location.push(j);
      }
     }
  }
  return location;
}


```





### Question 

> using the JavaScript language, have the function firstReverse(str) take the str parameter being passed and return the string in reversed order. 

> (firstReverse(str) 함수를 작성하세요. 문자열(str)이 주어졌을때, firstReverse(str) 함수는 주어진 문자열을 역순으로 반환합니다.)

## firstReverse

### My_Soultion




```js
function firstReverse(str) {
  // code here ... :)
  // str = "code"
  // str.split('') // ["c", "o", "d", "e"]
  // str.split('').reverse(); //["e", "d", "o", "c"]
  // str.split('').reverse().join('') // "edoc"
  return str.split('').reverse().join('');

}




```






### Question

> Using the JavaScript language, have the function ABCheck(str) take the str parameter being passed and return the true if the characters a and b are separated by exactly 3 places anywhere in the string at least once Otherwise return the false. 

> (ABCheck(str) 함수를 작성하세요. 문자열(str)이 주어졌을때, ABCheck(str) 주어진 문자열에서 함수는 문자 a 와 b 사이가 문자열 안에서 한번이라도 정확히 3글자 떨어져 있으면 true를 반환하고 그렇지 않은 경우는 모두 false 를 반환합니다.)


### My_Soultion


```js

function ABCheck(str) {
  // code goes here

  // lane Borrowed // true otherwise false;
  
  // 대문자를 소문자로 바꾼다. 
  // str 의 각chr 를 접근한다. 
  // a 를 발견하면 인덱스 번호를 착출한다 변수에 담는다. .
  // b 를 발견하면 인덱스 번호를 착출한다 변수에 담는다/
  // 만약 a 와 b
  if (str === undefined) {
    return false;
  }
  str = str.toLowerCase();
  for (let i = 0; i < str.length; i ++ ) {
    if (str[i] === "a" && str[i + 4] === "b") {
      return true;
    } else if (str[i] === "b" && str[i + 4] === "a" ) {
      return true;
    }
  }
  return false;
}



```








### Question

## filteredArray

>return a new array that all elements passed testFunction without using filter method (filter 메소드를 사용하지 않고 testFunction 함수를 통과하는 요소로만 이루어진 배열을 반환하는 함수를 작성하세요.)

### My_Soultion


```js

function filteredArray (array, testFunction) {
 
  let result = []; // 출력할 빈 배열을 만든다. 

  for (let i = 0; i < array.length; i ++ ) {
  // loop 를 돌면서 testFunction 안에 parameter 를 넣었을때 동작한다면
    if (testFunction(array[i])){
    // 그값을 새로운  array 넣어서 저장한다. 
      result.push(array[i])
    }
  }
  return result;
}




```


### Qeustion

> 다차원 배열을 가져와서, 1차원 배열로 변환합니다.

> 새 배열에는 다차원 배열의 모든 요소가 포함되어야 합니다.

## flatten 함수 만들기 

### My_Soution


```js

// for 문을이용한 것 

function flatten (nestedArray) {
    //[1, [2], [3, [[[4]]]]]
    //oneflat([1, [2], [3, [[[4]]]]])
    // result = [1, 2, 3, [[[4]]]]
    // result = [1, 2, 3, 4]
    let oneflat = function(array) {
      let resultArr = []
      for (let i in array) {
        if (Array.isArray(array[i])) {
          resultArr = resultArr.concat(array[i]);
        } else {
          resultArr.push(array[i]);
        }
      }
      return resultArr;
    }
    let isinArr = function(array) {
      for (let i in array) {
        if (Array.isArray(array[i])) {
          return true;
        }
      }
      return false;
    }
    while(isinArr(nestedArray)) {
      nestedArray = oneflat(nestedArray);
    }
    return nestedArray;
  };



function flatten (nestedArray, result) {


     // 재귀를 이용한것 

     result = [];
     function flatarr(nestedArray) {
       for(let i = 0; i < nestedArray.length; i++) {
         if(!Array.isArray(nestedArray[i])) {
           result = result.concat(nestedArray[i])
         } else {
           flatarr(nestedArray[i]);
         }
       }
     } flatarr(nestedArray);
     return result;
   };
 



```




### Qeustion


## delay 함수 만들기 


### My_Soultion

```js



  // 주어진 시간 (밀리초) 동안 함수를 지연한 다음 제공된 argument로 함수를 호출합니다.
  //
  // 원래 함수에 대한 argument는 wait parameter 뒤에 전달됩니다.
  // 예를 들어, 다음을 호출할 경우
  // _.delay(someFunction, 500, 'a', 'b');
  // someFunction('a', 'b') 은 500ms 이후에 호출됩니다.


  _.delay = function(func, wait, ...args) {

      setTimeout(function(){
        return func(...args);
      } ,wait);

  };




```



### Qeustion


## 최대 한번만 호출할 수 있는 함수 만들기 


### My_Soultion

```js
 
  function once(func) {
 
    // ... agrgs 사용한 함수 

    var alreadyCalled = false;
    let result;
    return function(...args) {
      if (!alreadyCalled) {
        alreadyCalled = true;
        result = func(...args);
      }
      return result;
    };
  };


// this 와 arguments 와 apply 를 사용한 함수 

    let alreadyCalled = false;

    let result;

  
    return function() {
      if(alreadyCalled) {
        return result 
    } else {
        alreadyCalled = true 
        return result = func.apply(this, arguments);
      }
    }
  };



```







### Qeustion


## 갹채를 함쳐주는 함수 만들기 2(key 덮어쓰지 않기 )


## My_Soultion

```js
 // extend와 비슷하지만, 이번엔 이미 존재하는 key에 대해 값을 덮어쓰기 하지 않습니다.
  function defaults (obj,...objs) {
    
    for (let i = 0; i < objs.length; i ++ ) {
      for (let prop in objs[i]){
        // 만약 기존에있는 obj 의 키값이 새로 더해진 obj 에 없다면 
        if (!(prop in obj)) { 
          // 기존에 있는 obj 의 push 해준다. 
          obj[prop] = objs[i][prop];
        }
      }
    }
    return obj;
  }




```





### Qeustion


## 갹채를 함쳐주는 함수 만들기


### My_Souliton

```js

extend = function(obj, ...objs) {
  
    //객체를 합쳐주는 함수를 만들어보자
  
    for (let i = 0; i < objs.length; i ++ ) {
      for (let prop in objs[i] ) {
        obj[prop] = objs[i][prop];
      }
    }
    return obj;
  }



// other_Soultion


    for(let i = 0; i < arguments.length; i++) {
      for(let key in arguments[i]) {
      obj[key] = arguments[i][key]
      }
    } return obj;
  };

```



### Qeustion


## some 함수 만들기 


### My_Soultion

```js


  // element가 하나라도 iterator에 의해 truthy한지 체크합니다.
  // iterator가 없다면, element 그 자체가 truthy한지 체크하세요.
function some(collection, iterator) {

    if(iterator === undefined) { // 이것을 왜하는지 ?
      for(let i = 0 ; i < collection.length ; i++) {
        if(Boolean(collection[i]) === true) {
          return true;
        }  
      }
    } else if (iterator) { // 이것은 왜? 
      for (let j = 0 ; j < collection.length ; j++) {
        if (Boolean(iterator(collection[j])) === true) {
          return true;
        }
      }
    } return false;
  };






```




### Qeustion


## every 함수 만들기


### My_Soultion

```js

// 모든 element가 iterator에 의해 truthy한지 체크합니다.
  function every(collection, iterator) {
  
  // function every(collection,iterator)
  // collection.every(terator(value, key, collection)) ???
  
    if(iterator === undefined) { // 이것을 왜하는지 ?
      for(let i = 0 ; i < collection.length ; i++) {
        if(Boolean(collection[i]) === false) {
          return false;
        }  
      }
    } else if (iterator) { // 이것은 왜? 
      for (let j = 0 ; j < collection.length ; j++) {
        if (Boolean(iterator(collection[j])) === false) {
          return false;
        }
      }
    } return true;
  };




```

### Qeustion


## contains 함수 만들기 


### My_Soultoin


```js
  //배열 또는 객체가 주어진 값을 포함하는지 체크합니다. (`===` 연산자를 사용해서 판단합니다.)

  _.contains = function(collection, target) {
 

    for (let i in collection ) {
      if (collection[i] === target ){
        return true
        } 
      }
      return false;
  }

    // 다른 깔끔한 방법
    // each 방법을 써서..

    if (Array.isArray(collection)) {
       for (let i = 0; i < collection.length; i ++  ) {
         if (collection[i] === target) {  
           return true;
         } else {
           return false;
         }
       }
     } else {
       for (let prop in collection) {
         if (collection[prop] === target) { 
           return true;
         } else {  
           return false;
         }
       }
     } 
      



```



### Question

## reduce

```js

// 각 항목에 대해 iterator(accumulator, item)를 반복적으로 호출하여, Reduces an array to a single value by repetitively calling
  // 하나의 값으로 줄입니다. accumulator는 누적값으로, 이전 iterator 호출의 반환값이어야 합니다.
  //
  // reduce에 대한 세번째 argument로 초기값을 전달 할 수 있습니다.
  // 만일 초기값이 전달되지 않으면, 첫번재 element가 accumulator로 사용되며, iterator에 전달되지 않습니다.
  // 즉, 초기값이 전달되지 않은 경우, iterator는 두번째 element로부터 시작합니다.
  //
  // 예제:
  //   const numbers = [1,2,3];
  //   const sum = _.reduce(numbers, function(total, number){
  //     return total + number;
  //   }, 0); // 6이 리턴됩니다
  //
  //   const identity = _.reduce([5], function(total, number){
  //     return total + number * number;
  //   }); // 5가 리턴됩니다, 전달한 iterator와 관계없이, 첫번째 element가 즉시 사용됩니다.
  


```


### My_Soultion

```js



  _.reduce = function(collection, iterator, accumulator) {
     
     // 1. 내가 생각 방법
      let i=0;
      if (accumulator === undefined) {
        accumulator = collection[0];
        i++;
      }
      for(i; i<collection.length; i++) {
        accumulator = iterator(accumulator, collection[i]);
      }
      return accumulator;
    }
  // accumulator가 undefined면 : accumulator에게 첫 번째 collection값을 넣고,
  // 그 후 i++를 통해 collection[0]이 아닌 collection[1]부터 iterator가 돌아감
  // 
```








### Question

## billTotal

> Write a function called billTotal that can be used to calculate the total to be paid at a restaurant -- including tip and tax -- given the subtotal (i.e. cost of food and drinks). We can assume that the tip will be 15% and tax will be 9.5%. Make sure that the tip does not include the tax!

```js
- input: a number representing the cost of food and drinks
- output: a number representing that cost plus an additional 15% tip and tax of 9.5%

```

### My_Soultion



```js


function billTotal(subtotal) {
  // YOUR CODE HERE

  // tip 15% = * 0.15
  // tax 9.5% = * 0.095
  
  // tip을 얼마 냈는지 조사후 변수에 저장
  // tax를 얼마나 냈는지 조사후 변수에 저장
  // tip & tax & subtotal 더한값을 출력
  
  let tip = subtotal * 0.15
  let tax = subtotal * 0.095
  
  return subtotal + tip + tax;
}

billTotal(10.00); // => 12.45


```




### Question


## multiplyBetween


> Write a function called "multiplyBetween". ("multiplyBetween" 함수를 작성하세요.)

> Given 2 integers, "multiplyBetween" returns the product between the two given integers, beginning at num1, and excluding num2. (두 정수가 주어졌을때, "multiplyBetween" 함수는 첫번째 숫자부터 두번째 숫자 전까지 모든 수를 곱한 값을 반환합니다.)

```js

let output = multiplyBetween(2, 5);
console.log(output); // --> 24

```

### My_Soultion



```js
function multiplyBetween(num1, num2) {
  // your code here
	let arr = [];
    if (num2 < num1 || num1 === num2 ) {
    return 0;
  	} else {
	  
	  while( num1 < num2 ) {
		arr.push(num1);
		num1 = num1 + 1;
      	
     }
  }
console.log(arr);
  return arr.reduce(function(acc,cur){
      return acc * cur;
  })
}


```




### Question

## computeSquareRoot

> Write a function called "computeSquareRoot". ("computeSquareRoot" 함수를 작성하세요.)

>Given a number, "computeSquareRoot" returns its square root. (숫자가 주어졌을때, "computeSquareRoot" 함수는 해당 수의 제곱근 값을 반환합니다.)

```js
let output = computeSquareRoot(9);
console.log(output); // --> 3


```
> Do not use Math.sqrt(); for this problem. Instead, use this iterative way of solving the problem: (Math.sqrt()를 사용하지 말고, 아래 링크에서 나온 방법을 통해 해결하세요.)



### My_Soultion

```js

unction computeSquareRoot(num) {
  
  let square = 1;
  let i = 0;
  
  while(true){
      i = i + 1
      
      square = (num / square + square) / 2;
      if(i=== num + 1) { 
       break;
      }
  } 
  return Number(square.toFixed());
}


/*
- doc 파일에 있는 내용 정리
5 / 2 = 2.5 -> 다음줄 2.5에 5/2를 대입
(2 + 2.5) / 2 = 2.25 ->(2+ (5/2)) / 2 = 2.25 = x + (num/x) / 2
5 / 2.25 = 2.222...
(2.25 + 2.222...) / 2 = 2.36111...
5 / 2.236111... = result
*/

/* !질문란
9를 넣으면 3이 나오지만,
4를 넣으면 2.000000000000002 이 계속나오길래
.toFixed()를 이용해서 소수점을 제거하여 결과값은 잘나오는데
테스트는 계속 fail로 나옵니다ㅠㅠ
toFixed()를 지우면 4를 넣었을시만 통과가 안되구요!
어떻게 해야할까요?ㅠㅠ
*/


// 처음에 square를 1로 선언해주셨는데, square는 단순히 1이 아닌, 
// 저희가 input으로 받은 값보다 같거나 작은 제곱수 중 가장 큰 값을 만들 수 있는 수가 되어야할 것 같습니다.

// 예를들어 5가 주어졌을 때 5보다 작은 제곱수는 4 square는 2
// 10이라면 10보다 작은 제곱수는 9 square는 3이 되어야할 것 같습니다.


```




### Question

## modulo

>Write a function called "modulo". ("modulo" 함수를 작성하세요.)

>Given 2 numbers, "modulo" returns the remainder after dividing num1 by num2. (두 숫자가 주어졌을때, "modulo" 함수는 첫번째 수를 두번째 수로 나눴을때 나머지 값을 반환합니다.)

```js


let output = modulo(25, 4);
console.log(output); // --> 1


```


### My_Soultion


```js

function modulo(num1, num2) {
    // num1 = 25 num2 = 4
  
  if (isNaN(num2) || num2 === 0) {
    return NaN;
  }

  // plusMinus 변수는 만약 첫번째 숫자가 plus 이면 마지막에 플러스를 마이너스를 표시하기 위해
  // 미리 변수를 지정해둔다.
  // 만약 num1 이 0보다 크면 plusMinus = 1
  // 만약 num2 가 0 보다 작으면 plusMinus = -1
  let plusMinus = num1 > 0 ? 1 : -1; //  이부분이 이해가 안됨. 

  num1 = Math.abs(num1);
  num2 = Math.abs(num2);

  while (num1 >= num2) {  // 25 >= 4
    num1 = num1 - num2; //  24 - 4 계속 빼면 = num1 = 1 
  }
  return num1 * plusMinus;  // 1 * plusMinus ( 1 ) 
}



```



### Question


## unique


```js

Return a duplicate-free version of the collection.
You don't need to care about non-primitive type elements.
Array will be contained only primitive type values. (string, number, boolean)


```


### My_Soultion



```js
unction unique(array) {
  // your code here


  let newArr = []

  for (let i = 0; i < array.length; i ++ ) {
    if (!newArr.includes(array[i])){
      newArr.push(array[i]);
    }
  }
    return newArr;
  }


  // 1. other_Soultion

  // function unique(array) {
  //   // your code here
  //   return array.reduce(function(acc, curr){
  //     if(!acc.includes(curr)){
  //       acc.push(curr);
  //       return acc;
  //     } else {
  //       return acc;
  //     }
  //   }, []);
  // }





 // 2. other_Soultion

//  function unique(array) {
//   // your code here
//   return Array.from(new Set(array))
// }






```




### Question

## tenThousandClub


```js

# tenThousandClub

Write a function, tenThousandClub, that takes in an array of information, salesTeam, and returns an array that lists the full names of each member of the sales team that has sales greater than $10,000.
Make sure the first and last names are separated by a space.

Hint: I recommend you write a helper function, salesToNumber, that converts the sales string to a number.
Feel free to look up parseInt() and slice() on MDN if you don't remember how they work.

- output: an array that lists the full names of each member of 10,000 club


```




### My_Soultion


```js


function tenThousandClub(salesTeam){
  // your code here

  // function salesToNumber(salesString){
  //   //get rid of dollar sign:
  //   let number = salesString.split('').splice(1)
  //   return parseInt(number.join(''));
  // }
  let newobj = salesTeam.filter(function(ele){
    return salesToNumber(ele.sales) >= 10000; 
  }).map(function(ele){
    return `${ele.name.first} ${ele.name.last}`;
  });
  return newobj;
}


// "$1234"  string to Number 숫자로 바꾸기 바꾸기 

// it's me
function salesToNumber(salesString){
  //get rid of dollar sign:
  let number = salesString.split('').splice(1)
  return parseInt(number.join(''));
}


// other's

// function salesToNumber(salesString){
//   //get rid of dollar sign:
//   return Number(salesString.slice(1));
// }

// other's

// function salesToNumber(obj){
//   return Number.parseInt(obj.sales.slice(1));
// }



```






### Question

## sumConsecutives


```js


You are given a list/array which contains only integers (positive and negative). Your job is to sum only the numbers that are the same and consecutive. The result should be one list.

Examples:
[1,4,4,4,0,4,3,3,1] should return [1,12,0,4,6,1]

So as you can see sum of consecutives 1 is 1
sum of 3 consecutives 4 is 12
sum of 0... and
sum of 2 consecutives 3 is 6 ...

[1,1,7,7,3] should return [2,14,3]
[-5,-5,7,7,12,0] should return [-10,14,12,0]

- output: an reduced array

```



### My_Soultion


```js

function sumConsecutives(s) {
    // your code here


    //[1,4,4,4,0,4,3,3,1] should return [1,12,0,4,6,1]
  
    let ret = []; // 마지막에 출력할  result 배열을 만든다. 
    let sum = 0;  // sum 이라는 것을 0 으로 초기화 시킨다. 

    for(let i = 0; i < s.length; i++) {

        // 첫번째 loop sum =  0 + 1 
        // 두번째 loop sum = 0 + 4 
        // 3번째 loop sum = 4 + 4 // 초기화 되지 않은 sum 과 다음에 나오르 4 를 합한다. 
       
        
        sum = sum + s[i];  
       
       
        // 첫번째 loop 
        // 만약 0번째있는 숫자 1과  1번째의 숫자4가 같지 않다면 
        // 조건문 1 을 ret 에 집어넣는다 [1]
        //  조건문  sum 이라는 것을 다시 0으로 초기화 한다.
        // 두번째 loop  
        // 1번째 있는 4와 2번째 있는 4와 같으므로 조건문에 해당이 안된다. 
        // sum 이 초기화 되지 않은채 위로 올라간다.   

        if(s[i] !== s[i + 1]) {
            ret.push(sum)  //  위에있는 sum 을 우선 채우고 
            sum = 0;    //  sum 을 다시 초기화 한다. 
        }
    }
     
    return ret;
}


```




### Question

## oldest


```js

# oldest

Write a function, oldest, that takes in an array of information, salesTeam, and returns a sentence with the person's first and last name, e.g. "The oldest student is Tina Fey".

If there is a tie for the oldest student, return the student whose name appears first in the salesTeam array.

- output: a string value with name of oldest person

```


### My_Soultion


```js


function oldest(salesTeam){
 
  // 먼저 배열안에 객체에 접근해서 모든 나이를 뽑아서 배열어 넣는다..
  // 나이중에 가장 높은 숫자를 변수에 담는다.
  // 변수에 담긴 가장 높은 숫자와 배열안에 객체에 나이가 같다면 first name  과 last name 을 가져온다. 
  
  var ageArr = salesTeam.map(function(ele){
    return ele.age;
  })
  var max = ageArr.reduce(function(a,c){
    return Math.max(a,c);
  });
  var fullName = [];
  salesTeam.forEach(function(ele){
    if ( ele.age === max) {
      fullName.push(`${ele.name.first} ${ele.name.last}`)
    }
  })
  return "The oldest student is " + fullName.join(" ");
}



```





### Question

## isAgeDiverse


```js

You will be given an array of objects representing data related to their age and total sales.

Your task is to return:
- `true` if members from all of the following age groups: teens, twenties, thirties, forties, fifties, sixties, seventies, eighties.
- `false` otherwise.

Your function should return true as there is at least one member from each age group.

- output: a boolean value representing whether the age range is diverse



```


### My_Soultion



```js

var isAgeDiverse = function(list) {
  
  // group 이 10-80 까지 는 true 리턴
  // 아니라면 false 리턴 
  
  var ageArr = list.map(function(ele){
    return ele.age; // [26, 55, 29, 53, 19, 25, 26]
  });
    for (let i = 0; i < ageArr.length; i = i + 1 ) {
      if (ageArr[i] >= 10 && ageArr[i] < 90) {
      return true;
    } else {
    return false;
    }
  };
};

  // other code here
  // 팀원이 10대~80대 면 true를 반환해라.
  // function filtering(el){  // 클로져를 써보자
  //   return el.age >= 10 && el.age < 90 
  // }
  // // every를 써서 모두가 맞는지 확인한다.
  // return list.every(filterin



```







### Question

## getTeenager

>Write a function, `getTeenager`, that takes in an array of information, salesTeam, and returns an array that lists the full names of each member of the sales team that is a teenager.

```js
Make sure the first and last names are separated by a space.

Notes:
- moving through each element of the array.
- check if they are a teenager (< 20).
- if they're a teenager, store their full name, separated by a space into the array.

* * *

- output: an array that lists the full names of each member of the sales team that is a teenager

```


### My_Soultion


```js


function getTeenager(salesTeam) {
  let teenager = [];

  
  for(let i=0; i < salesTeam.length; i++) {
    let fullName = salesTeam[i].name.first + ' ' + salesTeam[i].name.last;
    if(salesTeam[i].age < 20) {
      teenager.push(fullName)

    }
  }
  return teenager;
}


```

### other_Soultion



```js


function getTeenager(salesTeam) {
  // your code here
  let teenager = salesTeam.filter(function(ele){
    return ele.age < 20;
  });
  let result = [];
  teenager.forEach(function(ele){
    result.push(`${ele.name.first} ${ele.name.last}`);
  });
  return result;
}




```



### Question


## sumDigits


> Write a function called "sumDigits". ("sumDigits" 함수를 작성하세요.)

>Given a number, "sumDigits" returns the sum of all its digits. (숫자가 주어졌을때, "sumDigits" 함수는 숫자의 각 자리수를 모두 더한 값을 반환합니다.)
k


### My_Soultion


```js

function sumDigits(num) {
  let sum = 0;
  let stringNumArr = num.toString().split('');

  for (let i = 0; i < stringNumArr.length; i++) {
    if (stringNumArr[0] === '-' && i === 1) {
      sum = sum - Number(stringNumArr[1]);
    } else if (stringNumArr[i] !== '-') {
      sum = sum + Number(stringNumArr[i]);
    }
  }

  return sum;
}

```








### Question


## offLineMinimum



>Have the function `offLineMinimum(strArr)` take the strArr parameter being passed which will be an array of integers ranging from 1...n and the letter "E" and return the correct subset based on the following rules.


> The input will be in the following format: `["I","I","E","I",...,"E",...,"I"]` where the I's stand for integers and the E means take out the smallest integer currently in the whole set.
When finished, your program should return that new set with integers separated by commas.





### My_Soultion 

```js

function offLineMinimum(strArr) {


  let numArr=[];
  let resultArr=[];
   
  // ["5","4","6","E","1","7","E","E","3","2"]
  
  for(let i=0; i< strArr.length; i++){
    // 만약 E와 같지 않다면 
    if (strArr[i] !== 'E') {
      // 이코드는 7번 실행된다 왜냐하면 E 가 3개만 있기 때문이다. 
      
      numArr.push(strArr[i]);
    
     
      //   (1) ["5"]
      //   (2) ["5", "4"]
      //   (3) ["5", "4", "6"]
      //   (4) ["5", "6", "1"]
      //   (5) ["5", "6", "1", "7"]
      //   (6) ["6", "7", "3"]
      //   (7) ["6", "7", "3", "2"]   
      
      
      
      // // 만약 E와 같다면 
    } else if(strArr[i] === 'E') {
      
      
       let smallNum = numArr.reduce(function(acc,curr){
          
         // 첫번째 "E" 나오면  numArr = ["5","4",6] 작은수 => "4"
         // 두번째 "E" 나오면  numArr =  ["5", "6", "1", "7"] 작은수 => "1"
         // 세번째 "E" 나오면  numArr = ["5","6","7"]  작은수 => "5"

         // smallNum = ["4","1","5"] 3번에 담긴다 가장 작은수들이 coz E를 3번 찾았기 때문에
         
         if(acc < curr){
           return acc;
         } else {
           return curr;
         }
       });

      // 첫번째 "E" 나오면 smallNum = "4" 
      // 두번째 "E" 나오면 smallNum = "1"
      // 세번째 "E" 나오면 smallNum = "7"

      // resultArr 에 ["4","1","7"]; 담긴다.
       resultArr.push(smallNum); 
       
       // 첫번째 "E" 나오면 ["5","4","6"].splice(1,1) // "4" 삭제됨
       // 두번째 "E" 나오면 ["5", "6", "1", "7"].splice(2,1) // "1" 삭제됨
       // 세번째 "E" 나오면 ["5","6","7"].splice(0,1) // "5" // "5" 삭제됨  
       numArr.splice(numArr.indexOf(smallNum),1); 
   }
  }
    return resultArr.join(','); // 마지막으로 "4,1,5" =>>,나눠서 함친다.
 }


 
offLineMinimum(["1","2","E","E","3"]); // => '1,2'
offLineMinimum(["4","E","1","E","2","E","3","E"]); // => '4,1,2,3'
offLineMinimum(["5","4","6","E","1","7","E","E","3","2"]) // == > 
`4,1,5`



```


### other_Soultion



```js



function offLineMinimum(strArr) {
  
   
// offLinMininum은 배열에서 'E' 가 나오기 이전까지의 숫자들로 숫자의 set을 만들고 e가 등장 할 때 마다 숫자 set 중 가장 작은 수를 가지고와 리턴할 문자열에 포함시켜주는 함수이다.

    // 배열에서 'E'가 나오기 이전까지의 숫자들로 숫자의 Set을 만든다. --> numberSet
    // 배열에서 'E'가 등장하면, numberSet을 분류(작은 수~큰 수)하고 numberSet의 0번째 값(가장 작은 수)을 가지고와 result에 넣어준다.
    // 그리고 numberSet의 0번째 값은 제거해준다.
    // 그래야 다음 번에 'E'가 등장하면 그 요소를 제외한 나머지 값들 중에서 최소값을 구할 수 있기 때문이다.

    let numberSet=[];
    let result=[];

    for (let i = 0 ; i < strArr.length ; i++) {
        if (strArr[i] !== 'E') {
            numberSet.push(Number(strArr[i]));
        }
        else if (strArr[i] === 'E') {
            numberSet.sort();
            result.push(numberSet[0]);
            numberSet.shift();
        }
    }

    return result.join();
}




```









### Question 

## range

> Complete the below function called range that takes two integers as parameters, start and end, and returns an array containing all the whole numbers between them starting with start and up to end (you can use a any loop)

> After you write your function, you can test it using the above inputs to make sure that it behaves correctly.
 
 
### My_soultion


```js

function range(start, end) {
  // YOUR CODE HERE
  
  
    
  // 만약 strat 와 end 같다면 && 만약 strat 가 end 보다 작으면 [] 반환
  // for 문을 사용해 start 를 초기값으로 지정하고 end 보다 작을때까지 숫자 반환
  
  let arr = [];
  
  if ( start === end || start >= end ) {
    return [];
  } else { 
    for ( let i = start; i < end; i = i + 1 ) {
      arr.push(i);
    }
  }
  return arr;
  }

range(0, 4); // => [0, 1, 2, 3]
range(2, 7); // => [2, 3, 4, 5, 6]
range(10, 10); // => []
range(10, 2); // => []



```











### Question 

## longestName


> Given the following array of people, write a function that, when passed people as a parameter, returns the person (that is, your function should return an object) with the longest name (first, middle & last).
You can re-use getFullName function.


### My_Soution



```js

var people = [
  {name: {first: "Alyssa", middle: "P.", last: "Hacker"}, age: 26},
  {name: {first: "Ben", last: "Bitdiddle"}, age: 34},
  {name: {first: "Eva", middle: "Lu", last: "Ator"}, age: 40},
  {name: {first: "Lem", middle: "E.", last: "Tweakit"}, age: 45},
  {name: {first: "Louis", last: "Reasoner"}, age: 21}
];


function longestName(people) {
  // TODO: Your code here
  // 심플하게 객체에 있는 키값을 prop  가져와 함친다. 
  return Object.values(people[0].name).join(' ');
 

}

longestName(people); //"Alyssa P. Hacker"


```

 ### Question

## hammingDistance

> have the function `HammingDistance(strArr)` take the array of strings stored in `strArr`, which will only contain two strings of equal length andreturn the Hamming distance between them.
The Hamming distance is the number of positions where the corresponding characters are different.



```js
For example:
if `strArr` is `["coder", "codec"]` then your program should return 1.

```


### My_Soultion


```js


function hammingDistance(strArr) {
  // YOUR CODE HERE

  // count 변수에 0으로 초기화를 시켜놓는다.
  // arr1 변수를 만들어 strArr 첫번째 값을 넣어둔다.
  // arr2 변수를 많들어 strArr 두번째 값을 넣어둔다. 
  // while 문 이용해 arr1각각char arr2각각 Char 와 같이 않다면 count에 plus 1 증가 
  // 출력 count ;


  let count = 0;

  let str1 = strArr[0];
  let str2 = strArr[1];
  
  for (let i = 0; i < str1.length; i = i + 1 ) {
    if ( str1[i] !== str2[i] ) {
      count = count +  1;
    }
  }

  return count;
}

hammingDistance(["coder", "codec"]); // => 1
hammingDistance(["10011", "10100"]); // => 3
hammingDistance(["helloworld", "worldhello"]); // => 8




```



### Other_Soultion


```js


strArr[0][0] !== strArr[1][0] count++
strArr[0][1] !== strArr[1][1] count++
strArr[0][2] !== strArr[1][2] count++
strArr[0][3] !== strArr[1][3] count++
strArr[0][4] !== strArr[1][4] count++


// 위를 잘 참고하여...구현해본다!
// 각각 비교하면서 다른 값을 배열에 담아 개수를 리턴한다.



function hammingDistance(strArr) {
  return strArr[0].split('').filter((char, i) => char !== strArr[1][i]).length;
}

hammingDistance(["coder", "codec"]); // => 1
hammingDistance(["10011", "10100"]); // => 3
hammingDistance(["helloworld", "worldhello"]); // => 8
console.log(hammingDistance(["coder", "codec"]))


```







### Question 


## getFullName


>Write a function called 'getFullName' that takes in an object which has this structure:


### My_Soultion

```js

function getFullName(obj) {
  // YOUR CODE HERE
  //  변수를 만들어 person에 있는 키의 값들을 가져와서 조합시킨다. 
  // 변수를 출력한다. 
  
  
let fullName = person.name.first + " " + person.name.middle + " " + person.name.last;  

  return fullName;
}

var person = {
  name : {
    first : "Alyssa",
    middle: "P.",
    last: "Hacker"
  },
  age : 26
};
getFullName(person); //"Alyssa P. Hacker"

var personB = {
  name: {
    first: "Ben",
    last: "Bitdiddle"
  },
  age: 34
};
getFullName(personB); //"Ben Bitdiddle"


```



### Other_Soultion

```js


//함수 아래 케이스에 맞게 name값에 접근하여 fullName을 만든다.
//하나하나 따로 뽑기보다는 value를 배열로 받아서 합치는게 편하다 :)

function getFullName(obj) {
  return Object.values(obj.name).join(' ')
}


```





### Question 


## billTotal

>Write a function called billTotal that can be used to calculate the total to be paid at a restaurant -- including tip and tax -- given the subtotal (i.e. cost of food and drinks). We can assume that the tip will be 15% and tax will be 9.5%. Make sure that the tip does not include the tax!


### My_Soultion


```js


- input: a number representing the cost of food and drinks
- output: a number representing that cost plus an additional 15% tip and tax of 9.5%


function billTotal(subtotal) {
  // YOUR CODE HERE

  // tip 15% = * 0.15
  // tax 9.5% = * 0.095
  
  // tip을 얼마 냈는지 조사후 변수에 저장
  // tax를 얼마나 냈는지 조사후 변수에 저장
  // tip & tax & subtotal 더한값을 출력
  
  let tip = subtotal * 0.15
  let tax = subtotal * 0.095
  
  return subtotal + tip + tax;
}

billTotal(10.00); // => 12.45



```

### Other_Soultion



```js

// 뭐 단순하게...팁 15%, 세금 9.5% 더해주면 된다고 한다 :)

function billTotal(subtotal) {
  return (subtotal * 1.15 + subtotal * 0.095)
}

billTotal(10.00); // => 12.45





```






### Question


## primeMover



>Have the function primeMover(n) return the n-th prime number. The range will be from 1 to 5 * 10^4; (숫자(n)가 주어졌을때, 'primeMover(n)' 함수는 num 번째 소수를 반환합니다. 범위는 1에서 50,000 입니다.)

>For example: if n is 16 the output should be 53 as 53 is the 16th prime number. (예시: 만약 n 이 16이라면, 결과값은 16번째 소수인 53 입니다.)


### My_Soultion


```js


let primeMover = function(n) {
  // your code here


  let arr = [1];
  for ( let i = 1; i <100; i++) {
    for ( let j = 2; j < 100; j++ ) {
      if (j % i !== 0 ) {
       arr.push(j);
      }
    }
  }
  return arr[n];
}


```






### Question

## isOddWithoutModulo



> Write a function called "isOddWithoutModulo". ("isOddWithoutModulo" 함수를 작성하세요.)

>Given a number, "isOddWithoutModulo" returns whether the passed in number is odd. (숫자가 주어졌을때, "isOddWithoutModulo" 함수는 주어진 숫자가 홀수인지를 반환합니다.)


### My_Soultion 


```js

// 2. it is used by Math.floor 

function isOddWithoutModulo(num) { // floor 메소드로 참과 거짓을 출력할뿐만 아니라 정수로 만든다. 그것을 2로 나눠서 2로 다시 곱한값이 기존에 값과 일치하지 않는다면 홀수이므로 true 반환
  
  return Math.floor(num / 2) * 2 !== num;  

```



### Others_Soultion

```js

function isOddWithoutModulo(num) {
   // 예를 들어, num이 -17이라고 가정합니다. 
   num = Math.abs(num);
// num은 절대값이 되어 17이됩니다. 이를 통해 파라미터에 들어올 모든 음수를 커버할 수 있을 겁니다. 
   if( num === 0 )  // num은 현재 17로 0이 아니기 때문에 그 다음 else if로 넘어가게 됩니다. 
       return false;
   else if(num === 1) // num은 현재 17로 1이 아니기 때문에 그 다음 else로 넘어가게 됩니다. 
       return true;
   else { // 보통 홀수인지 아닌지를 판별하기 위해서 2로 나누었을 대 나머지값을 확인하는 방법을 씁니다. 
// 그 방법을 풀어보면 17 -2 -2 -2 -2 -2 -2...... 하여 0 혹은 1이 될 때까지 뻰다는 것을 의미합니다. 
       return isOddWithoutModulo(num-2); // 이 부분은 바로 위의 설명이 적용되는 부분입니다. 
// 자바스크립트는 재귀함수가 가능하여 함수 안에서 자기 자신을 호출할 수 있습니다.
// 이를테면 num이 17이었다면 위의 구문을 통해 다시  isOddWithoutModulo(17-2)를 호출하는 것입니다. 
// 위의 과정을 다시 반복하게 되면 isOddWithoutModulo(15) --> isOddWithoutModulo(13) --> isOddWithoutModulo(11).... 
// num이 0 혹은 1이 되어 if와 else if 구문에 걸려 return될 때까지 반복됩니다. 
   }
}


```





### Question


## getStringLength


> Write a function called "getStringLength". ("getStringLength" 함수를 작성하세요.)

>Given a string, "getStringLength" returns the length of the given string. (문자열이 주어졌을때, "getStringLength" 함수는 주어진 문자열의 길이를 반환합니다.)

>Do NOT use any native 'length' methods. (- 'length' 메소드를 사용하지 마세요.)





### My_Soultion

```js

function getStringLength(string) {
  // your code here

  // 1. count 변수를 만들어 초기값을 지정한다. 
  // 2. while loop를 이용해 string[count] 값을 지정해 조건문을 만든다. 
  // 3. 참이면 count 에 1씩 증가시킨다. 그러면 조건문에 인덱스 번호가 넘어가면 조건문이 문자의 길이만큼 값이 count 에 저장된다. 

  let count = 0;

  while (string[count]) {
    count = count + 1;
  };
  return count;
};


```





### Question

## getIndexOf

>Write a function called "getIndexOf". ("getIndexOf" 함수를 작성하세요.)

>Given a character and a string, "getIndexOf" returns the first position of the given character in the given string. (문자와 문자열이 주어졌을때, "getIndexOf" 함수는 주어진 문자열에서 주어진 문자가 나타나는 첫번째 위치를 반환합니다.)



### My_Soultion


```js
function getIndexOf(char, str) {

      for (let i = 0; i < str.length;  i = i + 1 ) {
          if ( str[i] === char ) {  //  만약 str 에 있는 문자들중에 char 같다면 
            return i;  // 리턴 인덱스 번호 
          } 
        }
      return -1; //  아니면 -1  반환
    }



```





### Question

## calculateBillTotal

> Write a function called "calculateBillTotal". ("calculateBillTotal" 함수를 작성하세요.)

>Given the pre tax and pre tip amount of a meal, "calculateBillTotal" returns the total amount due after tax and tip. (팁과 세금을 제외한 식사값이 주어졌을때, "calculateBillTotal" 함수는 팁과 세금이 포함된 총 식사값을 반환합니다.)

>Assume that sales tax is 9.5% and tip is 15%. (- 세금은 9.5% 팁은 15% 로 계산하세요.)
>Do NOT tip on the sales tax, only on the pre tip amount. (- 팁을 계산할때 세금을 포함하여 계산하지 마세요.)




### My_Soultion

```js

function calculateBillTotal(preTaxAndTipAmount) {
  // your code here

  // 1. salesTax 변수를 만들고 주어진 값의 0.095 곱한 값을 대입
  // 2. tip 변수를 만들고 주어진 값의 0.15 를 곱한 값을 대입
  // 3. 모든값을 더한후 리턴  
 

  let salesTax = preTaxAndTipAmount * 0.095;
  let tip = preTaxAndTipAmount * 0.15;

  return preTaxAndTipAmount + salesTax + tip;
}




```





### Question

## convertObjectToArray3

> Write a function called "convertObjectToList" which converts an object literal into an array of arrays, like this: (객체를 입력으로 받고 해당 객체를 다음과 같이 2차원 배열로 변형 할 수 있는 함수 "convertObjectToList"를 작성하세요.)




### My_Soultion

```js
function convertObjectToList(obj) {
  // your code here
  
  // 1. 마지막에 출력할 빈배열을 만든다. 
  // 2. for 문을 사용해서 객체안에 있는 key와 prop 값에 전근한다. 
  // 3. push 사용해 접근한 key값은 0번째 값에 넣고 prop 값은 1번째 값에 넣는다. 
  // 4. arr 리턴한다. 

  let arr = [];
  for ( let key in obj ) {
    arr.push([key,obj[key]]);
  }  
 return arr;
}




```


### Question

## isOdd

>Write a function called isOdd. ("isOdd" 함수를 작성하세요.)

>Given an integer, isOdd returns whether the integer is odd or not. (숫자가 주어졌을때, "isOdd" 함수는 주어진 숫자가 홀수 인지 아닌지를 반환합니다.)


### My_Soultion


```js

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

### My_Refactoring code

```js

function isOdd(num) {
  // your code here

  // 만약 num  % 2 의 나머지수가  0 이면 짝수 return false;
  // 그게 아니라면 true 리턴
  return num % 2 === 0 ? false : true;
}



```


### Question

## sum

>Summation to n: Let's implement the function sum that takes a single parameter n, and computes the sum of all integers up to n starting from 0, e.g.:

>(n까지의 총 합: n을 매개변수로 받아 0 부터 n 까지 모든 수의 총 합을 반환하는 함수를 작성하세요.)


### My_Soultion



```js
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

### Question


## onlyEvenElements


>Given an array of numbers, onlyEvenElements returns a new array of just the even numbers. (숫자로 이루어진 배열이 주어졌을때, "onlyEvenElements" 함수는 주어진 배열에 있는 짝수로만으로 이루어진 새로운 배열을 반환해야 합니다.)


### My_Soultion


```js

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


### Question

## removeOddValues

>Write a function removeOddValues that takes an object as an argument and returns an object with all key/value pairs removed for which the value holds an odd number. ("removeOddValues" 함수를 작성하세요. 객체가 주어졌을때, "removeOddValues" 함수는 주어진 객체의 key/value 페어 중 value 가 홀수 숫자인 페어가 제거된 객체를 반환하세요.)

>You'll need to use the "typeof" operator to first check that the values are numbers: (value가 숫자인지 확인하기 위하서는 "typeof" 연산자를 먼저 사용해야 합니다.)


### My_Soultion

 

```js

// first 

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



// Sceond 

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




//third


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



### Question

## firstCharacter

> In this exercise, a string is passed to a method and a new string has to be returned with the first character of each word in the string (문자열이 주어졌을때, "firstCharacter" 함수는 문자열의 각 단어 첫글자들로 이루어진 문자열을 반환하여야 합니다.)


> Attention! In test case 5 userinput is one space input char as ' ', please do not get confused with '', empty string (주의사항! 테스트 케이스 5 에서 주는 입력값은 띄어쓰기 한개(' ') 입니다. 빈 문자열('') 과 혼동하지 마세요.)


### My_Soultion


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

### Question

## dashInsert


>Have the function DashInsert insert dashes ('-') between each two odd numbers in str. (문자열이 주어졌을때, 'DashInsert' 함수는 문자열에 있는 두 홀수 사이에 대시('-')를 추가하여 반환합니다.)

>For example: if str is 454793 the output should be 4547-9-3. (예시: 주어진 문자열이 454793 이라면 결과값은 4547-9-3 입니다.) Don't count zero as an odd number. (0 을 홀수로 간주하지 마세요.)





```js

// 1/for 문


function DashInsert(string) {
 


 let output = [];
 let tmp=string.split('');
 for(let i=0;i<tmp.length;i++){
   //홀수가 연속해서 나올때 => i번째와 '-'을 넣는다.
   if(tmp[i]%2 && tmp[i+1]%2){// 1,3
     output.push(tmp[i],'-');//1,-,3
   }else{
     output.push(tmp[i]);
   }
 }
 return output.join('');
 }

///////////////////////////////////////////////////////////////////

// 1. reduce 

function DashInsert(string) {
 
 let output = '';
 let tmp = string.split('');
 output = tmp.reduce(function(acc,cur){
   if((acc)%2===1 && (cur)%2===1) return acc+'-'+cur;
   else return acc+cur;
 });
 return output;

}


////////////////////////////////////////////////////////////////////

// 2.splice

function DashInsert(string) {
  let arr = string.split('');
  for (let i = 0; i < arr.length; i++) {
    if ( arr[i] % 2 === 1 && arr[i + 1] % 2 === 1) {
      arr.splice(i +1,0,'-');
    }
  }
  return arr.join('');
}




```



### Question 

## longestWord


> sing the JavaScript language, have the function LongestWord take the sen parameter being passed and return the largest word in the string. (문장이 주어졌을때, 'LongestWord' 함수는 주어진 문장에서 가장 긴 단어를 반환합니다.)

>If there are two or more words that are the same length, return the first word from the string with that length. Assume sen will not be empty. (만약 가장 긴 단어가 두개 이상이라면, 첫번째로 등장하는 가장 긴 단어를 반환하세요. 문장은 빈 문자열이 아닙니다.)


### My_Soultion


```js 

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


### Question


## convertArrayToObject1


>Write a function 'transformFirstAndLast' that takes in an array, and returns an object with: (배열을 입력으로 받고 다음 조건에 만족하는 객체를 반환하는 함수 'transformFirstAndLast' 함수를 작성하세요.)

>the first element of the array as the object's key, and (1. 배열의 첫번째 요소를 객체의 키로 가집니다.)
the last element of the array as that key's value. (2. 배열의 마지막 요소를 해당 키의 값으로 가집니다.)



### My_Soultion


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


### Question

## convertObjectToArray1



>Write a function called "getAllKeys" which returns an array of all the input object's keys. (객체를 입력으로 받고 해당 객체의 키들을 배열로 반환하는 "getAllKeys" 함수를 작성하세요.)



### My_Soultion


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

### Question 


## convertArrayToObject2




> Write a function 'fromListToObject' which takes in an array of arrays, and returns an object with each pair of elements in the array as a key-value pair. (2차원 배열을 입력으로 받고 배열안에 있는 배열의 요소 페어를 키-값 페어로 가지는 객체를 반환하는 함수 'fromListToObject' 함수를 작성하세요.)



### My_Soultion


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


### Questoin


## convertObjectToArray2



>Write a function called "listAllValues" which returns an array of all the input object's values. (객체를 입력으로 받고 해당 객체의 값들을 배열로 반환하는 "listAllValues" 함수를 작성하세요.)


### My_Soultion


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




### Question

## convertArrayToObject3


> Write a function called "transformEmployeeData" that transforms some employee data from one format to another. (사원들의 정보를 다른 형태로 변형 할 수 있는 함수 "transformEmployeeData" 함수를 작성하세요.)

>The argument will look something like this: (사원들의 정보는 아래와 같은 배열로 주어질 수 있습니다.)



### My_Soultion

```js

function transformEmployeeData(array) {

  // 1. 맨 위 배열을 루프 데이터 가져온다.
  // 2. 가지고온 배열을 또 루프 를 돌려서 가져온다.
  // 3. 가지고온 배열을 0번째는 obj key 1번째는 value
  // 4. 만든 obj 를 배열에 푸시 
  
  
  let arr = [];
  
  for ( let i = 0; i < array.length; i = i + 1 ) {
    let data = {};
    for ( let n = 0; n < array[i].length; n = n + 1 ) {
      data[array[i][n][0]] = array[i][n][1];
    }
    arr.push(data);
  }
  return arr;


```


### other_Soultion


```js





function transformEmployeeData(array) {
 
 // your code here
 // [key] start: firstName - last: role
 // return [{}] index0 key; index1 value;
  
 // 배열 안에 객체가 들어가 있는 것을 반환해야하니까
 // 빈배열 선언하고 빈 객체 선언 해서 빈 객체에 값 넣고
 //그 객체를 빈 배열에 넣어주고
 // 최종적으로 return 그 배열 해 주면 됨

  let result = [];

  for (let i of array){ // 여기서 i 는 [['firstName', 'Joe'], ['lastName', 'Blow'], ['age', 42], ['role', 'clerk']]
    let obj = {};
   for (let j of i){ // 여기서 j는 ['firstName', 'Joe']
     obj[j[0]] = j[1]; // j의 0번 elemente 'firstName' , 1번 element 'Joe'
    // obj[array[j][0]] = array[j][1];
   }
   result.push(obj);
  }

return result;
}


```



### Qutestion 

## greetCustomers


>Write a function called "greetCustomer". ("greetCustomer" 함수를 작성하세요.)

>Given a name, "greetCustomer" returns a greeting based on how many times that customer has visited the restaurant. Please refer to the customerData object. (고객들의 방문 횟수를 가지고 있는 객체와 이름이 주어졌을때, "greetCustomer" 함수는 손님이 몇번 방문했는지에 따라 다른 인삿말을 반환합니다. customerData 객체를 참고해 주세요.)

### My_Soultion

```js

function greetCustomer(customerData, firstName) {
  let greeting = '';
  // your code here

  // 1 . 객체의 속성의 객체의 속성값 접근한다.
  // 2.  객체의 속성의 객체의 속성값이 undefinded 이라면 1 greeting 대입
  // 3.  객체의 속성의 객체의 속성값이 1 이라면 2  greeting 대입
  // 4.  객체의 속성의 객체의 속성값이 1 보다 크다면 3 greeting 대입

    if (!customerData[firstName]) {
        greeting = `Welcome! Is this your first time?`;
    } else if (customerData[firstName].visits === 1  ) {;
        greeting = `Welcome back, ${firstName}! We're glad you liked us the first time!`
    } else if ( customerData[firstName].visits > 1 ) {
        greeting =  `Welcome back, ${firstName}! So glad to see you again!`;
    }
    return greeting;
}

```


### Question

## convertDoubleSpaceToSingle


> Write a function called "convertDoubleSpaceToSingle". ("convertDoubleSpaceToSingle" 함수를 작성하세요.)

>Given a string, "convertDoubleSpaceToSingle" returns the passed in string, with all the double spaces converted to single spaces. (문자열이 주어졌을때, "convertDoubleSpaceToSingle" 함수는 주어진 문자열에 있는 띄어쓰기 두개(double spaces)를 띄어쓰기 한개(single space)로 변환한 뒤 해당 문자열을 반환합니다.)



### My_Soultion


```js

function convertDoubleSpaceToSingle(str) {
  
  // 1. 문자열을 split() 를 사용해서 str 변수에 배열로 저장한다.
  // 2. reduce 를 사용해서 배열에 담긴 문자의 single space로 만들어 출력한다. 

  let strArr = str.split("  ");
  let output = strArr.join(" ");
  return output;
}


// Refactoing

function convertDoubleSpaceToSingle(str) {
  return str.split("  ").join(" ");

}


```



### other_Soultion


```js

function convertDoubleSpaceToSingle(str) {
  return str.replace( /  +/g,' ');
}
잘되긴 하는데.... ㅡ,.ㅡ

/ +/g 부분이 이해가 가지 않습니다...............
/(빈칸 두개)+/g 를 찾아서 ' '로 바꿔준다는 것 같습니다.

```




### other_Soultion

```js

function convertDoubleSpaceToSingle(str) {

var array = str.split(' '); // 문자열 배열 만들기  [ 'string', '', 'with', '', 'double', '', 'spaces' ]

for (i = 0; i<=array.length; i++) { // for 문을 이용해 배열 접근 
  if (array[i] === '') { //만약 각각의 요소가 '' 와 같다면
    array.splice(i,1); // splice 접근해서 삭제 
  }
}

return array.join(' '); // 각각의 문자열을 join ' ' 를 나눠서 출력 

}


```
