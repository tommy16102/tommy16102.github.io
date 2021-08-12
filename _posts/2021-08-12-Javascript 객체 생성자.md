---
layout: post
title: "Javascript 객체 생성자"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-08-12 10:24 +0900
---

```javascript

// function-> new를 통해 객체 생성
function Person(){};
var p = new Person();
//p = Person { }

p.name='egoing';
p.introduce=function(){
	return 'my name is'+this.name;
}
//Person{ name : 'egoing' , introduce : funciton }
			
p.introduce()

//Person 생성자 
function Person(name){
	this.name=name;
	this.introduce=function() { console.log(this.name) }
}

var man = new Person("minsu");
man.introduce(); //minsu

var man2 = new Person("minho");
man2.introduce();//minho

```
