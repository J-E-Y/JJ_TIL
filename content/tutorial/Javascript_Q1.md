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


* my_answer


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



* my_answer

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




* my_answer

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


* my_answer


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



* my_answer

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


* my_answer

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


* my_answer

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




* my_answer

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



* my_answer

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


* my_answer

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


* my_answer

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


* my_answer


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


* my_answer

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



* my_answer

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

* my_answer

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

>If there are ties, it should return the first word in the parameters list. (만약 동률이 있다면, 그 중 앞에 있는 문자열을 반환해야 합니다.)



* my_answer

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

* my_answer

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



* my_answer

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


* my_answer

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




* my_answer

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



* my_answer

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
## **type**
---



**01_convertToString**

convertToString함수가 있습니다. 이 함수는 주어진 파라미터를 문자열의 형태로 변환합니다.



* my_answer

```

function convertToString(anything) {
  // 여기에 코드를 작성하세요
  return anything.toString();
  // return "" + anything;
  // return String(anything);
}

convertToString('hello')




```




**02_convertToNumber**

>convertToNumber함수가 있습니다. 이 함수는 주어진 파라미터를 숫자의 형태로 변환합니다.


>숫자로 변환할 수 없는 경우, NaN (Not a number) 이라는 결과가 나올것입니다. NaN은 숫자가 아님을 나타내는 특수한 값으로, 문자열이 아닙니다.



```

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







**03_isFalsy**

>isFalsy함수가 있습니다. falsy 값은, 거짓으로 취급되는 값을 의미합니다. 이 함수는 주어진 파라미터가 falsy값인지 아닌지를 평가합니다.


* my_answer

```

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


**04_getType**


>getType함수가 있습니다. 이 함수는 주어진 파라미터의 타입을 리턴합니다.

>Note:
>배열을 넘길 경우, 'object'라고 나올 수 있습니다. 배열과 객체는 어떻게 구분할 수 있을까요?
배열과 객체를 구분하려면 Array.isArray 메소드를 사용하면 됩니다.


* my_answer

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




---
## **object**
---


* 01_getProperty

>파라미터로 객체와 키를 받는 getProperty함수가 있습니다. 이 함수는 주어진 객체와 키를 이용하여 속성값을 찾아 리턴합니다.
만일 주어진 키가 객체의 속성에 없다면, undefined를 리턴하면 됩니다.


* my_answer


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



* 02_addProperty


>파라미터로 객체와 키를 받는 addProperty 함수가 있습니다. 이 함수는 주어진 객체에, 키 이름으로 속성을 만들고 값을 true로 설정합니다.



* my_answer

```
function addProperty(obj, propertyName) {
  // 여기에 코드를 작성하세요
  return obj[propertyName] = true;
  // return obj.propertyNmae = true; <<<is not working at all
  }

let john = {};

addProperty(john,'isprogrammer');
```


* Q

>obj[propertyName]를 이용했을 때는 테스트가 통과가 되고,
obj.propertyName를 이용했을 때는 통과가 되지 않습니다.
객체에 프로퍼티를 추가할 때 dot노테이션을 사용할 수 있는 걸로 알고있는데..이유가 뭘까요?


* answer

>. 으로 했을때는 바로 객체의 키로 접근하고 [ ] 으로 하면 변수로 접근합니다.
addProperty(steve, 'isProgrammer'); 이라는 함수 호출 구문이 있다고 가정하면
obj[propertyName] = true; 는 steve.isProgrammer = true; 이고
obj.propertyName = true; 는 steve.propertyName = true; 입니다. 완전히 다른값이 나오죠?






* 04_addObjectProperty


>파라미터로 두 개의 객체와 키를 받는 addObjectProperty 함수가 있습니다. 이 함수는 주어진 첫번째 객체에, 키 이름으로 속성을 만드는데, 그 값은 두번째 객체로 설정합니다.
객체의 키 값은 또다른 객체가 될 수 있음을 기억하세요.


* my_answer


```

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



* 05_removeProperty


>Write a function called "removeProperty". ("removeProperty" 함수를 작성하세요.)

>Given an object and a key, "removeProperty" removes the given key from the given object. (객체와 키가 주어졌을때, "removeProperty" 함수는 주어진 키에 해당하는 객체의 속성값을 제거해야 합니다.)



* my_answer



```

function removeProperty(obj, propertyName) {
  // 여기에 코드를 작성하세요
  delete obj[propertyName];
}

```


* 06_isPersonOldEnoughToVote

>Write a function called "isPersonOldEnoughToVote". ("isPersonOldEnoughToVote" 함수를 작성하세요.)

>Given a "person" object, that contains an "age" property, "isPersonOldEnoughToVote" returns whether the given person is old enough to vote. ("age" 속성을 가지고 있는 "person" 객체가 주어졌을때, "isPersonOldEnoughToVote" 함수는 그 사람이 미국에서 합법적으로 투표를 할 수 있는 나이인지를 반환해야 합니다.)


```

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



* 08_removeNumbersLargerThan


>Write a function called "removeNumbersLargerThan". ("removeNumbersLargerThan" 함수를 작성하세요.)

>Given a number and an object, "removeNumbersLargerThan" removes any properties whose values are numbers greater than the given number. (숫자와 객체가 주어졌을때, "removeNumbersLargerThan" 함수는 주어진 객체에서 주어진 숫자보다 큰 모든 숫자 속성을 제거합니다.)

* my_answer

```
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




* 09_removeOddValues


>Write a function called "removeOddValues". ("removeOddValues" 함수를 작성하세요.)

>Given an object, "removeOddValues" removes any properties whose values are odd numbers. (객체가 주어졌을때, "removeOddValues" 함수는 주어진 객체의 속성값이 홀수인 속성을 모두 제거합니다.)


* my_answer
```
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

* 10_countNumberOfKeys

>Write a function called "countNumberOfKeys". ("countNumberOfKeus" 함수를 작성하세요.)

>Given an object, "countNumberOfKeys" returns how many properties the given object has. (객체가 주어졌을때, "countNumberOfKeys" 함수는 객체안에 있는 속성들의 갯수를 반환합니다.)


* my_answer

```
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
```

* Model Solutions

```

function countNumberOfKeys(obj) {
  return Object.keys(obj).length;
}


```