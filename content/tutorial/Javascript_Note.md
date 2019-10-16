---
title: 5. Notes
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



------------------------------------------------------------------



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

for(let i = 0; i < 20; i++){
    tmp += fib(i) + " " 
}


```



```js




// 함수사용해서 피보나치 수열 만들기 

 function fibonacci(num){
      var a = 1, b = 0, temp;

        document.write(b + ", ");

        for(var i = num; i >= 1; i--){
            temp = a;
            a = a + b;
            b = temp;
            if(i == 1) document.write(b);
            else document.write(b + ", ");
      }
    }

    fibonacci(15);


// for 문을 사용해서 피보나치 수열 만들기 


var num = 15;
var a = 1, b = 0, temp;

document.write(b + ", ");

for(var i = num; i >= 1; i--){
temp = a;
a = a + b;
b = temp;
if(i == 1) document.write(b);
else document.write(b + ", ");
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





## e.target 과 e.target.parentNode 의 차이 


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








## 버튼 엔터키 작동 및 입력창 커서유지시키기 


```html


<h1>this is coffee machine<h1>
<div id = "menu">menu</div>
<input id = "input" type="text" placeholder = "what drink?">
<button id = "btn">order</button>
<ol id = "list">
  <li class = "americano">americano</li>
  <li class = "latte">latte</li>
  <li class = "flatWhite">flatWhite</li>
<ol>

```




```js
 
// 버튼을 누르면 list 가 추가되는데 사용자를 위하여 엔터로 control 할수 있게 하고 커서가 계속 입력창에 깜빡이게 하는 방법이다. 

let coffeeList = document.querySelector("#list");
let coffeeInput = document.querySelector("#input");
let add = document.querySelector("#btn");
// form tag를 만들어 input 과 btn tags 를 넣는다.  
  let form = document.createElement("form");
  document.body.appendChild(form);
  form.appendChild(coffeeInput);
  form.appendChild(add);

// form tag에 이벤트를 발생시킨다. 
// form 과 "submit" 의 기본동작은 엔터를 첬을때 새로고침 or 다른페이지로 넘어가게 되어있다. 
// 그것을 막기 위해서 function(event) 설정하고  event.preventDefalut() 넣어주면 된다. 

form.addEventListener('submit',function(event){
    event.preventDefault();
  let newList = document.createElement("li");  
  newList.setAttribute("class","new-list");
  coffeeList.appendChild(newList);
  newList.textContent = coffeeInput.value;
  coffeeInput.focus(); // input tag 에 함수를 넣는다. 입력후 계속 입력할수 있게 해준다. 
  
})




```






## addEventListener 사용하기 



```html
<h1>this is coffee machine<h1>
<div id = "menu">menu</div>
<input id = "input" type="text" placeholder = "what drink?">
<button id = "btn">order</button>
<ol id = "list">
  <li class = "americano">americano</li>
  <li class = "latte">latte</li>
  <li class = "flatWhite">flatWhite</li>
<ol>


```

```js

// 1. addEventListener
// 버튼을 누르면 menu 버튼이 한글로 바뀜

let xxx = document.querySelector("#btn");
let menu = document.querySelector("#menu");

xxx.addEventListener('click', function(){
  menu.innerHTML = "메뉴";
})

// 2 addEventListener 
// 버튼 누르면 리스트가 추가된다. 

let coffeeList = document.querySelector("#list");
let coffeeInput = document.querySelector("#input");
let add = document.querySelector("#btn");

add.addEventListener('click',function(){
  let newList = document.createElement("li")
  newList.setAttribute("class","new-list");
  coffeeList.appendChild(newList);
  newList.textContent = coffeeInput.value;
})



```



## onclick 동작하는 원리 

```html


<h1>this is coffee machine<h1>
<div id = "menu">menu</div>
<input id = "input" type="text" placeholder = "what drink?">
<button id = "btn">order</button>
<ol id = "list">
  <li class = "americano">americano</li>
  <li class = "latte">latte</li>
  <li class = "flatWhite">flatWhite</li>
<ol>
```


```js

// 1. onlick 동작하는원리 
// menu 버튼을 누르면 menu 가 red 로 변함  

let xxx = document.querySelector("#btn");

xxx.onclick = function() {
  document.querySelector("#menu").style.background="red";
}


```



## JS/HTML textContent 와 value 의 차이점 

```js

tag 안에 들어가는 글자내용은  textcontent 이고
input 안에 들어가있는 글자내용은 value 이다 


```



## 버튼누르면 새로운 글 추가 


* HTML
 
 
```html


  <button id="clickbtn">new_tweet</button>
    
    <div id="comments"></div>
 

```


* JS

```js


var DATA = [
  { user: 'ingikim', message: 'Welcome to Code States #codestates', created_at: '2019-01-03 12:30:20' },
  { user: 'satya', message: 'this is test message #pair #programming', created_at: '2019-01-04 18:30:20' },
  { user: 'sundar', message: 'code now! #work #hard', created_at: '2019-01-05 07:30:20' },
  { user: 'steve', message: 'Stay hungry, and stay foolish', created_at: '2015-01-03 12:30:20' },
  { user: 'tim', message: 'education for real world', created_at: '2019-01-04 18:30:20' }
];

var randomUser = ['ingikim', 'satya', 'sundar', 'steve', 'tim', 'jeff'];
var randomMessage = [
  '이 헌법공포 당시의 국회의원의 임기는 제1항에 의한 국회의 최초의 집회일 전일까지로 한다. 감사원은 원장을 포함한 5인 이상 11인 이하의 감사위원으로 구성한다.',
  '헌법재판소의 조직과 운영 기타 필요한 사항은 법률로 정한다. 모든 국민은 자기의 행위가 아닌 친족의 행위로 인하여 불이익한 처우를 받지 아니한다.',
  '헌법개정은 국회재적의원 과반수 또는 대통령의 발의로 제안된다. 국가는 재해를 예방하고 그 위험으로부터 국민을 보호하기 위하여 노력하여야 한다.',
  '모든 국민은 직업선택의 자유를 가진다. 군인은 현역을 면한 후가 아니면 국무총리로 임명될 수 없다. 행정권은 대통령을 수반으로 하는 정부에 속한다.',
  '민주평화통일자문회의의 조직·직무범위 기타 필요한 사항은 법률로 정한다. 국가는 농·어민과 중소기업의 자조조직을 육성하여야 하며, 그 자율적 활동과 발전을 보장한다.',
  '국회는 국정을 감사하거나 특정한 국정사안에 대하여 조사할 수 있으며, 이에 필요한 서류의 제출 또는 증인의 출석과 증언이나 의견의 진술을 요구할 수 있다.',
  '인간이 얼음에 고행을 따뜻한 가장 이것이다. 꽃이 곧 동력은 끝에 동산에는 그것은 거선의 별과 인생의 것이다. 구하지 착목한는 스며들어 인생의 것이다.',
  '새 가슴에 있는 만천하의 있다. 몸이 뜨거운지라, 청춘의 소리다.이것은 같으며, 피다. 설산에서 힘차게 옷을 피다. 놀이 그들의 인간의 주는 소금이라',
  '귀는 우리는 피에 무엇이 이것이다. 구하지 우리는 그들은 약동하다. 따뜻한 발휘하기 사람은 충분히 사막이다.'
]

function getRandomInt(min, max) {
  return Math.floor(Math.random() * (max - min)) + min;
}

function generateNewTweet() {
  var tweet = {};
  tweet.user = randomUser[getRandomInt(0, randomUser.length)];
  tweet.message = randomMessage[getRandomInt(0, randomMessage.length)];
  tweet.created_at = new Date().format(); // 어떻게 하면 보기 좋은 형태로 나타낼 수 있을까요?
  return tweet;
}

Number.prototype.padLeft = function() {
  if(this < 10) {
    return '0' + String(this);
  }
  else {
    return String(this);
  }
}

Date.prototype.format = function() {
  var yyyy = this.getFullYear();
  var month = (this.getMonth() + 1).padLeft();
  var dd = this.getDate().padLeft();
  var HH = this.getHours().padLeft();
  var mm = this.getMinutes().padLeft();
  var ss = this.getSeconds().padLeft();

  var format = [yyyy, month, dd].join('-') + ' ' + [HH, mm, ss].join(':');
  return format;
}





//2.check_new_tweet! 
function myFunction() {
    let  array = [];
    let obj = generateNewTweet();

    array.push("<div class='comment'>"
         + "<div class='username'>"  + obj.user + "</div>" 
         + "<div>" + obj.message + "</div>"
         + "<div>" + obj.created_at + "</div>"
         + "</div>");

    
  comments.innerHTML = array + comments.innerHTML;

}




let Button = document.querySelector('#clickbtn');

function randomTweet() {
    clickbtn.onclick = function() {
        myFunction();
    }
}

randomTweet();





```





## JS/HTML script 위치 

```js


//Html 파일에서 script 를 head 안에 넣으면 script 안에 써있는 코드들이 실행이 안된다 !

//하지만 script 안에 있는 코드들을 실행 시키려면 


window.onload = function () { } // 실행하고싶은 코드넣으면 실행할수 있다. 



```







## JS/HTML insertBefore()

```js

// html

<h1>test</h1> 
  
<ul id="subjects"> 
        <li>C</li> 
        <li>Python</li> 
</ul> 
  
  
// js

  <script>
  
  function myGeeks() { 
            var newItem = document.createElement("li"); 
            var textnode = document.createTextNode("Java"); 
            newItem.appendChild(textnode); 
  
            var list = document.getElementById("subjects"); 
            list.insertBefore(newItem, list.childNodes.lastChild); // 마지막으로 삽입하고 싶으면 lastChild
            
            list.insertBefore(newItem, list.childNodes[0]); //  첫번째로 삽입하고 싶으면 [0] 
            } 

 myGeeks();
  
  </script>

// html

// Java     // 삽입 되었다. 
// C
// Python





```






## JS/HTML랜덤글자 가져오기



```js

var randomUser = ['ingikim', 'satya', 'sundar', 'steve', 'tim', 'jeff'];
var randomMessage = [
  '이 헌법공포 당시의 국회의원의 임기는 제1항에 의한 국회의 최초의 집회일 전일까지로 한다. 감사원은 원장을 포함한 5인 이상 11인 이하의 감사위원으로 구성한다.',
  '헌법재판소의 조직과 운영 기타 필요한 사항은 법률로 정한다. 모든 국민은 자기의 행위가 아닌 친족의 행위로 인하여 불이익한 처우를 받지 아니한다.',
  '헌법개정은 국회재적의원 과반수 또는 대통령의 발의로 제안된다. 국가는 재해를 예방하고 그 위험으로부터 국민을 보호하기 위하여 노력하여야 한다.',
  '모든 국민은 직업선택의 자유를 가진다. 군인은 현역을 면한 후가 아니면 국무총리로 임명될 수 없다. 행정권은 대통령을 수반으로 하는 정부에 속한다.',
  '민주평화통일자문회의의 조직·직무범위 기타 필요한 사항은 법률로 정한다. 국가는 농·어민과 중소기업의 자조조직을 육성하여야 하며, 그 자율적 활동과 발전을 보장한다.',
  '국회는 국정을 감사하거나 특정한 국정사안에 대하여 조사할 수 있으며, 이에 필요한 서류의 제출 또는 증인의 출석과 증언이나 의견의 진술을 요구할 수 있다.',
  '인간이 얼음에 고행을 따뜻한 가장 이것이다. 꽃이 곧 동력은 끝에 동산에는 그것은 거선의 별과 인생의 것이다. 구하지 착목한는 스며들어 인생의 것이다.',
  '새 가슴에 있는 만천하의 있다. 몸이 뜨거운지라, 청춘의 소리다.이것은 같으며, 피다. 설산에서 힘차게 옷을 피다. 놀이 그들의 인간의 주는 소금이라',
  '귀는 우리는 피에 무엇이 이것이다. 구하지 우리는 그들은 약동하다. 따뜻한 발휘하기 사람은 충분히 사막이다.'
]


// getRandomInt(min,max)  이용해 인자만큼 가져오는 방법


function getRandomInt(min, max) {
  return Math.floor(Math.random() * (max - min)) + min;
}


// 각각 user or message or time 을 객체안에 넣는다.
// 여기서 들어가는 요소들은 랜덤하게 들어가게 된다. 

function generateNewTweet() {
  var tweet = {};
  tweet.user = randomUser[getRandomInt(0, randomUser.length)]; 
  tweet.message = randomMessage[getRandomInt(0, randomMessage.length)];
  tweet.created_at = new Date().format(); 
  return tweet;
}


```



## Get Current Data & Time in JS




```js


var today = new Date(); // Data 가져온다. 
var date = today.getFullYear()+'-'+(today.getMonth()+1)+'-'+today.getDate(); // 날짜
var time = today.getHours() + ":" + today.getMinutes() + ":" + today.getSeconds(); // 시간 

var dateTime = date+' '+time;  

dateTime // 2019-9-5 13:2:48"

```


## block 스코프와 function 스코프의 차이



```js

// block 스코프

for (let i = 0;  i < 5; i = i + 1) {
	console.log(i); //  0,1,2,3,4  출력된다. 
}

console.log(i) //  ReferenceError 출력 이유 : i라는 변수는 block let = i 선언되었을때 i 의 변수는  block 안에 제한 되기 때문이다.


// 
for (var i = 0;  i < 5; i = i + 1) {
	console.log(i); //  0,1,2,3,4  출력된다. 
}
console.log(i) // 5   이유: var 변수를 지정했을때 block의 범위를 넘어선다. 

```



## var or let 변수를 사용한 함수중 어던것이 에러??

![](/tutorial/Javascript_Note_files/Screen Shot 2019-08-28 at 4.41.59 PM.png)



```js

function greetSomeone (firstName ) { 
  let time = "night";
  
  if (time === "night") {         
    let greeting = "Good Night"; ////////// let greeting block 안에 갇혀 있다. 이 block 를 벗어나는 순간 효력을 잃는 다. 
  }
  
  
  return greeting + ' ' + firstName;  ///  greeting 실행되지 않는다 
}

greetSomeone('steve');

```


## var and let and const 


![](/tutorial/Javascript_Note_files/Screen Shot 2019-08-28 at 5.37.46 PM.png)



##  Strict Mode



```js


// 변수를 안전하게 쓰기위한 “use strict”

`use strict` //  처음 시작에 이렇게 달아둔다.

function showAge() {
  arr = [1234];     //  선언되지 않는 변수가 실행되지 않게 해준다. 
console.log(arr);
}


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






## parameter 지정하는 법 


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






## prototype를 사용해 ininstance 객체에 키값 속성값 추가하는법






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






## 객체안에 담겨있는 function 사용하기


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



## 함수가 객체의 키값으로 사용 


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


## key 배열 출력 - Object.keys, for in 문


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
