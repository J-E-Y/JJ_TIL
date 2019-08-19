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
 


# Today What I Learn ?
![](/tutorial/Javascript_Note_files/Screen Shot 2019-08-19 at 8.22.08 PM.png)




### for ( let 변수 in obj ) { }

> how propo works ? 

* 객체의 키를  변수에  넣어준다고 생각각하면 됩니다.



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
### array 
---

**Get the last item in an array**

```
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
