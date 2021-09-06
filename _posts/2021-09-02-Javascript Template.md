---
layout: post
title: "Javascript Template"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-09-02 08:55 +0900
---

```javascript
function sayHello(name){
    console.log(`hello my name is ${name}`);
}

sayHello('minsu'); //hello my name is minsu
sayHello('cheolsu'); //hello my name is cheolsu
```

```javascript

// template => json으로 응답을 받고, javascript object로 변환, 데이터 처리 한 뒤, DOM에 추가.
// 데이터 + html 문자열

const data = [
  {
    name:'coffee1',
    order:true,
    items:['americano','milk']
  },
  {
    name:'coffee2',
    order:false,
  }
]

const template = `<div>welcome ${data[0].name}!!`
console.log(template); //<div>welcome coffee1!!

```

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>JS Bin</title>
</head>
<body>
  <div id="cf"></div>
</body>
</html>
```

```javascript

//template literal

const data = [
  {
    name:'coffee1',
    order:true,
    items:['americano','milk']
  },
  {
    name:'coffee2',
    order:false,
  },
  {
    name:'coffee-king',
    order:true,
    items:['americano','latte']
  }
]

function fn(tags, name, items){
  if(typeof items ==="undefined"){
    items="<span style='color:red'>주문가능한 상품이 없습니다<span>";
  }
  console.log(items);
  return (tags[0]+name+tags[1]+items+tags[2])
}

data.forEach(v=>{
  let template = fn`<h2>welcome ${v.name}!!</h2>
    <h4>주문 가능항목</h4>
    <div>${v.items}</div>
    <br>`

   document.querySelector("#cf").innerHTML+=template
})

```
