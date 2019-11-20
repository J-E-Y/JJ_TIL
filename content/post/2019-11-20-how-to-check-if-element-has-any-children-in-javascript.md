---
title: <Javascript> How to check if element has any children in Javascript?
summary: ':rocket:' 
author: JohnJung
date: '2019-11-20'
slug: how-to-check-if-element-has-any-children-in-javascript
categories:
  - Javascript Post
tags: []
image:
  caption: ''
  focal_point: ''
---


```js

if (element.firstChild) {
    // It has at least one
}

if (element.hasChildNodes()) {
    // It has at least one
}

if (element.childNodes.length > 0) { // Or just `if (element.childNodes.length)`
    // It has at least one
}

if (element.children.length > 0) { // Or just `if (element.children.length)`
    // It has at least one element as a child
}

if (element.firstElementChild) {
    // It has at least one element as a child
}

var hasChildElements, child;
hasChildElements = false;
for (child = element.firstChild; child; child = child.nextSibling) {
    if (child.nodeType == 1) { // 1 == Element
        hasChildElements = true;
        break;
    }
}

function hasChildElement(elm) {
    var child, rv;

    if (elm.children) {
        // Supports `children`
        rv = elm.children.length !== 0;
    } else {
        // The hard way...
        rv = false;
        for (child = element.firstChild; !rv && child; child = child.nextSibling) {
            if (child.nodeType == 1) { // 1 == Element
                rv = true;
            }
        }
    }
    return rv;
}




```
