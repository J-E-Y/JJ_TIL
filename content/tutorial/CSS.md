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
##  Css: **@media queries**
---


* @media(max-width:800px) :  screen width < 800px 스크린이 800px 보다 작을때 명령을 내린다.

* @media(min-width:800px)  : screen width  > 800px스크린이 800px 보다 클때 명령을 내린다.


```css

    @media(max-width:800px) {
    p {
        font-size: 1px
        font-weight
        font-height
        Display:block;
  }
}

```

---
##  Css: **grid-template-columns**
---


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
