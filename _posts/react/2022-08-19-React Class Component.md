---
layout: post
title: "React Class Component"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- React
date: 2022-08-19 22:10 +0900
---

### class component
- 함수형 component와는 다르게 state X, lifeCycle 함수 X
- render함수 없으므로 return으로 화면 그림.

### Lifecycle

```javascript
import React from 'react'

class App extends React.Component{
  constructor(props){
    super(props);
    console.log('hello');
  }
  
  state = {
    count:0
  };

  add = () => {
    this.setState(current=>({count:current.count+1})); //setState -> render function 호출
  };
  
  remove = () => {
    this.setState(current=>({count:current.count-1})); //setState -> render function 호출
  }

  componentDidMount(){ //component born
    console.log('component rendered');
  }

  componentDidUpdate(){ //component update
    console.log('component updated');
  }

  componentWillUnmount(){ //component die
    console.log("Goodbye");
  }

  render(){
    console.log("im rendering");
    return(
      <div>
        <h1>Im a class {this.state.count}</h1>
        <button onClick={this.add}>Add</button>
        <button onClick={this.remove}>Minus</button>
      </div>
    )
  }
}

export default App;
```
> constructor() => render() => componentDidMount() => componentDidUpdate() => componentWilUnmount()

#### shouldComponentUpdate
- 값이 달라질때만 rendering => 최적화!.
```
import React, {Component} from 'react'

class Text extends Compoent{
  state={
    counter:0,
  };
  
  shouldComponentUpdate(nextProps, nextState, nextContext){ //
    if(this.state.counter!==nextState.counter) return true;
    return false;
  }
  
  onClick=()=>{ this.setState({ }) }; 
  
  render(){
    return(
      <div>
        <button onClick={this.onClick}></button>
      </div>
    )
  }
}
```

### Component vs PureComponent
- 두 컴포넌트 모두 props, state 변경에 따라 render 함수 호출
- Component => 이전의 state 변숫값과 동일하더라고 변수가 같은 이름으로 생성됐다고 인식 후 render
- PureComponent => 변숫값 동일하면 render 안함.
  - 성능 향상 시킬 수 있음
  - 함수형 컴포넌트에서는 Memo