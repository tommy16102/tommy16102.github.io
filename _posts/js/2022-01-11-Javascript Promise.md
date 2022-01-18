---
layout: post
title: "Javascript Promise"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2022-01-11 19:40 +0900
---

## Promise   
```javascript
let promise = new Promise(function(resolve, reject) {
  //executor
});
```
- executor : new Promise에 자동 전달되며, new Promise가 만들어질 때 실행.  
- executor는 처리 성공 여부에 따라 resolve나 reject 중 하나를 호출.  
  - resolve : 성공 -> 결과를 나타내는 value와 함께 호출.   
  - reject : 오류 -> 에러 객체를 나타내는 error와 함께 호출.  
- new Promise 생성자가 반환하는 promise객체는 state와 result 프로퍼티를 가짐.  
  - state : pending -> fulfilled(resolve)/rejected(reject).  
  - result : undefined -> value/error.  
![image](https://user-images.githubusercontent.com/75344562/148929279-82c3711c-6177-4ecc-a7aa-a5f43eb5f4df.png)  


```javascript
let promise = new Promise(function(resolve, reject) {
  setTimeout(() => resolve("done"), 1000);
});
```
![image](https://user-images.githubusercontent.com/75344562/148929476-d4a6d15a-e31f-46dc-95fc-2a89176a4d18.png)


```javascript
let promise = new Promise(function(resolve, reject) {
  setTimeout(() => reject(new Error("에러")), 1000);
});
```
![image](https://user-images.githubusercontent.com/75344562/148929652-2ed32b78-cae6-48e2-a4be-5f7c4464fae5.png)


## then, catch, finally  
### then  
- 첫번째 인수는 promise가 이행되었을 때, 두번째 인수는 promise가 거부되었을 때.  
```javascript
promise.then(
  function(result) { /*결과(result)를 다룸*/},
  function(error) { /*에러(error)를 다룸*/}
);
```  
### catch  
- 에러가 발생한 경우를 다룸.  
```javascript
let promise = new Promise((resolve, reject) => {
  setTimeout(() => reject(new Error("에러")), 1000);
});
promise.catch(alert);
```  
### finally  
- 성공,실패 여부 상관없이 프라미스가 처리되면 실행.  
```javascript
new Promise((resolve, reject) => {
})
  .finally(()=>)
  .then(result => ...);
```  

