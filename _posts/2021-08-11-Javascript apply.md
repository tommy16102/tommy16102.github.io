---
layout: post
title: "Javascript apply"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-08-11 12:04 +0900
---
```javascript
// arguments
o1 = {val1:1, val2:2, val3:3}
o2 = {v1:10, v2:50, v3:100, v4:25}

function sum(){
  var _sum=0;
	console.log(this);
	for(name in this){
		_sum+=this[name];
	}
	return _sum;
}
			
//o1, o2객체가 this.
sum.apply(o1) //6
sum.apply(o2) //185

o1 = {va11:1, val2:2, val3:3,sum:sum}
o2 = {v1:10, v2:50, v3:100, v4:25,sum:sum}
o1.sum(); //결과+sum함수
```
