---
layout: post
title: "React lifecycle"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- React
date: 2021-10-3 12:25 +0900
---

```javascript

import React from 'react'

//class component(state 필요x -> function component.)
class App extends React.Component{
  constructor(props){
    super(props);
    console.log('hello');
  }
  state={
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
```
import React, {Component} from 'react'

class Text extends Compoent{
  state={
    counter:0,
  };
  
  shouldComponentUpdate(nextProps, nextState, nextContext){ //값이 달라질때만 rendering => 최적화
    if(this.state.counter!==nextState.counter) return true;
    return false;
  }
  
  onClick=()=>{ this.setState({ }) }; //setState를 통해 값이 안바뀌어도 rendering
  
  render(){
    return(
      <div>
        <button onClick={this.onClick}></button>
      </div>
    )
  }
}
```
