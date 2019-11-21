---
title: <Javacript/Dom> checkbox 안에 있는 value 값 얻기
summary: ':rocket:'
author: JohnJung
date: '2019-11-21'
slug: javacript-checkbox-value
categories:
  - Javascript Post
tags: []
image:
  caption: ''
  focal_point: ''
---

* html

```html


<div class = "container">
    
    <input type="checkbox" class ="checks" value ="뜨거워"> hot
    <input type="checkbox" class ="checks" value ="추워"> clod
    <a href="#" onclick="submitFun();return false;">ok </a>

</div>

```

* js

```js



	function submitFun() {
		

		var checks = document.getElementsByClassName('checks')
		var str = "";
		

		for (let i = 0; i < checks.length; i++ ){

			if (checks[i].checked === true ) {
 				str += checks[i].value + "";
 			}
 		}
 		alert(str);
	}

```

