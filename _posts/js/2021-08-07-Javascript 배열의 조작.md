---
layout: post
title: "Javascript 배열"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-09-13 19:04 +0900
---
```javascript
var a = ['a','b','c']

a.length  //3

a.push('d') // ['a','b','c','d']

a.concat(['e','f']) // ['a','b','c','d','e','f']

a.unshit('0') // [0, 'a','b','c','d','e','f']

a.splice(1,6,1,2,3) //(시작,개수,변경) [0, 1, 2, 3]



a = ['a','c','b','e','d']

a.shift() // ['c','b','e','d']

a.pop() // ['c','b','e']

a.sort() // ['b','c','e']

a.reverse() // ['e','c','b']

```

# for each
```
// 인자로 주어진 함수 => 배열의 각 요소에서 한번씩 실행됨.
var colors = ['red', 'green', 'blue'];
color.forEach(color => console.log(color));
// red
// green
// blue
```

# filter
```
///배열 내 원소를 대상으로 함수 내 true return하는 원소만 남김.

function Filter() {return true;}
[1,2,3,4].filter(Filter) //[1,2,3,4]

function Filter2(i){
    return i>2;
}
[1,2,3,4,5].filter(Filter2) //[3,4,5]
[1,2,3,4,5].filter(i=>i>2) //[3,4,5]
```
