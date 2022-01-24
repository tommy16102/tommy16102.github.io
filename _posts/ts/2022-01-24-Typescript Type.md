---
layout: post
title: "Typescript Type"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Typescript
date: 2022-01-18 21:30 +0900
---

## Types  
Boolean, Number, String, Array  
String, Array, Tuple, Enum, Any, Void  
Null, Undefined, Never, Object  

#### Boolean  
```typescript
let f: boolean = false;
let t: boolean = true;
```

#### Number  
- 모든 숫자는 부동 소수.  
```typescript
let decimal: number = 6;
let binary: number = 0b10;
```

#### String  
```typescript
let name: string = "Hyemin";
let lines: string = `two
lines`;
```

#### Array  
- [], Array<>  
```typescript
let list: number[] = [1, 2];
let list2: Array<number> = [1, 2, 3];
```

#### Tuple  
- 요소의 타입과 개수가 고정된 배열.  
```typescript
let x: [string, number] = ["str", 10];
```

#### Enum  
```typescript
enum Color {Red, Green, Blue}
let c: Color = Color.Green; // 1
```

#### Any  
- 알지 못하는 타입.  
- 일부만 알고 전체는 알지 못할 때 유용.  
```typescript
let notSure: any = 4;
notSure = "sure";
notSure = false;

let list: any[] = [1, true, "free"];
```

#### Void  
- any의 반대.  
- null, undefined 만 할당 가능.  

#### Never  
- 절대 발생할 수 없는 타입.  
- 모든 타입에 할당 가능, 어떤 타입도 never에 할당 X.  
```typescript
// never를 반환하므로, 함수의 마지막에 도달 불가능.
function error(msg: string): never {
  throw new Error(msg);
}
```

#### Object  
- number, string, boolean, bigint, symbol, null, undefined가 아닌 나머지.  
```typescript
declare function create(o: object | null): void;
create(null);
create({ prop: 0});
create(3); //error. object X
```

