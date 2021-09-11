---
layout: post
title: "Javascript 비교 연산자"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-08-05 23:04 +0900
---

# ==과 ===

```javascript

//equal operator
1 == 1 //true
1 == 2 //false
"one" == "one" //true
"one" == "two" //false


//strict equal operator
1 == '1' //true
1 === '1' //false 숫자와 문자

null(값x) == undefined(값이 정의x) //true
null === undefined //false

true == 1 //true
true == '1' //true
true === 1 //false
true === '1' //false

0 === -0 //true
NaN === NaN //false

//!=, !==는 반대.

```

==연산자 대신 데이터의 타입도 보는 ===연산자를 쓰자!
  
  


