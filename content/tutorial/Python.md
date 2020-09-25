---
title: Python
date: 2019-04-29
draft: true
menu:
  tutorial:
    name: 6.Python
    weight: 6
toc: yes
type: docs
---



---
###  Python: **Operators**
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
###  Python: int float str
---


##### 1.`int`: 정수

```
x = input("숫자를 입력해주세요.:")
Y = input("숫자를 입력해주세요.:”)

x = 20
y = 30

Print(x+y)
>>>2030



x = `int`(input("숫자를 입력해주세요.:"))
Y = `int`(input("숫자를 입력해주세요.:"))

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
x = int(input("숫자를 입력하세요.:")
Y = int(input("숫자를 입력하세요.:")

sum = x + y

print("두 수의 합은, sum, "입니다.")
>>>두 수의 합은 50 입니다.


50  과 입니다 <<<를 붙이고싶다 또는 
문자를 숫자로 바꾸기 위해서 str 필요하다.

print("두 수의 합은"",`str`(sum),"입니다.")

>>>>두 수의 합은 50입니다.



Print(1,2,3,4,end=","). <<< 콤마로 띄어쓴다.
print(1,2,3,4,sep=",")  <<<<  중간에 문자 집어넣기

```




---
###  Python:Format_string
---


###### format 명령

##### [데이터타입] : s(문자열), c(한글자), d(정수), f(실수)



* example exercise 1-1


```
foramt_string = "섭씨 35도는 화씨 99도 입니다."

foramt_string = "섭씨 %f도는 화씨 %f도 입니다."


msg = foramt_string % (35.7, 99.23)
print(msg)

f 는 소수점 처리를 할수 있다.


foramt_string = "섭씨 '%0.2f'도는 화씨 '%-.4f'도 입니다."
msg = foramt_string % (35.7, 99.23)
print(msg)
```


















---
##  Python: Variables
---

> ariables are containers for storing data values.

* Example

```
x = 5
y = "John"
print(x)
print(y)
```


---
##  Python: conditional
---


```

if (a > b):
    [처리문 실행문]
elif [조건문 조건식]:
    [실행문 처리문]
else:
    [실행문]
"""
# 조건식 : 명제 -> 참과 거짓으로 판별할 수 있는 구문
# 참과 거짓 : True False
# a > b, a < b, a >= b, a <= b, a == b, a != b
# and, or
# not
# 0, "", False, []
# 상태 : empty


if not empty:
    청소를 한다.

a = 7
b = 8
c = 9
a > b and a > c
a > b or a > c
not (a > c)

a < b
a >= b
a <= b
a == b
a != b    
    
```
* Example


```
a = int(input("당신의 출생연도를 입력해주세요.:"))


age = 2019 - a + 1


if age >= 20:
print("당신은 성인입니다.”)

```



* Example


```
a = int(input("당신의 출생연도를 입력해주세요.:"))

age = 2019 - a + 1

if age >= 20:
print("당신은 성인입니다.")

else:
print("당신은 성인이 아닙니다.")
```


* Example exercise 1-1


```
# 사용자의 키와 체중을 입력받아서
# bmi 계산하여 출력하세요
# bmi = 체중(kg) / (키(m)의 제곱)


height = input("키를 입력하세요 : ")
height = float(height)




weight = input("체중을 입력하세요 : ")
weight = float(weight)


bmi = weight / ((height/100)**2)




# 키와 체중을 입력받고
# bmi 계산하고
# 18.5 미만 = 저체중
# 18.5 이상 23 미만 = 정상체중
# 23 이상 = 과체중


bmi_level = ""
if bmi < 18.5:
    bmi_level = "저체중"
elif 18.5 <= bmi < 23:
    bmi_level = "정상체중"
else:
    bmi_level =  "과체중"
print(bmi,bmi_level)

```

* Example exercise 1-2



```

# 섭씨 -> 화씨로 바꾸는 프로그램
# 화시 -> 섭씨로 바꾸는 기능
# 메뉴 입력 시작
print("-----MENU-----")
print("1. 섭씨 -> 화씨 변환")
print("2. 화씨 -> 섭씨 변환")
print("3. 프로그램 종료")
menu = input("메뉴를 선택하세요 : ")
# 메뉴 입력 끝


# 온도 계산 시작
if menu == "1":
    C = input("섭씨 온도를 입력하세요 : ")
    C = float(C)
    F = C * 1.8 + 32
    msg = "섭씨 "+str(C)+"도는 화씨 "+str(F)+"도 입니다."
    print(msg)
elif menu == "2":
    F = input("화씨 온도를 입력하세요 : ")
    F = float(F)
    C = (F - 32) / 1.8
    msg = "화씨 "+str(F)+"도는 섭씨 "+str(C)+"도 입니다."
    print(msg)
elif menu == "3":
    print("프로그램을 종료합니다.")
else:
    print("잘못 선택하셨습니다.")
```


---
##  Python: try, except
---


```

try:
    #[오류가 날지도 모르는 코드]
    a = int("a")
    print("in")
except ValueError:
    #[발생한 오류에 대응할 코드]
    print("fired exception")
except ZeroDivisionError:
    #[발생한 오류에 대응할 코드]
    print("fired exception")
except:
    #[발생한 오류에 대응할 코드]
    print("fired exception")
else:
    #[오류가 없이 지나왔을 경우 코드]
    print("no error")
finally:
    #[어쨋든 실행될 코드]
    print("anyway")
```

* exercise 1-1

```

number = input("정수를 입력하세요 : ")
try:
    number = int(number)
except ValueError:
    print("정수가 아닙니다. 다시 입력하세요.")
    number = input("정수를 입력하세요 : ")
    number = int(number)


result = number*number
print(result)


# 입력받은 정수의 제곱 값을 출력하는 프로그램
# 만약 숫자가 아니라면 다시 입력하라는 메시지를 출력한다.
# 다시 입력 하라는 메시지는 1회만
```


---
##  Python: While 
---

```

while [조건식]:
    [실행문]
    [실행문]
    [실행문]
    [실행문]

"""
1 예) 이런식으로 많이 쓰인다.

While True:
    Try:
    Break
    except
2 예)


while True:
    # 정수를 입력받는다. 정수가 입력될 때까지
    number = input("정수를 입력하세요 : ")
    try:
        number = int(number)
        break
    except:
        print("정수가 아닙니다. 다시 입력하세요.")


print(number)
```

* exercise

```

# 섭씨 -> 화씨로 바꾸는 프로그램
# 화시 -> 섭씨로 바꾸는 기능
# 메뉴 입력 시작
print("-----MENU-----")
print("1. 섭씨 -> 화씨 변환")
print("2. 화씨 -> 섭씨 변환")
print("3. 프로그램 종료")
menu = input("메뉴를 선택하세요 : ")
# 메뉴 입력 끝


# 온도 계산 시작
if menu == "1":
    while True:
        try:
            C = input("섭씨 온도를 입력하세요 : ")
            C = float(C)
            break
        except:
            print("다시 입력하세요.")


    F = C * 1.8 + 32
    msg = "섭씨 "+str(C)+"도는 화씨 "+str(F)+"도 입니다."
    print(msg)
elif menu == "2":
    while True:
        try:
            F = input("화씨 온도를 입력하세요 : ")
            F = float(F)
            break
        except:
            print("다시 입력하세요.")
    C = (F - 32) / 1.8
    msg = "화씨 "+str(F)+"도는 섭씨 "+str(C)+"도 입니다."
    print(msg)
elif menu == "3":
    print("프로그램을 종료합니다.")
else:
    print("잘못 선택하셨습니다.")

```
---
###  Python: for
---

* Description

```
# for [name] in [bucket]:
#     [실행문]
```

```

for n in range(10):
    print(n)
    print(n*n)

```



###### for, range 활용해서 1~100까지의 홀수의 합을 구하는 프로그램


```
total = 0
for x in range(1,101,2):
    total += x
    total = total + x
print(total)

```
```
# "Range는 횟수 용으로 많이 쓰인다."
# range(Y) : 0 ~ Y-1까지
# range(X,Y) : X ~ Y-1까지
# range(X,Y,Z) : X ~ Y-1까지인데, Z씩 증감
```
```
for n in range(0,12.2):
    print(n)
2
4
6
8
10
```

---
###  Python: Module
---


```

import datetime
변수 = datetime.datetime.now()
Print(변수)
Print(변수.strftime(“%y-%m-%d"))
Print(변수.year)
Print(변수.hour)
Print(변수.corosecond)

```
###### 윤년 프로그램 
```
# 윤년 프로그램을 짜본다.
# 윤년 2월 29일까지 있는 해
# 연도가 400으로 나누어 떨어지면 윤년
# 연도가 100으로 나누어 떨어지면 윤년 x
# 연도가 4로 나누어 떨어지면 윤년
# 1. 올해의 윤년여부 출력
# 2. 사용자의 입력을 받아서 윤년 여부 출력
# 3. 프로그램 종료
```

```

import datetime
while True:
    print("----Menu----")
    print("1. 올해 윤년 여부")
    print("2. 입력 받은 연도 윤년 여부")
    print("3. 프로그램 종료")
    menu = input("메뉴를 선택하세요 : ")


    if menu == "1":
        current_time = datetime.datetime.now()
        year = current_time.year
        if (year % 4 == 0 and year % 100 !=0) or year % 400 == 0:
            print("윤년입니다.")
        else:
            print("윤년이 아닙니다.")
    elif menu == "2":
        while True:
            try:
                year = input("판별하고자 하는 연도를 입력하세요 : ")
                year = int(year)
                break
            except:
                print("다시 입력하세요.")
        if (year % 4 == 0 and year % 100 !=0) or year % 400 == 0:
            print("윤년입니다.")
        else:
            print("윤년이 아닙니다.")
    elif menu == "3":
        break
        # exit()
    else:
        print("없는 메뉴 입니다.")

```


---
##  Python: function
---

```
# def [함수이름]([매개변수,입력값]):
#     [실행구문]
#     [return (반환값, 출력값)]
```

* example 1-1

```
A = 1
B = 2
x = 1+2
Print(x)

>>>3

함수 이용하기

def x (A,B) : 
    return A+B
print (x(1,2))

>>>3

```
* example 1-2

```
def sayHi():
    print("Hello Python")


sayHi()

```

* exercise 1-2

```

# 1~9까지의 각각의 제곱을 출력하는 함수를 만드세요.
def PrintSquare():
    for x in range(1,10):
        print(x*x)


PrintSquare()
PrintSquare()
PrintSquare()
PrintSquare()
PrintSquare()


def PrintSquare2(endNumber):
    for x in range(1,endNumber+1):
        print(x*x)


PrintSquare2(10)


```

* exercise 1-3

```
# 두개의 숫자를 전달 받아서
# 그 두 숫자의 합을 출력하는 함수
def printSum(number1, number2):
    print(number1+number2)


printSum(10, 22)

```

* exercise 1-4

```
# 별줄수 만들기

"""
사용자에게 줄 수를 입력받아서
해당 줄 수만큼 별을 출력하시오.
   *
  ***
 *****
"""


line_count = input("출력할 줄 수를 입력하세요 : ")
line_count = int(line_count)


max_width = line_count*2 - 1
format_string = "{:^"+str(max_width)+"s}"
for count in range(line_count):
    #blank_count = line_count-(count+1)
    #print(" " * blank_count, end="")
    start_count = 2 * count + 1




    msg = format_string.format("*"*start_count)
    print(msg)

   *
  ***
 *****

```

---
###  Python: Crawler
---


##### 1. 변수만들어서 저장하기 data.text 모든 리소스 불러오기

```

url = "https://www.naver.com/"
requests.get(url)
data = requests.get(url)
print(data.text)

```


##### 2. 제대로 돌아가고 있는지 확인


```
print (data.status_code)

“””
200
“””

200번대 - 정상
300번대 - redirect
400번대 - 리소스 오류
500번대 - 소스코드 오류
```



##### 3. Test 해보기 만약 이게 맞다면 응답해라

```

if data.status_code == requests.codes.ok:
    print("work out”)


```


##### 4. From bs4 import BeautifulSoup HTML를 해석해주는 역활 


```

Parsing(파싱) text 파일을 우리가 원하는 것을 불러오기 위해서는       parsing 필요하다.이럴때 BeautifulSoup 이라는 order 필요.

    html = BeautifulSoup(data.text,"html.parser")
    links = html.select(".PM_CL_realtimeKeyword_list_base .ah_a”)



 나열방식이 틀림



    (1)     for index,keyword in enumerate ( links,start=1 ) :
            print(index,keyword)
        
1 <sdsdsdsd>
2 <sdsdsdsd>
3 <sdsdsdss>



    (2).   For keyword in links[:3]:
           For keyword in links[::3]:
           Print(keyword)



    (3)
    
    for link in links:
        rank = link.select_one(".ah_r").text
        keyword = link.select_one(".ah_k").text
        print(rank,keyword,link.attrs["href"])

    

1 왕종명 http://search.naver.com/search.naver?where=nexearch&query=%EC%99%95%EC%A2%85%EB%AA%85&sm=top_lve&ie=utf8
2 grn http://search.naver.com/search.naver?where=nexearch&query=grn&sm=top_lve&ie=utf8
3 백예린 http://search.naver.com/search.naver?where=nexearch&query=%EB%B0%B1%EC%98%88%EB%A6%B0&sm=top_lve&ie=utf8
4 붐붐파워 http://search.naver.com/search.naver?where=nexearch&query=%EB%B6%90%EB%B6%90%ED%8C%8C%EC%9B%8C&sm=top_lve&ie=utf8
5 2019 스타벅스 벚꽃 md http://search.naver.com/search.naver?where=nexearch&query=2019+%EC%8A%A4%ED%83%80%EB%B2%85%EC%8A%A4+%EB%B2%9A%EA%BD%83+md&sm=top_lve&ie=utf8
6 나르샤 http://search.naver.com/search.naver?where=nexearch&query=%EB%82%98%EB%A5%B4%EC%83%A4&sm=top_lve&ie=utf8
7 아소방 매트 http://search.naver.com/search.naver?where=nexearch&query=%EC%95%84%EC%86%8C%EB%B0%A9+%EB%A7%A4%ED%8A%B8&sm=top_lve&ie=utf8

"""

