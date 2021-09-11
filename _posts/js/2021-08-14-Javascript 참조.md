---
layout: post
title: "Javascript 참조"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-08-14 20:24 +0900
---

```javascript

//복사(원시)
var a = 2;
var b = a;
console.log(b) //2
b=3;
console.log(a) //2

//참조(객체)
var a = {'id':1}
var b = a
console.log(b.id)//1
b.id=3;
console.log(a.id)//3

b={'id':2} //새롭게 객체 생성
console.log(a.id)//3

//함수
var a = 1;
function func(b){  //b=a b=2.
  b=2;
}
func(a);
console.log(a) //1

```
