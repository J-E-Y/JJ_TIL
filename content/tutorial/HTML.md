---
title: HTML( hyper text markup Language)
date: 2019-04-29
draft: true
menu:
  tutorial:
    name: Html
    weight: 2
toc: true
type: docs
---

---
##  html: **&lt;strong&gt;tag**
---

* Description

>The HTML &lt;strong&gt; tag gives text a strong emphasis which traditionally means that the text is displayed as bold by the browser. 

* Note 

>what's the difference bewteen &lt;strong&gt; tag and &lt;b&gt; ?

>strong tag :시각장애인들 낭독기를 사용할때 조금 더 굵 게 읽는다. 

>b tag :평상시대로 굵게 읽는다.

* Syntax

```
<body>
<p><strong>Emphasized text goes here</strong> but not here</p>
</body>

```
* Sample Output

```
Emphasized text goes here but not here
```

---
## html : **&lt;h1&gt;tag**
---

* Description

>The HTML **&lt;h1&gt;tag** tag defines the highest level or most important heading in the HTML document. This tag is also commonly referred to as the **&lt;h1&gt;tag** element.

* Syntax

```
<body>
<h1>Heading 1 goes here</h1>
</body>

```
Sample Output

```
Heading 1 goes here
```

---
## html **&lt;br&gt;tag**
---
 
* Description

> The HTML &lt;br&gt;tag defines a line break within text in the HTML document. This tag is also commonly referred to as the <&lt;br&gt; element.

* Syntax

```

<body>
<p>The paragraph starts here<br>
and ends on the next line.</p>
</body>

```

* Sample Output


```
The paragraph starts here
and ends on the next line.

```

---
`&nbsp;` : making space
---

---
## html **&lt;p&gt;tag**
---

* Description

>The HTML &lt;p&gt; tag defines a paragraph in the HTML document. This tag is also commonly referred to as the &lt;p&gt; element.


* syntax

```
<body>
<p>The paragraph goes here.</p>
</body>

```

* output

```
this 

The paragraph goes here.

this
```

* <Hr/> : making line break with line


---
## html **&lt;hr/&gt;tag**
---

* Description

>The HTML &lt;hr/&gt; tag defines a thematic break between paragraphs in HTML5, and a horizontal rule in HTML 4.01. This tag is also commonly referred to as the &lt;hr/&gt; element.

* Note

> The HTML &lt;hr/&gt; element makes line bewteen two paragraphs.

* Syntax

```
<body>
<p>This is the first paragraph.</p>
<hr>
<p>This is the second paragraph.</p>
</body>

```


---
## html **&lt;div&gt;tag**
---

* Description

> The HTML &lt;p&gt; tag defines a generic container in an HTML document that is generally used to group elements. This tag is also commonly referred to as the &lt;p&gt; element.

* Note
 
>The HTML &lt;p&gt; element is found within the <body> tag.
The <div> tag is generally used to group elements together.
&lt;p&gt;&lt;p&gt; :element is a block-level element.

> The &lt;p&gt; element is a block-level element.


* Syntax

```
<body>

<div>
  <div>this is the type of elemnt </div>
</div>

</body>

```


---
## html **&lt;span&gt;tag**
---

* Description

> The HTML &lt;span&gt; tag defines a generic inline container in an HTML document. This tag is also commonly referred to as the <&lt;span&gt; element.

* Note

> &lt;span&gt; tag is is generally used for styling purposes when there is no other element to use.
> &lt;span&gt; tag is a inline-level element
> &lt;span&gt; tag does not inherently represent anything


Syntax

```
<body>
<p><span>Span text goes here</span> and not here</p>
</body>


<body>
<p><span class="red_text">Span text goes here</span> and not here</p>
</body>

```

---
## html **&lt;nav&gt;tag**
---


* Description

> The HTML &lt;nav&gt; tag is an HTML5 element that defines a section with navigation links in the HTML document. This tag is also commonly referred to as the &lt;nav&gt; element. It is used to define a block of navigation links, either within the current document or to other documents


* Note

>The <nav> tag is used to create navigation in the HTML document.For IE browsers older than IE 9, use HTML5shiv which is a javascript workaround to provide support for the new HTML5 elements such as: &lt;header&gt;, &lt;main&gt;, &lt;article&gt;, &lt;section&gt;, &lt;aside&gt;, &lt;nav&gt;, &lt;footer&gt;.


* Syntax


```

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



---
## html **&lt;ul&gt;tag** (부모태그)
---


* Description

>The HTML &lt;ul&gt; tag defines an unordered list in the HTML document. This tag is also commonly referred to as the &lt;ul&gt; element.

* Note

> The HTML &lt;ul&gt; element is found within the <body> tag.
The &lt;ul&gt; tag is made up of <li> tags.
Use the &lt;ul&gt; tag when the list items have no numerical ordering.
You can nest &lt;ol&gt;, &lt;ul&gt; and &lt;ul&gt;menu lists.

* Syntax

```
<body>
<ul>
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ul>
</body>

```

* Sample Output


```
* First item
* Second item
* Third item

```

---
## html **&lt;li&gt;tag** (부모태그)
---

* Description

>The HTML &lt;li&gt; tag defines a list item in &lt;ol&gt;, &lt;ul&gt; or &lt;menu&gt; in the HTML document. This tag is also commonly referred to as the &lt;li&gt; element.


* Syntax

```
<body>
<ul>
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ul>
</body>

```

* Sample Output 1

```
<body>
<ol>
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ol>
</body>

```


* Sample Output 2

```
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

```
* Note

>The &lt;li&gt; tag is used within &lt;ol&gt;, &lt;ul&gt; or &lt;menu&gt;.
You can nest &lt;ol, &lt;ul> and &lt;menu&gt; lists. (자식태그) li 태그는 반드시 부모태그를 가지고 있다. 


---
## html **&lt;ol&gt;tag** 
---


* Description

>The HTML &lt;ol&gt; tag defines an ordered list in the HTML document. This tag is also commonly referred to as the &lt;ol&gt; element.

* Syntax

```
<body>
<ol>
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ol>
</body>

```

* Sample Output

 >1. First item
 >1. Second item
 >2. Third item
 
 
* Note

>The &lt;ol&gt; tag is made up of &lt;li&gt; tags. 
>Use the &lt;ol&gt; tag when the list items have numeric, meaningful ordering.
>You can nest &lt;ol&gt;, &lt;ul&gt; and &lt;menu&gt; lists.


---
## html **container** 
---


* Description

In HTML, the container is the area enclosed by the beginning and ending tags. For example < HTML > encloses an entire document while other tags may enclose a single word, paragraph, or other elements. In HTML code, all container must have a start and stop tag to close the container. Without a stop tag the start tag will apply to the entire document.
 

```html
<html>
  <head>
    ...
  </head>
  <body>
    <div id="container">
      ...
    </div>
  </body>
</html>
```

 
 * note
 
 >The container div, and sometimes content div, are almost always used to allow for more sophisticated CSS styling. The body tag is special in some ways. Browsers don't treat it like a normal div; its position and dimensions are tied to the browser window.

>But a container div is just a div and you can style it with margins and borders. You can give it a fixed width, and you can center it with margin-left: auto; margin-right: auto.

>Plus, content, like a copyright notice for example, can go on the outside of the container div, but it can't go on the outside of the body, allowing for content on the outside of a border.


---
## html : **cashing** : 파일을 따로 만든후 저장해놓는것
---

* how to use it? 

> &lt;link rel="stylesheet" href=“파일이름"&gt;

* Sample Output

```html

<!doctype html>

<html>
<title>web1 - Son</title>
<meta charset="ut-8">
<link rel="stylesheet" href="style.css">

```