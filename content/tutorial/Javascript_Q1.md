---
title: JS Basic
date: 2019-6
draft: true
menu:
  tutorial:
    parent: "Javascript"
    weight: 10
toc: true
type: docs
---


---
## Conditional : isOldEnoughToDrink
---

* 어떤 숫자, 이 경우에는 연령이 하나 주어졌을 때, isOldEnoughToDrink 함수는 주어진 연령의 사람이 미국에서 합법적으로 술을 마실 수 있는지의 여부를 반환해야 합니다.


```
function isOldEnoughToDrink(age) {
  // 여기에 코드를 작성하세요
  if (age < 21 ) {
    return false;
  } else {
    return true;
  }
}


```
