---
title: How to convert a string of numbers to an array of numbers?
summary: 'Javascript:rocket:' 
author: JohnJung
date: '2019-11-23'
slug: how-to-convert-a-string-of-numbers-to-an-array-of-numbers
categories:
  - Javascript Post
tags: []
image:
  caption: ''
  focal_point: ''
---


### Qeustion


```js
var a = "1,2,3,4";
var b = a.split(',');
/// ["1", "2", "3", "4"]

// how to make this : [1, 2, 3, 4] 

```


#### Soultion


* useing Array.map to convert each element into a number.

```js
var a = "1,2,3,4";

var b = a.split(',').map(function(item) {
    return parseInt(item, 10);
});

// b = [1, 2, 3, 4] 

```

* useing Map and Number


```js
var b = a.split(',').map(Number);

// b = [1, 2, 3, 4] 

```

* useing from()

```js

var b = Array.from(a.split(','),Number);

// b = [1, 2, 3, 4]
```