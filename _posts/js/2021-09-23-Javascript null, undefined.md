---
layout: post
title: "Javascript null, undefined"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-09-23 22:39 +0900
---

## null
##### 존재하지 않는 값, 비어 있는 값, 알 수 없는 값
##### ex) let age = null; //age를 알 수 없거나 값이 비어있다.
##### Number(null); //0

<br/>

## undefined
##### 값이 할당되지 않은 상태
##### 변수는 선언되었지만, 아직 값은 할당이 되지 않았을 때 자동으로 undefined 할당.
##### ex) let age;  alert(age); // undefined 출력
##### Number(undefined); //NaN
