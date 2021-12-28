---
layout: post
title: "Javascript 함수 바인딩"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-12-28 18:30 +0900
---

## 함수 바인딩
> this 정보가 사라지는 문제.  
> 객체 메서드가 객체 내부가 아닌 다른 곳에 전달되어 호출.  
```javascript
let user = {
  name: "John",
  sayHi() {
    alert(this.name);
  }
}

//setTimeout은 인수로 전달받은 함수를 호출할 때, this에 window를 할당.
//this.name은 window.name이므로 undefined가 됨.
setTimeout(user.sayHi, 1000);
```

*** 

# 해결 방법

## 1. 래퍼함수 사용

```javascript
let user = {
  name: "John",
  sayHi() {
    alert(this.name);
  }
}

setTimeout(function() {
  user.sayHi();
},1000);
setTimeout(()=>user.sayHi(), 1000);
```
 
## 2. 바인딩 

> this를 수정해주는 내장 메소드 bind 사용.   

```javascript
//func.bind를 통해 함수처럼 호출 가능한 특수 객체 반환
//해당 객체 호출하면 this가 context로 고정된 func가 반환
let boundFunc = func.bind(context);

let user = {
  name: "John"
};

function func() {
  console.log(this.name);
}

let Func = func.bind(user);
Func(); //John
```

#### 인수 바인딩

```javascript {
function mul(a, b){
  return a * b;
}

let triple = mul.bind(null, 3);
triple(4); // = mul(3,4) = 12
```
