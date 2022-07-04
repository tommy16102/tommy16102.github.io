---
layout: post
title: "Javascript 배열"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2022-07-04 15:59 +0900
---

# Array.of  

```javascript
new Array(1); 길이 1인 배열 생성(길이 설정)
new Array(1,2,3); [1, 2, 3] 배열 생성
Array.of(); 빈 배열 생성
Array.of(1); [1] 배열 생성(배열 내 요소 설정)
``` 

# 성긴 배열  

- 인덱스가 연속적이지 않은 배열  
  

```javascript
let a1 = []; //길이 0
let a2 = [,]; //길이 1

let arr = [1,5,6];
delete arr[1]; //요소에 undefined 할당.
arr //[1,,6]
```  
  
  
# pop, push, shift, unshift...  

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
a.sort((a, b) => a - b) //오름차순
a.sort((a, b) => b - a) //


a.reverse() // ['e','c','b']

a.splice(3,0,'f') //['e','c','b','f']

a.slice(1,3) //['c','b'] a배열 건드리지 않고 복사본 만듦 
```
concat, splice => 원본.  
slice => 원본 X, 복사본.  

# for of  
```javascript
let arr = ["빨강", "초록" ,"파랑"];
for (let col of arr) console.log(col); //빨강 초록 파랑
```
for...of => 현재 요소의 인덱스 X, 값만  
for...in => 모든 프로퍼티 대상으로 순회(length 등 필요없는 여러 프로퍼티도 순회).  사용 X!   


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

# reducer
```
///배열 내 요소 돌면서 반복 작업 수행(forEach, for, for...of) + 값 하나 도출
//accumulator : 이전 함수의 호출 결과. 초기값은 initial

let value = arr.reduce(function(accumulator, item, index, array) { }, [initial]);

let arr = [3, 5, 1, 2, 4];

let sum = arr.reduce((sum, item) => sum + item, 0);
//sum 0->3->8->9->11->15

//initial X -> 배열의 첫 번째 요소를 초기값으로 사용 + 두 번째 요소부터 함수 호출.
let result = arr.reduce((sum, item) => sum + item);
```



