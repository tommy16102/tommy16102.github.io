---
layout: post
title: "Javascript class"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-08-20 13:24 +0900
---

```javascript
//C++, java와 유사한 class 문법
class Person {
    
    //생성자
    constructor(first, last, age, gender, interests) {
    this.name = {
      first,
      last
    };
    
    this.age = age;
    this.gender = gender;
    this.interests = interests;
  }

  greeting() {
    console.log(`Hi! I'm ${this.name.first}`);
  };

  farewell() {
    console.log(`${this.name.first} has left the building. Bye for now!`);
  };
}

let han = new Person('Han', 'Solo', 25, 'male', ['Smuggling']);
han.greeting();
// Hi! I'm Han


//Person을 상속받는 Teacher class
class Teacher extends Person {
  constructor(first, last, age, gender, interests, subject, grade) {
    super(first, last, age, gender, interests);

    // subject and grade are specific to Teacher
    this.subject = subject;
    this.grade = grade;
  }
}
```
