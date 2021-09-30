---
layout: post
title: "Javascript Symbol"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-09-30 22:40 +0900
---
## Symbol

> 유일한 식별자

```
let id1 = Symbol("id");
let id2 = Symbol("id");

alert(id1 == id2); // false

console.log(id.description) //id
```

```
//유일성 보장

let id=Symbol("id")
let user = {}
user[id]=1; //symbol을 키로 사용=>for...in으로 접근불가, 복사 시 Object.assign사용!
```

## 전역 Symbol

> 전역 심볼 레지스트리에 존재 -> 이름 같으면 동일한 심볼 반환

```
let id=Symbol.for('id')
let id2=Symbol.for('id')
id===id2 //true

Symbol.keyFor(id) //id
```
