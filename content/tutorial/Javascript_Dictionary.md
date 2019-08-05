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
 
 
 ---
## **object and type **
---


* 01_removeStringValues


> Write a function called "removeStringValues". ("removeStringValues" 함수를 작성하세요.)

>Given an object, "removeStringValues" removes any properties on the given object whose values are strings. (객체가 주어졌을때, "removeStringValues" 함수는 속성값이 문자열인 모든 속성을 제거합니다.)
 


```

function removeStringValues(obj) {
  // 여기에 코드를 작성하세요.
  // 객체안에 있는 속성값이 문자열인지 판별한다.
  // 문자열이라면 삭제한다.
  for ( let prop in obj ) {
    if ( typeof obj[prop] === "string" ) {
      delete obj[prop]
    }
  }
}



```


* 02_removeNumberValues

> Write a function called "removeNumberValues". ("removeNumberValues" 함수를 작성하세요.)

>Given an object, "removeNumberValues" removes any properties whose values are numbers. (객체가 주어졌을때, "removeNumberValues" 함수는 속성값이 숫자인 모든 속성을 제거합니다.)

```
let obj = {
  a: 2,
  b: 'remaining',
  c: 4
};
function removeNumberValues(obj) {
  // 여기에 코드를 작성하세요.
  // prop 을 불러온다.
  // 불러온 prop 값을 숫자인지 판별한다/
  // 숫자이면 제거한다
  for ( let prop in obj ) {
    if ( typeof obj[prop] === "number" ) {
      delete obj[prop]
    }
  } 
  return obj;
}

removeNumberValues(obj);

```

* 03_removeArrayValues

> Write a function called "removeArrayValues". ("removeArrayValues" 함수를 작성하세요.)

>Given an object, "removeArrayValues" removes any properties whose values are arrays. (객체가 주어졌을때, "removeArrayValues" 함수는 속성값이 배열인 모든 속성을 제거합니다.)


```

let obj = {
  a: [1, 3, 4],
  b: 2,
  c: ['hi', 'there']
}
function removeArrayValues(obj) {
  // 여기에 코드를 작성하세요
  // prop 값을 불러온다
  // prop 값이 배열에 속하는지 판별한다
  // 배열에 속하면 제거한다.
  for ( let prop in obj ) {
    if (Array.isArray(obj[prop])) {
      delete obj[prop];
    }
  }
  return obj
}
removeArrayValues(obj)



```
