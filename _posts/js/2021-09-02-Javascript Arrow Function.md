---
layout: post
title: "Javascript Arrow Function"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-09-02 09:55 +0900
---
```javascript
//인자로 들어간 콜백 함수 길이 감소. ()=>()

// 1
setTimeout(function(){console.log('hi')},2000);
setTimeout(() => console.log('hi'),2000);

// 2
let newArr = [1,2,3,4,5].map(function(value,index,object){
  return value*2;
});

let newArr = [1,2,3,4,5].map(v=>{
  return v*2
});

let newArr = [1,2,3,4,5].map(v=>v*2)

//this bind(this)없이 arrow function을 통해 context 유지.

const myObj = {
  runTimeout(){
    setTimeout(()=>{
      console.log(this===window); //false. context 유지=>window x.
      this.printData();
    },1000);
  },
 printData(){
   console.log("hi codesquad!");
 }
}

 runTimeout(){
    setTimeout(function(){
      console.log(this===window); //true
      this.printData(); //실행 x. 
    },1000);
  },
  
  //실행하려면
    setTimeout(function(){
        console.log(this);
        console.log(this===window); //false
        this.printData();
      }.bind(this),1000); //bind(this).
  

