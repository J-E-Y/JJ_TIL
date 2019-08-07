---
title: JS My_Dictionary
date: 2019
draft: true
menu:
  tutorial:
    parent: "Javascript"
    weight: 9

toc: true
type: docs

---


---
## **String** 
---


* toString() :문자로 바꾸는것 

* String() :문자로 바꾸는것 

* str[index] 읽어서 찾아주는것 :immutable


```
let str = 'CodeStates';

str[0]; >> 'C'

but

str[0] = 'G' >> 바뀌지 않음.

str = 'Codestates'
 
Note: index로 접근은 가능하지만 쓸수는 없음 (read-only);

```

* toUpperCase() 소문자 대문자 바꿈:immutable


```
let str = 'CodeStates';

str.toUpperCase(); >>"CODESTATES

```

* toLowerCase() 대문자 소문자 바꿈:immutable


```

let str = "CodeStates";

str.toLowerCase()

```


* str.indexOf(serchValue); 찾기 


```

"Blue Whale"indexOf("Blue"); >>0
"Blue Whale".indexOf("hello"); >>-1
"Blue Whale".indexOf("Whale"); >>5


"canal".lastIndexOf("a") >> 3

```


* string.repeat(숫자입력) 반복하는것 

> ex


```
let chorus = 'Because I'm happy';

console.log('Chorus lyrics for "Happy": ' + chorus.repeat(27));

```

* charAt(index) :인덱스에 있는 값을 리턴한다.


> ex


```
var stringName = 'coding everybody';
alert(stringName.charAt(0)); // c
alert(stringName.charAt(stringName.length-1)); // y
alert(stringName.charAt(1000) == ''); // true

```


* sort() : 배열 정렬할때 


>ex

```

var numbers = [9,8,7,6,5,4,3,2,1];
alert(numbers.sort()); // array, [1,2,3,4,5,6,7,8,9]
alert(numbers); // array, [1,2,3,4,5,6,7,8,9], 원본을 변경한다. 
alert(numbers.sort() === numbers); // boolean, true, 원본과 반환값이 같다.
 
var numbers = [20, 10, 9,8,7,6,5,4,3,2,1];
//array, [1,10,2,20,3,4,5,6,7,8,9], 암시적으로 원소를 문자로 형변환 하기 때문에 10이 1뒤에 온다.
alert(numbers.sort()); 

```

> ex


```
var numbers = [20, 10, 9,8,7,6,5,4,3,2,1];
var x = function(a,b){
	return a-b;
}

console.log(numbers.sort(x));

[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 20]


순서반대 로 할려면
return a+b;

[20, 10, 9, 8, 7, 6, 5, 4, 3, 2, 1]

```


>추가 설명 from 생활코딩 사전 sort()



```

function sortNumber(a,b){
// 비교 대상인 a와 b가 인자로 전달된다.
//alert('a :'+a+', b:'+b);
// a에서 b를 뺀 결과가 음수면 a가 b보다 작고, 0이면 같다.
// sort메소드는 return 값이 음수,양수,0인지에 따라서 순서를 정한다.
return a-b;
}
var numbers = [20, 10, 9,8,7,6,5,4,3,2,1];
alert(numbers.sort(sortNumber)); // array, [1,2,3,4,5,6,7,8,9,10,20]


```


---
## **Number**
---


* parseInt() 숫자로 바꾸는것




---
## **Array**
---



* making array

```
1.
let arr = [1, 2, 3, 4];

2.

let arr = [];
arr[0] = 2;
arr[1] = 4;


```

* reading array

```

let arr = [1, 2, 3, 4];

arr[0]; 

> 1


arr[3];

> 4

```

* writing 

```
let arr = [1, 2, 3, 4];

arr[0] = 2;

> [2,2,3,4]; 

scores[9] = 50;

인덱스가 없다면 마지막에 붙는다 
>  [1, 2, 3, 4 ,50]
```


* Get the length from arr

```
let arr = [1, 2, 3, 4];
arr.length;
> 4

```
* Get the last item in an array

```
let arr = [1, 2, 3, 4] ;

* First
arr[arr.length - 1] ;


* Second
arr.slice(-1);

* Third
arr.slice(-1).pop();

```


* push() 뒤어 붙이기 

```
var arr = [1,2,3,4,];
arr.push(1);

arr; // = > [1,2,3,4,1]
```

* pop() 뒤에 있는거 빼기 

```
var arr = [1,2,3,4,];
arr.pop();

arr; // = > [1,2,3]
```


* unshift()	 앞에 붙이기

```
var arr = [1,2,3,4];

arr.unshift(1);

arr; // = > [1,1,2,3,4,];

```


* shift()  앞에 있는거 빼기

```
var arr = [1,2,3,4];

arr.shift();

arr; // = > [2,3,4,]

```

* concat() 더하기 

```
1.


Join two arrays:

var hege = ["Cecilie", "Lone"];
var stale = ["Emil", "Tobias", "Linus"];
var children = hege.concat(stale);

`변수에 담아야 한다` 왜냐하면 값이 변하지 않는다.
출력하면
console.log(children);

> ["Cecilie", "Lone", "Emil", "Tobias", "Linus"]

2.

var arr = [1,2,3,4,5];

arr.concat(6); 

console.log(arr) 

>> [1,2,3,4,5,]  

기존에 있는 것은 변하지 않는다.
변하게 하기위해서는 변수를 새로 만들기 !



3. 
arr.concat([6,7,8,9,10]);

>>arr

[1,2,3,4,5,6,7,8,9,10] 
여러게를 더할수 있다.

```


* join() 문자열로 바꾸기 



```
var arr = [1,2,3,4,5,6]

arr.join() ;

>>arr
["1","2","3","4","5","6"]
문자열로 바꿔준다. 

arr.join("");

>>arr
["123456"];
문자열 다 붙인다.

```

* indexOf() ()<<원소를 입력하면부터 앞에서 부터 찾아서 index번호 알려준다. 

```
var array = [2, 9, 9];
array.indexOf(2);     // 0
array.indexOf(7);     // -1
array.indexOf(9, 2);  // 2
array.indexOf(2, -1); // -1
array.indexOf(2, -3); // 0

```

* lastIndexOf() ()<<원소를 입력하면부터 뒤에서 부터 찾아서 index번호 알려준다. 



* slice() : `immutable`


> Examples

> Return a portion of an existing array

```js

var fruits = ['Banana', 'Orange', 'Lemon', 'Apple', 'Mango'];
var citrus = fruits.slice(1, 3);

// fruits contains ['Banana', 'Orange', 'Lemon', 'Apple', 'Mango']
// citrus contains ['Orange','Lemon']

```

* splice() : `mutable`


> Examples

> 1 . Remove 0 (zero) elements from index 2, and insert "drum"


```js

var myFish = ['angel', 'clown', 'mandarin', 'sturgeon'];
var removed = myFish.splice(2, 0, 'drum');

// myFish is ["angel", "clown", "drum", "mandarin", "sturgeon"] 
// removed is [], no elements removed

```

> Remove 0 (zero) elements from index 2, and insert "drum" and "guitar"Section



```js 

var myFish = ['angel', 'clown', 'mandarin', 'sturgeon'];
var removed = myFish.splice(2, 0, 'drum', 'guitar');

// myFish is ["angel", "clown", "drum", "guitar", "mandarin", "sturgeon"] 
// removed is [], no elements removed

```

> Remove 1 element from index 3

```js

var myFish = ['angel', 'clown', 'drum', 'mandarin', 'sturgeon'];
var removed = myFish.splice(3, 1);

// removed is ["mandarin"]
// myFish is ["angel", "clown", "drum", "sturgeon"]

```


> Remove 1 element from index 2, and insert "trumpet"


```js 

var myFish = ['angel', 'clown', 'drum', 'sturgeon'];
var removed = myFish.splice(2, 1, 'trumpet');

// myFish is ["angel", "clown", "trumpet", "sturgeon"]
// removed is ["drum"]

```


> Remove 2 elements from index 0, and insert "parrot", "anemone" and "blue"


```js


var myFish = ['angel', 'clown', 'trumpet', 'sturgeon'];
var removed = myFish.splice(0, 2, 'parrot', 'anemone', 'blue');

// myFish is ["parrot", "anemone", "blue", "trumpet", "sturgeon"] 
// removed is ["angel", "clown"]



```

> Remove 2 elements from index 2

```js

var myFish = ['parrot', 'anemone', 'blue', 'trumpet', 'sturgeon'];
var removed = myFish.splice(2, 2);

// myFish is ["parrot", "anemone", "sturgeon"] 
// removed is ["blue", "trumpet"]

```

> Remove 1 element from index -2

```js 

var myFish = ['angel', 'clown', 'mandarin', 'sturgeon'];
var removed = myFish.splice(-2, 1);

// myFish is ["angel", "clown", "sturgeon"] 
// removed is ["mandarin"]


```



> Remove all elements after index 2 (incl.)

```js
var myFish = ['angel', 'clown', 'mandarin', 'sturgeon'];
var removed = myFish.splice(2);

// myFish is ["angel", "clown"]
// removed is ["mandarin", "sturgeon"]


```



* split()

>문자열을 문자의 배열로 나누고 싶을 때 사용하는 메소드입니다.


```
var s = "hello, world this is jj";
s.split("");


"h", "e", "l", "l", "o", ",", " ", "w", "o", "r", "l", "d", " ", "t", "h", "i", "s", " ", "i", "s", " ", "j", "j"
```

```

var s = "hello, world this is jj";
s.split(",");
"hello", " world this is jj"
콤마가 생겼다. 콤마의 기준으로 갈라진다.
```

```
var s = "hello world t-h-i-s-i-s-j-j"
s.split("-");

"hello  world t", "h", "i", "s", "i", "s", "j", "j"
- 기준으로 갈라진다. 
```



* Array.isArray([]) :메서드는 인자가 Array인지 판별합니다.


> () 안에 비워 있으면 실행되지 않는다. 

>ex


```
Array.isArray([]);  // true
Array.isArray([1, 2, 3]);  // true
Array.isArray({foo: 123}); // false
Array.isArray('foobar');   // false
Array.isArray(undefined);  // false
```




---
## **object**
---




* Object.keys(객체)  : key 뽑기 into array
* Object.values(객체) : value 뽑기 into array
* Object.entries(객체) : 전체 뽑기 into array



```
let user = {
  name: "John",
  age: 30
};
Object.keys(person) = ["name", "age"]
Object.values(person) = ["John", 30]
Object.entries(person) = [ ["name","John"], ["age",30] ]

```


> 뽑은것들 변수에 담아서 배열 에 넣기  

```
let arrKey =  Object.keys(person);
>>["name", "age"]

let arrValues = Object.values(person);
>> ["John", 30]

let arrEntries = Object.entries(person);
>>[ ["name","John"], ["age",30] ]

```






* `obj.key` or `obj[key]` 


>for 문을 이용해 객체안에 있는 key value 뽑기


>ex 키값 뽑기 

```
let person = { name : "john" , age : 33 } ; 

for (let key in person) {
	console.log(key);
}

>>name
>>age

```


>ex value 뽑기 


```

let person = { name : "john" , age : 33 } ;

for (let key in person) {
	console.log(person[key]);
}

>>john
>>33

```


 * delete object.property
 * delete object["property"]
 
 
 > ex 
 
 
 ```
 
 var Employee = {
  age: 28,
  name: 'abc',
  designation: 'developer'
}

console.log(delete Employee.name);   // returns true
console.log(delete Employee.age);    // returns true

// When trying to delete a property that does 
// not exist, true is returned 
console.log(delete Employee.salary); // returns true
 
 ```
 
 

