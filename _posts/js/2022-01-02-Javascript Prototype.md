---
layout: post
title: "Javascript Prototype"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2022-01-02 19:00 +0900
---

## [[Prototype]]  
> 숨김 프로퍼티  
> null이나 다른 객체를 참조  
> 다른 객체를 참조하는 경우 참조 대상은 프로토타입.  
> Object에서 프로퍼티를 읽을 때, 해당 프로퍼티가 없으면 자동으로 프로토타입에서 프로퍼티 찾음.  

## __proto__  
> [[Prototype]]의 getter이자 setter  

```javascript
let animal = {
  eats: true
};
let rabbit = {
  jumps: true
};

rabbit.__proto__ = animal; //animal을 rabbit의 프로토타입으로
console.log(rabbit.eats); //rabbit에는 eats프로퍼티가 없으므로 [[Prototype]]이 참조하는 animal에서 eats를 읽음.
```
rabbit의 프로토타입은 animal.  
rabbit에서는 animal에서 구현된 프로퍼티와 메서드를 사용가능.  

```javascript
let animal = {
  eats: true,
  walk() {}
}
let rabbit = {
  __proto__: animal
}
rabbit.walk = function() {console.log('walk')}

rabbit.walk(); //프로토타입에 있는 메서드가 아닌 rabbit에 있는 walk 메서드가 실행.
```

### 반복문  
```javascript
let animal = {
  eats: true
}

let rabbit = {
  jumps: true,
  __proto__: animal
}

//Object.keys는 객체 자신의 키만 반환
Object.keys(rabbit);//jumps

//for..in 객체 자신의 키 + 상속 프로퍼티 키 모두
for(let prop in rabbit) //jumps, eats

rabbit.hasOwnProperty('eats'); //false
rabbit.hasOwnProperty('jumps'); //true
```

## 함수의 prototype  
> new 연산자를 사용해 만든 객체는  
> 생성자 함수의 프로토타입 정보를 사용해 [[Prototype]] 설정  
> F.prototype 프로퍼티는 new F를 호출할 때 만들어지는 새로운 객체의 [[Prototype]]을 할당.  

```javascript
let animal = {
  eats: true
};

function Rabbit(name) {
  this.name = name;
}

//new Rabbit을 호출해 만든 새로운 객체의 [[Prototype]]을 animal로 설정.
Rabbit.prototype = animal;
let rabbit = new Rabbit("토끼");
rabbit.eats; //true
```

### constructor
> 디폴트 프로퍼티 prototype은 constructor 프로퍼티 하나만 있으며,  
> 함수 자신을 가리킴.  

```javascript
function Rabbit() {}
//Rabbit.prototype = { constructor: Rabbit}

let rabbit = new Rabbit(); //{constructor: Rabbit}을 상속받음
rabit.constructor == Rabbit; //true
``` 

```javascript
function Rabbit() {}
Rabbit.prototype = { jumps: true}
let rabbit = new Rabbit();
rabbit.constructor === Rabbit; //false. prototype전체를 덮어쓰면서 constructor X

//constructor 다시 사용하기 위해
//수동으로 다시 constructor 만들어줌.
Rabbit.prototype = {
  jumps: true,
  constructor: Rabbit
}

```
