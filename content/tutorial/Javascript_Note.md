---
title: Notes
date: 2019
draft: true
menu:
  tutorial:
    parent: "Javascript"
    weight: 100

toc: true
type: docs

---

![](/tutorial/Javascript_Dictionary_files/javascriptt-light_870x220.png)
 
### Today What I Learn ?

![](/tutorial/Javascript_Note_files/Screen Shot 2019-08-19 at 8.22.08 PM.png)

---




---
### parameter 지정하는 법 
---

`ES6`

```js

function timeToGoHome(distance, speed = 20 ) { 

	return distance + speed;
}

timeToGoHome(10);

// 30

timeToGoHome(10,10); // 두번째 값인 지정했던 speed 값이 변한다. 

// 20



 // 만약 첫번째 값을 지정하고 출력하고 싶다면

function timeToGoHome(distance = 20, speed) { 

timeToGoHome(undefined,20) ;
// 40
 

```







---
### getMaxNum 함수 만들기 
---

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



---
### 현재 시간,날짜  || 년도 불러오기
---

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




---
### in 에 관해서
---

```js


obj = {a:1,b:2}; // obj 객체가 있다.

let obj2 = "a" in obj; //  obj 안에 a라는 키값이 있는지 확인한다. 

console.log(obj2) // >> true << true or false 로 값을 나타낸다.  



```





---
### prototype를 사용해 ininstance 객체에 키값 속성값 추가하는법
---





```js

// prototype를 사용해 모든 instance 객체에 property와 method 추가하는 법을 확인합니다

function objFunc(para) { // 객체를 담고있는 함수를 먼저 만든다.
      this.age = para; // key 는 name / property는 para  < 아직 모른다.
    }

    let newObj = new objFunc(33); // para 값이 33이 됨 따라서 info1 = { age:33 }
    newObj.name = "John"; //  // 함수안에 infor1 객체안에 키값이랑 property 를 추가한다.

newObj //>> objFunc = { age: 33 , name: "John" } name = "john" 이 추가됬다. 

// prototype 을 사용해서 추가하기

objFunc.prototype.text = function() { // 처음함수에 prototype을 넣는다.  그다음에 text라는 키값을 지정한다. 이키값은 함수이기도 하다. 그래서 키이면서도 함수인 text()가 실행되면 return값이 출력된다.  
	return "this is the stroy what I want to say to " + newObj.name; 
}

newObj.text(); // "this is the stroy what I want to say to john"


```





---
### 객체안에 담겨있는 function 사용하기
---

```js

  // 객체를 만들고 속성값에 text 내용을 출력할 함수를 만든다. 
  
 // 이름을 몇번 집어넣을지 num 라는 것을 Array(num+1)를 통해 만들고 join 메소드를 이용해 " " 띄어쓰기를 한후 text 를 출력한다.

obj1 = {
      name1 : "john",
      name2: "tim",
      funcSum: function (num) {
        return "They are " + this.name1 + " and the" +
        Array(num + 1).join(" " + this.name2);     
      }
    };

let massage = obj1.funcSum(2) //  객체안에 있는 속성인 funcSum(2) 호출한다.

console.log(massage) // >> "They are john and the tim tim"

```


---
### 함수가 객체의 키값으로 사용 
---

```js

// 객체와 함수를 이용한다.
// 장점 객체안에 키값을 자유롭게 사용할수 있다.

let funcGood = function (elem) {
      return elem + " is good man!";
    };
    let obj1 = { name: funcGood };
    

obj1.name("John") // >> john is good man!

// 만약 obj.name 이 다른 기능을 가지고있는 함수를 대입하면..

let funcBad = function (elem) {
      return elem + " is good bad!";
    };

obj.name = funcBad 

// 기존에 있던 obj.name 기능은 사라지고 obj.name 의 기능은

obj.name("john") // john is good bad!


```

---
### key 배열 출력 - Object.keys, for in 문
---

```js

var arr = [];
arr["a"] = 20;
arr["b"] = 10;
arr["c"] = 30;
arr["d"] = 40;

arr = [a: 20, b: 10, c: 30, d: 40];


console.log(arr);    
console.log(arr.length);  // 헉 키값으로 된 array는 length가 0??
// jquery each문으로 안돌아간다.
$.each(arr, function(index, el) {
	console.log(el);
});

 // key만 출력
console.log(Object.keys(arr)) // ["a", "b", "c", "d" ] 
// for in으로 출력하자

for (var i in arr) {  // in 연산자는 상속계통을 모두 검색하여 맴버가 존재하는지 확인한다. (반복문중 가장 느리다.)
	if (arr.hasOwnProperty(i)) {   // hasOwnProperty를 통해 해당 객체의 맴버인지 확인을 한다.
		console.log(arr[i]);
	}
}
//------------------------------------------------------------------------------------------------------
//  key array length 키 배열 사이즈  얻는 사용자함수
function arraySize(obj) {
	var size = 0, key;
	for (key in obj) {
		if (obj.hasOwnProperty(key)) {
			size++;
		}
	}
	return size;
};	
console.log(arraySize(arr));  // 4


출처: https://mylife365.tistory.com/286?category=624212 [변화에 적응하기]
```


---
### dot notation and  braket notation ?


>다른점은 dot notation 을 쓴것과 braket notation을 쓴것인데 이게 왜 다를까요???


* Example1

``` js
var obj = {steve:1, bob:2};
var steve = 'bob';

console.log(obj.steve);    // 1
console.log(obj['steve']); // also 1
console.log(obj[steve]);   // 2

```

* Example2

```js
var obj = {steve:1, bob:2};

console.log(obj.steve);    // 1
console.log(obj['steve']); // also 1
console.log(obj['bob']);   // 2



```

---
### first-class object()
---
```
함수를 변수, 매개변수 ,리턴값 으로 사용할수 있다 이것을

first-class value 
first-class citizen
first-class object

라고 부른다. 

```


* 값으로써 쓰이는 함수 예제


```
function cal(mode){
    var funcs = {
        'plus' : function(left, right){return left + right},
        'minus' : function(left, right){return left - right}
    }
    return funcs[mode];
}
alert(cal('plus')(2,1));
alert(cal('minus')(2,1));  
```


* 배열로서의 함수

```

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



---
### Callback
---

* 장점 

> 원래의 내장메소드에 있는 기능을 콜백 으로 바꿔서 사용할수 있다.

>값으로 사용될 수 있는 특성을 이용하면 함수의 인자로 함수로 전달할 수 있다. 값으로 전달된 함수는 호출될 수 있기 때문에 이를 이용하면 함수의 동작을 완전히 바꿀 수 있다. 인자로 전달된 함수 sortNumber의 구현에 따라서 sort의 동작방법이 완전히 바뀌게 된다.

>ajax를 사용할때 제이 쿼리를 이용해서 콜백이 사용된다. 

```
function sortNumber(a,b){
    // 위의 예제와 비교해서 a와 b의 순서를 바꾸면 정렬순서가 반대가 된다.
    return b-a;
}
var numbers = [20, 10, 9,8,7,6,5,4,3,2,1];
alert(numbers.sort(sortNumber)); // array, [20,10,9,8,7,6,5,4,3,2,1]
```

![](/tutorial/Javascript_Notes_files/Screen Shot 2019-07-17 at 4.46.43 PM.png)



---
### Dom : Dom을 이용해서 HTML문서를 제어할수 있다
---

##### DOM 객체의 값 바꾸기

* ex1-1 document.getElementsByTagName()

```

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

```

* ex1-2 document.getElementsById()


```
var a = document.getElementsById("main")
>> main 아이디 값의 tag를 가져와서  a 변수에 담는다

a
>> <p id = main>hello jj </p>

a.innerHTML = "hello John jung"

a

>><p id = main>hello john jung</p>

```


---
### 버튼 만들기
---


```
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




---
### 객체 숫자 계산 하는 방법
---

#### How to Count the Number of Properties of the JavaScript Object

>While working with JavaScript, I come across a requirement to count a number of properties in a JavaScript object. I found two ways to find the number of properties in an object. They are as follows:

```
Consider an object, "cat," as demonstrated below:

var cat = {
    name: 'foo',
    age: 9
}
```

>You can find a number of properties by iterating in a for loop and update counter, as shown in the below listing:

```
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
