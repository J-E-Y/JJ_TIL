---
title: 1. Dictionary
date: 2019
draft: true
menu:
  tutorial:
    parent: "Javascript"
    weight: 9

toc: true
type: docs

---

![](/tutorial/Javascript_Dictionary_files/javascriptt-light_870x220.png)
 

---
## **String** 
---


**str.includes()**

```js

// true or false 를 반환한다. 
// if 문에 넣어 쓴다. 

let str = 'To be, or not to be, that is the question.';

console.log(str.includes('To be'));       // true
console.log(str.includes('question'));    // true
console.log(str.includes('nonexistent')); // false
console.log(str.includes('To be', 1));    // false
console.log(str.includes('TO BE'));       // false
console.log(str.includes('')) 


```




**str.match(regexp)**

`immutable`


```js

// 문자열안에 있는 알파벳 뽑기.

let str = "abcdefgh23j2k4h6l3h1uiui24h4324jk3jh4k3h24"

let alphabet = str.match(/[a-zA-Z]/g);

// ["a", "b", "c", "d", "e", "f", "g", "h", "j", "k", "h", "l", "h", "u", "i", "u", "i", "h", "j", "k", "j", "h", "k", "h"]


```


**str[index]**

`immutable`


```js

// 1.글자 하나하나 가져오기

// 2. index로 접근은 가능하지만 쓸 수는 없음 (read-only)

// 3. + 연산자를 쓸수 있음.

// 4. length 쓸수 있음.

// let str = 'CodeStates';

// str[0]; >> 'C'

// but

// str[0] = 'G' >> 바뀌지 않음.

// str = 'Codestates'
 
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

>`immtuable`

>문자열을 문자의 배열로 나누고 싶을 때 사용하는 메소드입니다.

> 문자열을 배열로 만들때 유용


```js
let str = "hello, world this is jj";

1.str.split();
["hello, world this is jj"]


2. str.split("");
["hello", "world", "this", "is", "jj"]


3. str.split(" ");
["h", "e", "l", "l", "o", " ", "w", "o", "r", "l", "d", " ", "t", "h", "i", "s", " ", "i", "s", " ", "j", "j"]

```


```js

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

**str.charAt(index)** 

>인덱스에 있는 값을 리턴한다.


> ex


```
var stringName = 'coding everybody';
alert(stringName.charAt(0)); // c
alert(stringName.charAt(stringName.length-1)); // y
alert(stringName.charAt(1000) == ''); // true

```



**str.replace()**

>`immtable`


>값을 찾아서 원하는 값으로 바꿔준다 


```js
str = "john jung"
let newStr = str.replace(john,jj);

> "jj jung"

```
---
## **Number**
---



**num.toFixed( digits )**


```js
// 소수점 지정하는것 

var numObj = 12345.6789;

numObj.toFixed();       // Returns '12346': note rounding, no fractional part
numObj.toFixed(1);      // Returns '12345.7': note rounding
numObj.toFixed(6);      // Returns '12345.678900': note added zeros

```



**parseInt(value)** 
```js
// 정수로 파싱 한다. 
// 만약 Number 는 숫자로 만 변환해준다면 이메소드는 바로 15를 출력하게 해준다. 
// parseInt 는 집법 변환 할때도 쓰인다. 


parseInt(string, radix);

parseInt('0xF', 16);  // 15   >> 16진수는 f까지 있으니까 f 가15니까 
parseInt('F', 16);  // 15   
parseInt('17', 8);  // 15   10진법으로 전환해서 
parseInt(15,99 10); // 15
Number("15.123")

// 15.123

parseInt("15.123"")
 
// 15

```

**parseFloat(value)**


```js

parseFlaot("15.123")

// 15.123

```



**Number.isInteger(value)**

```js

// 정수인지 아닌지 판단하는 것

Number.isInteger(0);         // true
Number.isInteger(1);         // true
Number.isInteger(-100000);   // true
Number.isInteger(99999999999999999999999); // true

Number.isInteger(0.1);       // false
Number.isInteger(Math.PI);   // false

Number.isInteger(NaN);       // false
Number.isInteger(Infinity);  // false
Number.isInteger(-Infinity); // false
Number.isInteger('10');      // false


```



---
## **Math_method**
---


**Math.random()**

```js
// arguments :  없음
// return value :  0 과 1 사이의 난수를 반환한다. 

Math.random(); // 0.7915594421190384  // 콘솔에 찍으면 막 나온다. 
Math.random(); // 0.12480720616017948 // 난수가 반환이 되는 것이다. 
Math.random(); // 0.014493108986906034

// 이것을 이용해 특정 범이의 정수 리턴하기
// 사용자가 원하는 정수를 출력하는 함수 만들기

Math.random(); // 0.014493108986906034 //   // 0 과 1 사이의 숫자들 

Math.random() * 10 // >>8.031510209216247    // 0  ~ 10 까지 
Math.random() * 109 // >>50.031510209216247  // 0 ~ 109 까지 
Math.random() * 20 // >>14.031510209216247   // 0 ~ 20 까지 
Math.random() * 5 // >>2.031510209216247     // 0 ~ 5 까지 


function getRandomInt(num) {
	return Math.floor(Math.random() * num );
}

getRandomInt(10); // >> 6
getRandomInt(100); // >> 50
getRandomInt(20); // >> 15
getRandomInt(7); // >> 5

```


**Math.floor(x)**


```js

// 반환값(Return)
// number, 정수

//예제(Example)


Math.floor(5.12323); // number, 5
Math.floor(5.912321); // number, 5
Math.floor(5); // number, 5
Math.floor(-5.121323); // number, -6
Math.floor(-5.923213); // number, -6
```



**Math.abs(x)**


```js

// 함수는 주어진 숫자의 절대값을 반환합니다
// 소수점을 없애는 것은 안된다. 

Math.abs('-1');     // 1
Math.abs(-2);       // 2`
Math.abs(null);     // 0
Math.abs('');       // 0
Math.abs([]);       // 0
Math.abs([2]);      // 2
Math.abs([1,2]);    // NaN
Math.abs({});       // NaN
Math.abs('string'); // NaN
Math.abs();         // NaN
```



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

let arr = [1,2,3];
let max = arr.reduce(function(a, b) {
    return Math.max(a, b);
});


console.log(max)
>3

```


>  spread operator  사용해서 큰수 가져오기 

> arr 로 큰수를 가져오기 위해서는 ... 을 써야 Math.max() << 안에 들어간다. 

```js

let arr = [1, 2, 3];
let max = Math.max(...arr);

console.log(max)
>3

```


---
## **Array**
---


**arr.reverse()**


```js

let arr = [1, 2, 3];

arr.reverse();  // [3, 2, 1]


// 갹체안에있는 pro 값만 바꿀수 있다. 

let a = {0: 1, 1: 2, 2: 3, length: 3};

console.log(a); // {0: 1, 1: 2, 2: 3, length: 3}

Array.reverse.call(a); //same syntax for using apply()

console.log(a); // {0: 3, 1: 2, 2: 1, length: 3}



```




**arr.fill()**


```js

// fill 메서드는 value, start, end의 3개 인자를 가집니다

[1, 2, 3].fill(4);        // 4 로 채울것이다.
 // [4, 4, 4]           
[1, 2, 3].fill(4, 1);    // 4 로 채울건데 1번째 부터 쭉 
// [1, 4, 4]
[1, 2, 3].fill(4, 1, 2);   // 4 로 채울건데 1번쨰 부터 2번째까지   
//[1, 4, 3]
[1,2,3,4,5,6,7,8,9,10].fill(4, 3, 6); // 4 로 채울건데 3번째 부터 6번째 까지 (5 번째 까지 채워짐) 
// [1, 2, 3, 4, 4, 4, 7, 8, 9, 10]
[1, 2, 3].fill(4, 3, 3);  // 4 로 채울건데 3번째 부터 3번까지 값이 없다. 
// [1, 2, 3]





```








**arr.includes()**


```js

arr = ["a","b","c","d"];

arr.includes("a"); 
// true

arr.includes("f");
//false

```





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



```js

strArr = ["all", "before", "hello", "world"]

// a 가 크면 리턴 1  작은수부터 정렬
strArr.sort(function(a,b){
	if (a > b) {
	return 1;
} else if (a === b){
	return 0;
} else {
	return -1;
}
})


// a 가 작으면 리턴  큰수부터 정렬

strArr.sort(function(a,b){
	if (a > b) {
	return -1;
} else if (a === b){
	return 0;
} else {
	return 1;
}
})




```





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

`mutable`

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

`mutable`

> 앞에 붙이기

```
var arr = [1,2,3,4];

arr.unshift(1);

arr; // = > [1,1,2,3,4,];

```


**arr.shift()**  

`mutable`

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

* 만약 fruits.slice(1,`0`)

```js
var fruits = ['Banana', 'Orange', 'Lemon', 'Apple', 'Mango'];

fruits.slice(1, 0);

>> []  << 값이 사라진다. 
```



**arr.splice(start,deleteCount,"itme1",...")**

>`mutable`


> 배열 중간에 원소 추가, 삭제

> 중간에 element 를 삭제 할수 있는 방법이 이거뿐

```js

var array = [1,2,3,4,5];
// 배열 중간에 원소 삭제 
// array.splice(인덱스, 인덱스부터 삭제할 원소개수)
var o = array.splice(2, 1);  
console.log(array); // [1, 2, 4, 5]
console.log(o); // [3]  // 삭제된 원소 반환
// 배열 중간에 원소 추가 
// array.splice(인덱스, 인덱스부터 삭제할 원소개수(추가시 0), 추가할 원소 ...)
o = array.splice(3, 0, 99, 99, 99);  
console.log(array); // [1, 2, 4, 99, 99, 99, 5]
console.log(o); // []
/*
array.unshift();  // 첫번째 원소 추가
array.shift();     // 첫번째 원소 삭제
array.push();    // 마지막 원소 추가
array.pop();      // 마지막 원소 삭제
array.join();      // 배열의 모든 원소를 문자열로 변환하고 연결(+)한 결과 반환
*/      


```



**arr.concat(arr)** 

`immutable`

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

* 배열안에 모든 요소를 숫자로 바꾸기

```js



// 더 간단하게 해결할 수 있는 방법
['1', '2', '3'].map(Number); // [1, 2,3]


// 아래 라인을 보시면...
['1', '2', '3'].map(parseInt);
// 결과를 [1, 2, 3] 으로 기대할 수 있습니다.
// 그러나 실제 결과는 [1, NaN, NaN] 입니다.

// 그러나 `parseInt`와 달리 float이나 지수표현도 반환합니다.

['1.1', '2.2e2', '3e300'].map(Number); // [1.1, 220, 3e+300]


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


**arr.every()**

>every() 메서드는 배열 안의 모든 요소가 주어진 판별 함수를 통과하는지 테스트합니다.


>다음 예는 배열의 모든 요소가 10보다 더 큰지 테스트합니다.

```js
function isBigEnough(element, index, array) {
  return element >= 10;
}
[12, 5, 8, 130, 44].every(isBigEnough);   // false
[12, 54, 18, 130, 44].every(isBigEnough); // true
```

> 화살표 함수 사용

```js

[12, 5, 8, 130, 44].every(elem => elem >= 10); // false
[12, 54, 18, 130, 44].every(elem => elem >= 10); // true


```


**arr.some()**


> 하나라도 조건이 맞으면 true  반환한다. 

```js
var array = [1, 2, 3, 5];

var even = function(element) {
  // checks whether an element is even
  return element % 2 === 0;
};

console.log(array.some(even));
// expected output: true



```

---
## **Object**
---



**Object.keys(객체)  : `key` 뽑기 into array**
**Object.values(객체) : `value` 뽑기 into array**
**Object.entries(객체) : `전체`뽑기 into array**



```js
let user = {
  name: "John",
  age: 30
};
Object.keys(person) = ["name", "age"]
Object.values(person) = ["John", 30]
Object.entries(person) = [ ["name","John"], ["age",30] ]

```


> 뽑은것들 변수에 담아서 배열 에 넣기  

```js
let arrKey =  Object.keys(person);
>>["name", "age"]

let arrValues = Object.values(person);
>> ["John", 30]

let arrEntries = Object.entries(person);
>>[ ["name","John"], ["age",30] ]

```






**`obj.key` or `obj[key]** 


>for 문을 이용해 객체안에 있는 key value 뽑기


>ex 키값 뽑기 

```js
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


**delete object.property**
 
 
```js


let Employee = {
  firstname: "John",
  lastname: "Doe"
}



delete Employee.firstname; // 삭제명령
delete Employee["firstname"] // 삭제명령

console.log(Employee);

// 삭제됨
let Employee = {
  lastname: "Doe"
}

 
```

