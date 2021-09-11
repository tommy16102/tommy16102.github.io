---
layout: post
title: "Javascript 객체 2"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-09-02 17:24 +0900
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
man.constructor // function Person..

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



//Object.create, assign
var healthObj = {
  showHealth: function(){
    console.log("오늘 시간 : "+this.healthTime);
    
  }
}

const myHealth = Object.create(healthObj);
myHealth.name="name";
myHealth.lastTime="11:20";

const myHealth2 = Object.assign(Object.create(healthObj),{
  name:"name",
  lastTime:"11:20"
});

//Object assign
const previousObj = {
  name:"name",
  lastTime:"11:20"
};

//previousObj에서 추출한 뒤, 새로운 값으로 대체(없으면 그대로 씀)
const myHealth = Object.assign({},previousObj,{
  name:"name2"
});

console.log(previousObj===myHealth); //false.

const myHealth2 = Object.assign({},previousObj,{
});

console.log(previousObj===myHealth2); //false 객체는 다름.


//setPrototypeOf

const healthObj = {
  showHealth : function(){
    console.log(this.healthTime);
  },
  setHealth : function(newTime){
    this.healthTime = newTime;
  }
}

const healthChildObj = {
  getAge:function(){
    return this.age;
  }
}

Object.setPrototypeOf(healthChildObj,healthObj);

const childObj = Object.setPrototypeOf({
  age:22
},healthChildObj);

console.log(childObj);
```
