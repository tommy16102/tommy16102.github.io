---
layout: post
title: "Javascript Destructuring"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-12-25 16:8 +0900
---

### 구조 분해 할당  
> 객체나 배열을 변수로 분해    
  
***  

## 배열

```javascript
let arr = ["Bora", "Lee"];
let [fName, sName] = arr;
console.log(fName, sName); //Bora Lee
```

```javascript
//두 번째 요소는 생략
let [name, , title] = ["Julius", "Caesar", "abc", "Roma"];
console.log(title)//abc
```

```javascript
//변수 교환하기
let a = "A";
let b = "B";
[a, b] = [b, a];
```

#### '...'로 나머지 요소 가져오기  
```javascript
//rest는 나머지 배열 요소들이 저장된 새로운 배열이 됨.
let [name1, name2, ...rest] = ["Julius", "Caesar", "abc", "Roma"];
console.log(rest);
```

***  
  
  
## 객체 
> let {var1, var2} = {var1:..., var2:...}  

```javascript
let obj = {
  name: "John",
  age: 30
};

let {name, age} = obj;
console.log(name, age)//John 30

//name을 n, age를 a에 저장.
let {name: n, age: a} = obj;
console.log(n, a)//John 30
```

#### '...'로 나머지 요소 가져오기  
```javascript
let obj = {
  name: "John",
  age: 30,
  home: "Seoul"
};

let {name, ...rest} = obj;
console.log(rest); //{age:30, home:"Seoul"}
```

#### 중첩 구조분해  

> 객체나 배열이 다른 객체나 배열 포함하는 경우  

```javascript
let options = {
  size: {
    width: 100,
    height: 200
  },
  items: ["Cake", "Donut"],
  extra: true
};

let {
  size: { //width에 100, height에 200저장
    width,
    height
  },
  items: [item1, item2], //item1에 Cake, item2에 Donut 저장
  title = "Menu"
} = options;
```
