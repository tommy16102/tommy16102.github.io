---
layout: post
title: "React props"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- React
date: 2021-09-22 20:28 +0900
---
## Class

```
class NumberBaseball extends Component {  
    state={
        result:'',
        value:'',
        answer:getNumbers(),
        tries:[]
    }
    
    onSubmitForm = (e)=>{
        e.preventDefault();
    }

    onChangeInput = (e)=>{
        this.setState({value:e.target.value})
    }

    fruits=[
        {fruit: "사과", taste:"달다"},
        {fruit: "귤", taste:"시다"},
        {fruit: "배", taste:"맛있다"}
    ]

    render(){
        return (
            <>
                <h1>{this.state.result}</h1>
                <form onSubmit={this.onSubmitForm}>
                    <input maxLength={4} value={this.state.value} onChange={this.onChangeInput}></input>
                </form>
                <div>시도 : {this.state.tries.length}</div>
                <ul>
                    {this.fruits.map((v,i)=>
                        (
                            <Try key={i} value={v} index={i}/>
                        )
                    )}
                </ul>
            </>
        );
    }
}
```

```
import React, {Component} from 'react';

class Try extends Component{
    render(){
        return(
            <li>
                <div>{this.props.value.fruit} {this.props.value.taste}</div>
            </li>
        )
    }
}

export default Try

```
