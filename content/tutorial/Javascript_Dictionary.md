---
title: JS My_Dictionary
date: 2019
draft: true
menu:
  tutorial:
    parent: "Javascript"
    weight: 10

toc: true
type: docs

---

---
## parseInt() 숫자로 바꾸는것
---
---
## toString() 문자로 바꾸는것
---
---
## String.repeat() 반복하는것 
---


---
## charAt(index) :인덱스에 있는 값을 리턴한다.
---

* ex
```
var stringName = 'coding everybody';
alert(stringName.charAt(0)); // c
alert(stringName.charAt(stringName.length-1)); // y
alert(stringName.charAt(1000) == ''); // true

```


---
## sort() : 배열 정렬할때 
---



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


* 추가 설명 from 생활코딩 사전 sort()

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
