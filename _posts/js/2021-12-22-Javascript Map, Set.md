---
layout: post
title: "Javascript Map, Set"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-12-20 15:48 +0900
---

## Map  
키가 있는 데이터를 저장, but 객체와 달리 키에 다양한 자료형 허용.  
  
주요 메서드 1  
```javascript
let map = new Map();

map.set('key', 'value);
map.set(1, 'num');
map.set('1', 'str');

map.get(1); //'num'
map.get('1'); //'str' 
//키의 타입을 문자열로 변환하지 않기 때문에 1과 '1' 따로 저장.

map.delete(1);
map.size; //2
map.clear(); //저장되어있던 모든 요소 삭제
```

주요 메서드 2  
```javascript
let map = new Map([
  ['cucumber', 500],
  ['tomatoes', 150],
  ['onion', 50]
]);

for (let vegetable of map.keys()) {
  console.log(vegetable); //cucumber, tomatoes, onion
}

for (let amount of map.values()) {
  console.log(amout); //500, 150, 50
}

//키, 값 대상으로 함수 실행.
map.forEach( (value, key, map) => {} )
```


```
let obj = {
  name: "John",
  age: 20
};

let map = new Map(Object.entries(obj)); //객체를 Map으로

let obj2 = Object.fromEntries([ ['banana', 100] ]); //Map을 객체로
```



 
 ## Set  
중복 허용하지 않는 값을 모아놓은 컬렉션.  
  
주요 메서드  
```javascript
let set = new Set();

let john = { name: "John" };
let pete = { name: "Pete" };

set.add(john);
set.add(pete);
set.add(john);

set.size; //2

//value, valueAgain 같은 값 => Map과의 호환성!
set.forEach((value, valueAgain, set) => {} );
```







