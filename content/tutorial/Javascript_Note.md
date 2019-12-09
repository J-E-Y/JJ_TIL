#---
#title: x Notes
#date: 2019
#draft: true
#menu:
#  tutorial:
#    parent: "3.Javascript"
#    weight: 0
#
#toc: true
#type: docs
# 
#
#---

![](/tutorial/Javascript_Dictionary_files/javascriptt-light_870x220.png)
 
### Today What I Learn ?

![](/tutorial/Javascript_Note_files/Screen Shot 2019-08-19 at 8.22.08 PM.png)


------------------------------------------------------------------


## Immutably Rename Object Keys in Javascript



```js

obj = { name: 'Bobo' }
obj.somethingElse = obj.name
delete obj.name


```


## Unll 과 undefined 의 차이점


```js

// null 과 undefined 는 등록, 저장 여부이다.

//null 은 값은 값이지만 값으로써 의미없는 특별한 값이 등록되어 있는 것이고, undefined 는 등록이 되어있지 않기 때문에 초기화도 정의되지도 않은 것입니다.

//undefined 는 미리 선언된 전역변수(전역 객체의 프로퍼티)이며, null 은 선언,등록을 하는 키워드인 것입니다.




```



## How to check if element has any children in Javascript?



```js

if (element.firstChild) {
    // It has at least one
}

if (element.hasChildNodes()) {
    // It has at least one
}

if (element.childNodes.length > 0) { // Or just `if (element.childNodes.length)`
    // It has at least one
}

if (element.children.length > 0) { // Or just `if (element.children.length)`
    // It has at least one element as a child
}

if (element.firstElementChild) {
    // It has at least one element as a child
}

var hasChildElements, child;
hasChildElements = false;
for (child = element.firstChild; child; child = child.nextSibling) {
    if (child.nodeType == 1) { // 1 == Element
        hasChildElements = true;
        break;
    }
}

function hasChildElement(elm) {
    var child, rv;

    if (elm.children) {
        // Supports `children`
        rv = elm.children.length !== 0;
    } else {
        // The hard way...
        rv = false;
        for (child = element.firstChild; !rv && child; child = child.nextSibling) {
            if (child.nodeType == 1) { // 1 == Element
                rv = true;
            }
        }
    }
    return rv;
}




```



## array shuffle 함수 만들기 


```js
function shuffle(array) {
  var currentIndex = array.length, temporaryValue, randomIndex;

  // While there remain elements to shuffle...
  while (0 !== currentIndex) {

    // Pick a remaining element...
    randomIndex = Math.floor(Math.random() * currentIndex);
    currentIndex -= 1;

    // And swap it with the current element.
    temporaryValue = array[currentIndex];
    array[currentIndex] = array[randomIndex];
    array[randomIndex] = temporaryValue;
  }

  return array;
}

// Used like so
var arr = [2, 11, 37, 42];
arr = shuffle(arr);
console.log(arr);




// Another one

function shuffle(array) {
    
    let copy = array.slice();
    copy.sort(function(a, b){
      return Math.random() - 0.5;
    })
    return copy;
  };


```



## 다차원에 있는 배열 하나로 만들기 

```js

var nestedArray = [1, [2], [3, [[[4]]]]];

nestedArray.join().split(',').map(Number);

// [1, 2, 3, 4]


```




## 자바스크립트 javascript forEach, for of, for in 의 차이



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



## Array_method


```js

// array.forEach (callback(callbackFunction(element, index, array)   

// 리턴값 없다  

// forEach 로 배열의 합 구하기 

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






// array.fliter(callbackFunction(element, index, array) 

// 조건문을 통과하 것을 새로운 배열로 만드는 역활
//리턴값 있다. 
// map 함수는 filter함수와 같이 오브젝트도 컨트롤 할 수도 있습니다.

var testArray = [1,2,3,4,5];
var returnArray = testArray.map(function(currentValue, index, array){
        return currentValue * 2;
     })




// array.map(callbackFunction(element, index, array)    

// 콜백 함수의 실행 결과를 가지고 새로운 배열을 만들때 사용
// 리턴값 있다. 


// array.every(callbackFunction(currentValue, index, array), thisArg)

// every 함수는 배열의 모든 요소가 callbackFunction 에서 true를 리턴해야 true를 리턴, 하나라도 false가 떨어지면 false를 리턴합니다.

// every나 some 함수의 경우 배열내 값이 존재하는지 확인할때나 조건에 맞는(혹은 맞지 않는) 값이 있는지 확인 할 때 등 활용이 가능합니다.




//array.some(callbackFunction(currentValue, index, array), thisArg)


// some 함수는 배열의 요소 중 하나라도 callbackFunction에서 true를 리턴하면 true를 리턴 합니다.

// every나 some 함수의 경우 배열내 값이 존재하는지 확인할때나 조건에 맞는(혹은 맞지 않는) 값이 있는지 확인 할 때 등 활용이 가능합니다.





// sort   리턴값 필요

var array = [10,3,1,4,5,7,9,0];

array.sort(function(left, right){

return left - right;    // or right - left

}); 

// left-right(오름차순) 결과 : 0, 1, 3, 4, 5, 7, 9, 10
// right-left(내림차순) 결과 : 10, 9, 7, 5, 4, 3, 1, 0



// array.reduce(callbackFunction(previousValue, currentValue, currentIndex, array1), initialValue)

// 리턴값 필요 





```




##  every 와 some 의 차이점




> every 와 some 메서드는 배열을 순회하면서 특정 조건을 배열의 값들이 만족시키는지 검사하는 메서드로서 호출한 배열이 결론적으로 조건을 만족시키는지(true), 만족시키지 못하는지(false)를 알려준다. every 와 some 의 차이는 every 가 배열의 모든 값이 조건을 만족해야, some 은 일부만 만족해도 true 를 return 한다






## falsy 와 trythy

```js

undefined, false, null, 0, NaN, “ 는 false 로 취급(falsy)
(NaN : Not a Number)

위에 적힌 데이터가 아닌 모든 데이터는 trye로 취급(truthy)

```

## data fliter 와 foreach 로 다루기 

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



## 피보나치 수열



```js

// 피보나치 수열 

// 0 1 1 2 3 5 8 13 21 34 ......
// 점화식표현은 ==> f(n) = f(n-1) + f(n-2)  

// 5번째 숫자는? = f(n-1) + f(n-2)  
// n = 5 
// 5-1 = 4  네번째 피보나치 수열에 있는 3은  숫자와 5-2 = 3 세번째 피보나치 에 있는 숫자 2 를 더한값이 된다. 


// fib(n) 함수는 
// n 번째의 피보나치 수열에 숫자를 출력한다. 


function fib(n) {    // n = 10 
    if (n <= 1) {    // 만약 n 이 0 과 1 이라면 
        return n;    // 그것을 그냥 바로 출력해라 
    } else {         // 만약 그게 아니라면 
        return fib(n-2) + fib(n-1);  //  피보나치 수열에 8번째수와  + 9번째 수의 합을 리턴한다.  그럼 8번째 있는 수는 21 이고 9번째 있는 수는 34 이기 때문에 더한 값은 55가 된다. 

    }
}

fib(10) // ==> 55


function fib(n) {
 
	if (n === 0 ) { // n 이 0 이면 0을 출력하고 그만  
	return 0;      
	}
	if (n === 1 ) { // n 이 1 이면 1을 출력하고 그만 
	return 1;
}


return fib(n-1) + fib(n-2) 
	
}




```







```js

//fib(n) 함수는 
// 20번째 까지 피보나치 수열을 출력해낸다. 


function fib(n) {
    if ( n <= 1 ) {
        return n;
    } else {
        return fib(n - 1) + fib(n - 2);
    }
}

let  tmp = '';

for(let i = 0; i < 20; i++){ // 20번째 까지 
    tmp += fib(i) + " " 
}


```



```js



// 함수사용해서 피보나치 수열 만들기 

function fibonacci(num){
    var a = 1 
	  var b = 0
	  var temp;
	  
	  for(var i = num; i >= 1; i--){
            temp = a;
            a = a + b;
            b = temp;
            
			if(i === 1) {
			console.log(b);
            }	else {
			console.log(b);
      			
   		 }
        }
}


// for 문을 사용해서 피보나치 수열 만들기 


var num = 15;  // 몇번째까지 
var a = 1, b = 0, temp;

document.write(b + ", ");

for(var i = num; i >= 1; i--){
temp = a;
a = a + b;
b = temp;
if(i == 1) {
document.write(b);
} else {
document.write(b + ", ");
}
}

```




## checkbox 안에 있는 value 값 얻기 


```html



<div class = "container">
    
    <input type="checkbox" class ="checks" value ="뜨거워"> hot
    <input type="checkbox" class ="checks" value ="추워"> clod
    <a href="#" onclick="submitFun();return false;">ok </a>

</div>
<script>
	


	function submitFun() {
		

		var checks = document.getElementsByClassName('checks')
		var str = "";
		

		for (let i = 0; i < checks.length; i++ ){

			if (checks[i].checked === true ) {
 				str += checks[i].value + "";
 			}
 		}
 		alert(str);
	}






</script>


```





## e.target 와 e.target.parentNode or currentTarget의 차이점 


```js

* e.target === 클릭된애
* e.target.parentNode === 클릭된애 부모태그 
* e.target.parentNode.parentNode === 클릭된애 부모의 부모태그

```

### event.target 과 currentTarget 의 차이점

```js

* event.target 은 마우스 클릭할때 발생되는 이벤트가 일어나는 곳을 말하고
* event.currentTarget 은 addEventListener 를발생시키는 대상 

```










## 랜덤 숫자 원하는 수대로 뽑기 


```js

// for 문을 이용한 랜덤 숫자 원하는수대로 뽑기 
for ( let i = 0 ; i <= 30; i = i + 1 ) { 
  String(Math.random().toFixed(i).split('').slice(2).join('')) // slice(2) 를 이용해 0과 . 을 제거한 나머지 숫자들을 출력한다.  
}


```





## \d or \d+  차이점  


```js

// 둘다 `imutable`  이다 

// 정규식 표현으로 둘다 숫자를 뽑는 역활을 한다. 

// \d 는 모든 숫자를 각각 배열로 나눠서 출력하낟.  

let str = "123f456f789 10";
str.match(/\d+/g);

// ["1", "2", "3", "4", "5", "6", "7", "8", "9", "1", "0"]




// \d+ 숫자가 나란히 붙어있는 것으로 나뉜다. 
let str = "123f456f789 10";
str.match(/\d/g);

// ["123", "456", "789", "10"]



```





## Extract numbers from a string-Javascript



```js
var string = "border-radius:10px 20px 30px 40px";
var numbers = string.match(/\d+/g).map(Number); 

console.log(numbers);

// [10, 20, 30, 40]



```




## Making_GUID



```js

JavaScript
Its easy to make GUIDs in JavaScript. Below is code to get strings that look like GUIDs. This code just random GUIDs they are not claimed to be unique. Don't use these if its very important.

function S4() {
    return (((1+Math.random())*0x10000)|0).toString(16).substring(1); 
}
 
// then to call it, plus stitch in '4' in the third group
guid = (S4() + S4() + "-" + S4() + "-4" + S4().substr(0,3) + "-" + S4() + "-" + S4() + S4() + S4()).toLowerCase();


```








## 할당 연산자


```js
// 3 가지가 똑같은 것이다.  할당연산자

count = count + 1 
coutt+= 
count++

```











## getMaxNum 함수 만들기 

 
```js

function getMaxNums(...nums) {
	console.log(nums);
}

getMaxNums(1,2,3,4,5);  // nums 는 arr로 출력된다. 따라서 
// >>>(5) [1, 2, 3, 4, 5]



let getMaxNum = function(...nums) {
	
	return nums.reduce(function(acc,curr) {
		if ( acc > curr ) {
		  return acc;	
		} else {
		  return curr;
		}
	 })
}

getMaxNum(1,2,3,4,5) //  Math.max(5,4,3,2,1)  >> 5같다

// >> 5 출력 

```




## 현재 시간,날짜  || 년도 불러오기


```js
let a = new Date()

a > // Tue Aug 20 2019 15:14:58 GMT+0900 (Korean Standard Time)

let b = (a.getFullYear());

b > // 2019 
```



```js

let currentDate = new Date() // Date() 라는 함수가 이미저장되어있다. 
currentDate 

```





## in 에 관해서


```js


obj = {a:1,b:2}; // obj 객체가 있다.

let obj2 = "a" in obj; //  obj 안에 a라는 키값이 있는지 확인한다. 

console.log(obj2) // >> true << true or false 로 값을 나타낸다.  



```







## dot notation and  braket notation ?



```js


// 다른점은 dot notation 을 쓴것과 braket notation을 쓴것인데 이게 왜 다를까요???


// Example1


var obj = {steve:1, bob:2};
var steve = 'bob';

console.log(obj.steve);    // 1
console.log(obj['steve']); // also 1
console.log(obj[steve]);   // 2


// Example2


var obj = {steve:1, bob:2};

console.log(obj.steve);    // 1
console.log(obj['steve']); // also 1
console.log(obj['bob']);   // 2


```


## first-class object()



```js
함수를 변수, 매개변수 ,리턴값 으로 사용할수 있다 이것을

first-class value 
first-class citizen
first-class object

라고 부른다. 

// 값으로써 쓰이는 함수 예제



function cal(mode){
    var funcs = {
        'plus' : function(left, right){return left + right},
        'minus' : function(left, right){return left - right}
    }
    return funcs[mode];
}
alert(cal('plus')(2,1));
alert(cal('minus')(2,1));  


// 배열로서의 함수

var process = [
    function(input){ return input + 10;},
    function(input){ return input * input;},
    function(input){ return input / 2;}
];
var input = 1;
for(var i = 0; i < process.length; i++){
    input = process[i](input);
}
alert(input);

```
![](/tutorial/Javascript_Notes_files/Screen Shot 2019-07-17 at 4.10.02 PM.png)




## Callback


```js



// 장점 


/*
원래의 내장메소드에 있는 기능을 콜백 으로 바꿔서 사용할수 있다.

값으로 사용될 수 있는 특성을 이용하면 함수의 인자로 함수로 전달할 수 있다. 값으로 전달된 함수는 호출될 수 있기 때문에 이를 이용하면 함수의 동작을 완전히 바꿀 수 있다. 인자로 전달된 함수 sortNumber의 구현에 따라서 sort의 동작방법이 완전히 바뀌게 된다.

ajax를 사용할때 제이 쿼리를 이용해서 콜백이 사용된다. 


*/

function sortNumber(a,b){
    // 위의 예제와 비교해서 a와 b의 순서를 바꾸면 정렬순서가 반대가 된다.
    return b-a;
}
var numbers = [20, 10, 9,8,7,6,5,4,3,2,1];
alert(numbers.sort(sortNumber)); // array, [20,10,9,8,7,6,5,4,3,2,1]
```

![](/tutorial/Javascript_Notes_files/Screen Shot 2019-07-17 at 4.46.43 PM.png)



```js

// 콜백 함수를 사용해서 함수 사용해기 

// first = element
// second = index
// third = array

function foo(first,second,third) {
	if ( first > second ) {
		console.log(first);
	} else {
		console.log(second);  
	}
}

function forEach(arr,test) {
	for (let i = 0; i < arr.length; i = i + 1 ) {
		foo(arr[i],i,arr); // 함수
    	}
	}

```






## Dom 이란 ? 

```js

// Dom을 이용해서 HTML문서를 제어할수 있다

// DOM 객체의 값 바꾸기

// ex1-1 document.getElementsByTagName()




document.getElementsByTagName() 
>>html에 있는 tag name 을 가져오는 명령이다.

var list = document.getElementsByTagName('h2') 
>>모든 h2를 list 라는 변수에 담아오겠다. 

태그 이름을 바꾸기 위해서는 

a
>> [h2,h2]

a[0]
>> <h2>hello 1</h2>

a[1]
>> <h2>hello 2</h2>
이렇게 배열안에 들어가 있다. 

a[1].innerHTML = "good morning"
heelo 2 >> good morning 으로 바뀐다. 

이것이 dom 의 역활 이다. 



// ex1-2 document.getElementsById()


var a = document.getElementsById("main")
>> main 아이디 값의 tag를 가져와서  a 변수에 담는다

a
>> <p id = main>hello jj </p>

a.innerHTML = "hello John jung"

a

>><p id = main>hello john jung</p>

```



## 버튼 만들기



```js
<body>
    <h1>함수를 이용해 버튼 만들기</h1>
    
    
    // 1.value 를 지정하기 in HTML
    
    
    <input id = "input1" type ="text">
    <button id ="button1">cilck</button>
    
    
    <script>
    
    // 2. 함수&변수를 만들어서 준비한다 
    
        var ret = function(){
            document.getElementById("input1");
            console.log(input1.value);
        }
    
        var button = document.getElementById("button1");
        
        
    // 3 .입력받을 ID 값을 받는 함수를 연결해준다.
       
        button1.onclick = ret; 

    /script>
    


</body>

```



## 객체 숫자 계산 하는 방법



```js

// How to Count the Number of Properties of the JavaScript Object

// While working with JavaScript, I come across a requirement to count a number of properties in a JavaScript object. I found two ways to find the number of properties in an object. They are as follows:




Consider an object, "cat," as demonstrated below:

var cat = {
    name: 'foo',
    age: 9
}


// You can find a number of properties by iterating in a for loop and update counter, as shown in the below listing:

let count = 0;
for (var c in cat) {
    count = count + 1;
}
console.log(count);// 2

```

>Above code will print "2" as the output.

>The above approach not only prints the object's own enumerable properties, but it also prints properties of objects to which it is linked. To further understand it, let us consider the below listing:

```
var animal = {
    canRun: true
}
var cat = {
    name: 'foo',
    age: 9
}
cat.__proto__ = animal;

```

>There are two objects, cat andanimal, and the cat object is linked to an animal object using the __proto__ property. Now, when you use a for loop to iterate and count a number of properties, it will also count the enumerable properties of the animal object. Therefore, the code listing below will print "3."


```
var animal = {
    canRun: true
}
var cat = {
    name: 'foo',
    age: 9
}
cat.__proto__ = animal;
let count = 0;
for (var c in cat) {
    count = count + 1;
}
console.log(count);// 3

```


>A JavaScript for loop will iterate through all the linked properties of the object.

>To count the object's own enumerable properties, you may consider using another approach, Object.keys(), which only enumerates the object's own enumerable properties. It does not enumerate the object's linked properties.

>Moving forward, let us again consider the cat object which is linked to animal object and count the number of properties using Object.keys:


```

var animal = {
    canRun: true
}
var cat = {
    name: 'foo',
    age: 9
}
cat.__proto__ = animal;
var count = Object.keys(cat).length;
console.log(count);

```

>Now you will get "2" printed as the output.

>Object.keys only enumerates the object's own enumerable properties.

>If the object's property enumerable is set to false, then it is not a member of the Object.keys array. Let us again consider the cat object and set its name property enumerable to false.

```
var cat = {
    name: 'foo',
    age: 9
}
Object.defineProperty(cat, 'name', { enumerable: false });

```

>Now, when you use Object.keys to find a number of properties, it will count only one.


```
var count = Object.keys(cat).length;
console.log(count);  // print 1
```

>In closing, these are the two ways that you can use to find the number of properties in a JavaScript object







---
### iteration statements
---



**반복문 순서**

```
 반복문

1. let i = 0  처음에 실행

2. i < 4 조건을 검사  

3. 반복할 내용 돌리고

4. i = i + 1 마지막으로  실행한다. 
  
```  

**difference bewteen for in or  for of**

* for in

```js

let list = [4, 5, 6];

for (let i in list) {
   console.log(i); // "0", "1", "2",
}

```

* for of 

>for of 는  `for (let i = 0; i < arr.length; i = i + 1 ) { }` 쓰는 것이랑  동일하다 


```js

let list = [4, 5, 6];

for (let i of list) {
   console.log(i); // "4", "5", "6"
}
```



**For Loop**

```js

// 요소를 불러오기 위해 i 라는 변수를 지정한다. 
// 불러오는 두가지 방법이 있다.

1.

for ( let i = 0; i < obj[key].length; i = i + 1 )

2.

for(var i in obj[key])


```






---
## **Array**
---

**Notes** 


```js
 1. 기존에 arr 를 새로운 newArr 라는 변수를 지정해 쓰는 경우에
 만약 newArr 를 바꾸면 기존의 arr 까지 바뀌게 된다. 
 
 2. 그런데 만약 새로운 newArr 라는 변수에 arr.slice() 로 copy 한 것을 저장하여 쓰게 된다면 기존에 arr 값이 변하지 않는다. 
 
SumUp

기존에 arr 에 영향을 주지 않으려면 array 를 copy해서 써라! 
 
```


**Rest 파라미터와 Spread 연산자 정리하기 (feat. 함수의 가독성을 높이는 방법)**


```js
Rest 파라미터 (Rest Parameter)

Rest 파라미터는 Spread 연산자(...)를 사용하여 함수의 파라미터를 작성한 형태를 말한다. 즉, Rest 파라미터를 사용하면 함수의 파라미터로 오는 값들을 "배열"로 전달받을 수 있다.

(Java에서 public static void func(String... strs){...} 이런식의 가변인자와 유사)

사용 방법은 파라미터 앞에 (...)을 붙인다.


function foo(...rest) {
  console.log(Array.isArray(rest)); // true
  console.log(rest); // [ 1, 2, 3, 4, 5 ]
}
foo(1, 2, 3, 4, 5);


* function foo(param1, param2, ...rest){~~} 처럼 앞에 파라미터는 일반적인 파라미터로 받을 수 있고 그 뒤부터는 Rest 파라미터로 받을 수 있다.

- 단, Rest파라미터는 항상 제일 마지막 파라미터로 있어야 한다. 예를들어 function foo(...rest, param1, param2){~}는 사용 불가능하다.

arguments VS rest 파라미터

ES5에서도 가변 인자 함수의 경우 arguments 객체를 통해 인자값을 확인할 수 있었다.


var foo = function () {
  console.log(arguments);
};
foo(1, 2); // { '0': 1, '1': 2 }


그렇다면 arguments와 rest파라미터의 차이점은 무엇일까?

답부터 말하면 arguments는 유사 배열 객체고 rest는 배열이다.

유사 배열 객체(array-like object)는 간단하게 순회가능한(iterable) 특징이 있고 length 값을 알 수 있는 특징이 있는 것이다. 즉, 배열처럼 사용할 수 있는 객체를 말한다.

무슨 말이냐면 arguments는 유사배열객체이기 때문에 Array 오브젝트의 메서드를 사용할 수 없다.

따라서 ES6에서는 arrow function에 arguments는 사용할 수 없을 뿐더러 Rest 파라미터를 사용하면 더 유연한 코드를 작성할 수 있는 것이기 때문에 Rest 파라미터 사용을 권장한다.

Spread 연산자 (Spread Operator)

Spread 연산자는 연산자의 대상 배열 또는 이터러블(iterable)을 "개별" 요소로 분리한다.


// 배열
console.log(...[1, 2, 3]); // -> 1, 2, 3
 
// 문자열
console.log(...'Helllo');  // H e l l l o
 
// Map과 Set
console.log(...new Map([['a', '1'], ['b', '2']]));  // [ 'a', '1' ] [ 'b', '2' ]
console.log(...new Set([1, 2, 3]));  // 1 2 3
Colored by Color Scripter


이터러블(iterable)은 Array, String, Map, Set, DOM구조다.

iterator를 생성해서 next()로 순회할 수 있는 자료구조가 이터러블이라고 생각하면 된다.

* 함수의 파라미터로 사용하는 방법


// ES6
function foo(x, y, z) {
  console.log(x); // 1
  console.log(y); // 2
  console.log(z); // 3
}
const arr = [1, 2, 3];
foo(...arr);// Array를 받아서 각 매개변수로 전달되었다.


Rest와 헷갈리지 않기!

Rest는 함수 선언문의 파라미터에 Spread(...)연산자를 이용해서 받으면 가변인자를 받아 배열로 만들어서 사용하는 것이고, 함수 호출문의 파라미터에 Spread(...)연산자를 이용해서 호출하면 배열이 해당 매개변수로 각각 매핑되는 것은 다르다.

//Rest
function foo(param, ...rest) {
  console.log(param); // 1
  console.log(rest);  // [ 2, 3 ]
}
foo(1, 2, 3);
 
//Spread호출
function bar(x, y, z) {
  console.log(x); // 1
  console.log(y); // 2
  console.log(z); // 3
}
bar(...[1, 2, 3]);


- 또한 Rest에서는 선언에서 Spread연산자를 제일 뒤에만 써야하지만, Spread호출에서는 중간중간 사용해도 상관없다.

* 배열에서 사용하는 방법 (가독성UP)


//ES5
var arr = [1, 2, 3];
console.log(arr.concat([4, 5, 6])); // [ 1, 2, 3, 4, 5, 6 ]
 
// ES6
const arr = [1, 2, 3];
// ...arr은 [1, 2, 3]을 개별 요소로 분리한다
console.log([...arr, 4, 5, 6]); // [ 1, 2, 3, 4, 5, 6 ]


- concat() 대신 가독성이 더 좋아졌다.


// ES5
var arr1 = [1, 2, 3];
var arr2 = [4, 5, 6];
 
// apply 메소드의 2번째 인자는 배열. 이것은 개별 인자로 push 메소드에 전달된다.
//Array.prototype.push.apply(arr1, arr2);
//arr1.push(arr2); => [1,2,3,[4,5,6]]
console.log(arr1); // [ 1, 2, 3, 4, 5, 6 ]
 
// ES6
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
 
// ...arr2는 [4, 5, 6]을 개별 요소로 분리한다
arr1.push(...arr2); // == arr1.push(4, 5, 6);
 
console.log(arr1); // [ 1, 2, 3, 4, 5, 6 ]


- push를 개별 요소로 전달할 수 있으니 훨씬 간결하고 가독성 또한 좋아졌다.

* 객체에서 사용하기

const o1 = { x: 1, y: 2 };
const o2 = { ...o1, z: 3 };
console.log(o2); // { x: 1, y: 2, z: 3 }
 
const target = { x: 1, y: 2 };
const source = { z: 3 };
// Object.assign를 사용하여도 동일한 작업을 할 수 있다.
// Object.assign은 타깃 객체를 반환한다
console.log(Object.assign(target, source)); // { x: 1, y: 2, z: 3 }


```


**Get the last item in an array**

```js
let arr = [1, 2, 3, 4] ;

* First
arr[arr.length - 1] ;


* Second
arr.slice(-1);

* Third
arr.slice(-1).pop();

```



**배열안에 있는 문자열 빼는 방법**


```

var newArray = [];
  for (let i = 0; i < arr.length; i++) {
    if (typeof(arr[i]) === 'string') {
      newArray.push(arr[i]);
    } 
  }

```

**How to find the sum of an array of numbers**

[This is link](https://stackoverflow.com/questions/1230233/how-to-find-the-sum-of-an-array-of-numbers)



**9 Ways to Remove Elements From A JavaScript Array**

[This is link](https://love2dev.com/blog/javascript-remove-from-array)

**JavaScript Arrays: slice vs splice**

[This is link](https://wsvincent.com/javascript-array-slice-vs-splice/)
