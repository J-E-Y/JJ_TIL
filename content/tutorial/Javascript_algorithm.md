---
title:  __Algorithm_3
date: 2019-04-29
draft: true
menu:
  tutorial:
    parent: "7.Javascript"
    weight: 3
toc: yes
type: docs
---


![](/tutorial/Javascript_Dictionary_files/javascriptt-light_870x220.png)


---------------------------------------------------------------------------



### Qeustion 

### scrabble word calculator

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

### Other_Soultion

```js

const char_points = {
  "a": 1,
  "e": 1,
  "i": 1,
  "o": 1,
  "u": 1,
  "l": 1,
  "n": 1,
  "r": 1,
  "s": 1,
  "t": 1,
  "d": 2,
  "g": 2,
  "b": 3,
  "c": 3,
  "m": 3,
  "p": 3,
  "f": 4,
  "h": 4,
  "v": 4,
  "w": 4,
  "y": 4,
  "k": 5,
  "j": 8,
  "x": 8,
  "z": 10,
  "q": 10
};


const reducer = (accumulator, currentValue) => accumulator + currentValue;


function word_calc(w) {
  // convert your string array to relevant numbers 
  const splitted_array = w.split("").map(function(item) {
    return char_points[item]
  });

  // You can use simple loop to sum up or reduce to reduce and sum the array
  const total = splitted_array.reduce(reducer);
  console.log(total)
}


word_calc("zoo") // 12
word_calc("bus") // 5


```


```js


function word_calc(w) {
  let total=0;
  // convert your string array to relevant numbers and add it to the total
  w.split("").map(function(item) {
    total += char_points[item];
  });
  console.log(total)
}


word_calc("zoo") // 12
word_calc("zoozoo") // 24
word_calc("bus") // 5


```





### Question

### 4칙연산 함수 만들기 

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


/*

better code

var answer = {
  add:function(fir, sec){
    return fir+sec;
  },
  subtract:function(fir, sec){
    return fir-sec;
  },
  multiply:function(fir, sec) {
    return fir*sec;
  },
  divide:function(fir, sec) {
    return fir/sec;
  }
}

*/


```




### nonUniqueElements(data)

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





### Check_Point_1 Scope

   * 8번에 result인 x 가 10인 이유는 이해가 되는데 

**10번에 함수밖에있는 result 인  x 가 어떻게 outer(),inner()함수에 변수 x 를 가져왔는지** 이해가 잘안되어 질문을 드립니다..  제가 이해하기로는 단순히 var 이 함수안에서 다시 선언되지 않아서 인가요?

부탁드립니다.  




### 8번문제 

```js

var x = 10;

function outer () {
  var x = 20;
  function inner () {
    x = x + 10;
    return x;
  }
  inner();
}

outer();

var result = x;  // 10


```

### 10번 문제 

```js
var x = 10;

function outer () {
  x = 20;
  function inner () {
    x = x + 20;
  }
  inner();
}

outer();

var result = x; // 40


```

### 해답



> 8 번 문제 함수안에 변수가 let var const 선언되면 함수범위(스코프 범위)를 벗어나서 변수를 쓸수가 없다 


> 10번 문제  함수 안에 변수가 선언되지 않고 전역에 선언되었기 때문에 함수안에 x는 전역에 있는 것을 할당 하게 되어 가져온후 그것을 어니서나 쓸수 있는 변수가 되어버린것이다. 



### check_point 2 _Closure
 

  * 클로저를 정의한다면 
  
    * 함수안에 또다른 함수를 실행 외부함수가 실행 `종료된 뒤에도` 여전히 내부함수가 계속 외부함수였던 스코프에 접근할수 있다. 



#### Qeustion

```js
var add = function(x) {
   function sum (y) {
      return x + y;
  }
  return sum;
}

var foo = add(1) // 이렇게 하면 x는 1로 저장된다. 

foo(2) // 1 + 2 되어서 3 

var total1 = foo(10) // 1 + 10 = 11
var total2 = foo(11) // 1 + 11 = 12

var total3 = foo(12) // 1 + 12 = 13
var total4 = foo(13) // 1 + 13 = 14

var total5 = foo(14) // 1 + 14 = 15
var total6 = foo(15) // 1 + 15 = 16

var total7 = foo(16) // 1 + 16 = 17
var total8 = foo(17) // 1 + 17 = 18

```



## check_point-4 
* 1번 - What message will eventually be alerted? After how long?
  * setTimeout(function(){jj.sayHi()},1000) 
* 2번 - What message will eventually be alerted? After how long?
  * setTimeout(jj.sayHi,1000)
* 3번 - What message will eventually be alerted? After how long?
  * setTimeout(jj.sayHi.bind(jj), 1000);
* 5번 - What message will eventually be alerted? After how long?
  * setTimeout(jj.sayHi.bind(tim), 1000); 
  
```js

var esther = "eshter";
var jj = {
  name: "jj",
  sayHi: function() {
    alert(this.esther + " says hi");
  }
}; this 값이 바껴버린다. 

var tim = {
  name : "tim"
}

//1.After how long?

setTimeout(function(){jj.sayHi()},1000) //  jj say hi 
// this 값이 jj되서 jj.name 원하는 바되로 jj say hi 가 나온다. 


//2. After how long?
// 하지만 
setTimeout(jj.sayHi,1000) // esther says hi

// 이렇게 콜백 함수를 넣는다면 this 값이 window 가 되어서
// jj.sayHi를 불렀지만 esther. says hi 가 나온다. 

//3. Ater how long?

setTimeout(jj.sayHi.bind(jj), 1000); // jj say hi
 
// 이렇게 하면 2번에서 나오는 esther  say hi 를 방지할수 있다 
// 한마디로 this값을 원래 의도대로 jj 를 가르키게 하여 1초 후에 jj.name 되어 jj say hi  가 된다. 

//4. Ater how long?

setTimeout(jj.sayHi.bind(tim), 1000); // tim say hi

 // this 는 tim  bind(tim) 으로 인해 this 값을 정해줬다. 
  // 출력 

var sayHiTim = jj.sayHi.bind(tim) // 이렇게 묶어서 사용할수 있다. 

sayHiTim // tim.name + "says hi " 묶인채로 저장된다.  

// ƒ () {
//    alert(this.name + " says hi");
//  }


sayHiTim() //  tim say hi
```


* 5번 - After the following code runs, what will be the value of result? 
6번 - After the following code runs and all setTimeout callbacks run, what will be the value of result?


```js

//5 번

function foo () {

  var data = 10;

  bar(function (players) {
    data = players;
  });

  return data;
}

//1.
///////////////////////////////////  
// bar 함수는 callback 함수를 받아서 인자값을 20으로 한다. 
function bar (callback) {
  callback(20);
}

var result = foo(); // 20

//2

setTimout() // 안에 넣고 callback(20) 을 실행한다. 

///////////////////////////////////
///////////////////////////////////


function foo () {

  var data = 10;

  bar(function (players) {
    data = players;
  });

  return data;
}

function bar (callback) {
  setTimeout(function () {
    callback(20);
  }, 500);
}

var result = foo(); //  값이 변하지 않아서 10 이다 



```


* result 값이 42 가 되게 exercise 함수를 작성하라 


```js
function exercise (???) {
  ???
}

var a = exercise(10, function (x) {
  return x + 2;
});

var b = exercise(15, function (x) {
  return x * 2;
});

var result = a + b;



function exercise (x,f) {
  return f(x);
}


```
