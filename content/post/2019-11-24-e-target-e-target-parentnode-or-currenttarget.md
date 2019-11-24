---
title: 'e.target 와 e.target.parentNode or currentTarget의 차이점 '
summary: 'Javascript:rocket:' 
author: JohnJung
date: '2019-11-24'
slug: e-target-e-target-parentnode-or-currenttarget
categories:
  - Javascript Post
tags: []
image:
  caption: ''
  focal_point: ''
---

* event.target 와 event.target.parentNode 차이점 

```js

* e.target === 클릭된애
* e.target.parentNode === 클릭된애 부모태그 
* e.target.parentNode.parentNode === 클릭된애 부모의 부모태그

```
* event.target 과 currentTarget 의 차이점

```js

* event.target 은 마우스 클릭할때 발생되는 이벤트가 일어나는 곳을 말하고
* event.currentTarget 은 addEventListener 를발생시키는 대상 

```

