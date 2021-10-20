---
layout: post
title: "Javascript Object.keys"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-10-20 22:10 +0900
---

```
Object.keys(obj) // 객체의 키만 담은 배열 반환
Object.values(obj) // 객체의 값만 담은 배열 반환
Object.entries(obj) //객체의 [key,val] 담은 배열 반환

let user={
    name:'hyemin',
    age:25
}

Object.keys(user)
(2) ['name', 'age']
Object.values(user)
(2) ['hyemin', 25]
Object.entries(user)
(2) [Array(2), Array(2)]


```
