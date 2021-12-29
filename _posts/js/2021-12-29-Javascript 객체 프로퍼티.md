---
layout: post
title: "Javascript 객체 프로퍼티"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-12-29 21:40 +0900
---

## 프로퍼티 플래그  
> writeable : true이면 값 수정 가능.  
> enumerable : true이면 반복문 통해 나열 가능.  
> configurable : true이면 프로퍼티 삭제 및 플래그 수정 가능.  

### 프로퍼티 정보 확인 
```javascript
// Object.getOwnPropertyDescriptor(obj, propertyName)를 통해 정보 확인

let user = { 
  name: "John"
};

Object.getOwnPropertyDescriptor(user, "name");
/*
 "value": "John",
 "writable": true,
 "enumerable": true,
 "configurable" :true
*/
```

### 플래그 변경
```javascript
// Object.defineProperty(obj, propertyName, descripter)

let user = {};
Object.defineProperty(user, "name". {
  value: "John"
});

Object.getOwnPropertyDescriptor(user, "name");
/*
  defineProperty로 프로퍼티 만든 경우, 플래그 값 명시 안하면 자동으로 false 됨.
  writeable, enumerable, conigurable => false
*/
```
#### configuration: false
> configurable 플래그 수정 X    
> enumerable 플래그 수정 X  
> writeable: false를 true로 바꿀 수 없음. true를 false로 바꾸는 건 가능.  

#### Object.defineProperties(obj, descriptors) : 프로퍼티 여러개 한번에 정의  
#### Object.preventExtensions(obj) : 새로운 프로퍼티 추가 X  
#### Object.seal(obj) : 새로운 프로퍼티 추가나 삭제 막아줌 (configurable: false)
#### Object.freeze(obj) : 새로운 프로퍼티 추가나 삭제 막아줌 (configurable: false, writeable: false)  

*** 

## getter, setter

```
let obj = {
  get propName() { //getter },
  set propName(value) { //setter }
}

//getter => 프로퍼티 읽음, setter => 프로퍼티에 값 할당

let user = {
  name: "John",
  surname: "Smith"
  
  get fullName() {
    return `${this.name} ${surname}`;
  }
  
  set fullName(value) {
    [this.name, this.surname] = value.split(' ');
  }
}

user.fullName = "Hyemin Seo"; //setter
user.name; //getter, Hyemin
user.surname; //getter, Seo

//defineProperty로도 가능.
Object.defineProperty(user, "fullName", {
  get() {
    return `${this.name} ${this.surname}`;
  }
  
  set(value) {
    [this.name, this.surname] = value.split(' ');
  }
}
```

