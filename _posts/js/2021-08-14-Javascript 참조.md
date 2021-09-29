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

// 참조(객체)
// 변수에 객체가 그대로 저장x, 메모리 내 어딘가 저장되어 있는 객체의 주소인 객체에 대한 참조값이 저장.
//복사시, 저장되어 있던 객체에 대한 참조 값이 복사되고, 객체는 복사 x
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
