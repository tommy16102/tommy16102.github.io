---
layout: post
title: "Javascript arguments"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-08-11 11:04 +0900
---
```javascript
// arguments
// 인자 구현x 함수 -> 인자 전달
function sum(){
    var _sum=0;
    for(var i=0;i<arguments.length;i++) sum+=arguments[i];
    return _sum;
}

sum(1,2,3) //arguments.length = 3,  sum = 6
sum() //arguments.length = 0, sum = 0

//length
function one(arg1){}
one() //one.length = 1, arguments.length = 0
one(1) //one.length = 1, arguments.length = 1
one(1,2) //one.length = 1, arguments.length = 1

function two(arg1, arg2){}
two(1,2) //two.length = 2, arguments.length = 2
two(1,2,3) //two.length = 2, arguments.length = 3
```

