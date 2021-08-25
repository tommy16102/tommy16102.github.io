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
# 선언

```
var //지역 및 전역

let //블록범위 지역변수

const //블록범위 읽기 전용 상수

var <-> let,const

ex)
var x=1;
{
 var x=2;
}
console.log(x); //2

let x=1;
{
 let x=2;
}
console.log(x); //1
```

# 기타
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


# 비동기
```
파라미터로 함수를 전달받아, 함수의 내부에서 실행하는 함수=>콜백함수  
미래의 특정 시점에 값을 제공 하겠다는 약속을 반환=>promise
```
