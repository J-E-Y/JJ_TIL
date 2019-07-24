---
title: JS Basic
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

