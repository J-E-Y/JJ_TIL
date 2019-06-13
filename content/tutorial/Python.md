---
title: 
date: 2019-04-29
draft: true
menu:
  tutorial:
    name: Python
    weight: 4
toc: true
type: docs
---

---
##  Python: **Operators**
---

* Arithmetic operators
* Assignment operators
* Comparison operators
* Logical operators


### Arithmetic Operator


|               |                  | 
| ------------- |:----------------:| -----:  |
|   +           |   Addition       |	x + y	 |
|   -	          |   Subtraction    |	x - y  |	
|   *	          |   Multiplication |	x * y  |	
|   /	          |   Division       |	x / y  |	
|   %	          |   Modulus        |	x % y  |
|   **	        |   Exponentiation |	x ** y |	 
|   //	        |   Floor division |	x // y |


### Assignment Operators


|               |                   | 
| ------------- |:-----------------:| -------:  |
|=	            |x = 5	            |x = 5	    |
|+=	            |x += 3	            |x = x + 3  |	
|-=	            |x -= 3	            |x = x - 3  | 	
|*=	            |x *= 3	            |x = x * 3  |	
|/=	            |x /= 3	            |x = x / 3  |	
|%=	            |x %= 3	            |x = x % 3  |	
|//=	          |x //= 3            |	x = x // 3|	
|`**=`	        |x `**= 3`          |	x = x ** 3|	
|&=	            |x &= 3             |	x = x & 3 |	
||=	            |x |= 3             |	x = x | 3	|
|^=	            |x ^= 3             |	x = x ^ 3	|
|>>=	          |x >>= 3            |	x = x >> 3|	
|<<=	          |x <<= 3            |	x = x << 3|



### Comparison Operators

|               |                         | 
| ------------- |:-----------------------:| ----------:    |
|==	            |Equal                    |	x == y	       |
|!=	            |Not equal                |	x != y	       |
|`>`	          |Greater than             | x > y	         |
|`<`	          |Less than                |	x < y	         |
|`>=`	          |Greater than or equal to |	x >= y         |	
|`<=`	          |Less than or equal to	  | x  <= y        |


### Python Logical Operators


|               |                                                       | 
| ------------- |:-----------------------------------------------------:| ------------:        |
|and 	          |Returns True if both statements are true	              |x < 5 and  x < 10	   |
|or	            |Returns True if one of the statements is true          |	x < 5 or x < 4	     |
|not	          |Reverse the result, returns False if the result is true|	not(x < 5 and x < 10)|



* exmple

```
Print(1+1) 더하기
2
Print(1-1) 빼기
0
Print(1*1) 곱하기
1
Print(3**3) 제곱
18
Print(8/2) 나누기
4
Print(3/2*4) 순서대로 곱하기 나누기 우선 그다음에 빼기 더하기
6.0
Print(7//3) 몫구하기 (3이 몇번들어갈수 있는지)
2
Print(3%2) 나머지값구하기(나머지가 1 남는다)
1


# 연산자 우선 순위
# **
# *,/,//,%
# +, -

# 문자열 연산
# + : 문자열 끼리 붙여주는 역할 "Hi" + "Hello" => "HiHello"
# * : "Hi"*3 => “HiHiHi"

# 문자열을 표현하는 방법, 만드는 방법
"She said \"Hi\"" # 'She said "Hi"'
'I\'m Jake' # 특수문자나 특별한 알파벳 앞에 \(슬래시)를 붙여서 특수 기능을
# 수행하는 것을 이스케이핑 문자 혹은 이스케이핑 처리

```


---
##  Python: **Variables**
---

* Description

>ariables are containers for storing data values.
Unlike other programming languages, Python has no command for declaring a variable.
A variable is created the moment you first assign a value to it.

* Example 1


```

x = 5
y = "John"
print(x)
print(y)

>>5
>>John
```


* Example 2

```

x = 4 # x is of type int
x = "Sally" # x is now of type str
print(x)

>>Sally
```


* Example

```
x = "awesome"
print("Python is " + x)

>>Python is awesome
```
* Note

* Variable Names

>A variable can have a short name (like x and y) or a more descriptive name (age, carname, total_volume). Rules for Python variables:
A variable name must start with a letter or the underscore character
A variable name cannot start with a number
A variable name can only contain alpha-numeric characters and underscores (A-z, 0-9, and _ )
Variable names are case-sensitive (age, Age and AGE are three different variables)



```
# 변수 이름?
# 대소문자 구분
# 알파벳, 숫자, 한글 : 숫자는 맨앞에는 사용 금지
# 특수문자 : _
# 명사나 동사형

# 표기법
# sayHi : 두번째 단어부터 단어의 첫글자는 대문자
# SayHi : 모든 단어의 첫글자는 대문자
# say_hi : 모두 소문자, 단어사이에 _
# strSayHi : 변수명 앞에 변수의 타입을 기록
```


---
##  Python: **int float tr **
---


##### `int`: 정수

```
x = input(“숫자를 입력해주세요.:")
Y = input(“숫자를 입력해주세요.:”)

x = 20
y = 30

Print(x+y)
>>>2030



x = `int`(input(“숫자를 입력해주세요.:”))
Y = `int`(input(“숫자를 입력해주세요.:”))

x = 20
y = 30

Print(x+y)
>>>50
```


##### 2. `float` :실수  () 소수점 나타내주는것

```
x = `float`(input(“숫자를 입력해주세요.:”)) >>20
Y = `float`(input(“숫자를 입력해주세요.:”)) >>30

Print(x+y)
50.0

```

##### 3. `Str`  :문자 이것을 사용하면 숫자를 문자로 변환시킬수 있다.

```
x = int(input(“숫자를 입력하세요.:")
Y = int(input(“숫자를 입력하세요.:”)

sum = x + y
print(“두 수의 합은, sum, “입니다.")
>>>두 수의 합은 50 입니다.


50  과 입니다 <<<를 붙이고싶다 또는 
문자를 숫자로 바꾸기 위해서 str 필요하다.

print(“두 수의 합은”,`str`(sum),”입니다.”)

>>>>두 수의 합은 50입니다.



Print(1,2,3,4,end=“,”). <<< 콤마로 띄어쓴다.
print(1,2,3,4,sep=“,”)  <<<<  중간에 문자 집어넣기

```


