---
layout: post
title: "Javascript 객체"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-09-29 12:53 +0900
---
```javascript
//1
{key:value}
var score = {'a':98, 'b':95, 'c':99}

//2
var score = {};
score['a']=98
score['b']=95
score['c']=99

score['a'] //98
score['b'] //95
score.a //98
score.b //95

delete score.c //c 삭제

for(var key in score) document.write(key+' '+score[key]) // a 98 b 98

//객체와 함수를 담은 객체
var list = {
  'score' : {'a':98, 'b':95, 'c':99},
  'show' : function() {
    for(var key in this.score) document.write(key+' '+this.score[key])
  }
}

list.show() //a 98 b 98 c 99

let user = {
  name: "John",
  age: 30,
  "likes birds": true  // 복수의 단어 likes birds는 따옴표로 묶어야 합니다.
};


//계산된 프로퍼티
s='name'
let user={
  [s]:'john'  //프로퍼티 이름을 변수 s에서 가져와서 name이 된다.
}
user[s]='john' //위의 것과 같은 결과. user{'name':'john'}

let user={
  ['my'+s]:'john'  //user{'myname':'john'}
} 

//단축
function makeUser(name, age) {
  return {
    name, // name: name 
    age,  // age: age 
    // ...
  };
}
let user=makeUser('john',25) //user{name:'john', age:25}


//프로퍼티 확인 "key" in object
let obj={
    name:'john',
    age:undefined
}
obj.sex //undefined
obj.age //undefined

'sex' in obj //false
'age' in obj //true

```
