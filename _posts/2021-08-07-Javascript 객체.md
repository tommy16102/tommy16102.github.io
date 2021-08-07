---
layout: post
title: "Javascript 객체"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-08-07 16:34 +0900
---
```javascript
//1
{key:value}
var score = {'a':98, 'b':95, 'c':99}

//2
var score = {};
score['a']=98
score['b']=95
score['c']=99

score['a'] //98
score['b'] //95
score.a //98
score.b //95

for(var key in score) document.write(key+' '+score[key]) // a 98 b 98 c 99

//객체와 함수를 담은 객체
var list = {
  'score' : {'a':98, 'b':95, 'c':99},
  'show' : function() {
    for(var key in this.score) document.write(key+' '+this.score[key])
  }
}

list.show() //a 98 b 98 c 99
```
