---
layout: post
title: "Javascript let, const"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-08-26 19:04 +0900
---
# 선언 let, const  
- var : 지역 및 전역  
- let : 볼록범위 지역변수  
- const : 볼록범위 읽기 전용 상수  

```
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

# 호이스팅  
- var은 선언, 초기화, 할당의 변수 생성 3단계에서 선언과 초기화가 한번에 이뤄짐.=>변수를 위한 공간 확보 후, undefined로 초기화.  
- 반면 let은 선언, 초기화가 분리되어 있음. => 초기화는 변수 선언문에 도달했을 때 이뤄짐. 초기화 전 변수 접근->에러  
- 스코프의 시작지점부터 초기화 시점까지 let 변수 참조 x  

```
console.log(a); //undefined
var a=3;

선언문 -> 해당 스코프의 선두로 옮
다음과 같이 호이스팅이 됨.

var a;
console.log(a);
a=3;
```

### try, catch
```
function ex() {
    var a = 3;
    try {
        throw "exception"
    } catch(a) {
        a = 5;
    }
    return a;
}
```
- catch 블록 안에서만 스코프가 적용되기 때문에 a는 3.  

# const
```
//const는 재할당이 금지되지만, 객체 타입일 경우 객체에 대한 참조는 변경하지 못하지만,  
//객체의 프로퍼티는 보호되지 않음. 배열 및 Object의 값은 변경 가능.

const const user={name:'lee'};
user.name='kim';
console.log(user); //{name:'kim'}
```

> 변수 선언 기본적으로 const, 변경이 필요할 땐 let. var는 es6에선 자제.
