---
layout: post
title: "Javascript 호출 스케줄링"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-12-27 20:59 +0900
---

## 호출 스케줄링 
> setInterval => 일정한 시간마다 함수를 실행.  
> setTimeout => 일정한 시간 후에 함수를 실행. 

***

### setTimeout

```javascript
function sayHi() {
  alert("Hi");
};

setTimeout(sayHi, 1000);
//1초 후에 sayHi 실행.

function sayHi(who) {
  alert(`${who} HI!`);
}

//세번째 인자는 함수에 전달.
setTimeout(sayHi, 10000, "Hyemin");
```

***  

## setInterval 

```javascript
let timer = setInterval(()=>console.log("째깍"), 1000);
timer(); //1초마다 째깍 출력.
```

*** 

## 중첩 setTimeout  
setInterval 사용안하고 일정 간격두고 실행.  

```javascript
let timer = setTimeout(function tick() {
  console.log("쨰깍");
  timer = setTimeout(tick, 2000);
}, 2000);
```

> setTimeout은 지연 간격 보장.  
> 함수의 실행이 종료된 이후 지연 간격 지난 후 다음 함수의 실행.  
> setInterval는 지연 간격 보장 X.  
> 함수 실행하는 데 소모되는 시간이 지연 간격에 포함되서 지연 간격보다 길어지면 연속 호출. 


