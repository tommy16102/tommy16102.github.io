---
layout: post
title: "Javascript 여러가지"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2022-01-30 20:45 +0900
---

# 화살표 함수 this
```
화살표 함수에서 this를 참조하면, 화살표 함수가 아닌 ‘평범한’ 외부 함수에서 this 값을 가져온다.

let user = {
  firstName: "보라",
  sayHi() {
    let arrow = () => alert(this.firstName);
    arrow();
  }
};

user.sayHi(); // 보라

let user={
    name:'hyemin',
    print:()=>{console.log(user.name);}
}
uesr.print() //hyemin.    화살표함수를 통해 외부로 나옴?.

let user={
    name:'hyemin',
    print:()=>{console.log(this);}
}
user.print() //window    화살표함수를 통해 this는 외부의 window 객체.
```

# toString/valueOf
```
let user = {
  name: "John",
  money: 1000,

  // hint가 "string"인 경우
  toString() {
    return `{name: "${this.name}"}`;
  },

  // hint가 "number"나 "default"인 경우
  valueOf() {
    return this.money;
  }

};

alert(user); // toString -> {name: "John"}
alert(+user); // valueOf -> 1000
alert(user + 500); // valueOf -> 1500
```

# 모듈화

hi.js

```
function hi(){alert('hi')}
```

main.html

```
...
<head>
  <script src = "hi.js"></script>
</head>
<body>
  <script> hi() </script>
</body>
...
```

node.circle.js

```
var PI = Math.PI;
exports.area = function(r) { return PI*r*r;}
```

node.demo.js

```
var res = require('./node.circle.js');
console.log(res.area(5))
```

node node.demo.js 실행  


# 비동기
```
파라미터로 함수를 전달받아, 함수의 내부에서 실행하는 함수=>콜백함수  

미래의 특정 시점에 값을 제공 하겠다는 약속을 반환=>promise

function square(a){
  return new Promise(function(resolve){
    setTimeout(function(){
      resolve(a*a);
    },500)
  })
}

square(10).then(square).then(console.log);
```

pending: 초기, fulfill: 수행 o, reject: 수행 x, settled: fulfill/reject but pending x

![화면 캡처 2021-08-25 193832](https://user-images.githubusercontent.com/75344562/130776326-408fa602-4415-4917-86f1-e1ed57ee2e2f.png)

# JSON

```
const a = [1,2,3,4,5]
const strA = JSON.stringify(a);  // '[1,2,3,4,5]' 배열을 문자열로
const arrA = JSON.parse(strA);  // [1, 2, 3, 4, 5] 문자열을 다시 배열로.
```

# 버블링  

- 한 요소에 이벤트 발생시, 해당 요소에 할당된 핸들러 동작  
- 이어서 부모요소의 핸들러 동작  
- 이 과정을 최상위의 부모 만날때까지 반복.  

```
<style>
  body * {
    margin: 10px;
    border: 1px solid blue;
  }
</style>

<form onclick="alert('form')">FORM
  <div onclick="alert('div')">DIV
    <p onclick="alert('p')">P</p>
  </div>
</form>
```
- p 클릭시 p->div->form  
- div 클릭시 div->form  
- form 클릭시 form  


# 캡처링  

- 버블링과 반대  
- 이벤트가 하위요소로 전파  
- elem.addEventListener(..., true); 로 캡처링 단계 동작 가능 
```
<form>form
  <div>div
    <p>p</p>
   </div>
</form>

<script>
for(let elem of document.querySelectorAll('*')){
  elem.addEventListener('click', e=>console.log("캡쳐링", e.tagName), true);
  elem.addEventListener('click', e=>console.log("버블링", e.tagName));
 }
```
- p 클릭 시, HTML-BODY-FORM-DIV-P 캡처링  
- P-DIV-FORM-BODY-HTML 버블링  


