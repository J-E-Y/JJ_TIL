---
title: Javascript
date: 2019-04-29
draft: true
menu:
  tutorial:
    name: Javascript
    weight: 4
toc: true
type: docs
---

---
### 1. showing data in browser
---

```javascript

<!DOCTYPE html>
<html>
<body>
    <h2>Javascript_note</h2>
    <p id="demo">what time is it now ?</p>

</body>
</html>
```

```javascript

var demo = document.getElementById('demo');
demo.innerHTML = Date();

```

  

 