---
layout: post
title: "Javascript 연산"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2022-03-10 17:25 +0900
---

## 연산

```javascript
'1'+2 //12
2+'1' //21  => 하나가 문자열이면 다른 하나도 문자열로 변환.

6-'2', '6'/'2' //4, 3 => 문자열이 숫자로 변환.
"2"*"3" //6

let apple="2";
+apple, Number(apple) //2 => 단항 덧셈 연산자가 Number역할 수행.
```

## null vs undefined

```javascript
undefined == null //true
undefined === null //false

null, undefined 숫자형으로 변환
null => 0, undefined => NaN

null == 0 // true
undefined == 0 //false
```

## null 병합 연산자 ??  
```
let firstName = null;
let lastName = null;
let nickName = "바이올렛";

// null이나 undefined가 아닌 첫 번째 피연산자
alert(firstName ?? lastName ?? nickName ?? "익명의 사용자"); // 바이올렛

let height = 0;
height || 100; // 100. 
height && 100; //0

||는 첫 번째 truthy 값을 반환합니다. 0은 falsy로 취급합니다.
??는 첫 번째 정의된(defined) 값을 반환합니다.
```
