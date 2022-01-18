---
layout: post
title: "Javascript async, await"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2022-01-18 21:30 +0900
---

## async  
- function 앞에 붙이면 Promise를 반환.  
```javascript
async function f() {
  return 1;
}

f().then(alert); //1
```

## await  
- async 함수 안에서 작동.  
```javascript
async function f() {
  let promise = new Promise((resolve, reject) => {
    setTimeout(() => resolve("1"),1000)
  });
  
  let result = await promise;
}
```
- promise가 처리될 때까지 기다림.    
- promise.then과 같은 역할.  
***  
```javascript
let response = await fetch('/.../..');
let user = await response.json();

// 최상위 레벨에서도 await 사용가능.
(async () => {
  let response = await fetch('/.../..');
  let user = await response.json();
})();
```
