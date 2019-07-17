---
title: JS algorithm
date: 2019-45
draft: true
menu:
  tutorial:
    parent: "Javascript"
    weight: 20
toc: true
type: docs
---


---
## Conditional : areSameLength
---

* 2개의 문자열이 주어졌을 때, areSameLength는 문자열들의 길이가 같으면 true를, 아니면 false를 반환해야 합니다.

```
function areSameLength(string1, string2) {
	if (string1.length === string2.length) {
	  return true;
	} else {
    return false;
  }
}


areSameLength("they","hello");

```



---
## Conditional : isPasswordLongEnough
---

* isPasswordLongEnough 함수는 문자열과 정수를 parameter로 입력받는 함수로, 여기서는 암호의 최소 요구 길이를 판단합니다. 문자열의 길이가 충분한지 여부를 반환해야 합니다.

```
function isPasswordLongEnough(password, minimumLength) {
	// your code here
	if (password.length >minimumLength) {
	  return true;
	} else {
	  return false;
	}
	// start solution

	// end solution
}

isPasswordLongEnough('hello',5);

```
---
## Conditional :  bouncer
---

* 문자열의 형태로 이름, 정수 형태로 나이를 입력받는 bouncer 함수는, 주어진 나이에 따라 환영 메시지 혹은 거절 메시지를 리턴합니다.


```
function bouncer(name, age) {
  // This code is not right...I couldn't find it why 
  if (age >= 21) {
    return 'Welcome,' +name+ '!';
  } else{
    return 'Go home,'  +name+ '.';
  }
}  


function bouncer(name, age) {
  // this code is right
  if (age >= 21){
    return 'Welcome, ' +name+ '!'
  } else {
    return 'Go home, ' +name+ '.'
  }
}

```
---
## Conditional :  getLargerString
---

* 두 문자열이 주어졌을 때, getLargerString 함수는 더 긴 문자열을 반환해야 합니다.


```

function getLargerString(string1, string2) {
	// your code here
	// start solution

	// end solution
	if (string1.length > string2.length) {
	  return string1;
	} else if (string1.length === string2.length){
	  return string1;
	} else {
	  return string2; 
	}
}

```
---
## Conditional :  1-5 isEven
---


* isEven 함수는 정수 하나를 입력받아 그 정수가 짝수인지 아닌지를 반환해야 합니다.



```
function isEven(num) {
	// your code here
	// start solution

	// end solution
	if (num % 2 === 0 ){
	  return true;
	} else {
	  return false;
	}
}

isEven(22)
```



---
## Conditional :  isPositive
---


* 정수 하나가 주어졌을 때, `isPositive` 함수는 그 정수가 양수인지 아닌지를 반환해야 합니다.


```
function isPositive(num) {
	// your code here
	// start solution
  
	// end solution
	if (num >= 0 ){
	  return true;
	} else {
	  return false;
	}
};

isPositive(42);
```

---
## Conditional :  bounceBlacklist
---


* 이전에 작성했던 `bounce` 함수에서 새로운 요구사항이 추가되었습니다. 특정 사람을 거절하는 기능입니다. "Joe"라는 사람은 우리의 블랙 리스트로, 이 사람은 나이에 관계없이 거절하기로 결정하였습니다. 기존의 `bounce`함수를 수정하여, "Joe"라는 사람은 무조건 거절 메시지를 보낼 수 있도록 작성하십시오.


```
??? it's not sovled out??

function bouncerBlackList(name, age) {
  if (name === 'Joe') {
    return 'Go home,' + name + '!';
  }
  if ( age > 20 ) {
  	return 'Welcome, ' + name + '!';
  } else {
  	return 'Go home, ' + name + '.';
  }  
}
```

---
## Conditional :  scoreToGrade
---



숫자 하나를 매개변수로 받아서, 그 점수에 상응하는 성적 등급을 나타내는 문자열을 반환하는 함수 `scoreToGrade`를 작성하세요.


```
function scoreToGrade(score) {
  if (score < 60){
    return 'F';
  } else if (score < 70) {
    return 'D';
  } else if (score < 80) {
    return 'C';
  } else if (score < 90) {
    return 'B';
  } else if (score < 100) {
    return 'A';
  }
}

```


---
## Conditional :  convertScoreToGradeWithPlusAndMinus
---

```
// Write a function called "convertScoreToGradeWithPlusAndMinus".

// Given a score, "convertScoreToGradeWithPlusAndMinus" returns a string representing the letter grade corresponding to the given score.

// Notes:
// * (100 - 90) --> 'A'
// * (89  - 80) --> 'B'
// * (79  - 70) --> 'C'
// * (69  - 60) --> 'D'
// * (59  -  0) --> 'F'
// * If the given score is greater than 100 or less than 0, it should return 'INVALID SCORE'.
// * If the score is between the 0 and 2 (inclusive) of a given range, return the letter with a '-'
// * If the score is between the 8 and 9 (inclusive) of a given range, return the letter with a '+'
// * There are is no F+ and there is no F-.

```


```
function convertScoreToGradeWithPlusAndMinus(score) {
  var output = '';
  var lastNum = score.toString().slice(-1);
  if ((score > 100) && (score < 50)) {
    return 'INVALID SCORE';
  } else if(score === 100) {
    return 'A+';
  } else if(score >= 90 && score <= 99) {
      output = output + 'A';
  } else if(score >= 80 && score <= 89) {
      output = output + 'B';
  } else if(score >= 70 && score <= 79) {
      output = output + 'C';
  } else if(score >= 60 && score <= 69) {
      output = output + 'D';
  } else if(score < 60) {
      output = output + 'F';
  }
    if(parseInt(lastNum) <= 2 && parseInt(lastNum) >= 0) { 
    output = output + '-';
  } else if(parseInt(lastNum) >= 8 && parseInt(lastNum) <= 9) {
    output = output + '+';
  }
  return output;
}

convertScoreToGradeWithPlusAndMinus(72)


```



---
## Conditional :  scoreToGrade
---

```
scoreToGrade` 함수를 수정하여 등급 글자 뒤에 +나 -를 붙이는 작업을 할 때, 반복되는 코드가 상당히 많았었다는 것을 눈치채셨나요? 반복되는 것이 많다는 것은, 훨씬 더 나은 방법이 있다는 분명한 신호입니다.

`letter`와 `score`라는 두 전달인자를 받아서 다음과 같이 작동하는 도우미 함수 `letterGrade`를 작성하세요.
```

```
function letterGrade(letter, score) {
  var lastNum = score.toString().slice(-1);
  if (score === 100) {
    return 'A+';
  } else if (parseInt(lastNum) <= 2 && parseInt(lastNum) >= 0 ){
    return letter + '-';
  } else if (parseInt(lastNum) >= 8 && parseInt(lastNum)<= 9) {
    return letter + '+';
  }else if (parseInt(lastNum) > 2  && parseInt(lastNum)< 8 ) {
    return letter;
  }
}

letterGrade("A",50);

```


---
## Loop:  countChars
---


* 문자열 하나와 글자 하나를 매개변수로 받는 함수 `countChars`를 작성하세요. 이 함수는 주어진 문자열에서 주어진 글자가 몇 개나 들어가 있는지를 세어서 숫자로 반환해야 합니다. 문자열의 첫번째 글자를 알아내려면, 다음과 같은 문법을 사용하면 됩니다.

```

function countChars(string, character) {
  var result = string;
  var count = 0;
  var i = 0;
  while ( i < string.length) {
    if (result[i] === character) {
      count = count + 1 ;
    } 
    result.slice(0,1);
    i++
  }
  return count;
}

countChars("hello","h");

```
---
## Loop:  repeatString
---



* 문자열을 n번 반복해보도록 합시다. 반복할 문자열 `string`과 그 문자열을 몇 번 반복하는지를 나타내는 숫자 `n`을 매개변수로 받는 함수 `repeatString`을 작성하세요.



```
function repeatString(string, num) {
  return string.repeat(num);
}

repeatString("code",3);

```