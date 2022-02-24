---
layout: post
title: "Javascript 정규표현식"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2022-02-24 16:10 +0900
---

## 정규표현식  
- 문자열에서 특정 패턴 찾기 가능.  
- 형식은 /패턴/.  

```javascript
let arr = ['나는', '나비', '단비', '갈비'];

//나로 시작하는 문자열 /^ /
arr.filter(elem => elem.match(/^나/));  
['나는', '나비']

//비로 끝나는 문자열 / $/
arr.filter(elem => elem.match(/비$/));
['나비', '단비', '갈비']
```
