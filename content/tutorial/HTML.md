---
title: Html
date: 2019-04-29
draft: true
menu:
  tutorial:
    name: Html
    weight: 2
toc: true
type: docs
---

![](/tutorial/HTML_files/Screen Shot 2019-09-13 at 5.15.58 PM.png)


## &lt;strong&gt;
---

```js

/*

The HTML <strong> tag gives text a strong emphasis which traditionally means that the text is displayed as bold by the browser. 



Note 

what's the difference bewteen strong tag and b tag ?

strong tag :시각장애인들 낭독기를 사용할때 조금 더 굵 게 읽는다. 

b tag :평상시대로 굵게 읽는다.

*/

```


## &lt;h1&gt;
---

```html

<!--  

The HTML <h1> tag defines the highest level or most important heading in the HTML document. This tag is also commonly referred to as the <h1> element.

-->



<!--  Syntax-->


<body>
<h1>Heading 1 goes here</h1>
</body>


```




## &lt;br&gt;
---
 
```html


<!-- The HTML <br> tag defines a line break within text in the HTML document. This tag is also commonly referred to as the <br> element.-->


<!-- Syntax -->



<body>
<p>The paragraph starts here<br>
and ends on the next line.</p>
</body>



```



## `&nbsp;`  (making space)
---
 
 
```js

/*
HTML will only display one space between words, no matter how many times you press the space bar. To force an extra space to show up, type `&nbsp;` in the area where you want to force the space.

*/

```

## &lt;p&gt;
---


```html 

<!---
The HTML <p> tag defines a paragraph in the HTML document. This tag is also commonly referred to as the <p> element.-->

* syntax


<body>
<p>The paragraph goes here.</p>
</body>




```





## &lt;hr&gt;
---


```html

<!--

The HTML <hr> tag defines a thematic break between paragraphs in HTML5, and a horizontal rule in HTML 4.01. This tag is also commonly referred to as the <hr> element.

* Note

The HTML <hr> element makes line bewteen two paragraphs.

* Syntax

-->


<body>
<p>This is the first paragraph.</p>
<hr>
<p>This is the second paragraph.</p>
</body>

```



## &lt;div&gt;
---


```html

<!--

The HTML <p> tag defines a generic container in an HTML document that is generally used to group elements. This tag is also commonly referred to as the <p> element.

* Note
 
The HTML <p> element is found within the <body> tag.
The <div> tag is generally used to group elements together.

<p> :element is a block-level element.


* Syntax


-->

<body>

<div>
  <div>this is the type of elemnt </div>
</div>

</body>

```



## &lt;span&gt;
---

```html

<!--

`height 와 width 적용이 안된다.` 하지만 Disply 사용해서 적용할수 있다 


The HTML <span> tag defines a generic inline container in an HTML document. This tag is also commonly referred to as the <span> element.

Note

<span>  tag is is generally used for styling purposes when there is no other element to use.
<span>  tag is a inline-level element
<span> tag does not inherently represent anything


Syntax

-->

<body>
<p><span>Span text goes here</span> and not here</p>
</body>

<body>
<p><span class="red_text">Span text goes here</span> and not here</p>
</body>

```


## &lt;nav&gt;
---


```html

<!--

The HTML <nav> tag is an HTML5 element that defines a section with navigation links in the HTML document. This tag is also commonly referred to as the <nav> element. It is used to define a block of navigation links, either within the current document or to other documents


* Note

 The <nav> tag is used to create navigation in the HTML document.For IE browsers older than IE 9, use HTML5shiv which is a javascript workaround to provide support for the new HTML5 elements such as: <header>, <main>, <article>, <section>, <aside>, <nav>, <footer>.


* Syntax

-->



<body>
<nav>
  <ul>
    <li><a href="/section1/index.html">Section1</a></li>
    <li><a href="/section2/index.html">Section2</a></li>
    <li><a href="/section3/index.html">Section3</a></li>
  </ul>
</nav>
</body>

```




## &lt;ul&gt; (부모태그)
---


```html

<!--

* Description

The HTML <ul> tag defines an unordered list in the HTML document. This tag is also commonly referred to as the <ul> element.

* Note

The HTML <ul> element is found within the <body> tag.
The <ul> tag is made up of <li> tags.
Use the <ul> tag when the list items have no numerical ordering.
You can nest <ol>, <ul> and <ul>menu lists.

* Syntax


-->


<body>
<ul>
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ul>
</body>


```


## &lt;li&gt;(부모태그)
---


```html

<!--

* Description

>The HTML <li> tag defines a list item in <ol>, <ul> or <menu> in the HTML document. This tag is also commonly referred to as the <li> element.


* Syntax

-->


<body>
<ul>
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ul>
</body>




<body>
<ol>
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ol>
</body>



* Sample Output 2


<body>
<menu type="toolbar">
  <li>
    <menu label="File">
      <button type="button" onclick="new()">New</button>
      <button type="button" onclick="save()">Save</button>
    </menu>
  </li>
  <li>
    <menu label="Edit">
      <button type="button" onclick="copy()">Copy</button>
      <button type="button" onclick="paste()">Paste</button>
    </menu>
  </li>
</menu>
</body>

<!--
* Note

The <li> tag is used within <ol>, <ul> or <menu>.
You can nest <ol, <ul> and <menu> lists. (자식태그) li 태그는 반드시 부모태그를 가지고 있다. 

-->

```

---
## html : **&lt;ol&gt;tag** 
---


```html

<!--

* Description

>The HTML <ol> tag defines an ordered list in the HTML document. This tag is also commonly referred to as the <ol> element.

* Syntax

-->




<body>
<ol>
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ol>
</body>


<!--

* Note

The <ol> tag is made up of <li> tags. 
Use the <ol> tag when the list items have numeric, meaningful ordering.
You can nest <ol>, <ul> and <menu> lists.

-->

```



## container 
---


```html

<!--

* Description

In HTML, the container is the area enclosed by the beginning and ending tags. For example < HTML > encloses an entire document while other tags may enclose a single word, paragraph, or other elements. In HTML code, all container must have a start and stop tag to close the container. Without a stop tag the start tag will apply to the entire document.
 

-->



<html>
  <head>
    
  </head>
  <body>
    <div id="container">
      
    </div>
  </body>
</html>





<!--

 * note
 
 The container div, and sometimes content div, are almost always used to allow for more sophisticated CSS styling. The body tag is special in some ways. Browsers don't treat it like a normal div; its position and dimensions are tied to the browser window.

But a container div is just a div and you can style it with margins and borders. You can give it a fixed width, and you can center it with margin-left: auto; margin-right: auto.

Plus, content, like a copyright notice for example, can go on the outside of the container div, but it can't go on the outside of the body, allowing for content on the outside of a border.


-->

```




## cashing 
---


```html

<!--

* Description

파일을 따로 만든후 저장해놓는것


* how to use it? 

<link rel="stylesheet" href=“파일이름">


* Sample Output

-->


<!doctype html>

<html>
<title>web1 - Son</title>
<meta charset="ut-8">
<link rel="stylesheet" href="style.css">

```



## &lt;form&gt;
---


```html


<!--

* Description

The HTML `<form> tag` is used to create a form on a web page that has interactive controls for user input. This tag is also commonly referred to as the `<form>` element.

* Syntax

-->

<body>
  <form action="" method="get">
    Company: <input type="text" name="company"><br>
    Address: <input type="text" name="address"><br>
    <input type="submit" value="Submit">
  </form>
</body>


```

Sample Output

![](/tutorial/HTML_files/Screen Shot 2019-06-01 at 9.40.42 PM.png)


