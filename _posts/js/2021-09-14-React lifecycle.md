---
layout: post
title: "React lifecycle"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-09-14 15:55 +0900
---

```javascript

import React from 'react'

//class component.
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
