---
title:  __Algorithm_3
date: 2019-04-29
draft: true
menu:
  tutorial:
    parent: "6.Javascript"
    weight: 3
toc: yes
type: docs
---


![](/tutorial/Javascript_Dictionary_files/javascriptt-light_870x220.png)


---------------------------------------------------------------------------


## nonUniqueElements(data)

### Question

> You are given a non-empty list of integers (X). For this task, you should return a list consisting of only the non-unique elements in this list. To do so you will need to remove all unique elements (elements which are contained in a given list only once). When solving this task, do not change the order of the list. Example: [1, 2, 3, 1, 3] 1 and 3 non-unique elements and result will be [1, 3, 1, 3].

```js

Input: A list of integers.

Output: An iterable of integ

var assert = require('assert');

if (!global.is_checking) {
    assert.deepEqual(nonUniqueElements([1, 2, 3, 1, 3]), [1, 3, 1, 3], "1st example");
    assert.deepEqual(nonUniqueElements([1, 2, 3, 4, 5]), [], "2nd example");
    assert.deepEqual(nonUniqueElements([5, 5, 5, 5, 5]), [5, 5, 5, 5, 5], "3rd example");
    assert.deepEqual(nonUniqueElements([10, 9, 10, 10, 9, 8]), [10, 9, 10, 10, 9], "4th example");
    console.log("Coding complete? Click 'Check' to review your tests and earn cool rewards!");
}

```



### My_Soulion

```js
function nonUniqueElements(data) {
    let overLap = data.filter((ele,index)=>{
        return data.indexOf(ele) !== index
        })
    overLap = Array.from(new Set(overLap));
    
    return data.filter(function(val) {
        return overLap.indexOf(val) !== -1;
    })
}




```


### Others

```js



function checkio(data) {
    return data.filter(function(a){
        return data.indexOf(a) !== data.lastIndexOf(a)    
    });
}
```