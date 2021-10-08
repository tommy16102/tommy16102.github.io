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

a.splice(1,1) //(시작, 개수) [0,2,3] 공간도 없어져서 길이 줄어든다. 리턴 삭제된 요소

//개수 0이면 삭제안하고 추가 가능.

delete a[1] //[0,,3] 길이는 안줄어든다.



a = ['a','c','b','e','d']

a.shift() // ['c','b','e','d']

a.pop() // ['c','b','e']

a.sort() // ['b','c','e']

a.reverse() // ['e','c','b']

a.splice(3,0,'f') //['e','c','b','f']

a.slice(1,3) //['c','b'] a배열 건드리지 않고 복사본 만듦 
```

# for each
```
// 인자로 주어진 함수 => 배열의 각 요소에서 한번씩 실행됨.
var colors = ['red', 'green', 'blue'];
color.forEach(color => console.log(color));
// red
// green
// blue

["Bilbo", "Gandalf", "Nazgul"].forEach((item, index, array) => {
  alert(`${item} is at index ${index} in ${array}`);
});
//Bilbo is at index 0 in Bilbo,Gandalf,Nazgul
//Gandalf is at index 1 in Bilbo,Gandalf,Nazgul
//Nazgul is at index 2 in Bilbo,Gandalf,Nazgul
```

# find
```
let users = [
  {id: 1, name: "John"},
  {id: 2, name: "Pete"},
  {id: 3, name: "Mary"}
];

let user = users.find(item => item.id == 1);

alert(user.name); // John
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
