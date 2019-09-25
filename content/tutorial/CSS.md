---
title: Css
date: 2019-04-29
draft: true
menu:
  tutorial:
    name: Css
    weight: 3
toc: true
type: docs
---



![](/tutorial/CSS_files/Screen Shot 2019-09-15 at 5.21.03 PM.png)


## &lt;style&gt; 
---

```css

/*syntax*/

<style>

a {
  color:red
  }

</style>



<dd>a :  selector(선택자)</dd>
<dd>{Color:red}; : declaration (선언)</dd>
<dd>{Color} :  property (속성)</dd>
<dd>{Color:red} : property value (속성값)</dd>

```





## 스크롤 만들기 


```html

<!--Vertical scroll bar in div which is a child of css grid column -->

<div class="A">
  <div class="B">
    <div class="C">search</div>
    <div class="D">
      <div class="E">1</div>
      <div class="E">2</div>
      <div class="E">3</div>
      <div class="E">4</div>
      <div class="E">5</div>
      <div class="E">6</div>
      <div class="E">7</div>
      <div class="E">8</div>
      <div class="E">9</div>
      <div class="E">10</div>
      <div class="E">11</div>
      <div class="E">12</div>
      <div class="E">10</div>
      <div class="E">11</div>
      <div class="E">12</div>
      <div class="E">10</div>
      <div class="E">11</div>
      <div class="E">12</div>
    </div>
  </div>
</div>

```


```js
// 먼제 부모 tag 에 grid 명령과 max-hight 을 준다. 

.A {
  max-height: 300px; /* matters */
  display: grid; /* matters */
  overflow: hidden; /* matters */
}


```

```css

html, body, .A {
  height: 100%; /* matters */
  width: 100%;
  margin: 0;
  padding: 0;
}

.A {
  max-height: 300px; /* matters */
  display: grid; /* matters */
  overflow: hidden; /* matters */
}

.B {
  display: grid; /* matters */
  overflow-y: auto; /* matters */
}

.D {
  overflow-y: scroll; /* matters */
}

.C {
  padding: 10px;
  background-color: #07f;
}

.E {
  padding: 10px;
  background-color: #eee;
}


```


![](/tutorial/CSS_files/Screen Shot 2019-09-25 at 8.37.27 PM.png)







## BoxModel
---

```css
{
font-size:20px;
text-align:center;
text-decoration:none; : 밑줄없애기
text-decoration:underline; : 언더라인 만들어라
Border-bottom:red 20px solid;
Border-right: lightblue 20px solid;
Border-right:none; (오른쪽에 있는 선 없애기)
Margin:20px; 가장자리
Padding:20px;
width:20px;  : 폭
Display:none; 
Display:block; : 전체화면을 이용해라 (block level element)
Display:inline; : 부분화면을 이용해라 (inline element)
}

```



## wrapper
---





```css

/* Most basic example */ 

#wrapper {
    width: 500px;
    margin: 0 auto;
}
```

```html

<body>
    <div id="wrapper">
        Piece of text inside a 500px width div centered on the page
    </div>
</body>

<!-- * How the principle works

Create your wrapper and assign it a certain width. Then apply an automatic horizontal margin to it by using `margin: 0 auto;` or `margin-left: auto;` `margin-right: auto;.` The automatic margins make sure your element is centered.
-->



```





## media queries
---




```css

/* @media(max-width:800px) :  screen width < 800px 스크린이 800px 보다 작을때 명령을 내린다.

@media(min-width:800px)  : screen width  > 800px스크린이 800px 보다 클때 명령을 내린다.
*/


    @media(max-width:800px) {
    p {
        font-size: 1px
        font-weight
        font-height
        Display:block;
  }
}

```


## Grid
---

![](/tutorial/CSS_files/Screen Shot 2019-09-23 at 11.52.20 AM.png)


```html


<div class = "container">

<div calss = "child1">1</div>
<div calss = "child2">2</div>
<div calss = "child3">3</div>
<div calss = "child4">4</div>
<div calss = "child5">5</div>
<div calss = "child6">6</div>
<div calss = "child7">7</div>
<div calss = "child8">8</div>
<div calss = "child9">9</div>

<div>


```

* HTML

```js

.container {
  
  display: grid;  // 처음 시작을 지정해준다. 
  grid-template-columns: 40% 60%; // 위에 있는 그림이 4대 6으로 나뉜다.  
  grid-template-columns: 4fr 6fr;  //  4대 6으로 나뉜다. 
  grid-gap:1rem; // 사이마다 공간을 줄때 4fr 6fr 로 쓰는것을 권장한다. % 로 사용하면 여백이 뒤에 생기기 때문.. 
  
  grid-template-columns: repeat(3, 1fr); // 이것은  1fr 이 세번 반복 
  grid-template-columns: 1fr 1fr 1fr; // 이것과 동일하다. 

  grid-template-columns: 200px 1fr; // 200 픽셀로 왼쪽 것을 고정하고 오른쪽 것을 늘리는 것이다. 

  grid-auto-rows: 200px; // 200 픽셀 씩 모두 통일
  grid-auto-rows: minmax(200px,auto); // 이것은 동일한데 content 늘어나면 같이 같이 늘어난다. 

}

```

* Css


```js

// 1번칸 늘리기 

.child1 {
  
  grid-column: 1/4 // 열에서 1부터 4까지 차지한다. 

}

```

![](/tutorial/CSS_files/Screen Shot 2019-09-23 at 9.44.12 AM.png)

```js

// 4번칸 밑으로 늘리기 

 gird-column:3; // 3번 열부터 시작해라 
 gird-row :2/4; // 2번부터 4버까지 차지하라 
 


```
![](/tutorial/CSS_files/Screen Shot 2019-09-23 at 9.45.18 AM.png)




```js

// 9번칸을 4번안에 집어넣는다. 
  
 gird-colum:3;
 gird-row:3/5;
 


```

![](/tutorial/CSS_files/Screen Shot 2019-09-23 at 9.47.05 AM.png)
