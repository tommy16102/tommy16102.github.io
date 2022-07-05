---
layout: post
title: "Javascript 함수 정의방법"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-09-26 17:10 +0900
---
```
함수 선언문
function func() {}
-> func()

함수 표현식
let func = function() {}
-> func()
```

### 함수 선언문 vs 함수 표현식  
- 함수 선언문은 함수 선언문이 정의되기 전에 호출 가능.  
- 자바스크립트는 스크립트 실행 전, 준비(초기화)단계에서 전역의 함수 선언문을 찾고, 해당 함수를 생성하기 때문.  
- 함수가 선언된 블록 내 어디에서든 유효.  

```javascript
sayHi("John"); // Hello, John
function sayHi(name) {
  alert( `Hello, ${name}` );
}

if (age < 18) {
  welcome(); //정의되기전 호출 가능.
                         
  function welcome() { //함수 선언문 블록 내 어디에서든 유효
    alert("안녕!");      
  }                      
  welcome();               
}

// 함수 표현식은 함수 선언되기전 접근 불가능
sayHi("John"); // error!

let sayHi = function(name) { 
  alert( `Hello, ${name}` );
};
```

### 함수 선언문을 사용하자! 
