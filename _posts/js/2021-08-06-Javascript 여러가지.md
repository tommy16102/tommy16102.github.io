---
layout: post
title: "Javascript 여러가지"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-09-02 11:20 +0900
---
# 선언

```
var //지역 및 전역

let //블록범위 지역변수

const //블록범위 읽기 전용 상수

var <-> let,const

ex)
var x=1;
{
 var x=2;
}
console.log(x); //2

let x=1;
{
 let x=2;
}
console.log(x); //1
```

# 기타
```
alert() -> 경고창

prompt() -> 입력한 값 결과로

document.write() -> 화면 출력

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

# for each
```
// 인자로 주어진 함수 => 배열의 각 요소에서 한번씩 실행됨.
var colors = ['red', 'green', 'blue'];
color.forEach(color => console.log(color));
// red
// green
// blue
```

# spread
```
//펼침 연산자.  배열을 펼침.

let arr=['apple','banana','carrot'];
let data=[...arr];
console.log(data); ///apple banana carrot

let data2=[1,2,...arr,3,4];
console.log(data2); //1 2 apple banana carrot 3 4

function sum(a,b,c){
  return a+b+c;
}

let data3=[1,2,3];
console.log(sum(...data3)); //6
```

# rest parameter
```
//spread와는 다르게 매개변수로 ... => 배열 받음.

function checkNum(...arr){
  console.log(arr);
}
checkNum(10,2,3,4,5);
```

# destructuring
```
///array
let arr = [1,3,5,7,9];
let [first,,third] = arr;
console.log(first, third) //1 5

//object
let obj={
  name:'js',
  age:55,
  address:'seoul'
}

let{name,age}=obj;
console.log(name,age);

let{name:n, age:a}=obj;
console.log(n,a)

//eventlistener
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>JS Bin</title>
</head>
<body>
  <div>안녕하세요</div>
  <script>
    document.querySelector('div').addEventListener('click',function({type,target}){
      console.log(type,target.innerText);
    })
  </script>
</body>
</html>
```
