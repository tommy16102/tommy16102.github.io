---
layout: post
title: "Javascript 옵셔널 체이닝"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-09-30 22:15 +0900
---


> obj?.prop – obj가 존재하면 obj.prop을 반환하고, 그렇지 않으면 undefined를 반환함
> obj?.[prop] – obj가 존재하면 obj[prop]을 반환하고, 그렇지 않으면 undefined를 반환함
> obj?.method() – obj가 존재하면 obj.method()를 호출하고, 그렇지 않으면 undefined를 반환함

```
?.앞의 대상이 undefined/null이면 평가 멈추고 undefined 반환.
?. 앞의 변수는 꼭 선언되어있어야함.

let user={}
alert(user?.address?.street); // undefined

let user = null;

alert( user?.address ); // undefined
alert( user?.address.street ); // undefined

```
