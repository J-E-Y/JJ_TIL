---
title: React with Babel or React with typescript
author: ''
date: '2020-03-11'
slug: react-with-babel-or-react-with-typescript
categories: []
tags: []
image:
  caption: ''
  focal_point: ''
---

# React with Babel [es6,jsx] 


![](/post/2020-03-11-react-with-babel-or-react-with-typescript_files/Screen Shot 2020-03-11 at 7.45.23 PM.png)

![](/post/2020-03-11-react-with-babel-or-react-with-typescript_files/Screen Shot 2020-03-11 at 8.04.29 PM.png)

바벨이란?

바벨은 컴파일러  버전이 틀린 자바스크립트 문법을 읽을수 있게 컴파일 해주는 것이다. 




### react를 돌리기 위해서는 필수적인 모듈이 필요하다. 
## 리엑트를 설정할때 필수적인것

1.Module bundler
webpack :     

2.Loader :  webpack 이 jsx 가 들어있는 파일을  컴퍼넌트를 작성한 파일을 읽고나서 설정하는 곳이  Lpader 이다. 
babel-loader : loader 중에 가장 필수로 들어가는게 바벨 loader이다.
바벨로드를 쓰기위해서 
babel-core 받아야하고
어떤 바벨을 쓸것이냐 babel-preset-env 받아야 하고
Jsx 를 transform하기 위해서는 
babel-plugin-transform-react-jsx
받아야 한다. 


3.react 
react 라이브러리
react-dom 최종 랜더가 리엑트돔






# React with Typescript


![](/post/2020-03-11-react-with-babel-or-react-with-typescript_files/Screen Shot 2020-03-11 at 7.45.52 PM.png)



![](/post/2020-03-11-react-with-babel-or-react-with-typescript_files/Screen Shot 2020-03-11 at 7.51.23 PM.png)


ts-loader 하는 일은 간단하다. 

웹팩에서 파일을 읽어서 타입스크립트를 자바스크립트로 변경해서 내려준다. 

ts loader 를 하기위해서 
ts loader 를 깔면 typescript 를 깔아야 한다. 
여기서는 Eslint 를 쓰지않고 tslint를 쓴다. 



