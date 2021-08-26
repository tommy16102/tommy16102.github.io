---
layout: post
title: "Javascript 비동기"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-08-26 14:24 +0900
---

```javascript
동기 => 순차적 실행, 어떤 작업이 수행 중일때 다른 작업은 대기.

비동기 => 어떤 작업이 수행이 중일때 다른 작업도 수행 가능(병렬적)
          ex) 서버에서 데이터를 가져와서 출력하는 태스크를 수행할 때, 서버에 데이터를 요청한 이후, 응답할 때까지,
              대기하는 것이 아니라 다음 태스크를 수행 가능.
```
동기  
![동기](https://user-images.githubusercontent.com/75344562/130908248-9cff1f63-c2f3-468e-8cb2-a0d71fbf6799.png)

비동기  
![비동기](https://user-images.githubusercontent.com/75344562/130908653-b7f6593f-2860-4a8f-bca1-9fe4aad4f9f3.png)

