---
layout: post
title: "Javascript 상속"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-08-13 18:24 +0900
---

```javascript
function Person(name){
    this.name=name;
}
//prototype 상속을 받기위한 템플릿.
//prototype 객체의 원형
Person.prototype.name=null;
Person.prototype.introduce=function(){
  return 'my nickname is '+this.name;
}

function Programmer(name){
  this.name = name;
}

//prototype <- 생성자
Programmer.prototype = new Person();
Programmer.prototype.coding=function(){
  return 'hello world';
}

var p2 = new Programmer('bbb');
document.write(p2.introduce());
document.write(p2.coding()+'<br>');

function Designer(name){
  this.name=name;
}

Designer.prototype=new Programmer();
Designer.prototype.design = function(){
  return 'beautiful';
}

var p3 = new Designer('ccc');
document.write(p3.introduce());
document.write(p3.design());
```
