---
layout: post
title: "Javascript 여러가지"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-08-06 23:04 +0900
---

```
alert() -> 경고창

prompt() -> 입력한 값 결과로

document.write() -> 화면 출력

```

# 모듈화

hi.js

```
function hi(){alert('hi')}
```

main.html

```
...
<head>
  <script src = "hi.js"></script>
</head>
<body>
  <script> hi() </script>
</body>
...
```



node.circle.js

```
var PI = Math.PI;
exports.area = function(r) { return PI*r*r;}
```

node.demo.js

```
var res = require('./node.circle.js');
console.log(res.area(5))
```

node node.demo.js 실행
