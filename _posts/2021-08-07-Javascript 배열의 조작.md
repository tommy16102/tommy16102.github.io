---
layout: post
title: "Javascript 배열"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-08-07 15:04 +0900
---
```javascript
var a = ['a','b','c']

a.length  //3

a.push('d') // ['a','b','c','d']

a.concat(['e','f']) // ['a','b','c','d','e','f']

a.unshit('0') // [0, 'a','b','c','d','e','f']

a.splice(1,6,1,2,3) //(시작,개수,변경) [0, 1, 2, 3]



a = ['a','c','b','e','d']

a.shift() // ['c','b','e','d']

a.pop() // ['c','b','e']

a.sort() // ['b','c','e']

a.reverse() // ['e','c','b']

```
