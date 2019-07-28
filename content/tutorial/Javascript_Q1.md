---
title: JS Basic 1
date: 2019-6
draft: true
menu:
  tutorial:
    parent: "Javascript"
    weight: 10
toc: true
type: docs
---


---
## Conditional : isOldEnoughToDrink
---

>어떤 숫자, 이 경우에는 연령이 하나 주어졌을 때, isOldEnoughToDrink 함수는 주어진 연령의 사람이 미국에서 합법적으로 술을 마실 수 있는지의 여부를 반환해야 합니다.


```
function isOldEnoughToDrink(age) {
  // 여기에 코드를 작성하세요
  if (age < 21 ) {
    return false;
  } else {
    return true;
  }
}


```

---
## Conditional : checkAge 
---


>이름과 나이를 파라미터로 받는 checkAge라는 함수는 두개 중 하나의 메시지를 리턴합니다.

>만일 21살보다 적으면, Go home, {전달받은_이름}! 만일 21살이거나 더 나이가 많으면, Welcome, {전달받은_이름}! 을 리턴하세요. 쉼표와 공백, 느낌표까지 정확히 리턴해야 합니다.


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




---
## Conditional : equalsTen
---

>Write a function called "equalsTen". ("equalsTen" 함수를 작성하세요.)

>Given a number, "equalsTen" returns whether or not the given number is 10. ("숫자가 주어졌을때, "equalsTen" 함수는 숫자가 10과 같은지 반환합니다.)



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




---
## Conditional : isGreaterThan
---


>Write a function called "isGreaterThan". ("isGreaterThan" 함수를 작성하세요.)

>Given 2 numbers, "isGreaterThan" returns whether num2 is greater than num1. (두 숫자가 주어졌을때, "isGreaterThan" 함수는 두번째 숫자(num2)가 첫번째 숫자(num1)보다 큰지 반환해야 합니다.)


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



---
## Conditional : isEven
---


>Write a function called "isEven". ("isEven" 함수를 작성하세요.)

>Given a number, "isEven" returns whether it is even. ("숫자가 주어졌을때, "isEven" 함수는 주어진 숫자가 짝수인지 반환합니다.)


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



---
## Conditional : isEvenAndGreaterThanTen
---

>Write a function called "isEvenAndGreaterThanTen". ("isEvenAndGreaterThanTen" 함수를 작성하세요.)

>Given a number, "isEvenAndGreaterThanTen" returns whether it is both even and greater than 10. (숫자가 주어졌을때, "isEvenAndGreaterThanTen" 함수는 주어진 숫자가 10보다 크고 짝수인지 반환해야 합니다.)




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


---
## Conditional : convertScoreToGrade
---


>Write a function called "convertScoreToGrade". ("convertScoreToGrade" 함수를 작성하세요.)

>Given a score, "convertScoreToGrade" returns a string representing the letter grade corresponding to the given score. (점수가 주어졌을때, "convertScoreToGrade" 함수는 주어진 점수와 대응하는 등급을 문자열로 반환합니다.)

```
Notes:

(100 - 90) --> 'A'
(89 - 80) --> 'B'
(79 - 70) --> 'C'
(69 - 60) --> 'D'
(59 - 0) --> 'F'
If the given score is greater than 100 or less than 0, it should return 'INVALID SCORE'. (만약 주어진 점수가 100을 초과하거나 0 미만이라면 'INVALID SCORE' 를 반환해야 합니다.)

```



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


---
## Conditional : Or
---



>Write a function called "or". ("or" 함수를 작성하세요.)

>Given 2 boolean expressions, "or" returns true or false, corresponding to the || operator. (boolean 두개가 주어졌을때, "or" 함수는 || 연산자에 대응하는 true 나 false 를 반환합니다.)

```
Notes:

Do not use the || operator. (|| 연산자를 사용하지 마세요.)
Use ! and && operators instead. (대신 ! 와 && 연산자를 사용하세요.)
```

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




---
## Conditional : isEitherEvenAndLessThan9
---



>Write a function called "isEitherEvenAndLessThan9". ("isEitherEvenAndLessThan9" 함수를 작성하세요.)

>Given two numbers, 'isEitherEvenAndLessThan9' returns whether at least one of them is even, and, both of them are less than 9. (숫자 두개가 주어졌을때, 'isEitherEvenAndLessThan9' 함수는 2가지 조건을 검사합니다. 우선 두 숫자 중 적어도 하나가 짝수인지, 그리고 두 숫자 모두 9보다 작은지를 확인합니다. 두 조건을 모두 만족 했을 때만 true를 반환합니다.)



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
## string : getFullName
---



>Write a function called "getFullName". ("getFullName" 함수를 작성하세요.)

>Given a first and a last name, "getFullName" returns a single string with the given first and last names separated by a single space. (이름과 성이 주어졌을때, "getFullName" 함수는 이름과 성이 띄어쓰기 하나를 사이에 둔 단일 문자열을 반환해야 합니다.)


```

function getFullName(firstName, lastName) {
  // 여기에 코드를 작성하세요
  let output = firstName + lastName;
  return firstName + " " + lastName;
}
  
getFullName('john','jung')

```



---
## string : getLengthOfWord
---



>Write a function called "getLengthOfWord". ("getLengthOfWord" 함수를 작성하세요.)

>Given a word, "getLengthOfWord" returns the length of the given word. (단어가 주어졌을때, "getLengthOfWord" 함수는 단어의 길이를 반환해야 합니다.)


```

function getLengthOfWord(word) {
  // 여기에 코드를 작성하세요
  let count = word.length;
  return count;
}
getLengthOfWord("hello")

```


---
## string : computeAverageLengthOfWords
---




>Write a function called "computeAverageLengthOfWords". ("computeAverageLengthOfWords" 함수를 작성하세요.)

>Given two words, "computeAverageLengthOfWords" returns the average of their lengths. (두 단어가 주어졌을때, "computeAverageLengthOfWords" 함수는 두 단어 길이의 평균값을 반환합니다.)



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


---
## string : isOddLength
---


>Write a function called "isOddLength". ("isOddLength" 함수를 작성하세요.)

>Given a word, "isOddLength" returns whether the length of the given word is odd. (단어가 주어졌을때, "isOddLength" 함수는 주어진 단어의 길이가 홀수인지 반환해야 합니다.)


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


---
## string : isEvenLength
---


>Write a function called "isEvenLength". ("isEvenLength" 함수를 작성하세요.)

>Given a word, "isEvenLength" returns whether the length of the word is even. (단어가 주어졌을때, "isEvenLength" 함수는 주어진 단어의 길이가 짝수인지 반환해야 합니다.)



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

---
## string : repeatString
---



>Write a function called "repeatString". ("repeatString" 함수를 작성하세요.)

>Given a string and a number, "repeatString" returns the given string repeated the given number of times. (문자열과 숫자가 주어졌을때, "repeatString" 함수는 주어진 문자열을 주어진 숫자만큼 반복하여 반환해야 합니다.)


```

function repeatString(string, num) {
  // your code here
 var repeatation = string.repeat(num) 
 return repeatation;
}

repeatString("thewordofGod is the way",50)
```



---
## string : findShortestOfThreeWords
---


>Write a function called "findShortestOfThreeWords". ("findShortestOfThreeWords" 함수를 작성하세요.)

>Given 3 strings, "findShortestOfThreeWords" returns the shortest of the given strings. (문자열 3개가 주어졌을때, "findShortestOfThreeWords" 함수는 주어진 문자열 중 가장 짧은 문자열을 반환해야 합니다.)

```

Notes:

If there are ties, it should return the first word in the parameters list. (만약 동률이 있다면, 그 중 앞에 있는 문자열을 반환해야 합니다.)

```
```
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



---
## string : countCharacter
---


>Write a function called "countCharacter". ("countCharacter" 함수를 작성하세요.)

>Given a string input and a character, "countCharacter" returns the number of occurences of a given character in the given string. (문자열과 문자가 주어졌을때, "countCharacter" 함수는 주어진 문자열에서 주어진 문자가 몇개가 있는지를 반환해야 합니다.)



```

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



---
## string : areValidCredentials
---




>Write a function called "areValidCredentials". ("areValidCredentials" 함수를 작성하세요.)

>Given a name and a password, "areValidCredentials", returns true if the name is longer than 3 characters, AND, the password is at least 8 characters long. Otherwise it returns false. (이름과 비밀번호가 주어졌을때, "areValidCredentials" 함수는 이름이 3글자이상 그리고 비밀번호가 8글자 이상이면 true를 반환합니다.)

* ex1
```
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
```

function findMinLengthOfThreeWords(word1, word2, word3) {
  var arr = [];
  arr.push(word1, word2, word3);
  arr.sort();
  return arr[0].length;
}
findMinLengthOfThreeWords("dwdsdsdsdsdsdsdwd","ddwwd","wdwdwdsdsdwdwwd")

```
* ex3

```
function findMinLengthOfThreeWords(word1, word2, word3) {
  // your code here
  /* START SOLUTION */
  words = [word1, word2, word3];
  return words.sort()[0].length;
  /* END SOLUTION */
}

```

* ex4

```

function findMinLengthOfThreeWords(word1, word2, word3) {
  return Math.min(word1.length, word2.length, word3.length)
}
```


---
## Math : computeAreaOfATriangle
---


>Given the base and height of a triangle, "computeAreaOfATriangle" returns its area. (삼각형의 밑변과 높이가 주어졌을때, "computeAreaOfATriangle" 함수는 삼각형의 넓이를 반환합니다.)


```
function computeAreaOfATriangle(base, height) {
  // your code here
  let ret = base * height / 2;
  return ret;
}

```


---
## Math : computePerimeterOfACircle
---


>Write a function called "computePerimeterOfACircle". ("computePerimeterOfACircle" 함수를 작성하세요.)

>Given the radius of a circle, "computePerimeterOfACircle" returns its perimeter. (원의 반지름이 주어졌을때, "computePerimeterOfACircle" 함수는 원의 둘레를 반환하세요.



```

function computePerimeterOfACircle(radius) {
  // your code here\
  //원의 둘레 = 2 X 반지름 X 원주율 = 지름 X 원주율
  let ret = radius * 2 * Math.PI;
  return ret;
}

computePerimeterOfACircle(200);


```




---
## Math : computeAverageOfNumbers
---



>Write a function called "computeAverageOfNumbers". ("computeAverageOfNumbers" 함수를 작성하세요.)

>Given an array of numbers, "computeAverageOfNumbers" returns their average. (숫자이 배열이 주어졌을때, "computeAverageOfNumbers" 함수는 그들의 평균을 반환합니다.)

```

Notes:

If given an empty array, it should return 0. (만약 빈배열이 주어졌다면, 0을 반환해야 합니다.)

```

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

---
## type : 01_convertToString
---

convertToString함수가 있습니다. 이 함수는 주어진 파라미터를 문자열의 형태로 변환합니다.


* Note

```
let output = convertToString(120);
console.log(output); // --> '120'

let output2 = convertToString('hello');
console.log(output2); // --> 'hello'

let output3 = convertToString(true);
console.log(output3); // --> 'true'
```



```

function convertToString(anything) {
  // 여기에 코드를 작성하세요
  return anything.toString();
}

convertToString('hello')




```
