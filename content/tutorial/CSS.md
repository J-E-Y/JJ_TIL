---
title: CSS
date: 2019-04-29
draft: true
menu:
  tutorial:
    name: Css
    weight: 3
toc: true
type: docs
---

---
##  Css: **&lt;style&gt;tag**
---

* Syntax

```css
a {
  color:red
  }
```

* Note

<dd>a :  selector(선택자)</dd>
<dd>{Color:red}; : declaration (선언)</dd>
<dd>{Color} :  property (속성)</dd>
<dd>{Color:red} : property value (속성값)</dd>


---
##  Css: **BoxModel**
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


---
## Css: **wrapper** 
---



* Most basic example 

```css

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
```

* How the principle works

Create your wrapper and assign it a certain width. Then apply an automatic horizontal margin to it by using `margin: 0 auto;` or `margin-left: auto;` `margin-right: auto;.` The automatic margins make sure your element is centered.



---
##  Css: **group elements tag**
---


* <div>text</div>  : block element

* <span>text</span> :  inline element  
       the both : 디자인 용으로 쓰임 

* ID="적용할코드"  그리고 #  

```css
<style>

#grid {

</style> 
```

```html

<body>
  <div id="grid"> text </div>
</body>

```
}
# id 값으로 쓴gird는 중복이 안된다.
* grid-template-columns : 박스안에선긋고 나란히정렬
#grid {
    
* class=“묶을 이름” and . :caution *.saw and .active 순서가 바뀌면 컴퓨터는 최근에 명령때린 것에 명령을 우선순위로 한다.
<1h class="saw">web</h1>
<1h class="saw active">CSS</h1>

<style>

.saw {
    Color:red;
}
.active {
    Color:bule;
}

</style>

        
3.  media queries 
@media(max-width:800px) : 
screen width < 800px 스크린이 800px 보다 작을때 명령을 내린다.
@media(min-width:800px)  : screen width  > 800px스크린이 800px 보다 클때 명령을 내린다.
<style>
    @media(max-width:800px) {
        #grid {
            Display:block;
}

</style>

4. cashing 파일을 따로 만든후 저장해놓는것!!<link rel="stylesheet" href=“파일이름">
    

<!doctype html>
<html>
<title>web1 - Son</title>
<meta charset="ut-8">
<link rel="stylesheet" href="style.css">

<body>
  <h1><a href="index.html">web</a></h1>
<div id="grid">
  <ol>
  <li><a href="1.html">Father</a></li>
  <li><a href="2.html">Son</a></li>
  <li><a href="3.html">Spirit</a></li>
</ol>
<div id="article">
<h2>Son</h2>
<p>son is the expression
</p>
</div>
</div>
</body>
</html>

```


# grid-template-columns

* Description

> Defines the columns of a grid container. You can specify the width of a column by using a keyword (like auto) or a length (like 10px). The number of columns is determined by the number of values defined in the space-separated list.



* grid-template-columns: none;

>No columns are defined, so you only have one.

![](/tutorial/HTML_files/test1.png)

* grid-template-columns: auto auto auto;

>You can use the keyword auto so that each column resizes itself automatically.
![](/tutorial/CSS_files/test2.png)


* grid-template-columns: 80px auto 1rem;

>You can mix the units.

![](/tutorial/CSS_files/test3.png)

* grid-template-columns: 40px 1fr 2fr;

>You can use the fr flex unit to distribute the remaining space across all flex columns.

![](/tutorial/CSS_files/test4.png)


