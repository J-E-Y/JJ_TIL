---
title: Daliy_Coding_Level_1
author: JohnJung
date: '2019-11-14'
slug: javascript-daliy-coding-level-1
categories: []
tags:
  - Javascript
menu:
  tutorial:
    parent: "6.Javascript"
    weight: 2
toc: yes
type: docs
summary: 'write here:rocket:' 
---



### Question

## longestWord

> Using the JavaScript language, have the function LongestWord take the sen parameter being passed and return the largest word in the string. (문장이 주어졌을때, 'LongestWord' 함수는 주어진 문장에서 가장 긴 단어를 반환합니다.)

>If there are two or more words that are the same length, return the first word from the string with that length. Assume sen will not be empty. (만약 가장 긴 단어가 두개 이상이라면, 첫번째로 등장하는 가장 긴 단어를 반환하세요. 문장은 빈 문자열이 아닙니다.)





### My_Soultion


```js

// It's used by sort() 

function longestWord(string) {

 // 1. 주어진 문장을 배열로 만들기(split)
 let tmp = string.split(' ');
 //let sorted_tmp =[];
 // ['I','love','codestates'];
 // 2. sort() 사용 => 성능 떨어짐
 let x = function(a,b){
   return b.length-a.length;
 };
 // 3. 0번째 요소 출력
 return tmp.sort(x)[0];
}

////////////////////////////////////////////////////////

// It's used by reudce(1)

function longestWord(string) {
 
 let tmp = string.split(' ');
 let max = tmp[0];
 for(let i =1;i<tmp.length;i++){
   if(tmp[i].length>max.length){
     max = tmp[i];
   }
 }
 return max;
}


/////////////////////////////////////////////////////////

// It's used by reudce(2) 화살표

function longestWord(string) {

return string.split(' ').reduce((acc,cur)=> acc.length<cur.length? cur:acc);
}



```




### Question

## firstCharacter

> In this exercise, a string is passed to a method and a new string has to be returned with the first character of each word in the string (문자열이 주어졌을때, "firstCharacter" 함수는 문자열의 각 단어 첫글자들로 이루어진 문자열을 반환하여야 합니다.)



### My_Soultion


```js

function firstCharacter (string) {
 // Your code here
 
 
 // 1. for문 이용
 
 let output = [];
 let temp_arr = [];

 // 1. split으로 단어로 나눠서 배열 만들기
 
 temp_arr = string.split(' ');
 // 2. 각 인덱스의 첫번째 문자를 배열 output 에 담기
 for(let i=0;i<temp_arr.length;i++){
   output.push(temp_arr[i][0]);
 }
 
 // 4. 출력
 return output.join('');
 
 
 
 ////////////////////////////////////////////////////////////////////////
 
 // 2. Reduce 이용
 return string.split(' ').reduce(function(acc,cur){
   return acc+cur[0];
 
 },'');
 
 // 3. Reduce이용 2
 return string.split(' ').reduce( (acc,cur)=>acc+cur[0] ,'');
}




```





### Question

## isOldEnoughToDrink


>어떤 숫자, 이 경우에는 연령이 하나 주어졌을 때, isOldEnoughToDrink 함수는 주어진 연령의 사람이 미국에서 합법적으로 술을 마실 수 있는지의 여부를 반환해야 합니다.


### My_Soultion


```js
function isOldEnoughToDrink(age) {
  // 여기에 코드를 작성하세요
  if (age < 21 ) {
    return false;
  } else {
    return true;
  }
}


```


### Question  

## checkAge

>이름과 나이를 파라미터로 받는 checkAge라는 함수는 두개 중 하나의 메시지를 리턴합니다.

>만일 21살보다 적으면, Go home, {전달받은_이름}! 만일 21살이거나 더 나이가 많으면, Welcome, {전달받은_이름}! 을 리턴하세요. 쉼표와 공백, 느낌표까지 정확히 리턴해야 합니다.



### My_Soultion

```

function checkAge(name, age) {
  // 여기에 코드를 작성하세요
  if (age >= 21){
    return 'Welcome, ' + name+ '!';
  } else {
    return 'Go home, ' + name+ '!';
  }
};

```




### Question 

## equalsTen


>Write a function called "equalsTen". ("equalsTen" 함수를 작성하세요.)

>Given a number, "equalsTen" returns whether or not the given number is 10. ("숫자가 주어졌을때, "equalsTen" 함수는 숫자가 10과 같은지 반환합니다.)




### My_Soultion

```
function equalsTen(num) {
  // 여기에 코드를 작성하세요
  if ( num !== 10){
    return false;
  }else if (num === 10 ){
    return true;
  }
}

equalsTen(10);


```




### Question 

## isGreaterThan


>Write a function called "isGreaterThan". ("isGreaterThan" 함수를 작성하세요.)

>Given 2 numbers, "isGreaterThan" returns whether num2 is greater than num1. (두 숫자가 주어졌을때, "isGreaterThan" 함수는 두번째 숫자(num2)가 첫번째 숫자(num1)보다 큰지 반환해야 합니다.)


### My_Soultion


```

function isGreaterThan(num1, num2) {
  // 여기에 코드를 작성하세요
  if ( num1 === num2 ){
    return false;
  } else if ( num1 < num2) {
    return true;
  } else {
    return false;
  }
}

isGreaterThan(20,30)

```



### Question 

## isEven


>Write a function called "isEven". ("isEven" 함수를 작성하세요.)

>Given a number, "isEven" returns whether it is even. ("숫자가 주어졌을때, "isEven" 함수는 주어진 숫자가 짝수인지 반환합니다.)



### My_Soultion

```
function isEven(num) {
  // 여기에 코드를 작성하세요
  if ( num % 2 === 0 ) {
    return true;
  } else {
    return false;
  }

}

isEven(21)

```



### Question 

## isEvenAndGreaterThanTen


>Write a function called "isEvenAndGreaterThanTen". ("isEvenAndGreaterThanTen" 함수를 작성하세요.)

>Given a number, "isEvenAndGreaterThanTen" returns whether it is both even and greater than 10. (숫자가 주어졌을때, "isEvenAndGreaterThanTen" 함수는 주어진 숫자가 10보다 크고 짝수인지 반환해야 합니다.)


### My_Soultion

```
function isEvenAndGreaterThanTen(num) {
  // 여기에 코드를 작성하세요
  if ( num % 2 === 0 && num > 10 ){
    return true;
  } else {
    return false;
  }
}
isEvenAndGreaterThanTen(13);


```


### Question 

## convertScoreToGrade


>Write a function called "convertScoreToGrade". ("convertScoreToGrade" 함수를 작성하세요.)

>Given a score, "convertScoreToGrade" returns a string representing the letter grade corresponding to the given score. (점수가 주어졌을때, "convertScoreToGrade" 함수는 주어진 점수와 대응하는 등급을 문자열로 반환합니다.)


### My_Soultion

```
function convertScoreToGrade(score) {
  // 여기에 코드를 작성하세요
  if ( score > 100 || score < 0) {
    return "INVALID SCORE";
  } else if ( score >= 90 ) {
    return "A";
  } else if ( score >= 80 ) {
    return "B";
  } else if ( score >= 70 ) {
    return "C";
  } else if ( score >= 60 ) {
    return "D";
  } else {
   return 'F';
  }
}
convertScoreToGrade(0);

```


### Question 

### Or




>Write a function called "or". ("or" 함수를 작성하세요.)

>Given 2 boolean expressions, "or" returns true or false, corresponding to the || operator. (boolean 두개가 주어졌을때, "or" 함수는 || 연산자에 대응하는 true 나 false 를 반환합니다.)




### My_Soultion

```
function or(expression1, expression2) {
  // 여기에 코드를 작성하세요
  if ( expression1 !== false  ) {
    return true;
  } else if ( expression2 !== false ) {
    return true;
  } else {
    return false;
  }

}

```



### Question 

## isEitherEvenAndLessThan9




>Write a function called "isEitherEvenAndLessThan9". ("isEitherEvenAndLessThan9" 함수를 작성하세요.)

>Given two numbers, 'isEitherEvenAndLessThan9' returns whether at least one of them is even, and, both of them are less than 9. (숫자 두개가 주어졌을때, 'isEitherEvenAndLessThan9' 함수는 2가지 조건을 검사합니다. 우선 두 숫자 중 적어도 하나가 짝수인지, 그리고 두 숫자 모두 9보다 작은지를 확인합니다. 두 조건을 모두 만족 했을 때만 true를 반환합니다.)



### My_Soultion

```

function isEitherEvenAndLessThan9(num1, num2) {
  if ((num1 % 2 === 0 || num2 % 2 === 0) && (num1 < 9 && num2 < 9)) {
    return true;
  } else {
    return false;
  }
}


```




---
### Question : getFullName
---



>Write a function called "getFullName". ("getFullName" 함수를 작성하세요.)

>Given a first and a last name, "getFullName" returns a single string with the given first and last names separated by a single space. (이름과 성이 주어졌을때, "getFullName" 함수는 이름과 성이 띄어쓰기 하나를 사이에 둔 단일 문자열을 반환해야 합니다.)


### My_Soultion

```

function getFullName(firstName, lastName) {
  // 여기에 코드를 작성하세요
  let output = firstName + lastName;
  return firstName + " " + lastName;
}
  
getFullName('john','jung')

```




### Question 

## getLengthOfWord




>Write a function called "getLengthOfWord". ("getLengthOfWord" 함수를 작성하세요.)

>Given a word, "getLengthOfWord" returns the length of the given word. (단어가 주어졌을때, "getLengthOfWord" 함수는 단어의 길이를 반환해야 합니다.)


### My_Soultion

```

function getLengthOfWord(word) {
  // 여기에 코드를 작성하세요
  let count = word.length;
  return count;
}
getLengthOfWord("hello")

```



### Question 

## computeAverageLengthOfWords




>Write a function called "computeAverageLengthOfWords". ("computeAverageLengthOfWords" 함수를 작성하세요.)

>Given two words, "computeAverageLengthOfWords" returns the average of their lengths. (두 단어가 주어졌을때, "computeAverageLengthOfWords" 함수는 두 단어 길이의 평균값을 반환합니다.)


### My_Soultion


```
function computeAverageLengthOfWords(word1, word2) {
  // your code here
  // count
  var firstNum = word1.length;
  var sceondNum = word2.length;
  var ret = (firstNum + sceondNum) / 2;
  return ret;
  }
  computeAverageLengthOfWords("whatIYouDoing?","this is JJ")


```



### Question 

## isOddLength



>Write a function called "isOddLength". ("isOddLength" 함수를 작성하세요.)

>Given a word, "isOddLength" returns whether the length of the given word is odd. (단어가 주어졌을때, "isOddLength" 함수는 주어진 단어의 길이가 홀수인지 반환해야 합니다.)


### My_Soultion

```
function isOddLength(word) {
  // your code here
  let countNum = word.length;
  if ( countNum % 2 !== 0) {
    return true;
  } else {
    return false;
  }
}

isOddLength("heeeee")
```



### Question 

## isEvenLength



>Write a function called "isEvenLength". ("isEvenLength" 함수를 작성하세요.)

>Given a word, "isEvenLength" returns whether the length of the word is even. (단어가 주어졌을때, "isEvenLength" 함수는 주어진 단어의 길이가 짝수인지 반환해야 합니다.)



### My_Soultion

```

function isEvenLength(word) {
  // your code here
  var countNum = word.length;
  if ( countNum % 2 === 0 ) {
    return true;
  } else {
    return false;
  }
}

isEvenLength("hee")


```


### Question 

## repeatString




>Write a function called "repeatString". ("repeatString" 함수를 작성하세요.)

>Given a string and a number, "repeatString" returns the given string repeated the given number of times. (문자열과 숫자가 주어졌을때, "repeatString" 함수는 주어진 문자열을 주어진 숫자만큼 반복하여 반환해야 합니다.)

### My_Soultion

```

function repeatString(string, num) {
  // your code here
 var repeatation = string.repeat(num) 
 return repeatation;
}

repeatString("thewordofGod is the way",50)
```




### Question 

## findShortestOfThreeWords



>Write a function called "findShortestOfThreeWords". ("findShortestOfThreeWords" 함수를 작성하세요.)

>Given 3 strings, "findShortestOfThreeWords" returns the shortest of the given strings. (문자열 3개가 주어졌을때, "findShortestOfThreeWords" 함수는 주어진 문자열 중 가장 짧은 문자열을 반환해야 합니다.)

>If there are ties, it should return the first word in the parameters list. (만약 동률이 있다면, 그 중 앞에 있는 문자열을 반환해야 합니다.)



### My_Soultion

```js
function findShortestOfThreeWords(word1, word2, word3) {
  // your code here
  if ( word1.length < word2.length && word3.length ) {
    return word1;
  } else if (word1.length === word2.length && word3.length){
    return word1;
  } else if ( word2.length < word1.length && word3.length ){
  return word2;
  } else if ( word3.length < word2.length && word1.length ) {
    return word3;
  }
}

findShortestOfThreeWords("111","222","333333333")
```




### Question 

## countCharacter

>Write a function called "countCharacter". ("countCharacter" 함수를 작성하세요.)

>Given a string input and a character, "countCharacter" returns the number of occurences of a given character in the given string. (문자열과 문자가 주어졌을때, "countCharacter" 함수는 주어진 문자열에서 주어진 문자가 몇개가 있는지를 반환해야 합니다.)

### My_Soultion

```js

function countCharacter(str, char) {
  // your code here
  let countRet = 0;
  for ( let i = 0; i < str.length; i = i + 1 ) {
    if ( str.charAt(i) === char ) {
      countRet = countRet + 1 ;
    }
  }
  return countRet;
}

countCharacter("hello", "l" );



```




### Question

## areValidCredentials





>Write a function called "areValidCredentials". ("areValidCredentials" 함수를 작성하세요.)

>Given a name and a password, "areValidCredentials", returns true if the name is longer than 3 characters, AND, the password is at least 8 characters long. Otherwise it returns false. (이름과 비밀번호가 주어졌을때, "areValidCredentials" 함수는 이름이 3글자이상 그리고 비밀번호가 8글자 이상이면 true를 반환합니다.)



### My_Soultion

* ex1

```js
function findMinLengthOfThreeWords(word1, word2, word3) {
  // your code here
  if (word1.length === (word2.length && word3.length)){
    return word1.length
  } else if (word1.length < (word2.length && word3.length)){
    return word1.length;
  } else if (word2.length < (word1.length && word3.length) ){
    return word2.length;
  } else if (word3.length < (word1.length && word2.length) ){
    return word3.length;
  }
}

findMinLengthOfThreeWords("111","2222","33333")

```
* ex2

```js

function findMinLengthOfThreeWords(word1, word2, word3) {
  var arr = [];
  arr.push(word1, word2, word3);
  arr.sort();
  return arr[0].length;
}
findMinLengthOfThreeWords("dwdsdsdsdsdsdsdwd","ddwwd","wdwdwdsdsdwdwwd")

```
* ex3

```js

function findMinLengthOfThreeWords(word1, word2, word3) {
  // your code here
  /* START SOLUTION */
  words = [word1, word2, word3];
  return words.sort()[0].length;
  /* END SOLUTION */
}

```

* ex4

```js

function findMinLengthOfThreeWords(word1, word2, word3) {
  return Math.min(word1.length, word2.length, word3.length)
}
```



### Question 

## computeAreaOfATriangle



>Given the base and height of a triangle, "computeAreaOfATriangle" returns its area. (삼각형의 밑변과 높이가 주어졌을때, "computeAreaOfATriangle" 함수는 삼각형의 넓이를 반환합니다.)


### My_Soultion

```js

function computeAreaOfATriangle(base, height) {
  // your code here
  let ret = base * height / 2;
  return ret;
}

```



### Question 

## computePerimeterOfACircle



>Write a function called "computePerimeterOfACircle". ("computePerimeterOfACircle" 함수를 작성하세요.)

>Given the radius of a circle, "computePerimeterOfACircle" returns its perimeter. (원의 반지름이 주어졌을때, "computePerimeterOfACircle" 함수는 원의 둘레를 반환하세요.




### My_Soultion

```

function computePerimeterOfACircle(radius) {
  // your code here\
  //원의 둘레 = 2 X 반지름 X 원주율 = 지름 X 원주율
  let ret = radius * 2 * Math.PI;
  return ret;
}

computePerimeterOfACircle(200);


```





### Question 

## computeAverageOfNumbers


>Write a function called "computeAverageOfNumbers". ("computeAverageOfNumbers" 함수를 작성하세요.)

>Given an array of numbers, "computeAverageOfNumbers" returns their average. (숫자이 배열이 주어졌을때, "computeAverageOfNumbers" 함수는 그들의 평균을 반환합니다.)



### My_Soultion

```
function computeAverageOfNumbers(nums) {
  // your code here
  let sum = 0;
  if ( nums.length === 0 ) {
    return 0;
  }
  for (let i = 0; i < nums.length; i = i + 1 ){
    sum = sum + nums[i]
  }
  return sum / nums.length; 
}
computeAverageOfNumbers[1,2,3,4,5,6];

```


### Question


## convertToString

> convertToString함수가 있습니다. 이 함수는 주어진 파라미터를 문자열의 형태로 변환합니다.



### My_Soultion

```js

function convertToString(anything) {
  // 여기에 코드를 작성하세요
  return anything.toString();
  // return "" + anything;
  // return String(anything);
}

convertToString('hello')




```

### Question


## convertToNumber

>convertToNumber함수가 있습니다. 이 함수는 주어진 파라미터를 숫자의 형태로 변환합니다.


>숫자로 변환할 수 없는 경우, NaN (Not a number) 이라는 결과가 나올것입니다. NaN은 숫자가 아님을 나타내는 특수한 값으로, 문자열이 아닙니다.


### My_Soution

```js

function convertToNumber(anything) {
  anything = Number(anything);
  
  if(!anything){
    return NaN;
  }else{
    return anything;
  }
}
convertToNumber('hello')



```



### Question



## isFalsy

>isFalsy함수가 있습니다. falsy 값은, 거짓으로 취급되는 값을 의미합니다. 이 함수는 주어진 파라미터가 falsy값인지 아닌지를 평가합니다.


### My_Soultion

```js

function isFalsy(anything) {
  // 여기에 코드를 작성하세요
   if ( typeof anything === 'undefined' ) {
      return true;
    } else if (!anything) {
      return true;
    } else if ( anything === null ) {
      return true;
    } else if ( anything === 0 ) {
      return true;
    } else if (anything === NaN ) {
      return true;
    } else if ( anything === '' ) {
      return true;
    } else {
      return false;
    }
} 

isFalsy('hello');

```

### Question


## getType


>getType함수가 있습니다. 이 함수는 주어진 파라미터의 타입을 리턴합니다.

>Note:
>배열을 넘길 경우, 'object'라고 나올 수 있습니다. 배열과 객체는 어떻게 구분할 수 있을까요?
배열과 객체를 구분하려면 Array.isArray 메소드를 사용하면 됩니다.


### My_Soultion

```

function getType(anything) {
  // 여기에 코드를 작성하세요
  // if 문을 사용해서 문자,숫자, boolean , arry, object 을 구분하는 것을 사용한다.
  if (Array.isArray(anything) === true ) {
    return 'array'
  } else 
  return typeof anything;
}


getType([1,2,3,4])

```




### Question

## getProperty

>파라미터로 객체와 키를 받는 getProperty함수가 있습니다. 이 함수는 주어진 객체와 키를 이용하여 속성값을 찾아 리턴합니다.
만일 주어진 키가 객체의 속성에 없다면, undefined를 리턴하면 됩니다.


### My_Soultion


```

function getProperty(obj, propertyName) {
  return obj[propertyName];
}
let person = {
  name: 'Steve',
  age: 16
};

getProperty(person,"name");
```

### Question

## addProperty


>파라미터로 객체와 키를 받는 addProperty 함수가 있습니다. 이 함수는 주어진 객체에, 키 이름으로 속성을 만들고 값을 true로 설정합니다.



### My_Soultion



```js
function addProperty(obj, propertyName) {
  // 여기에 코드를 작성하세요
  return obj[propertyName] = true;
  // return obj.propertyNmae = true; <<<is not working at all
  }

let john = {};

addProperty(john,'isprogrammer');




// Questoin


/*
obj[propertyName]를 이용했을 때는 테스트가 통과가 되고,
obj.propertyName를 이용했을 때는 통과가 되지 않습니다.
객체에 프로퍼티를 추가할 때 dot노테이션을 사용할 수 있는 걸로 알고있는데..이유가 뭘까요?


answer

으로 했을때는 바로 객체의 키로 접근하고 [ ] 으로 하면 변수로 접근합니다.
addProperty(steve, 'isProgrammer'); 이라는 함수 호출 구문이 있다고 가정하면
obj[propertyName] = true; 는 steve.isProgrammer = true; 이고
obj.propertyName = true; 는 steve.propertyName = true; 입니다. 완전히 다른값이 
나오죠?

*/






```







### Question

## addObjectProperty


>파라미터로 두 개의 객체와 키를 받는 addObjectProperty 함수가 있습니다. 이 함수는 주어진 첫번째 객체에, 키 이름으로 속성을 만드는데, 그 값은 두번째 객체로 설정합니다.
객체의 키 값은 또다른 객체가 될 수 있음을 기억하세요.


### My_Soultion


```js

function addObjectProperty(obj1, propertyName, obj2) {
  // 여기에 코드를 작성합니다.
  obj1[propertyName] = obj2; 
  return obj1;
}
let person1 = {
  name: 'Joe',
  role: 'Team Member'
};
let person2 = {
  name: 'Steve',
  role: 'CEO'
};


addObjectProperty(person1, 'manager', person2);


```

### Question

## removeProperty


>Write a function called "removeProperty". ("removeProperty" 함수를 작성하세요.)

>Given an object and a key, "removeProperty" removes the given key from the given object. (객체와 키가 주어졌을때, "removeProperty" 함수는 주어진 키에 해당하는 객체의 속성값을 제거해야 합니다.)



### My_Soultion



```js

function removeProperty(obj, propertyName) {
  // 여기에 코드를 작성하세요
  delete obj[propertyName];
}

```


### Question

## isPersonOldEnoughToVote

>Write a function called "isPersonOldEnoughToVote". ("isPersonOldEnoughToVote" 함수를 작성하세요.)

>Given a "person" object, that contains an "age" property, "isPersonOldEnoughToVote" returns whether the given person is old enough to vote. ("age" 속성을 가지고 있는 "person" 객체가 주어졌을때, "isPersonOldEnoughToVote" 함수는 그 사람이 미국에서 합법적으로 투표를 할 수 있는 나이인지를 반환해야 합니다.)


```js

function isPersonOldEnoughToVote(person) {
  // your code here
  // 1. if 사용해서 18세 이상일 경우 리턴 참
  // 2. 아닐경우 거짓
  if ( person.age >= 18 ) {
    return true;
  } else {
    return false;
  }
}

```


### Question

## removeNumbersLargerThan


>Write a function called "removeNumbersLargerThan". ("removeNumbersLargerThan" 함수를 작성하세요.)

>Given a number and an object, "removeNumbersLargerThan" removes any properties whose values are numbers greater than the given number. (숫자와 객체가 주어졌을때, "removeNumbersLargerThan" 함수는 주어진 객체에서 주어진 숫자보다 큰 모든 숫자 속성을 제거합니다.)

### My_Soultion

```js
let obj = {
  a: 8,
  b: 2,
  c: 'montana',
  d: 10,
  e: 4,
  f: 5
}

function removeNumbersLargerThan(num, obj) {
  // your code here
  for (let key in obj){
    if ( obj[key] > num ) {
    delete obj[key];
    }
  }
return obj;
}

removeNumbersLargerThan(3,obj)

```


### Question

## removeOddValues


>Write a function called "removeOddValues". ("removeOddValues" 함수를 작성하세요.)

>Given an object, "removeOddValues" removes any properties whose values are odd numbers. (객체가 주어졌을때, "removeOddValues" 함수는 주어진 객체의 속성값이 홀수인 속성을 모두 제거합니다.)


### My_Soultion


```js
let obj = {
  a: 2,
  b: 3,
  c: 4,
  d: 7
};
function removeOddValues(obj) {
  // your code here
  // 1. value 을 불러온다
  // 2. value 홀수 있지 짝수 인지 구분한다.
  // 3. value 가 홀수 일때 삭제한다.
  for ( let key in obj ) {
    if ( obj[key] % 2 === 1 ) {
      delete obj[key];
    }
  }
  return obj;
  }
  removeOddValues(obj)


```


### Question

## countNumberOfKeys

>Write a function called "countNumberOfKeys". ("countNumberOfKeus" 함수를 작성하세요.)

>Given an object, "countNumberOfKeys" returns how many properties the given object has. (객체가 주어졌을때, "countNumberOfKeys" 함수는 객체안에 있는 속성들의 갯수를 반환합니다.)


### My_Soultion

```js
function countNumberOfKeys(obj) {
  // 여기에 코드를 작성하세요
  // 1.숫자출력할 변수를 0으로 초기화한다.
  // 2.for 문을 이용해 객체를 나열한다.
  // 3. 나열한 객체를 변수안에 넣는다.
  let count = 0;
  for ( let key in obj ) {
    count = count + 1 ;
    }
    return count;
}

let obj = {
  a: 1,
  b: 2,
  c: 3,
  d: 4
};
countNumberOfKeys(obj)



// * Model Solutions

function countNumberOfKeys(obj) {
  return Object.keys(obj).length;
}

```




### Question

## printObject

>객체를 파라미터로 받는 printObject 함수는 객체 안에 정의된 키와 값 쌍을 조합한 문자열을 리턴합니다. 문자열은 한 줄에 하나의 키/값 쌍을 콜론(:) 및 공백문자와 함께 표시하며, 또다른 키/값 쌍 사이에는 줄바꿈 문자가 포함되어 있습니다.



### My_Soultion

```

let obj = { name: 'Steve', age: 13, sex: 'Male' };

function printObject(obj) {
  let ret = ""
  for ( let key in obj ) {
    ret = ret + key +": " + obj[key]+ "\n";
  }
  return ret;
};
printObject(obj);

```


### Question

## extends


> Write a function called "extend". ("extend" 함수를 작성하세요.)

>Given two objects, "extend" adds properties from the 2nd object to the 1st object. (객체 두개가 주어졌을때, "extend" 함수는 두번째 객체의 속성을 첫번째 객체에 추가해야 합니다.)

>Add any keys that are not in the 1st object. (첫번째 객체에 없는 모든 키를 추가하세요.)

>If the 1st object already has a given key, ignore it (do not overwrite the property value). (만약 첫번째 객체에 이미 있는 키라면, 값을 덮어쓰지 말고 무시하세요.)

>Do not modify the 2nd object at all. (두번째 객체는 수정하지 마세요.)


### My_Soultion

```js

et obj1 = {
  a: 1,
  b: 2
};
let obj2 = {
  b: 4,
  c: 3
};

function extend(obj1, obj2) {

  // 여기에 코드를 작성하세요
  // 1. obj2 의 key들을 반복합니다.
  // 2. obj2 안에 있는 key 가  obj1 key 안에에 포함 되어있는지 if 문을 써서 확인한다.
  // 4. 포함되어있지 않으면 ob1에 추가한다.
  
  for ( let key in obj2 ) {
      if (!( key in obj1 )) {
        obj1[key] = obj2[key];
      }
    }
  }
  

```

### Question

## countAllCharacters


> Write a function called "countAllCharacters". ("countAllCharacters" 함수를 작성하세요")

>Given a string, "countAllCharacters" returns an object where each key is a character in the given string. The value of each key should be how many times each character appeared in the given string. (문자열이 주어졌을때, "countAllCharacters" 함수는 주어진 문자열의 각각의 문자를 키로 가지는 객체를 반환합니다. 각 키의 값은 해당 문자가 주어진 문자열에서 몇번 나오는지를 나타냅니다.)



```js

function countAllCharacters(str) {
  let obj = {};
  for (let i = 0; i < str.length; i++) { // input으로 받은 문자열에서 하나의 character씩 loop를 돕니다.
    
    if (obj[str[i]] === undefined) { 
// 그런데 obj란 객체에 character가 들어 있지 않다면 새로운 문자열이기 때문에 객체에 char를 추가하고 0으로 만들어 줍니다.
      obj[str[i]] = 0;
    }
    obj[str[i]]++;  // 그 이후 이 곳에서 char key의 value 값을 1 더해줍니다.
  }
  return obj;
}

let output = countAllCharacters('banana');
console.log(output); // --> {b: 1, a: 3, n: 2}


```


### Question

## removeStringValues


> Write a function called "removeStringValues". ("removeStringValues" 함수를 작성하세요.)

>Given an object, "removeStringValues" removes any properties on the given object whose values are strings. (객체가 주어졌을때, "removeStringValues" 함수는 속성값이 문자열인 모든 속성을 제거합니다.)
 

### My_Soultion

```js

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


### Question

## removeNumberValues

> Write a function called "removeNumberValues". ("removeNumberValues" 함수를 작성하세요.)

>Given an object, "removeNumberValues" removes any properties whose values are numbers. (객체가 주어졌을때, "removeNumberValues" 함수는 속성값이 숫자인 모든 속성을 제거합니다.)


## My_Soultion


```js

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



### Question

## removeArrayValues

> Write a function called "removeArrayValues". ("removeArrayValues" 함수를 작성하세요.)

>Given an object, "removeArrayValues" removes any properties whose values are arrays. (객체가 주어졌을때, "removeArrayValues" 함수는 속성값이 배열인 모든 속성을 제거합니다.)



### My_Soultion

```js

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




### Question


## getFirstElement


> Write a function called "getFirstElement". ("getFirstElement" 함수를 작성하세요.)

>Given an array, "getFirstElement" returns the first element of the given array. (배열이 주어졌을때, "getFirstElement" 함수는 주어진 배열의 첫번째 요소를 반환해야 합니다.)


### My_Soultion

```js

function getFirstElement(array) {
  // 여기에 코드를 작성하세요.
  // 배열을 0번째 숫자를 불러온다.
  if ( array.length === 0 ) {
    return undefined;
  } else
  return array[0];
}

```

### Question

## getLastElement


> Write a function called "getLastElement". ("getLastElement" 함수를 작성하세요.)

>Given an array, "getLastElement" returns the last element of the given array. (배열이 주어졌을때, "getLastElemeent" 함수는 주어진 배열의 마지막 요소를 반환해야 합니다.)


### My_Soultion


```js

function getLastElement(array) {
  // 여기에 코드를 작성하세요
  // 만약 배열의 길이가 0 이라면 undefinded 출력
  // 아니라면 return 마지막 배열숫자 출력
  if ( array.length === 0 ) {
    return undefined;
  } else {
    let lastNum = array[array.length -1]
    return lastNum;
  }
}

```


### Question

## getNthElement

> Write a function called "getNthElement". ("getNthElement" 함수를 작성하세요.)

> Given an array and an integer, "getNthElement" returns the element at the given integer, within the given array. (배열과 숫자가 주어졌을때, "getNthElement" 함수는 주어진 배열에서 n번 인덱스의 요소를 반환해야 합니다.)


### My_Soultion



```js

function getNthElement(array, n) {
  // 여기에 코드를 작성하세요
  // 만약 배열에 길이가 0보다 크면 코드 진행실행 아니면 undefinded
  // 배열에 n번째 있는 숫자를 변수에 저장
  // 배열안에 있는 n 번째의 숫자 출력
  if ( array.length > 0 ) {
    let ret = array[n];
    return ret;
  } else {
    return undefined;
  }
}



```

### Question

## addToFront

> Write a function called "addToFront". ("addToFront" 함수를 작성하세요.)

>Given an array and an element, "addToFront" adds the given element to the front of the given array, and returns the given array. (배열과 요소가 주어졌을때, "addToFront" 함수는 주어진 요소를 배열의 맨앞에 추가하고 주어진 배열을 반환해야 합니다.)


### My_Soultion


```js


function addToFront(arr, element) {
  arr.unshift(element);
  return arr;
}


```



### Question

## addToBack

> Write a function called "addToBack". ("addToBack" 함수를 작성하세요.)

>Given an array and an element, "addToBack" returns the given array with the given element added to the end. (배열과 요소가 주어졌을때, "addToBack" 함수는 주어진 요소를 배열의 맨뒤에 추가하고 주어진 배열을 반환해야 합니다.)


### My_Soultion


```js

function addToBack(arr, element) {
  // 여기에 코드를 작성하세요.
  // push 사용해 element 값을 뒤에 추가한다.
  arr.push(element);
  return arr;
}


```


### Question

## joinArrays

> Write a function called "joinArrays". ("joinArrays" 함수를 작성하세요.)

>Given two arrays, "joinArrays" returns an array with the elements of "arr1" in order, followed by the elementsin "arr2". (두 배열이 주어졌을때, "joinArrays" 함수는 첫번째 배열(arr1)과 두번째 배열(arr2) 순서로 합쳐진 배열을 반환해야 합니다.)



### My_soultion

```js

function joinArrays(arr1, arr2) {
  // your code here
  // 변수를 만들어 배열1에 배열2를 집어넣는다.
  // 출력한다.
  let arrRet = arr1.concat(arr2);
  return arrRet
  
}


```


### Question


## getElementsAfter

> Write a function called "getElementsAfter". ("getElementsAfter" 함수를 작성하세요.)

>Given an array and an index, "getElementsAfter" returns a new array with all the elements after (but not including) the given index. (배열과 인덱스가 주어졌을때, "getElementsAfter" 함수는 주어진 배열의 인덱스 이후 요소들을 (자신은 포함하지 않고) 새로운 배열로 반환해야 합니다.)


### My_Soultion



```js

function getElementsAfter(array, n) {
  // your code here
  // 새로운 빈배열을 만든다.
  // 초기값을 n+1을 한 for 문을 이용해 배열인덱스를 불러온다.
  // 불러온 값을 새로운 배열에 push를 사용해 담는다.
  // 출력한다.
  let newArr = [];
  for (let i = n + 1;  i < array.length; i = i + 1 ) {
    newArr.push(array[i]);
  }
  return newArr;
}
getElementsAfter(['a', 'b', 'c', 'd', 'e'], 1);


```

### Question

## getElementsUpTo

> Write a function called "getElementsUpTo". ("getElementsUpTo" 함수를 작성하세요.)

>Given an array and a index, "getElementsUpTo", returns an array with all the elements up until, but not including, the element at the given index. (배열과 인덱스가 주어졌을때, "getElementsUpTo" 함수는 주어진 배열의 인덱스 이전 요소들을 (자신은 포함하지 않고) 새로운 배열로 반환해야 합니다.)

### My_Soultion


```js

function getElementsUpTo(array, n) {
  let newArr = array.slice(0,n);
  return newArr
}
getElementsUpTo(['a', 'b', 'c', 'd', 'e'], 3);


```

### Question

## getAllElementsButFirst

>Write a function called "getAllElementsButFirst". ("getAllElementsButFirst" 함수를 작성하세요.)

>Given an array, "getAllElementsButFirst" returns an array with all the elements but the first. (배열이 주어졌을때, "getAllElementsButFirst" 함수는 첫번째 요소를 제외한 배열을 반환해야 합니다.)

### My_Soultion

```js

function getAllElementsButFirst(array) {
  // your code here
  // shift 를 이용해서 앞에 있는 요소를 뺀다.
  // 그리고 기존에 배열을 출력한다. 
  array.shift();
  return array;
}

getAllElementsButFirst([1,2,3,4])


```

### model solution


```js


function getAllElementsButFirst(array) {
  return array.slice(1, array.length);
}
```


### Question

## getAllElementsButLast

>Write a function called "getAllElementsButLast". ("getAllElementsButLast" 함수를 작성하세요.)

>Given an array, "getAllElementsButLast" returns an array with all the elements but the last. (배열이 주어졌을때, "getAllElementsButLast" 함수는 마지막 요소를 제외한 배열을 반환해야 합니다.)



### My_Soultion

```js

function getAllElementsButLast(array) {
  // your code here
  // slice 를 이용해서 마지막 숫자를 삭제한다.
  // 출력한다.
  array.pop()
  return array
}



```



### Question


## removeFromFront

>Write a function called "removeFromFront". ("removeFromFront" 함수를 작성하세요.)

>Given an array, "removeFromFront" returns the given array with its first element removed. (배열이 주어졌을때, "removeFromFront" 함수는 첫번째 요소를 삭제한 주어진 배열을 반환해야 합니다.)


### My_Soultion

```js

function removeFromFront(arr) {
  // your code here
  // 메소드 사용해서 첫번째요소 자르기 
  arr.shift();
  return arr;
}

```
### Question

## removeFromBack

>Write a function called "removeFromBack". ("removeFromBack" 함수를 작성하세요.)

>Given an array, "removeFromBack" returns the given array with its last element removed. (배열이 주어졌을때, "removeFromBack" 함수는 마지막 요소를 삭제한 주어진 배열을 반환해야 합니다.)


### My_Soultion

```js

function removeFromBack(arr) {
  // your code here
  //배열 메소드 이용해서 뒤에 있는거 자르기
  arr.pop();
  return arr;
}


```

### Question

## removeFromBackOfNew

>Write a function called "removeFromBackOfNew". ("removeFromBackOfNew" 함수를 작성하세요.)

>Given an array, "removeFromBackOfNew" returns a new array containing all but the last element of the given array. (배열이 주어졌을때, "removeFromBackOfNew" 함수는 마지막 요소를 제외한 모든 요소를 가지고 있는 새로운 배열을 반환해야 합니다.)



### My_Soultion

```js

function removeFromBackOfNew(arr) {
  // your code here
  // 빈 배열을 만든다. 
  // 배열을 가져오는데 length를 이용해 마지막숫자를 뺀수를 가져온다
  // 가져온 숫자를 새로운 배열에 넣는다. 
  // arrNew 를 출력한다. 
  let arrNew = [];
  for (let i = 0; i < arr.length -1; i = i + 1 ) {
    arrNew.push(arr[i]);
  }
  return arrNew
  }


```


### model solution


```js
function removeFromBackOfNew(arr) {
  // your code here
  // 마지막 숫자를 뺀 배열값을 변수에 담는다.
  // 담은 변수를 출력한다.
  let sliced = arr.slice(0,arr.length-1)
  return sliced; 
  
  }

```

### Question

## addToBackOfNew


>Write a function called "addToBackNew". ("addToBackNew" 함수를 작성하세요.)

>Given an array and an element, "addToBackNew" returns a clone of the given array, with the given element added to the end. (배열과 요소가 주어졌을때, "addToBackNew" 함수는 주어진 배열의 복사본 끝에 주어진 요소가 추가된 배열을 반환합니다.)


### My_Soultion

```js


function addToBackOfNew(arr, element) {
  // your code here
  arr = arr.concat(element);
  return arr;
  }
  
```


### model soultion

```js

function addToBackOfNew(arr, element) {
  const newArr = arr.slice();
  newArr.push(element);
  return newArr;
}

```

### Question

## joinArrayOfArrays

>Write a function called "joinArrayOfArrays". ("joinArrayOfArrays" 함수를 작성하세요.)

>Given an array of arrays, "joinArrayOfArrays" returns a single array containing the elements of the nested arrays. (배열들의 배열이 주어졌을때, "joinArrayOfArrays" 함수는 배열들의 요소를 모두 담고 있는 단일 배열을 반환합니다.)


> it is used by reduce and concat

### My_Soultion

```js

function joinArrayOfArrays(arr) {

  output = arr.reduce(function(acc,cur) {
    return acc.concat(cur); 
    })
    return output;
  }


```

### Question

## getAllLetters

> Write a function called "getAllLetters". ("getAllLetters" 함수를 작성하세요.)

>Given a word, "getAllLetters" returns an array containing every character in the word. (단어가 주어졌을때, "getAllLetters" 함수는 주어진 단어에 포함된 모든 문자를 담고 있는 배열을 반환합니다.)

### My_Soultion

```js
function getAllLetters(str) {
  // your code here
  // 만약 빈문자 열이라면 빈 배열을 리턴한다.
  // 만약 빈배열이 아니라면 문자를 split method 사용한다.
  if ( str === "" ) {
    return str = [];
  } else {
    return str.split("")
  }
}

```

### Question
 
## getAllWords
 
> Write a function called "getAllWords". ("getAllWords" 함수를 작성하세요.)

>Given a sentence, "getAllWords" returns an array containing every word in the sentence. (문장이 주어졌을때, "getAllWords" 함수는 주어진 문장에 포함된 모든 단어를 담고 있는 배열을 반환합니다.)
 
 
 
### My_Soultion
 
```js
 
 
 function getAllWords(str) {
  if (str === '') {
    return [];
  } else {
    return str.split(' ');
  }
}

```



### Question

## removeElement


> Write a function called "removeElement". ("removeElement" 함수를 작성하세요.)

>Given an array of elements, and a "discarder" parameter, "removeElement" returns an array containing the items in the given array that do not match the "discarder" parameter. (배열과 "discarder" 매개변수가 주어졌을때, "removeElement" 함수는 주어진 배열에서 "discarder" 매개변수와 일치하지 않는 모든 요소를 포함하는 배열을 반환합니다.)


### My_Soultion

```js


unction removeElement(array, discarder) {
  // your code here
   /* 
  1. 빈배열이면 빈배열을 반환
  2. 새로운 빈배열을 만든다. newArr
  3. 모든 element를 조사한다.
  4. element가 discarder와 다르다면 newArr에 push로 넣는다.
  5. 위에경우가 아니라면 newArr을 반환
   */

  if ( array === [] ) {
    return [];
  }
  let newArr = [];
  for (let i = 0; i < array.length; i = i + 1 ) {
    if ( discarder !== array[i] ) {
      newArr.push(array[i])
    } 
  }
  return newArr;
}
```


### Question

## keep

> Write a function called "keep". ("keep" 함수를 작성하세요.)

>Given an array and a keeper element, "keep" returns an array containing the items that match the given keeper element. (배열과 "keeper" 매개변수가 주어졌을때, "keep" 함수는 "keeper" 매개변수와 일치하는 모든 요소

### My_Soultion

```js
function keep(array, keeper) {
  // your code here
  // 만약 배열이 비워있다면 빈배열 리턴
  // 새로운 빈배열을 만든다.
  // for 문을 사용해 배열을 조사
  // 만약 keeper라는 매개변수가 있는지 조사
  // 만약 있다면 push를 사용해 새로운 배열에 투입
  // 새로운 배열 출력
  if ( array === []) {
    return [];
  }
  let newArr = [];
  for ( let i = 0; i < array.length; i = i + 1 ) {
    if ( array[i] === keeper ) {
      newArr.push(array[i]);
    }
  }
  return newArr;
}

```


### Question


## findSmallestElement


> Write a function called "findSmallestElement". ("findSmallestElement" 함수를 작성하세요.)

>Given an array of numbers, "findSmallestElement" returns the smallest number within the given array. (숫자의 배열이 주어졌을때, "findSmallestElement" 함수는 주어진 배열에서 가장 작은 수를 반환합니다.)



### My_solution



```js
// It is used by sort();



function findSmallestElement(arr) {

  만약 arr 비워있다면 빈배열 리턴
  메소드 slice()이용해 복사 
  복사한 배열을 sort()를 이용해 작은숫자가 앞으로 올수 있도록 정렬
  0번째 있는 요소 출력


  if ( arr.length === 0 ){ 
    return 0;
  }
  let newArr = arr.slice();
  let sortArr = function(a,b) {
    return a-b;
  }
  newArr.sort(sortArr); 
  return newArr[0];
}

```



```js

// It is used by reudce and if 

function findSmallestElement(arr) {
  if (arr.length < 1) {  // satisfies Notes requirement
    return 0;
  }
  var newNum = arr[0];  // create number placeholder (start with first number of array)
  for (let i in arr) {  // iterate thru array
    if (arr[i] < newNum) {  // if element is larger than current placeholder number
      newNum = arr[i];  // make that element the new placeholder number
    }
  }
  return newNum;
}

```


```js

// It is used by reudce and if ????? 


function findSmallestElement(arr) {
  
  if(arr.length === 0) {
    return 0;
  } else {
    var smallestNum = arr.reduce(function(a,b) {
      return a < b ? a: b;
    });
    return smallestNum;
  }
}
```



```js

// it is used by reudce and Math method

function findSmallestElement(arr) {

  if ( arr.length === 0 ) {
    return 0;
  }

  output = arr.reduce(function(acc,cur){
    return Math.min(acc,cur);

  })  
  return output;
}
```



```js

// it is used by reudce and Math method

function findSmallestElement(arr) {

  if ( arr.length === 0 ) {
    return 0;
  }

  return Math.min(...arr);
}
```


### Question

## computeSumOfAllElements

> Write a function called "computeSumOfAllElements". ("computeSumOfAllElements" 함수를 작성하세요.)

>Given an array of numbers, "computeSumOfAllElements" returns the sum of all the elements in the given array. (숫자의 배열이 주어졌을때, "computeSumOfAllElements" 함수는 주어진 배열의 모든 요소의 합을 반환합니다.)


### My_Solution



```js
function computeSumOfAllElements(arr) {
  
  // your code here.
  // 빈 배열을 만든다.
  // count 변수 초기화 한해서 만든다.
  // arr 안에 값들을 조사한다.
  // count 변수안에 조사한 값들을 더해서 넣는다.
  let sum = 0;
  for ( let i = 0; i < arr.length; i = i + 1 ) {
    sum = sum + arr[i];
  }
  return sum
}

```


```js
// it used by reduce 


function computeSumOfAllElements(arr) {
  if ( arr.length === 0 ) {
    return 0;
  }
  return arr.reduce(function(acc,val){
    return acc + val;
  })
  
}

```



### Question
## computeProductOfAllElements


>Write a function called "computeProductOfAllElements". ("computeProductOfAllElements" 함수를 작성하세요.)

>Given an array of numbers, "computeProductOfAllElements" returns the products of all the elements in the given array. (숫자의 배열이 주어졌을때, "computeProductOfAllElements" 함수는 주어진 배열의 모든 요소의 곱을 반환합니다.)






### My_Solution


```js




function computeProductOfAllElements(arr) {
  
  // 먄약 배열이 비워있다면 0 리턴;
  // 0으로 된 마지막에 출력할 변수 생성;
  // for 문을 사용해 배열안에 있는 요소 조사
  // 생성한 변수 안에 조사한 요소들을 곱셈하여 넣는다.
  // 변수 출려
  
  if ( arr.length === 0 ) {
    return 0;
  }
  let ret = 1;
  for ( let i = 0; i < arr.length; i = i + 1 ) {
    ret = ret * arr[i];
  } 
  return ret;
}
```


```js


// It is used by redcue method
function computeProductOfAllElements(arr) {
    
    
    if ( arr.length === 0 ) {
    return 0;
  }
  return arr.reduce(function(acc,cur) {
    return acc * cur;
  })

}


```

### Question

## getLengthOfLongestElement


>Write a function called "getLengthOfLongestElement". ("getLengthOfLongestElement" 함수를 작성하세요.)

>Given an array, "getLengthOfLongestElement" returns the length of the longest string in the given array. (배열이 주어졌을때, "getLengthOfLongestElement" 함수는 주어진 배열에서 가장 긴 문자열의 길이를 반환합니다.)


### My_Solution


```js

// it is used by sort()


function getLengthOfLongestElement(arr) {

  if ( arr.length === 0 ){
    return 0;
  } 
  sortArr = function (a, b) { 
    return b.length - a.length;
    }
    let ret = arr.sort(sortArr)[0]
    return ret.length;
}

```


```js

// It is used by for loop and if


function getLengthOfLongestElement(arr) {
  
  if ( arr.length === 0 ) {
    return 0;
  } 

  let lgth = 0; // => 3  =>5
  let longest;  // =>"one" => "three" 
  
  for ( let i = 0; i < arr.length; i = i + 1) {
    if(arr[i].length > lgth) {
      // 첫번째 요소는 "one" 길이는 3 > 0
      // 두번째 요소는 "two" 길이는 3 > 3 : 실행이 안됨
      // 세번째 요소는 "three" 길이는 5 > 3 : 실행되면서 최종적으로 longest변수에 "three"가 담긴다. 
        lgth = arr[i].length;
        longest = arr[i].length;
    }      
  } 
  return longest;
}


```



```js



/*


it is used by reduce method

comment

return a.length or return b.length 하면 안되는 이유. length를 리턴에 넣으면 다음  a 와 b.length의 길이를 비교하기 때문에 안되는거더라구요. 그래서 함수 밖에 붙여주면 숫자로 반환되는 거구요.




*/

function getLengthOfLongestElement(arr) {

 
 return arr.reduce(function(a,b) {
      if (a.length >= b.length) {
        return a;
      } else {
        return b;
      }
  }).length
}
```

### Question


## filterOddLengthWords


> Write a function called "filterOddLengthWords". ("filterOddLengthWords" 함수를 작성하세요.)

>Given an array of string, "filterOddLengthWords" returns an array containing only the elements of the given array whose lengths are odd numbers. (문자열의 배열이 주어졌을때, "filterOddLengthWords" 함수는 주어진 배열의 요소 중 문자열의 길이가 홀수인 문자열만을 요소로 가지는 배열을 반환합니다.)


### My_Soultion


```js



unction filterOddLengthWords(words) {

  // it passed test
  // it's good to practice useing filter 

  // your code here
  // output 빈 배열을 만든다.
  // for 문을 이용해 배열안에 있는 요소를 조사한다.
  // 만약 배열안에 있는 각각의 요소가 홀수라면 ture
  // ture 인 값을 output 배열에 넣는다.
  // 넣은 값을 출력한다.
  
  let output = [];
  for  ( let i = 0; i < words.length; i = i + 1 ) {
    if ( words[i].length % 2 !== 0 ) { 
      output.push(words[i]);
    }
  }
  return output;
}


```
### modle_Soultion


```js



// input: an array of strings
// output: return an array containing only the elements of the given array whose lengths are odd numbers

function filterOddLengthWords(arr) {  // HoF
  return arr.filter(function(i) {  // filters each even length elements to its own array
    return i.length % 2 !== 0;
  });
}


```






### Question

## getElementOfArrayProperty

>Write a function called "getElementOfArrayProperty". ("getElementOfArrayProperty" 함수를 작성하세요.)

>Given an object, a key, and a numerical index, "getElementOfArrayProperty" returns the value of the element at the given index of the array located within the given object at the given key. (객체와 키, 그리고 숫자로된 인덱스값이 주어졌을때, "getElementOfArrayProperty" 함수는 주어진 키에 위치한 배열의 인덱스에 해당하는 값을 반환합니다.)


### My_Soultion 

```js

function getElementOfArrayProperty(obj, key, index) {
  // your code here
 
   if (!Array.isArray(obj[key])){
    return undefined;
  } 
  return obj[key][index]; 
} 
let obj = {
  key: ['Jamil', 'Albrey']
};

getElementOfArrayProperty(obj,'key',0);


```

### Question


## select


>Write a function called "select". ("select" 함수를 작성하세요.)

>Given an array and an object, "select" returns a new object whose properties are those in the given object AND whose keys are present in the given array. (배열과 객체가 주어졌을때, "select" 함수는 주어진 객체의 키값 중 주어진 배열에 포함된 키값만을 속성으로 가지는 새로운 배열을 반환합니다.)

### My_Soultion

```js

function select(arr, obj) {
  // your code here
  let newObj = {};
  for (let key in obj ) {
    for (let i = 0; i < arr.length; i = i + 1 ) {
      if (key === arr[i] ) {
       newObj[key] = obj[key]
      }

    }

  } 
  return newObj;
}


```

### Question

## getNthElementOfProperty

> Write a function called "getNthElementOfProperty". ("getNthElementOfProperty" 함수를 작성하세요.)

>Given an object and a key, "getNthElementOfProperty" returns the nth element of an array located at the given key. (객체와 키가 주어졌을때, "getNthElementOfProperty" 함수는 주어진 키에 위차한 배열의 n번째 요소를 반환합니다.)


### My_Soultion

```js

function getNthElementOfProperty(obj, key, n) {
  // your code here
  // 만약 주어진 키에 위차하는 속성값이 배열이 아니라면 undefinded 
  // 만약 그게 아니라면 주어진 키값의 인덱스 번호 리턴
  if ( !Array.isArray(obj[key])) {
    return undefined;
  } else {
    return obj[key][n];
  }
}

```


### Question

## getElementsLessThan100AtProperty


> Write a function called "getElementsLessThan100AtProperty". ("getElementsLessThan100AtProperty" 함수를 작성하세요.)

>Given an object and a key, "getElementsLessThan100AtProperty" returns an array containing all the elements of the array located at the given key that are less than 100. (객체와 키값이 주어졌을때, "getElementsLessThan100AtProperty" 함수는 주어진 키에 위치하는 배열에서 100 보다 작은 값으로만 이루어진 배열을 반환합니다.)


### MY_Soultion


```js

function getElementsLessThan100AtProperty(obj, key) {
  for (let prop in obj) {
    if (! Array.isArray(obj[key])){
    return [];
    } else if ( !prop in obj ) {
      return [];
    }
  }
    let retArr = [];
    for ( let prop2 in obj ) {
    for ( let i = 0; i < obj[prop2].length; i = i + 1) {
      if ( obj[prop2][i] < 100 ) {

        retArr.push(obj[prop2][i]);
      }

  }
    }
    return retArr;
  }



```



### My_Re_Soultion

```js


function getElementsLessThan100AtProperty(obj, key) {

  if ( ! Array.isArray(obj[key])) {
    return [];
  } else {
  return obj[key].filter(cur => cur < 100);

  }
}

```

### Question

## getLastElementOfProperty


> Write a function called "getLastElementOfProperty". ("getLastElementOfProperty" 함수를 작성하세요.)

>Given an object and a key, "getLastElementOfProperty" returns the last element of an array located at the given key. (객체와 키가 주어졌을때, "getLastElementOfProperty" 함수는 주어진 키에 위치한 배열의 마지막 요소를 반환합니다.)


### My_Solution

```js
function getLastElementOfProperty(obj, key) {
  
  // 1. 만약 key의 값에 prop 배열이 아니라면 undefined 출력
  // 2. 배열에 있는 마지막 요소 pop 메소드 이용해서 빼서 변수안에 넣기
  // 3. 변수 리턴 

  if (!Array.isArray(obj[key])) {
    return undefined;
    } else {
      let lastNum = obj[key].pop()
      return lastNum
  } 
}

```

### modle_Solution

```js

// 1.마지막 배열에 요소 가져오기 위해 length - 1 이라는 방법을 썻다.

function getLastElementOfProperty(obj, key) {
  let prop = obj[key];
  if (!Array.isArray(prop)) {
    return undefined
  }

  return prop[prop.length - 1]
}

```

### Question

## getSquaredElementsAtProperty


> Write a function called "getSquaredElementsAtProperty". ("getSquaredElementsAtProperty" 함수를 작성하세요.)

>Given an object and a key, "getSquaredElementsAtProperty" returns an array containing all the squared elements of the array located at the given key. (객체와 키가 주어졌을때, "getSquaredElementsAtProperty" 함수는 주어진 키에 위치하는 배열의 요소들의 제곱을 요소로 가지는 배열을 반환합니다.)


### My_Soultion

```js


function getSquaredElementsAtProperty(obj, key) {


  
  // 1. 만약 주어진 key 의 값이 배열이 아니라면 빈배열 출력
  // 2. 만약 주어진 key 의 값이 길이가 0 같이 않다면 빈배열
  // 3. 마지막에 출력할 새로운 변수 생성
  // 4. 곱셈할 값을 넣기 위한 새로운 변수 또 생성 
  // 5. 배열안에 있는 요소들 곱하기
  // 6. 곱한값을 arr 이라는배열에 넣는다.    


 if (!Array.isArray(obj[key])) {
    return [];
 } else if (obj[key].length === 0 ){
   return [];
 }
  let arr = [];
  let conut;
  for ( let i = 0; i < obj[key].length; i = i + 1 ) {
    conut = obj[key][i]*obj[key][i];
    arr.push(conut);
  }
 return arr;
}

```


### other Soultion

```js



function getSquaredElementsAtProperty(obj, key) {
  var arr = [];
  if(Array.isArray(obj[key])){
    for(var i in obj[key]){
      var squared =obj[key][i]*obj[key][i];
      arr.push(squared);
    }
  }
  return arr;
}

var obj = {
  key: [2, 1, 5]
};
var output = getSquaredElementsAtProperty(obj, 'key');
console.log(output);


```
### Question

## getAllButLastElementOfProperty



> Write a function called "getAllButLastElementOfProperty". ("getAllButLastElementOfProperty" 함수를 작성하세요.)

>Given an object and a key, "getAllButLastElementOfProperty" returns an array containing all but the last element of the array located at the given key. (객체와 키가 주어졌을때, "getAllButLastElementOfProperty" 함수는 주어진 키에 위치하는 배열의 마지막 요소를 제외한 배열을 반환합니다.)


### My_Solution 


```js

function getAllButLastElementOfProperty(obj, key) {
  
  
  // 1.마지막에 출력할 arr 빈배열 생성
  // 2.만약 key의 값의 prop 가 배열이 아니라면 빈배열 리턴
  // 3.만약 key의 값의 prop 의 길이가 0 과 같이 않다면 빈배열 리턴
  // 4.선언된 arr 안에 obj[key] 값을 넣는다.
  // 5.pop()메소드 사용해 마지막 요소 제거
  // 6.arr 리턴


  let arr = [];
  if (!Array.isArray(obj[key])) {
    return [];
  } else if ( obj[key].length === 0 ) {
    return [];
  } else {
    arr = obj[key];
    arr.pop()
  }
  return arr;
}

```

### Question

## getProductOfAllElementsAtProperty


>Write a function called "getProductOfAllElementsAtProperty". ("getProductOfAllElementsAtProperty" 함수를 작성하세요.)

>Given an object and a key, "getProductOfAllElementsAtProperty" returns the product of all the elements in the array located at the given key. (객체와 키가 주어졌을때, "getProductOfAllElementsAtProperty" 함수는 주어진 키에 위치한 배열의 요소의 곱을 반환합니다.)

### My_soultion


```js

// It is used by for 


function getProductOfAllElementsAtProperty(obj, key) {

  // 1. arr 변수 만들어 key값의 prop 값을 넣는다
  // 2. 곱한값을 담을 sum 이라는 변수 생성 
  // 3. 만약 key의 prop 배열이 아니라면 0을 리턴
  // 4. 만약 key의 prop 길이가 0 과 같다면  0;
  // 5. for 문사용해 arr안에 있는 숫자를 곱한값을 sum 안에 저장
  // 6. sum 출력 
  
  
  let arr = obj[key];
  let sum = 1;
  if ( !Array.isArray(obj[key])) {
    return 0;
  } else if ( obj[key].length === 0 ) {
    return 0;
  }
  for ( let n = 0 ; n < arr.length ; n = n + 1 ) {
    sum = sum * arr[n];
  }
  return sum;
}


```



```js

// It is used by reduce

function getProductOfAllElementsAtProperty(obj, key) {
  if (! Array.isArray(obj[key] )) {
    return 0; 
  } else if ( obj[key].length === 0 ){
    return 0;
  }
  let arr = obj[key];
  return arr.reduce(function(acc,cur) {
    return acc * cur;
  }) 
}

```








