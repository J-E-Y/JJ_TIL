---
title: JS algorithm
date: 2019-45
draft: true
menu:
  tutorial:
    parent: "Javascript"
    weight: 12
toc: true
type: docs
---

![](/tutorial/Javascript_Dictionary_files/javascriptt-light_870x220.png)


--------------------------------------------------------------------


### Question

>Have the function primeMover(n) return the n-th prime number. The range will be from 1 to 5 * 10^4; (숫자(n)가 주어졌을때, 'primeMover(n)' 함수는 num 번째 소수를 반환합니다. 범위는 1에서 50,000 입니다.)

>For example: if n is 16 the output should be 53 as 53 is the 16th prime number. (예시: 만약 n 이 16이라면, 결과값은 16번째 소수인 53 입니다.)

### My_Soultion


```js


let primeMover = function(n) {
  // your code here


  let arr = [1];
  for ( let i = 1; i <100; i++) {
    for ( let j = 2; j < 100; j++ ) {
      if (j % i !== 0 ) {
       arr.push(j);
      }
    }
  }
  return arr[n];
}


```








* primeMover




### Question

* isOddWithoutModulo



> Write a function called "isOddWithoutModulo". ("isOddWithoutModulo" 함수를 작성하세요.)

>Given a number, "isOddWithoutModulo" returns whether the passed in number is odd. (숫자가 주어졌을때, "isOddWithoutModulo" 함수는 주어진 숫자가 홀수인지를 반환합니다.)


### My_Soultion 


```js

// 2. it is used by Math.floor 

function isOddWithoutModulo(num) { // floor 메소드로 참과 거짓을 출력할뿐만 아니라 정수로 만든다. 그것을 2로 나눠서 2로 다시 곱한값이 기존에 값과 일치하지 않는다면 홀수이므로 true 반환
  
  return Math.floor(num / 2) * 2 !== num;  

```



### Others_Soultion

```js

function isOddWithoutModulo(num) {
   // 예를 들어, num이 -17이라고 가정합니다. 
   num = Math.abs(num);
// num은 절대값이 되어 17이됩니다. 이를 통해 파라미터에 들어올 모든 음수를 커버할 수 있을 겁니다. 
   if( num === 0 )  // num은 현재 17로 0이 아니기 때문에 그 다음 else if로 넘어가게 됩니다. 
       return false;
   else if(num === 1) // num은 현재 17로 1이 아니기 때문에 그 다음 else로 넘어가게 됩니다. 
       return true;
   else { // 보통 홀수인지 아닌지를 판별하기 위해서 2로 나누었을 대 나머지값을 확인하는 방법을 씁니다. 
// 그 방법을 풀어보면 17 -2 -2 -2 -2 -2 -2...... 하여 0 혹은 1이 될 때까지 뻰다는 것을 의미합니다. 
       return isOddWithoutModulo(num-2); // 이 부분은 바로 위의 설명이 적용되는 부분입니다. 
// 자바스크립트는 재귀함수가 가능하여 함수 안에서 자기 자신을 호출할 수 있습니다.
// 이를테면 num이 17이었다면 위의 구문을 통해 다시  isOddWithoutModulo(17-2)를 호출하는 것입니다. 
// 위의 과정을 다시 반복하게 되면 isOddWithoutModulo(15) --> isOddWithoutModulo(13) --> isOddWithoutModulo(11).... 
// num이 0 혹은 1이 되어 if와 else if 구문에 걸려 return될 때까지 반복됩니다. 
   }
}


```








### Question


* getStringLength


> Write a function called "getStringLength". ("getStringLength" 함수를 작성하세요.)

>Given a string, "getStringLength" returns the length of the given string. (문자열이 주어졌을때, "getStringLength" 함수는 주어진 문자열의 길이를 반환합니다.)

>Do NOT use any native 'length' methods. (- 'length' 메소드를 사용하지 마세요.)





### My_Soultion

```js

function getStringLength(string) {
  // your code here

  // 1. count 변수를 만들어 초기값을 지정한다. 
  // 2. while loop를 이용해 string[count] 값을 지정해 조건문을 만든다. 
  // 3. 참이면 count 에 1씩 증가시킨다. 그러면 조건문에 인덱스 번호가 넘어가면 조건문이 문자의 길이만큼 값이 count 에 저장된다. 

  let count = 0;

  while (string[count]) {
    count = count + 1;
  };
  return count;
};


```





### Question

* getIndexOf

>Write a function called "getIndexOf". ("getIndexOf" 함수를 작성하세요.)

>Given a character and a string, "getIndexOf" returns the first position of the given character in the given string. (문자와 문자열이 주어졌을때, "getIndexOf" 함수는 주어진 문자열에서 주어진 문자가 나타나는 첫번째 위치를 반환합니다.)



### My_Soultion


```js
function getIndexOf(char, str) {

      for (let i = 0; i < str.length;  i = i + 1 ) {
          if ( str[i] === char ) {  //  만약 str 에 있는 문자들중에 char 같다면 
            return i;  // 리턴 인덱스 번호 
          } 
        }
      return -1; //  아니면 -1  반환
    }



```







### Question

* calculateBillTotal

> Write a function called "calculateBillTotal". ("calculateBillTotal" 함수를 작성하세요.)

>Given the pre tax and pre tip amount of a meal, "calculateBillTotal" returns the total amount due after tax and tip. (팁과 세금을 제외한 식사값이 주어졌을때, "calculateBillTotal" 함수는 팁과 세금이 포함된 총 식사값을 반환합니다.)

>Assume that sales tax is 9.5% and tip is 15%. (- 세금은 9.5% 팁은 15% 로 계산하세요.)
>Do NOT tip on the sales tax, only on the pre tip amount. (- 팁을 계산할때 세금을 포함하여 계산하지 마세요.)

### My_Soultion

```js

function calculateBillTotal(preTaxAndTipAmount) {
  // your code here

  // 1. salesTax 변수를 만들고 주어진 값의 0.095 곱한 값을 대입
  // 2. tip 변수를 만들고 주어진 값의 0.15 를 곱한 값을 대입
  // 3. 모든값을 더한후 리턴  
 

  let salesTax = preTaxAndTipAmount * 0.095;
  let tip = preTaxAndTipAmount * 0.15;

  return preTaxAndTipAmount + salesTax + tip;
}




```



* calculateBillTotal

### Question

* convertObjectToArray3

> Write a function called "convertObjectToList" which converts an object literal into an array of arrays, like this: (객체를 입력으로 받고 해당 객체를 다음과 같이 2차원 배열로 변형 할 수 있는 함수 "convertObjectToList"를 작성하세요.)


### My_Soultion

```js
function convertObjectToList(obj) {
  // your code here
  
  // 1. 마지막에 출력할 빈배열을 만든다. 
  // 2. for 문을 사용해서 객체안에 있는 key와 prop 값에 전근한다. 
  // 3. push 사용해 접근한 key값은 0번째 값에 넣고 prop 값은 1번째 값에 넣는다. 
  // 4. arr 리턴한다. 

  let arr = [];
  for ( let key in obj ) {
    arr.push([key,obj[key]]);
  }  
 return arr;
}




```



### isOdd

>Write a function called isOdd. ("isOdd" 함수를 작성하세요.)

>Given an integer, isOdd returns whether the integer is odd or not. (숫자가 주어졌을때, "isOdd" 함수는 주어진 숫자가 홀수 인지 아닌지를 반환합니다.)

* My_Soultion



```
function isOdd(num) {
  // your code here
  // 파라미터를 2로 나누었을때의 나머지를 판별별
  // 나머지가 1인경우, true를 리턴
  // 나머지가 0인경우, false를 리턴
  if (num % 2 === 1 ) {
    return true;
  } else {
    return false;
  }
}

```

**sum**

>Summation to n: Let's implement the function sum that takes a single parameter n, and computes the sum of all integers up to n starting from 0, e.g.:

>(n까지의 총 합: n을 매개변수로 받아 0 부터 n 까지 모든 수의 총 합을 반환하는 함수를 작성하세요.)

* My_Soultion



```
function sum(n) {
  let result = 0;
  //반복문을 이용하여 0부터 n까지의 숫자를 더하여 출력
  for (let i = 0; i <= n; i++) {
    result = result + i;
  }
  return result;
  
  // your code here
}
sum(3);
sum(4);

```
## onlyEvenElements


>Given an array of numbers, onlyEvenElements returns a new array of just the even numbers. (숫자로 이루어진 배열이 주어졌을때, "onlyEvenElements" 함수는 주어진 배열에 있는 짝수로만으로 이루어진 새로운 배열을 반환해야 합니다.)

* My_Soultion


```

function onlyEvenElements(arr) {
  //짝수값을 입력받을 빈배열을 선언한다.
  let result = [];
  //입력받은 배열안에 있는는 값을 판별하기위해 불러온다.
  for (let i = 0; i < arr.length; i++) {
    //값이 짝수인지를 if 문을 써서 판별한다. 
    if (arr[i] % 2 === 0) {
      //값이이 짝수인경우 빈배열에 집어넣는다.
      result.push(arr[i]);
    }
  }
  return result;
  // your code here
}


```

## removeOddValues

>Write a function removeOddValues that takes an object as an argument and returns an object with all key/value pairs removed for which the value holds an odd number. ("removeOddValues" 함수를 작성하세요. 객체가 주어졌을때, "removeOddValues" 함수는 주어진 객체의 key/value 페어 중 value 가 홀수 숫자인 페어가 제거된 객체를 반환하세요.)

>You'll need to use the "typeof" operator to first check that the values are numbers: (value가 숫자인지 확인하기 위하서는 "typeof" 연산자를 먼저 사용해야 합니다.)

* My_Soultion

> first 

```
function removeOddValues(object) {
  // 1.홀수숫자인 페어가가 아닌 값들을 입력받을을 빈 객체를를 만든다.
  let object2 = {};
  // 2. value 값들을 판별하기 위해 키값을 반복시킨다.
  for (let k in object) {
  // 3. value 값이 숫자이고 짝수이면 빈객체에 대입한다. 
    if (typeof(object[k]) === 'number' && object[k] % 2 === 0) {
      object2[k] = object[k];
  //4. value 값이 문자형이면 객체에 대입한다. 
    } else if ( typeof(object[k]) === "string" ) {
      object2[k] = object[k];
    } 
  }
  return object2;
  // your code here
}

```


> Sceond 


```

function removeOddValues(input) {
	
// 1. 결과를 담을 객체를 만듭니다. 
	
  	let result = {};

// 2. input 으로 받은 object 안에 key 를 모두 반복합니다. 
  
  for (let key in input) {
	  let value = input[key];
	  let isNumber = typeof value === 'number';

	  if (isNumber ) {
	 
// key의 해당 하는 value가 짝수인지 확인합니다.
	 
    let isEven = value % 2 === 0;
    if (isEven) {
	 
// 만든 객체에 key, value를 추가합니다.
	 
    result[key] = value;
	    }
   }
// 숫자가 아니면
	
    else {
	
//만든 객체에 key, value 를 추가합니다.

  	result[key] = value;	
    }
  }
  return result;
}

removeOddValues({ a: 1, b: 2, c: 3, d: 'hello' })


```



> third

```

function removeOddValues(object) {
  //1. value 값을 판별하기 위해 key 값을 반복한다.
  for (let k in object) {
  //2. value 값이 숫자이고 홀수이면 삭제한다. 
    if (typeof(object[k]) === 'number' && object[k] % 2 === 1) {
    delete object[k];
     }
  }
  return object;
  }

```


## firstCharacter

> In this exercise, a string is passed to a method and a new string has to be returned with the first character of each word in the string (문자열이 주어졌을때, "firstCharacter" 함수는 문자열의 각 단어 첫글자들로 이루어진 문자열을 반환하여야 합니다.)


> Attention! In test case 5 userinput is one space input char as ' ', please do not get confused with '', empty string (주의사항! 테스트 케이스 5 에서 주는 입력값은 띄어쓰기 한개(' ') 입니다. 빈 문자열('') 과 혼동하지 마세요.)


* My_Soultion


```js

unction firstCharacter (string) {
 // Your code here
 
 
 // for문 이용
 
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

* dashInsert


>Have the function DashInsert insert dashes ('-') between each two odd numbers in str. (문자열이 주어졌을때, 'DashInsert' 함수는 문자열에 있는 두 홀수 사이에 대시('-')를 추가하여 반환합니다.)

>For example: if str is 454793 the output should be 4547-9-3. (예시: 주어진 문자열이 454793 이라면 결과값은 4547-9-3 입니다.) Don't count zero as an odd number. (0 을 홀수로 간주하지 마세요.)





```js

// 1/for 문


function DashInsert(string) {
 


 let output = [];
 let tmp=string.split('');
 for(let i=0;i<tmp.length;i++){
   //홀수가 연속해서 나올때 => i번째와 '-'을 넣는다.
   if(tmp[i]%2 && tmp[i+1]%2){// 1,3
     output.push(tmp[i],'-');//1,-,3
   }else{
     output.push(tmp[i]);
   }
 }
 return output.join('');
 }

///////////////////////////////////////////////////////////////////

reduce 

function DashInsert(string) {
 
 let output = '';
 let tmp = string.split('');
 output = tmp.reduce(function(acc,cur){
   if((acc)%2===1 && (cur)%2===1) return acc+'-'+cur;
   else return acc+cur;
 });
 return output;

}


////////////////////////////////////////////////////////////////////

// 2.splice

function DashInsert(string) {
  let arr = string.split('');
  for (let i = 0; i < arr.length; i++) {
    if ( arr[i] % 2 === 1 && arr[i + 1] % 2 === 1) {
      arr.splice(i +1,0,'-');
    }
  }
  return arr.join('');
}




```




## longestWord


> sing the JavaScript language, have the function LongestWord take the sen parameter being passed and return the largest word in the string. (문장이 주어졌을때, 'LongestWord' 함수는 주어진 문장에서 가장 긴 단어를 반환합니다.)

>If there are two or more words that are the same length, return the first word from the string with that length. Assume sen will not be empty. (만약 가장 긴 단어가 두개 이상이라면, 첫번째로 등장하는 가장 긴 단어를 반환하세요. 문장은 빈 문자열이 아닙니다.)


* My_Soultion


```

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


## convertArrayToObject1

* Question

>Write a function 'transformFirstAndLast' that takes in an array, and returns an object with: (배열을 입력으로 받고 다음 조건에 만족하는 객체를 반환하는 함수 'transformFirstAndLast' 함수를 작성하세요.)

>the first element of the array as the object's key, and (1. 배열의 첫번째 요소를 객체의 키로 가집니다.)
the last element of the array as that key's value. (2. 배열의 마지막 요소를 해당 키의 값으로 가집니다.)




* My_Soultion


```js

function transformFirstAndLast(array) {
  // your code here

  // 1. 마지막으로 출력할 객체를 만든다.
  // 2. 배열의 첫번째 요소를 가져와 변수에 담는다.
  // 3. 배열의 마지막 요소를 가져와 변수에 담는다.
  // 4. 객체안에 첫번째 요소를 키로 설정한다.
  // 5. 객체안에 마지막 요소를 prop 설정한다. 

  let ret = {};
  ret[array[0]] = array[array.length -1 ];
  return ret;
}



```


## convertObjectToArray1

* Question


>Write a function called "getAllKeys" which returns an array of all the input object's keys. (객체를 입력으로 받고 해당 객체의 키들을 배열로 반환하는 "getAllKeys" 함수를 작성하세요.)



* My_Soultion


```js


function getAllKeys(obj) {
// your code here

// 1. 마지막에 출력할 새로운 배열을 만든다
// 2. for in key 값을 가져온다. 
// 3. 가져온 값을 새로 만든 배열에 넣는다.
let arr = [];
for ( key in obj ) {
  arr.push(key);
}
return arr;
}


```

## convertArrayToObject2


* Question 


> Write a function 'fromListToObject' which takes in an array of arrays, and returns an object with each pair of elements in the array as a key-value pair. (2차원 배열을 입력으로 받고 배열안에 있는 배열의 요소 페어를 키-값 페어로 가지는 객체를 반환하는 함수 'fromListToObject' 함수를 작성하세요.)



* My_Soultion


```js
function fromListToObject(array) {
  // your code here
  
  //  1. output 할 빈객체를 생성한다.  
  //  2. for 문으로 배열 안에 있는 배열을 조사한다.
  //  3. 배열안에 있는 배열의 0번째 를 키값 1번째를 prop 에 넣는다.
 
  
  let obj = {};

  for ( let i = 0; i < array.length; i = i + 1 ) {
    obj[array[i][0]] = array[i][1];
    }
    return obj
}



```


## convertObjectToArray2


* Questoin

>Write a function called "listAllValues" which returns an array of all the input object's values. (객체를 입력으로 받고 해당 객체의 값들을 배열로 반환하는 "listAllValues" 함수를 작성하세요.)


* My_Soultion


```js
function listAllValues(obj) {
  // your code here
  
  // 1. output 할 빈 배열을 생셩
  // 2. for in prop 값을 조사
  // 3. prop 값을 빈배열에 넣는다. 
  // 4. output 출력한다. 
  
  let arr = [];
  for ( prop in obj ) {
    arr.push(obj[prop]);
  } 
  return arr;
}




```


**convertArrayToObject3**


* Question

> Write a function called "transformEmployeeData" that transforms some employee data from one format to another. (사원들의 정보를 다른 형태로 변형 할 수 있는 함수 "transformEmployeeData" 함수를 작성하세요.)

>The argument will look something like this: (사원들의 정보는 아래와 같은 배열로 주어질 수 있습니다.)



* My_Soultion

```js

function transformEmployeeData(array) {

  // 1. 맨 위 배열을 루프 데이터 가져온다.
  // 2. 가지고온 배열을 또 루프 를 돌려서 가져온다.
  // 3. 가지고온 배열을 0번째는 obj key 1번째는 value
  // 4. 만든 obj 를 배열에 푸시 
  
  
  let arr = [];
  
  for ( let i = 0; i < array.length; i = i + 1 ) {
    let data = {};
    for ( let n = 0; n < array[i].length; n = n + 1 ) {
      data[array[i][n][0]] = array[i][n][1];
    }
    arr.push(data);
  }
  return arr;


```


* other_Soultion


```js





function transformEmployeeData(array) {
  // your code here
 // [key] start: firstName - last: role
 // return [{}] index0 key; index1 value;
  
 // 배열 안에 객체가 들어가 있는 것을 반환해야하니까
 // 빈배열 선언하고 빈 객체 선언 해서 빈 객체에 값 넣고
 //그 객체를 빈 배열에 넣어주고
 // 최종적으로 return 그 배열 해 주면 됨

  let result = [];

  for (let i of array){ // 여기서 i 는 [['firstName', 'Joe'], ['lastName', 'Blow'], ['age', 42], ['role', 'clerk']]
    let obj = {};
   for (let j of i){ // 여기서 j는 ['firstName', 'Joe']
     obj[j[0]] = j[1]; // j의 0번 elemente 'firstName' , 1번 element 'Joe'
    // obj[array[j][0]] = array[j][1];
   }
   result.push(obj);
  }

return result;
}


```


**greetCustomers**

* Qutestion 

>Write a function called "greetCustomer". ("greetCustomer" 함수를 작성하세요.)

>Given a name, "greetCustomer" returns a greeting based on how many times that customer has visited the restaurant. Please refer to the customerData object. (고객들의 방문 횟수를 가지고 있는 객체와 이름이 주어졌을때, "greetCustomer" 함수는 손님이 몇번 방문했는지에 따라 다른 인삿말을 반환합니다. customerData 객체를 참고해 주세요.)

* My_Soultion

```js

function greetCustomer(customerData, firstName) {
  let greeting = '';
  // your code here

  // 1 . 객체의 속성의 객체의 속성값 접근한다.
  // 2.  객체의 속성의 객체의 속성값이 undefinded 이라면 1 greeting 대입
  // 3.  객체의 속성의 객체의 속성값이 1 이라면 2  greeting 대입
  // 4.  객체의 속성의 객체의 속성값이 1 보다 크다면 3 greeting 대입

    if (!customerData[firstName]) {
        greeting = `Welcome! Is this your first time?`;
    } else if (customerData[firstName].visits === 1  ) {;
        greeting = `Welcome back, ${firstName}! We're glad you liked us the first time!`
    } else if ( customerData[firstName].visits > 1 ) {
        greeting =  `Welcome back, ${firstName}! So glad to see you again!`;
    }
    return greeting;
}

```

**convertDoubleSpaceToSingle**

* Question

> Write a function called "convertDoubleSpaceToSingle". ("convertDoubleSpaceToSingle" 함수를 작성하세요.)

>Given a string, "convertDoubleSpaceToSingle" returns the passed in string, with all the double spaces converted to single spaces. (문자열이 주어졌을때, "convertDoubleSpaceToSingle" 함수는 주어진 문자열에 있는 띄어쓰기 두개(double spaces)를 띄어쓰기 한개(single space)로 변환한 뒤 해당 문자열을 반환합니다.)



* My_Soultion


```js

function convertDoubleSpaceToSingle(str) {
  
  // 1. 문자열을 split() 를 사용해서 str 변수에 배열로 저장한다.
  // 2. reduce 를 사용해서 배열에 담긴 문자의 single space로 만들어 출력한다. 

  let strArr = str.split("  ");
  let output = strArr.join(" ");
  return output;
}


// Refactoing

function convertDoubleSpaceToSingle(str) {
  return str.split("  ").join(" ");

}


```



* other_Soultion


```js

function convertDoubleSpaceToSingle(str) {
  return str.replace( /  +/g,' ');
}
잘되긴 하는데.... ㅡ,.ㅡ

/ +/g 부분이 이해가 가지 않습니다...............
/(빈칸 두개)+/g 를 찾아서 ' '로 바꿔준다는 것 같습니다.

```




* other_Soultion

```js

function convertDoubleSpaceToSingle(str) {

var array = str.split(' '); // 문자열 배열 만들기  [ 'string', '', 'with', '', 'double', '', 'spaces' ]

for (i = 0; i<=array.length; i++) { // for 문을 이용해 배열 접근 
  if (array[i] === '') { //만약 각각의 요소가 '' 와 같다면
    array.splice(i,1); // splice 접근해서 삭제 
  }
}

return array.join(' '); // 각각의 문자열을 join ' ' 를 나눠서 출력 

}


```
