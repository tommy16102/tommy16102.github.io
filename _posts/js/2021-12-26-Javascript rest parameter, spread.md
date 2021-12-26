---
layout: post
title: "Javascript Rest & Spread"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-12-26 20:59 +0900
---

## 나머지 매개변수 
> 함수에 넘겨주는 인수의 개수에 제약이 X  
> 매개변수를 배열.

```javascript
//rest parameter는 항상 마지막에 위치
function showName(first, last, ...titles) { ... }
showName("Hyemin", "Seo", "A", "B"); //"A"와 "B"가 배열 titles의 요소가 된다.
```

```javascript
//arguments로 인수 접근
function showName() {
  console.log(arguments.length);
  console.log(arguments[0]);
}

showName("Hyemin", "Seo");
//arguments.length 2
//arguments[0] "Hyemin"
```
***  

## Spread  
> 배열을 매개변수로(나머지 매개변수와 반대)
  
```javascript
let arr = [3, 5, 1];
Math.max(...arr) //5

let str = "Hello";
console.log([...str]); //H, e, l, l, o
```

```javascript
//Object.assign 대신 배열 복사
let arr = [1, 2, 3];
let copy = [...arr];

console.log(arr === copy); //참조가 다르기 때문에 false

//객체 복사
let obj = { a: 1, b: 2 };
let objCopy = { ...obj };
```
