---
title:  __Algorithm_3
date: 2019-04-29
draft: true
menu:
  tutorial:
    parent: "6.Javascript"
    weight: 3
toc: yes
type: docs
---


![](/tutorial/Javascript_Dictionary_files/javascriptt-light_870x220.png)


---------------------------------------------------------------------------



### Qeustion 

## scrabble word calculator

> implement the word_calc method to return the correct Scrabble word score. The scores are already set up for you to use and are managed within Dictionaries:

```js

one_point_values = ["a", "e", "i", "o", "u", "l", "n", "r", "s", "t"];
two_point_values = ["d", "g"];
three_point_values = ["b", "c", "m", "p"];
four_point_values = ["f", "h", "v", "w", "y"];
five_point_values = ["k"];
eight_point_values = ["j","x"];
ten_point_values = ["z","q"];


word_calc("zoo") // 12
word_calc("bus") // 5

```

### My_soultion



```js


function word_calc(word) {



	var inputArr = word.split("");
	var countArr = [];
	var dataArr = [one_point_values,two_point_values,three_point_values,four_point_values,five_point_values,eight_point_values,ten_point_values];
	var total = 0;
	function sum(array) {
		var countArr = [];
		var sum = 0;
		if(array[0]=== one_point_values[0]) {
			 for (let i = 0; i < inputArr.length; i ++ ) {	
			 	if (array.includes(inputArr[i])) {
		  		countArr.push(inputArr[i])
		  	} 
		  	sum = countArr.length * 1;
		  	
		  }
			countArr = [];
		} 

		else if (array[0]=== two_point_values[0]){
			 for (let i = 0; i < inputArr.length; i ++ ) {	
			 	if (array.includes(inputArr[i])) {
		  		countArr.push(inputArr[i])
		  	} 
		  	sum = countArr.length * 2;
	  	 
		  }
			countArr = [];	
		}
		
		else if (array[0]=== three_point_values[0]) {
			 for (let i = 0; i < inputArr.length; i ++ ) {	
			 	if (array.includes(inputArr[i])) {
		  		countArr.push(inputArr[i])
		  	} 
		  	sum = countArr.length * 3;
	  	 	
		  }
			countArr = [];
		}
			
		else if (array[0]=== four_point_values[0]) {
			 for (let i = 0; i < inputArr.length; i ++ ) {	
			 	if (array.includes(inputArr[i])) {
		  		countArr.push(inputArr[i])
		  	} 
		  	sum = countArr.length * 4;
	  	 }
            countArr = [];
		}

		else if (array[0]=== five_point_values[0]) {
			 for (let i = 0; i < inputArr.length; i ++ ) {	
			 	if (array.includes(inputArr[i])) {
		  		countArr.push(inputArr[i])
		  	} 
		  	sum = countArr.length * 5;
          }
			countArr = [];
		}
		
		else if (array[0]=== five_point_values[0]) {
			 for (let i = 0; i < inputArr.length; i ++ ) {	
			 	if (array.includes(inputArr[i])) {
		  		countArr.push(inputArr[i])
		  	} 
		  	sum = countArr.length * 8;
		  }
			countArr = [];
		} 
		
		else if (array[0]=== ten_point_values[0]) {
			for (let i = 0; i < inputArr.length; i ++ ) {	
			 	if (array.includes(inputArr[i])) {
		  		countArr.push(inputArr[i])
		  	} 
		  	sum = countArr.length * 10;
		  }
			countArr = [];
        }
		total = total + sum;
    }

    dataArr.forEach((ele)=>{
    	sum(ele);
    })

    return total;


}


```




### Question

## 4칙연산 함수 만들기 

> Create a basic calulator with the following functions add,subtract,multiply and divide, implement the correct code to return correct mathematical value the functions should take two arguments

```js

// 파이썬 문제이지만 자바스크립트로 풀어보았습니다. 

// 이렇게 출력하게 만드는 문제입니다. 
Answer.add(2,2) // 4
Answer.subtract(2,2) // 0
Answer.multiply(2,2)// 4
Answer.divide(2,2)// 1.0

// 저는

answer.call(add,2,2) // 4
answer.call(subtract,2,2) // 0
answer.call(multiply,2,2) // 4
answer.call(divide,2,2) // 1.0

```

### My_Soultion


```js
var add = {
	add: 0
}
var subtract = {
	
}
var multiply = {
	multiply: 0
}
var divide = {
	divide: 0
}

var answer = function (first,second) {
  if(this === add) {
	return this.add = first + second; 
  } else if ( this === subtract) {
	return this.subtract = first - second;
  } else if (this === multiply) {
  	return this.multiply = frist * second;
  } else if ( this === divide ) {
	return this.divide = first / second;
  }
}


```




## nonUniqueElements(data)

### Question

> You are given a non-empty list of integers (X). For this task, you should return a list consisting of only the non-unique elements in this list. To do so you will need to remove all unique elements (elements which are contained in a given list only once). When solving this task, do not change the order of the list. Example: [1, 2, 3, 1, 3] 1 and 3 non-unique elements and result will be [1, 3, 1, 3].

```js

Input: A list of integers.

Output: An iterable of integ

var assert = require('assert');

if (!global.is_checking) {
    assert.deepEqual(nonUniqueElements([1, 2, 3, 1, 3]), [1, 3, 1, 3], "1st example");
    assert.deepEqual(nonUniqueElements([1, 2, 3, 4, 5]), [], "2nd example");
    assert.deepEqual(nonUniqueElements([5, 5, 5, 5, 5]), [5, 5, 5, 5, 5], "3rd example");
    assert.deepEqual(nonUniqueElements([10, 9, 10, 10, 9, 8]), [10, 9, 10, 10, 9], "4th example");
    console.log("Coding complete? Click 'Check' to review your tests and earn cool rewards!");
}

```



### My_Soulion

```js
function nonUniqueElements(data) {
    let overLap = data.filter((ele,index)=>{
        return data.indexOf(ele) !== index
        })
    overLap = Array.from(new Set(overLap));
    
    return data.filter(function(val) {
        return overLap.indexOf(val) !== -1;
    })
}




```


### Others

```js



function checkio(data) {
    return data.filter(function(a){
        return data.indexOf(a) !== data.lastIndexOf(a)    
    });
}
```