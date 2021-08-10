---
layout: post
title: "Javascript 함수의 용도"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-08-10 17:04 +0900
---
```javascript

//값으로서의 함수
var a = function() {}

//객체의 속성값으로 담겨진 함수 -> 메소드
a = {
    b : function() {}
}
a.b();

//increase함수가 cal함수의 첫번째 인자의 값으로 전달
function cal(func, num) {
    return func(num);
}
function increase(num){
    return num+1;
}

cal(increase,1);

function cal(func, num){
    var func = increase(num){ return num+1; }
    return func(1)
}

//리턴 값으로서의 함수
function cal(mode){
    var funcs = {
        'plus' : function(left,right){ return left+right; },
        'minus' : function(left,right){ return left-right;}
    }
    return funcs[mode];
}

cal('plus')(2,3) //5

//배열 값으로서의 함수
var process = [
    function(input){ return input*10; }
    function(input){ return input*input; }
    function(input){ return input/2; }
]
for(var i=0;i<process.length;i++) console.log(process[i](1))


//콜백함수 sortfunc함수를 매개변수로 => 함수가 값이라서 가능.
var numbers = [20,9,10,8,7,6,5,4,3,2,1];
var sortfunc = function(a, b) return a-b;

numbers.sort(sortfunc);
//[1,2,3,4,5,6,7,8,9,10,20]

```

