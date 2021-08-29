---
layout: post
title: "Javascript 연습들"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-08-29 14:24 +0900
---



1. filter, includes, from을 사용해서 문자열 'e'가 노드로 구성된 배열 만들어서 반환

```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>ex</title>
</head>
<body>
  <ul>
    <li>apple</li>
    <li>orange</li>
    <li>banana</li>
    <li>strawberry</li>
  </ul>
  <script>
    function print(){
      let list = document.querySelectorAll('li');

      let arr = new Array();
      for(var i=0;i<list.length;i++){
        arr.push(list[i].innerHTML);
      }

      let newArr = Array.from(arr.filter(function(str){
        return str.includes('e');
      }));
      console.log(newArr);
    }
    print();
  </script>
</body>
</html>
```

# 모던 자바스크립트(javascript) 개발을 위한 ES6 강좌(인프런)
