---
title: 1.My_dictionary
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



**str[index]**

`immutable`

> 1.글자 하나하나 가져오기

> 2. index로 접근은 가능하지만 쓸 수는 없음 (read-only)

> 3. + 연산자를 쓸수 있음.

> 4. length 쓸수 있음.



```
let str = 'CodeStates';

str[0]; >> 'C'

but

str[0] = 'G' >> 바뀌지 않음.

str = 'Codestates'
 
```

**str..toUpperCase()** 

`immutable`

> 소문자를 대문자로 바꿈

```
let str = 'CodeStates';

str.toUpperCase(); >>"CODESTATES

```

**str.toLowerCase()**

`immutable`


>대문자 소문자 바꿈


```

let str = "CodeStates";

str.toLowerCase()

```




**num.toString()** 

> 1.숫자를 문자로 바꾸는것 

```js

let num = 10;

num.toString();    

>> '10'

```



> 2.`Tip`배열에 담겨있는 문자열을 꺼낼때도 사용



```js
arr = ["this is john"]; //이문자를 꺼내기 위해서는 toString();

let words = arr.toString();

>words
> "this is john"



function getAllWords(str) {
  // your code here
  // toString 를 사용해 배열에 있는 문자를 꺼내서 새로운 변수에 담는다 
  // 변수에 담긴 문자를 나누는 메소드를 사용해  새로운 변수에 또 담는다.
  // 변수를 출력한다.
  if ( str === "" ) {
    let arr = [];
    return arr;
  } else {
  let words = str.toString();
  let ret = words.split(" ");
  return ret
  }
}

```


**String(obj)** 

>숫자를 문자로 바꾸는것 


>String, 이 함수는 변환하려는 객체의 toString() 메소드를 사용하는 것과 동일함



```js
var t = [1,2,3];

console.log(String(t)); 

>>"1,2,3"

```



**str.split()**


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




**str.indexOf(serchValue)** 


> 찾기 


```

"Blue Whale"indexOf("Blue"); >>0
"Blue Whale".indexOf("hello"); >>-1
"Blue Whale".indexOf("Whale"); >>5


"canal".lastIndexOf("a") >> 3

```


* str.repeat(숫자입력) 반복하는것 

>


```
let str = 'Because I'm happy';

console.log('Chorus lyrics for "Happy": ' + chorus.repeat(27));

```

**strcharAt(index)** 

>인덱스에 있는 값을 리턴한다.


> ex


```
var stringName = 'coding everybody';
alert(stringName.charAt(0)); // c
alert(stringName.charAt(stringName.length-1)); // y
alert(stringName.charAt(1000) == ''); // true

```



---
## **Number**
---


* parseInt() 숫자로 바꾸는것





---
## **Math_method**
---

**Math.max()**
**Math.min()**

> 큰수,작은수 가져오기


> EX 큰수 가져오기 

```js

Math.max(10, 20);   //  20
Math.max(-10, -20); // -10
Math.max(-10, 20);  //  20
```

> reduce 사용해서 큰수 가져오기

```js

var arr = [1,2,3];
var max = arr.reduce(function(a, b) {
    return Math.max(a, b);
});
```


>  spread operator  사용해서 큰수 가져오기 

```js

var arr = [1, 2, 3];
var max = Math.max(...arr);

```


---
## **Array**
---


**Array.isArray()**

>메서드는 인자가 Array인지 판별합니다.


> () 안에 비워 있으면 실행되지 않는다. 


```
Array.isArray([]);  // true
Array.isArray([1, 2, 3]);  // true
Array.isArray({foo: 123}); // false
Array.isArray('foobar');   // false
Array.isArray(undefined);  // false
```



**arr.indexOf(seachElement)** 


>`immutable`

> str.indexOf 랑 똑같다.

> element 존재 확인 할때 유용

> 발견되지 않으면 -1  표시 

> ()<<원소를 입력하면부터 앞에서 부터 찾아서 index번호 알려준다. 
> 비슷한 목적을 가진 메소드로는 includes,find가 있음

```js

var array = [2, 9, 9];
array.indexOf(2);     // 0
array.indexOf(7);     // -1
array.indexOf(9, 2);  // 2
array.indexOf(2, -1); // -1
array.indexOf(2, -3); // 0

```

**arr.lastIndexOf(seachElement)** 

> ()<<원소를 입력하면부터 뒤에서 부터 찾아서 index번호 알려준다. 


```js
var anyString = 'Brave new world';

console.log('The index of the first w from the beginning is ' + anyString.indexOf('w'));
// logs 8
console.log('The index of the first w from the end is ' + anyString.lastIndexOf('w')); 
// logs 10
console.log('The index of "new" from the beginning is ' + anyString.indexOf('new'));
// logs 6
console.log('The index of "new" from the end is ' + anyString.lastIndexOf('new'));
// logs 6

```


**arr.sort(sortfunc)**


> `mutable`

>1.배열을 정렬한다.

>2.알파벳 순서로 정렬한다.

>3.숫자의 경우 암시적으로 문자열로 형변환 하기 때문에 숫자 1이 숫자 10보다 먼저 나온다.

>4.sortfunc 로 비교 대상인 두개의 인자를 전달하는데, 리턴 값에 따라서 선후를 판단한다.



> Example 1

```

var numbers = [9,8,7,6,5,4,3,2,1];
alert(numbers.sort()); // array, [1,2,3,4,5,6,7,8,9]
alert(numbers); // array, [1,2,3,4,5,6,7,8,9], 원본을 변경한다. 
alert(numbers.sort() === numbers); // boolean, true, 원본과 반환값이 같다.
 
var numbers = [20, 10, 9,8,7,6,5,4,3,2,1];
//array, [1,10,2,20,3,4,5,6,7,8,9], 암시적으로 원소를 문자로 형변환 하기 때문에 10이 1뒤에 온다.
alert(numbers.sort()); 

```

> Example 2


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


> Example 3



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

> Description from others

```

위의 sort함수를 보면 parameter로 function이 올수 있다은건 이 문서를 보고 알수 있습니다.
그런데 sort함수 parameter인 function의 parameter와 retrun에 대한 설명(?)은 어떻게 알수 있나요??

예를들어서
var numbers = [20, 10, 9,8,7,6,5,4,3,2,1]; 
function sortNumber(a,b){
return a - b;
}

이럴때, sortNumber함수(내가 만들려는 함수 )의 파라미터가 2개 (a,b)인건 어찌 알수있고, 
return함수가 어떻게 동작하는지는 어떻게 알수 있을까요?


```



> Description from others

```js

우선 [20, 10, 9,8,7,6,5,4,3,2,1]의 배열에서 a-b라는 연산을 모두 한 다음 
그 결과값으로 정렬하는 것이 결코 아닙니다.
뭐하러 굳이 뺄셈을 하고 그 값으로 또 정렬하겠습니까? 

자바스크립트의 정확한 알고리즘은 아니지만 
쉽게 정렬 알고리즘을 설명하면 이렇습니다. 

(a,b) 형식으로 지정한 두 인자를 차례로 비교합니다.

우선 배열 numbers[0]과 numbers[1] 즉, 20과 10을 비교해 볼까요?
20-10 = 10 
결과값이 10 즉, 양수입니다.
sort함수에 sortNumber(a,b)의 return 값으로 양수 10을 전달합니다. 
그럼 sort함수가 양수값을 전달받고 배열의 순서를 바꾸어 버립니다. 
(정확하게 말하면 두 배열 안에 든 값을 교체)
그럼 배열이 [10, 20, 9,8,7,6,5,4,3,2,1] 이렇게 바뀝니다. 

그 다음 numbers[0]과 numbers[2] 즉 10과 9를 비교합니다. 10 - 9 = 1 >0, 양수입니다. 
결과값이 양수이므로 또 10과 9의 순서를 바꿉니다. 
이런 식으로 계속 두 인자를 비교해서 결과값이 양수가 나오면 순서를 바꾸고, 
음수가 나오면 순서를 그대로 유지하는 겁니다.

배열이 바뀌어가는 순서를 보면 이해하기 쉽습니다.

[(20), (10), 9,8,7,6,5,4,3,2,1] 20-10 = 10, 즉 양수이므로 순서바뀜! ()는 비교되는 인자값.
[(10), 20, (9),8,7,6,5,4,3,2,1] 10 - 9 = 1 또 양수, 순서 바뀜.
[(9), 20, 10, (8),7,6,5,4,3,2,1] 반복...
[(8), 20, 10, 9,(7)...]
...
[(2). 20, 10...3, (1)]
[(1), 20, 10...]

그럼 배열 내에서 가장 작은 값 1이 찾아지겠죠. 

[1, 20, 10, 9,8,7,6,5,4,3,2]

1의 순서는 바뀌지 않습니다. 1-2 = -1 
즉 결과값이 음수이기 때문이죠. 

그 다음은 두번째 배열 차례입니다.
20 - 10 = 10 > 0 이므로 순서를 또 바꿉니다. 

[1, (20), (10), 9,8,7,6,5,4,3,2]
[1, (10), 20, (9), 8...]
[1, (9), 20, 10, (8)...]

이런 식으로 반복하다 보면 두번째로 작은 값 2도 찾게 됩니다. 

....

[1, 2, 20, 10, 9,8,7,6,5,4,3]

그럼 다음은 세번째... 
이렇게 지루하게 반복하면 결국 정렬이 됩니다.

물론 실제 자바스크립트에서는 비교하는 순서가 다릅니다. 
다른 알고리즘을 쓰기 때문이죠.

이렇게 차례차례 비교해 나가면 인간이 이해하기는 쉽지만 
연산량이 기하급수적으로 늘어나기 때문에 다른 정렬 알고리즘을 쓰는 것이죠.

실제로는 
[20, 10, 9,8,7,6,5,4,3,2,1]
배열의 양쪽 끝부터 비교하고 (20, 1), 
그 다음 배열의 가운데 값을 차례로 비교해 나갑니다. (1,6)
디버깅해 보시면 쉽게 아실 수 있을 겁니다
```

> Description from others


```js
ar numbers = [20, 10, 9,8,7,6,5,4,3,2,1]; 
function sortNumber(a,b){
return a - b;
}
를 하게 되면 모든 값들끼리 a - b를 하게 됩니다. 

그렇게 나온 값들을 sort()에 넣으면, (a - b)의 순서가 숫자가 낮은 것부터 높은 순서대로 정렬이 되겠죠.
-19(1 - 20), -9(1-10), -8(1-9), -7(1-8), -6(1-7), -5(1-6), -4(1-5), -3(1-4), -2(1-3), -1(1-2)
-18(2-20), -8(2-10), -7(2-9), -6(2-8), -5(2-7), -4(2-6), -3(2-5), -2(2-4), -1(2-3), 0(2-2), 1(2-1)
-17(3-20), -7(3-10), -6(3-9), -5(3-8), -4(3-7), -3(3-6), -2(3-5), -1(3-4), 0(3-3), 1(3-2), 2(3-1)
...
10(20-10), 11(20-9), 12(20-8), 13(20-7), 14(20-6), 15(20-5), 16(20-4), 17(20-3), 18(20-2), 19(20-1)

그럼 계산된 숫자의 크기에 따라서 a와 b의 순서가 sort()에 의해 재배열 되어
1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 20
가 나옵니다.

```



**arr.push(newElement)**

>`mutable`

>마지막 배열에 추가 

```
var arr = [1,2,3,4,];
arr.push(1);

arr; // = > [1,2,3,4,1]
```

**arr.pop()** 

>`mutable`

> 뒤에 있는배열 제거 



```js
var arr = [1,2,3,4,];
arr.pop();

arr; // = > [1,2,3]
```


**arr.unshift()**	 

> 앞에 붙이기

```
var arr = [1,2,3,4];

arr.unshift(1);

arr; // = > [1,1,2,3,4,];

```


**arr.shift()**  

>앞에 있는거 빼기

```
var arr = [1,2,3,4];

arr.shift();

arr; // = > [2,3,4,]

```


**arr.slice(bein,end)**

> `immutable`
> 문자열의 특정구간을 검색




* `tip` 복제할수 있는 기능도 있다.

```js
let obj1 = [1,2,3,4,5,6];
let obj2 = obj1.slice();

>> obj2 = [1,2,3,4,5,6 ];

```

* 2번째 인덱스 부터 가져온다

```js
var fruits = ['Banana', 'Orange', 'Lemon', 'Apple', 'Mango'];
var myFruits = fruits.slice(2);

myFruits = ["Lemon", "Apple", "Mango"]


```


* Return a portion of an existing array

```js

var fruits = ['Banana', 'Orange', 'Lemon', 'Apple', 'Mango'];
var citrus = fruits.slice(1, 3);

// fruits contains ['Banana', 'Orange', 'Lemon', 'Apple', 'Mango']
// citrus contains ['Orange','Lemon']

```



**arr.splice(start,deleteCount,"itme1",...")**

>`mutable`

> 중간에 element 를 삭제 할수 있는 방법이 이거뿐





* Remove 0 (zero) elements from index 2, and insert "drum"


```js

var myFish = ['angel', 'clown', 'mandarin', 'sturgeon'];
var removed = myFish.splice(2, 0, 'drum');

// myFish is ["angel", "clown", "drum", "mandarin", "sturgeon"] 
// removed is [], no elements removed

```

* Remove 0 (zero) elements from index 2, and insert "drum" and "guitar"Section



```js 

var myFish = ['angel', 'clown', 'mandarin', 'sturgeon'];
var removed = myFish.splice(2, 0, 'drum', 'guitar');

// myFish is ["angel", "clown", "drum", "guitar", "mandarin", "sturgeon"] 
// removed is [], no elements removed

```

* Remove 1 element from index 3

```js

var myFish = ['angel', 'clown', 'drum', 'mandarin', 'sturgeon'];
var removed = myFish.splice(3, 1);

// removed is ["mandarin"]
// myFish is ["angel", "clown", "drum", "sturgeon"]

```


* Remove 1 element from index 2, and insert "trumpet"


```js 

var myFish = ['angel', 'clown', 'drum', 'sturgeon'];
var removed = myFish.splice(2, 1, 'trumpet');

// myFish is ["angel", "clown", "trumpet", "sturgeon"]
// removed is ["drum"]

```


* Remove 2 elements from index 0, and insert "parrot", "anemone" and "blue"


```js


var myFish = ['angel', 'clown', 'trumpet', 'sturgeon'];
var removed = myFish.splice(0, 2, 'parrot', 'anemone', 'blue');

// myFish is ["parrot", "anemone", "blue", "trumpet", "sturgeon"] 
// removed is ["angel", "clown"]



```

* Remove 2 elements from index 2

```js

var myFish = ['parrot', 'anemone', 'blue', 'trumpet', 'sturgeon'];
var removed = myFish.splice(2, 2);

// myFish is ["parrot", "anemone", "sturgeon"] 
// removed is ["blue", "trumpet"]

```

* Remove 1 element from index -2

```js 

var myFish = ['angel', 'clown', 'mandarin', 'sturgeon'];
var removed = myFish.splice(-2, 1);

// myFish is ["angel", "clown", "sturgeon"] 
// removed is ["mandarin"]


```



* Remove all elements after index 2 (incl.)

```js
var myFish = ['angel', 'clown', 'mandarin', 'sturgeon'];
var removed = myFish.splice(2);

// myFish is ["angel", "clown"]
// removed is ["mandarin", "sturgeon"]


```



**arr.concat(arr)** 

> `immutable`
> 더하기 

```js
1.

let letters = ['a', 'b', 'c'];
let numbers = [1, 2, 3];

letters.concat(numbers);


// result in ['a', 'b', 'c', 1, 2, 3]


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





**arr.forEach()**

> `immutable`

> 배열에 길이 만큼 반복 실행하는 용도! 

>forEach()는 주어진 callback을 배열에 있는 각 요소에 대해 오름차순으로 한 번씩 실행합니다



```js
var array1 = ['a', 'b', 'c'];

array1.forEach(function(element) {
  console.log(element);
});

// expected output: "a"
// expected output: "b"
// expected output: "c"


```


> 3가지 인자값을 싱행 할수 있다. 

* 요소 값
* 요소 인덱스
* 순회 중인 배열


```
function logArrayElements(element, index, array) {
  console.log('a[' + index + '] = ' + element);
}

// Notice that index 2 is skipped since there is no item at
// that position in the array.
[2, 5, , 9].forEach(logArrayElements);
// logs:
// a[0] = 2
// a[1] = 5
// a[3] = 9

```


**arr.map()**

> `immutable`

> callback 내에서 리턴이 필요하다.

> 기존배열과 길이가 같고 , 형태가 다른 배열을 만들때 유용


* 배열에 있는 값 각 각  100으로나누고 싶다?

```js

let arr = [100 ,200 ,500 ];

let newArr = arr.map(function(cur,idx,arr){
return cur / 100;
})

>>newArr = [1, 2, 5]


```
* 배열 안에있는 것을 다른 형태로 출력 하고 싶다.?(길이)

```js


arr2 = ["code","states"];

let newArr2 = arr2.map(function(cur){
	return cur.length
});

>> newArr2 = [4, 6]

```

**arr.filter()**

> 걸러주는 역활 한다. 

> return 필요



```js

let arr = [1,2,3,4,5,6];

newArr = arr.filter(function(cur,index,arr2){

	return cur < 2;
})


newArr = [1];



```


**arr.reduce(callback,[,initalValue])**

>`immutable`

> return value :  최종 누적값

>모든 element 값을 누적해 하나의 결과로 리턴할 때 유용

>The reducer function takes four arguments:

>Accumulator (acc)

>Current Value (cur)

>Current Index (idx)

>Source Array (src)


* 배열안에 있는 값을 각 각 더하고 싶을때 ?

```js
let arr = [1, 2, 3, 4];

let count = arr.reduce(function(acc.cur){
  return acc + cur;
  // 1 + 2 + 3 + 4
});

conunt => 10

```



* 초기값 5 를 넣고 더했을때

```js

let arr = [1, 2, 3, 4];

let count = arr.reduce(function(acc.cur) {
  return acc + cur;
  //5 + 1 + 2 + 3 + 4
},5);


count = >> 15

```





**arr.join(separator)** 

>`immutable`

> 배열의 원소를 결합해서 하나의 문자열로 만든다.
> 공백이 있는 곳에  요소를 더할수 있다.


```js

let arr = ["welcome","coding","everybody"];
arr.join(" ");
"welcome coding everybody"

arr.join(" hi ")
"welcome hi coding hi everybody"

```
---
## **object**
---



* Object.keys(객체)  : `key` 뽑기 into array
* Object.values(객체) : `value` 뽑기 into array
* Object.entries(객체) : `전체`뽑기 into array



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
