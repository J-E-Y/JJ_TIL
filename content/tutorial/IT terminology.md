---
title: Technical terms
date: 2019-04-29
draft: true
menu:
  tutorial:
    name: 1.Technical terms
    weight: 2
toc: yes
type: docs
---

## UI&UX

#### UI (user Interface)
  
  * The user interface (UI), in the industrial design field of human–computer interaction, is the space where interactions between humans and machines occur

  * 사용자가 제품이나 서비스를 마주할때 말하는 용어
  * 아이폰을 보고 있으면 아이폰 UI
  * 자판기를 보고 있으면 음료자판기 UI


#### UX (user experience)

  * refers to a person's emotions and attitudes about using a particular product, system or service. It includes the practical, experiential, affective, meaningful and valuable aspects of human–computer interaction and product ownership. Additionally,

  * 사용자가 제품이나 서비스의 UI를 마주할 때 익숙하게 사용할 수 있도록 하는 요소
  * 저런 문구의 UI이를 UX로 전환하면  우리가 보는 핸드폰다이어리 구조가 완성된다.


![](/tutorial/IT terminology_files/2.png)

## NAT

* Network Address Translation



* NAT 이란 무엇인가?

  * User 가 웹사이트에 접촉하려고 할때 IP주소가 같지 않아 불가능 하다.하지만 NET이라는 기능으로 인해 private IP주소를 public IP주소로 바꿔주어서 interface 가능하도록 도와준다 


* 또한 다음에 또 접촉하려고 했을때 원활한 접근을 위해 기록해둔다 

  *  NET 은 두가지를 한다
  * 접촉할수있게 사용자의 IP주소를 pubilc IP 주소로 바꿔준다.
  * 다음 원활한 접근을 위해 기록해둔다


![](/tutorial/IT terminology_files/1.png)




## port


* Port 란?

  * 컴퓨터의 Lan선은 하나인데 통신을 필요로 하는 프로그램이 다수일 때 이 다수의 프로그램을 구별할 수 있는 번호가 Port이다.




![](/tutorial/IT terminology_files/port.png)





## port forwarding


* 포트포워딩 (Port Forwarding)이란?

  * 포트 포워딩(port forwarding) 또는 포트 매핑(port mapping)은 컴퓨터 네트워크에서 패킷이 라우터나 방화벽과 같은 네트워크 게이트웨이를 가로지르는 동안 하나의 IP 주소와 포트 번호 결합의 통신 요청을 다른 곳으로 넘겨주는 네트워크 주소 변환(NAT)의 응용이다.

  * 쉽게 설명하면 부여받은 IP가 외부에서 내 장치에 접근할 수 있도록 포트, 즉 문을 열어주는 것입니다.
  

* 언제 Port forwarding 사용하는가?


  * Web server를 자신의 컴퓨터부터 시작하고 싶을때 port forwarding 을 사용해야 한다.

* How dose port forwarding work ? 

  * 사람들이 나의 컴퓨터로 들어오기 위해서는 public IC주소 (wan IP주소를) 알려주어야 한다. `BUT`사람들이 Public IP주소로 들어오면 어느곳으로 이동해야하는지 모른다.

  * 이것을 실행하기 위한것이 port forwarding 이다. 

  * How to convert it ? Router port forwarding 설정을 하면된다.



![](/tutorial/IT terminology_files/prot for1.png)


* ```내부 IP주소가 web server 를 설치할 컴퓨터IP이고```
* ```외부 IP주소가 나의 public IP에 주소를 만들 port 번호 이다.```


![](/tutorial/IT terminology_files/2.png)

![](/tutorial/IT terminology_files/4.png)

![](/tutorial/IT terminology_files/3.png)











## URL 

![](/tutorial/IT terminology_files/Screen Shot 2019-12-16 at 6.07.41 PM.png)


* 첫번째 URL 

* protocol

> indicates how to access the resource 

* IP address and URL name  

> the computer where the resource is located 

* port 

> can be running multiple network applications

* resource

> the web server uses this info to identify the resource

* 두번째 URL Query string

* ? 문자가 보이면 쿼리 

> passing some info to the web server ? 바로 질러서 접근할수 있게 해준다.



* 세번째 URL Fragment


  * # 보이면 재빨리 찾아서 보내준다. 
 
> 만약 이것이 없다면 resource 가 web sever 에 가서 저장된 모든 것들을 찾아야 하기 때문이다. 



* encoding

![](/tutorial/IT terminology_files/Screen Shot 2019-12-16 at 6.15.13 PM.png)


> 문자를 다른현태로 바꿔주는것

* 더공부할 내용

  * ASCII / ANSI / EUC-KR / CP949 / UTF-8 / UNICODE



## Client & sever


> HTTP://www.santaged.name/2014/07/up=andnwjkd.thml

* HTTP : 프로토콜

* www.santaged.name: 웹서버

* 2014/07/up=andnwjkd.thml : web Resource in web sever



*  FTP_protocol & HTTP_protocol


  * HTTP_Protocol 은  is merge protocol in the web client and the web server

  * FTP protocol is used for transferring files



  * What is Web Resource  

  * 간략 하게 말해서 a web client 가 PDC or HTML Document 등등을 web server 를 통해서 접근하는 것들을 web Resource 라고 한다. 

  * web resource 안에는 `static` 와 `dynamic` resource 가 담겨있다.

> Statice resource 는 바뀌지 `않는` 정보들을 말하고 

> Dynmic resource 는 web client 에서 `바꾼` 정보드를 반영하는 것들을 말한다. 



* HTTP Transaction & a stateless protocol

![](/tutorial/IT terminology_files/Screen Shot 2019-12-16 at 5.26.30 PM.png)

  * a stateless protocol 

  * a web client  가 요청한 것을 web sever 는 web resource 에서 가져온다. 
  다음번에 가져올때 이것을 기억못하게 되고 다시 새로운 a web client 가 web sever 에게 접근하게 되는 과정을 a stateless protocol 이라고 한다. 


* HTTP Transaction
  
  * a web client 가 web sever 에게 요청을 보내고 그 요청된것을 Response 하는 과정을 HTTP Transaction 이라고 부른다. 
  


## HTTP 


* HTTP : `H`ypertext `T`ransfer `P`rotocal


![](/tutorial/IT terminology_files/Screen Shot 2019-12-16 at 5.43.03 PM.png)


* it's this combination if HTTP and URL that makes the web work.

![](/tutorial/IT terminology_files/Screen Shot 2019-12-16 at 5.51.55 PM.png)



## HTML & Internet



* HTTP HTML 

* HTTP : `H`ypertext `T`ransfer `P`rotocal

* HTML : `H`ypertext `M`arkup `L`anguage 



* 1. 브라우저에서 주소를 치면 나의 컴퓨터는 서버컴퓨터에 `요청(get)`한다.
* 2. 요청할때 이루어지는 언어가 바로 `HTTP` 로 이루어 져 있다. 
* 3. 서버는 요청받은 내용을 `브라우저` 에게 `HTML` 언어로 `전달`해준다. 


* HTTPS


  * HTTPS : `H`yperText `T`ransfer `P`rotocol `S`ecure

  * 해커들을 방지하기 위해 만들어져 보호시켜주는 시스템

  *  (HTTPS) is an extension of the Hypertext Transfer Protocol (HTTP).


  * SSL : `S`ecure `S`ockets `L`ayer

  * TLS : `T`ransport `L`ayer `S`ecurity




* 1.IP 와 DNS


  * IP : `I`nternet `P`rotocol

  * 간단히 말해서 컴퓨터의 주소 IP

> IP 주소는 전통적으로 32비트 길이를 가지고 있고 지금은 128비트 긴주소를 사용한다. 



* 2.DNS

  * DNS : `D`omain `N`ame `S`ystem

  * DNS  는 

![](/tutorial/IT terminology_files/Screen Shot 2019-12-16 at 3.47.39 PM.png)

* 어떻게 `DNS`는 무엇을 하는가? 

  * 1.사용자가 웹다른 사이트를 가고싶을때 검색을 하게 된다. 

  * 2.그럴때 IP 주소를 알야아 하는데 

  * 3.그럴때 우리 컴퓨터 안에있는 DNS 가 IP주소를 찾아서 알려준다. 

  * 4.DNS 하나가 모든 정보를 가지고 있지 않기 때문에 친구들에게 물어봐서 알려준다. 


*DNS 원리과 위험성*

* 원리

  * DNS 가 하나라면 혼잡하기 때문에 나눠서 연결되도록 설계 되었다.

  * 지역을 나누는 것이다. 

  * 예)

![](/tutorial/IT terminology_files/Screen Shot 2019-12-16 at 4.04.29 PM.png)




* DNS 서버는 정부나 교육기관을 위한 공개되어 있고 누구나 사용 가능한 커뮤니케이션 프로토콜로 제작되었습니다. 


*위험성*
  * DNS SPOOFING 이라 불리는 것은 해커들이 DNS 서버에 침입해서 주소를 바꿔서 사용자를 다른곳으로 보내버린다. 


* 3.패킷 과 라우터


* 패킷  (packet)


###### 정보를 주고받을때 패킷을 통해 전단된다. 

![](/tutorial/IT terminology_files/Screen Shot 2019-12-16 at 4.08.03 PM.png)

###### 용량이 많을때 나눠서 보낸다. 

![](/tutorial/IT terminology_files/Screen Shot 2019-12-16 at 4.09.25 PM.png)

* 라우터 

> 패킷을 `관리`하는 것이 라우터 

> 패킷을 나눠서 보낼때 충돌과 교통이 혼잡 할수가 있다 이것을 방지하기 위해 라우터가 그것을 통제한다. 

> 도착 순서를 다르게 만든다. 

![](/tutorial/IT terminology_files/Screen Shot 2019-12-16 at 4.10.04 PM.png)



* TCP

  * TCP : `T`ransMission `C`ontrol `P`rotocol 전송 제어 프로토콜


> TCP 는 전송중 끊어진 것들을 다시 원활하게 다시 전송할수 있게 만드는 아주 안전한 메일 시스템과 같은 것이다. 

> TCP 가 다 모든 패킷 (사용자가 보낸 정보)  가 도착했는지 확인하고 공유한다. 






## URL & URI



* URL 과 URI 의 차이점 

> `URL`(Uniform Resource Locator) : 네트워크상에서 자원이 어디있는지를 알려주는 주소. 정의 뜻으로는 어떤 차이가 있는지 구별이 어렵다.

> `URI`(Uniform Resource Identifier) : 인터넷에 있는 자원을 식별할 수 있는 유일한 문자열 주소로, 인터넷에서 요구되는 기본조건으로 인터넷 프로토콜과 항상 함께 붙어 있다.





* 예) 주소로 차이점을 느껴보자.

  *  http://localhost:8080/profile.jsp의 뜻은 localhost라는 서버에 profile.jsp 라는 자원이 있다는 걸 알려주는 주소다. 자원의 위치를 알 수 있는 주소기에 uri도 되며 url도 된다.


  *  http://localhost:8080/profile.jsp?addr=seoul&age=22 로 url 의 끝에 쿼리 문자열이 붙으면, 이런 주소는 url이 아닌 uri 이다.

  * 간단하게 그냥 서버에 있는 자원의 위치 주소에다가 요청 처리에 필요한 값이 포함여부의 차이를 보면 될것 같다. 

`갑이 포함되면 uri, 포함 안되면 url.`







## JavaScript 와 ECMAScript

* JavaScript는 1996년에 만들어졌고, 그 다음에 JavaScript의 표준화를 위해 1997년에 ECMAScript가 만들어졌습니다. 당시 기준에서 JavaScript는 ECMAScript 사양을 따르고 있었기 때문에, JavaScript는 ECMAScript 사양을 준수하고 있던 언어의 예시였습니다.

* 여기서 우리는 재미있는 사실을 하나 알 수 있습니다. 바로, ECMAScript는 JavaScript를 기반으로 하는 동시에, JavaScript 역시 ECMAScript를 기반으로 한다는 거죠.

* 둘의 뗄레야 뗄 수 없는 관계, 그리고 그 두 용어가 혼용되어서 사용되던 이유는 바로 여기에서부터 출발하지 않았을까 생각해봅니다.


## Web storage

* Web storage (웹 스토리지)


  * local storage는 우리가 아는 세션과 비슷하고 session storage는 쿠키와 비슷합니다.
자바스크립트로만 읽고 쓰기가 가능해 서버에서 바로 접근할 수 없고 문자열만 관리가 가능하다는 단점이 있습니다.

  * 하지만 매번 서버로 전송해야하는 쿠키와 달리 불필요한 트래픽이 없고상대적으로 여유로운 저장공간에 문자열을 객체 정보로 저장할 수 있다는 강점이 있죠.

  * 로컬 스토리지는 만료 기간의 설정이 없기 때문에 브라우저의 종료와 관계 없이 정말 영구적으로 데이터를 저장할 수 있습니다.os를 재설치 하거나 브라우저를 날려버리는 특수한 상황을 제외하고서요.

  * 또한 모든 페이지가 사용자릐 로컬 스토리지를 공유하고 브라우저창에 관계없이 사이트 별로 생성 됩니다.

  * 세션 스토리지는 브라우저 종료시 사라지고, 새 탭이나 다른 브라우저에서 공유할 수 없습니다. 하나의 페이지 안에서 저장되고 살아있는 데이터라고 생각하시면 됩니다. 우리가 하나의 사이트를 접속하면 하나의 세션이 이루어지는 원리입니다.

![](/tutorial/IT terminology_files/7D12ECCA-909C-4AE9-8788-58DCD391293F.png)




## Proxy sever


![](/tutorial/IT terminology_files/BD37F54D-B97E-41B5-BEEF-E92F3E0BAFF9.png)


## TLS

#### TLS (Transport Layer Security,)

> 클라이언트/서버 응용 프로그램이 네트워크로 통신을 하는 과정에서 도청, 간섭, 위조를 방지하기 위해서 설계되었다. 그리고 암호화를 해서 최종단의 인증, 통신 기밀성을 유지시켜준다.


## CPU 

#### 중앙 처리 장치 또는 CPU (central processing unit) 

* CPU 처리하는 용도 데이터를 읽고  처리하고  다시쓰는  동작을 합니다. 


* 컴퓨터 시스템을 통제하고 프로그램의 연산을 실행하는 가장 핵심적인 컴퓨터의 제어 장치, 혹은 그 기능을 내장한 칩을 말한다. 컴퓨터 안의 중앙 처리 장치(CPU)는 외부에서 정보를 입력 받고, 기억하고, 컴퓨터 프로그램의 명령어를 해석하여 연산하고, 외부로 출력하는 역할을 한다. 따라서 중앙 처리 장치(CPU)는 컴퓨터 부품과 정보를 교환하면서 컴퓨터 시스템 전체를 제어하는 장치로, 모든 컴퓨터의 작동과정이 중앙 처리 장치(CPU)의 제어를 받기 때문에 컴퓨터의 두뇌에 해당한다고 할 수 있다. 

* 실제의 CPU 칩엔 실행 부분뿐만 아니라 캐시 등의 부가 장치가 통합된 경우가 많다.
CPU에는 MCU(Micro Control Unit)와 주변 장치(외부 확장 장체에 관한 IC)가 다 들어있는 Soc(System On Chip)가 있다. 주변 IC가 따로 달려 있을 경우, 그것은 MCU라고 할 수 있다


## SSL


#### SSL (Secure Sockets Layer)  보안 소켓 계층

*월드 와이드 웹 브라우저와 웹 서버 간에 데이터를 안전하게 주고받기 위한 업계 표준 프로토콜. 미국 넷스케이프 커뮤니케이션스사가 개발했고, 마이크로소프트사 등 주요 웹 제품 업체가 채택하고 있다. SSL은 웹 제품뿐만 아니라 파일 전송 규약(FTP) 등 다른 TCP/IP 애플리케이션에 적용할 수 있으며, 인증 암호화 기능이 있다. 

* 인증은 웹 브라우저와 웹 서버 간에 서로 상대의 신원을 확인하는 기능이다. 예를 들면, 웹 브라우저를 사용하는 웹 서버를 사용한 가상 점포의 진위(眞僞) 여부를 조사할 수 있다. 암호화 기능을 사용하면 주고받는 데이터가 인터넷상에서 도청되는 위험성을 줄일 수 있다.




## 메소드란?


#### 객체안에 함수가 들어있는것이 메소드

```js

// 객체 만든다 
// obj 의 키는 foo
// foo 의 값은 function()
// obj.foo() 메소드 호출한것이다. 
obj = {
    foo: function () {
        return “hello world”
    }
  }

obj.foo() // “hello world” 
// 

```

## ASCII(아키스) 



#### 아키스 코드란 무엇인가?

* ASCII (American Standard Code for Information Interchange, 미국 정보 교환 표준 부호)

* 영문 알파벳을 사용하는 대표적인 문자 코딩

* 컴퓨터는 0과 1 숫자 밖에 모르기 때문에 문자도 숫자로 기억합니다. 이때, 어떤 숫자와 어떤 문자를 대응시키는가에 따라 여러 가지 인코딩 방식이 있는데 통상 아스키 코드 방식을 많이 사용합니다.

* 아스키 코드(ASCII Table)는 0번부터 127번까지만 사용합니다. 127번 이후 코드를 사용했던 적도 있었는데 이는 표준이 아니며 운영체제마다 다른 코드(문자)를 배치했기 때문에 호환이 되지 않습니다. 윈도우즈 운영체제는 현재 128번부터 255번 사이에 포함된 문자를 출력하려는 시도에 대해 물음표(?)를 출력해서 사용하면 안된다는 것을 알려줍니다. 128번과 255번 문자는 물음표는 아니지만 사용할 수 없는 문자입니다.


#### ASCII Table (아스키 코드표 )

![](/tutorial/IT terminology_files/ASCII Table.png)



#### ex)

* alphabetPosition 함수 만들기

* In this exercise, you are required to, given a string, replace every letter with its position in the alphabet. (문자열이 주어졌을때, 각각의 문자를 알파벳의 몇번째 인지 숫자로 바꾸는 함수를 작성하세요.) If anything in the text isn't a letter, ignore it and don't return it. a being 1, b being 2, etc. (만약 문자가 알파벳이 아니라면, 무시하고 결과값에 포함하지 마세요. a 는 1, b 는 2, 등등 으로 변환됩니다.)


* output

```js
alphabetPosition("The sunset sets at twelve o' clock."); 
// "20 8 5 19 21 14 19 5 20 19 5 20 19 1 20 20 23 5 12 22 5 15 3 12 15 3 11"

```


```js

var alphabetPosition = function (str) {
 // Your code here
 let output = [];
 // 1. 배열로 바꾼다
 let temp = str.toUpperCase();
 // 2. THE SUNSET SETS AT....
 for(let i=0;i<temp.length;i++){
   if(typeof(temp[i]) ==='string'){
     if(temp[i].charCodeAt(0) - 64 > 0)
       output.push(temp[i].charCodeAt(0) - 64);
   }
 }
 return output.join(' ');
}



```






