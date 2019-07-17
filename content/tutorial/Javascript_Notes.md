---
title: JS Notes
date: 2019
draft: true
menu:
  tutorial:
    parent: "Javascript"
    weight: 100

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


---
## function 
---
```
함수를 변수, 매개변수 ,리턴값 으로 사욜할수 있다 이것을

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
## 콜백
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

