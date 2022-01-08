---
layout: post
title: "Javascript 클래스와 상속"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2022-01-08 22:40 +0900
---

## 클래스  
- Javascript에서 함수의 한 종류  
- 기본 문법  
```javascript
class Class {
  constructor() { ... }
  method1() { ... }
}
```
> new Class()를 통해 내부에서 정의한 method1가 들어있는 객체가 생성  
> constructor()를 통해 객체를 초기화  
- 실제로 하는 일  
```javascript
class User{
  constructor(name) { this.name = name; }
  sayHi() { alert(this.name); }
}
```
![image](https://user-images.githubusercontent.com/75344562/148646866-68daaafe-8e9e-4463-9c62-fd2ecdb7816e.png)  

> User라는 이름의 함수를 생성.  
> 함수 본문은 constructor에서 가져옴.  
> sayHi와 같은 메서드는 User.prototype에 저장.
> User === User.prototype.constructor; //true
> 이후, new User를 통해 객체를 만들며, prototype 프로퍼티를 통해 메서드 호출.  

***  

### 클래스 필드
- 어떤 종류의 프로퍼티도 클래스에 추가 가능.  
```javascript
//name프로퍼티 추가.
class User {
  name = "보라";
  sayHi() { ... }
}
```

***

## 상속 extends
- 클래스를 다른 클래스로 확장.  
```javascript
class Animal {
  constructor(name) {
    this.speed = 0;
    this.name = name;
  }
  run(speed) {
    this.speed = speed;
    alert(`${this.name} 은/는 속도 ${this.speed}로 달립니다.`);
  }
  stop() {
    this.speed = 0;
    alert(`${this.name} 이/가 멈췄습니다.`);
  }
}

class Rabbit extends Animal {
  hide() {
    alert(`${this.name} 이/가 숨었습니다!`);
  }
}

let rabbit = new Rabbit("토끼");
rabbit.run(5); //Animal 메서드 접근 가능.
rabbit.hide();
```
- extends는 프로토타입을 기반으로 동작.
- Rabbit.prototype.[[Prototype]]을 Animal.prototype으로 설정.  

### 메서드 오버라이딩
- super.method(...) => 부모 클래스에 정의된 메서드 method를 호출.  
- super(...) => 부모 생성자 호출.  


### 생성자 오버라이딩
- 다른 클래스를 상속받는 클래스가 자체 생성자가 없는 경우 constructor 자동생성.    
```javascript
//생성자는 부모 constructor를 호출하며,
//인수를 모두 전달.
class Rabbit extends Animal {
  constructor(...args) {
    super(...args);
  }
}
```
- 상속 클래스의 생성자에선 반드시 this를 사용하기 전에 super(...) 호출.  
- super를 호출해서 부모 생성자를 실행해야 빈 객체를 만들고 this에 이 객체를 할당.   




