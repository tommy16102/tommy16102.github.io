---
layout: post
title: "Javascript let, const"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-08-26 19:04 +0900
---
# 선언

```
var //지역 및 전역

let //블록범위 지역변수

const //블록범위 읽기 전용 상수

var <-> let,const

ex)
var x=1;
{
 var x=2;
}
console.log(x); //2

let x=1;
{
 let x=2;
}
console.log(x); //1
```

# 호이스팅

```
//선언문 -> 해당 스코프의 선두로 옮김
console.log(a); //undefined
var a=3;

console.log(b); //error
let b=3;

//var은 선언,초기화,할당의 변수 생성 3단계에서 선언과 초기화가 한번에 이뤄짐.=>변수를 위한 공간 확보 후, undefined로 초기화.

//반면 let은 선언, 초기화가 분리되어 있음. => 초기화는 변수 선언문에 도달했을 때 이뤄짐. 초기화 전 변수 접근->에러
//스코프의 시작지점부터 초기화 시점까지 let 변수 참조 x 
```
