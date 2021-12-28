---
layout: post
title: "Javascript call forwarding"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-12-28 11:04 +0900
---

## Call Forwarding  
> func.call, func.apply  
> context와 인수 전체를 다른 함수에 전달  

***  

## Call  

> func.call(this, ...arguments)  

```javascript
function sayHi() {
  alert(this.name);
}

let user = { name: "John" };
let user2 = { name: "Seo" };

sayHi.call(user); //John
sayHi.call(user2); //Seo
```

***  

## Apply  

> func.apply(this, arguments)  
> call은 복수 인수를 따로 받지만, apply는 인수를 유사 배열 객체로 받음  
> js엔진 내부에서 apply를 최적화해서 더 빠름.  

```
func.call(context, ...args); //args를 분해
func.apply(context, args);
```

*** 

### 메서드 빌리기.

```javascript
//일반 배열에서 join메서드를 빌려와서 호출.

function hash() {
  alert( [].join.call(arguments) );
}

hash(1, 2); //1,2
