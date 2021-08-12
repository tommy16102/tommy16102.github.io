---
layout: post
title: "Javascript 객체 2"
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


//this window
function func() {console.log(this)} //this는 window

//this 객체
var obj = { func: function() {if(this==obj) console.log(this)} } //this는 obj

var funcThis;
function Func() {
	funcThis = this; 
}

var o1 = Func(); //funcThis == window
var o2 = new Func(); //funcThis == o2


//sum 함수 객체
function sum(x,y) {return x+y;}
sum(1,2)//3

var sum2 = new Function('x','y','return x+y')
sum2(1,2)//3

//apply
function func() {}
func() //this -> window

var a = {}
func.apply(a) //this -> a
```
