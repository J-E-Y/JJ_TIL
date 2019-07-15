---
title: algorithm
date: 2019-45
draft: true
menu:
  tutorial:
    parent: "Javascript"
    weight: 20
toc: true
type: docs
---

## if 1-1  areSameLength

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




## if 1-2 isPasswordLongEnough


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

## if 1-3  bouncer


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

## if 1-4 getLargerString


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
## if 1-5 isEven



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




## if 1-6 isPositive



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


## if 1-7 bounceBlacklist



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