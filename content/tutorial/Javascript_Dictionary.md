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


````
"Blue Whale"indexOf("Blue"); >>0
"Blue Whale".indexOf("hello"); >>-1
"Blue Whale".indexOf("Whale"); >>5


"canal".lastIndexOf("a") >> 3

```


* string.repeat(숫자입력) 반복하는것 

>ex


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