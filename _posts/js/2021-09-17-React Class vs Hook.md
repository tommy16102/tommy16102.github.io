---
layout: post
title: "React Class vs Hook"
author: Hyemin Seo
comments: true
tags:
- js
categories:
- Javascript
date: 2021-09-17 08:55 +0900
---

# Class

```javascript

class GuguDan extends React.Component{               
    state={
        first:Math.ceil(Math.random()*9),
        second:Math.ceil(Math.random()*9),
        value:'',
        result:''
    };

    //render는 setState를 할 때마다 실행-> 자주 실행되니 밖으로 빼줌.
    onSubmit=(e)=>{
        e.preventDefault();
        if(this.state.first * this.state.second === parseInt(this.state.value)){
            this.setState((prevState)=>{ //예전 값(바꾸기전 상태값)있으면 함수 사용하기! prevState(예전 값)
                return {
                    result:`${prevState.value} 정답!`,
                    first:Math.ceil(Math.random()*9),
                    second:Math.ceil(Math.random()*9),
                    value:'' 
                }
            })
        }
        else{
            this.setState({
                result:'땡!',
                value:''
            });
        }
        this.input.focus();
    }
    onRefInput=(c)=>{this.input=c};
    onChange=(e)=>{this.setState({value:e.target.value})};

    render(){
        return (
            <React.Fragment>
                <div>{this.state.first} 곱하기 {this.state.second}는?</div>
                <form onSubmit={this.onSubmit}>
                    <input ref={this.onRefInput} type="number" value={this.state.value}
                        onChange={this.onChange}/>
                        <button>입력!</button>
                </form>
                <div>{this.state.result}</div>
            </React.Fragment>
        )
    }
}
```
  
  
# Hook

```javascript

const Gugudan = ()=>{
    //함수 컴포넌트의 Hooks
    const [first,setFirst] = React.useState(Math.ceil(Math.random()*9));
    const [second,setSecond] = React.useState(Math.ceil(Math.random()*9));
    const [value,setValue] = React.useState('');
    const [result,setResult] = React.useState('');

    const inputRef = React.useRef();

    const onChangeInput=(e)=>{
        setValue(e.target.value);
    }

    const onSubmitForm=(e)=>{
        e.preventDefault();
        if(first * second === parseInt(value)){
            setResult('정답 : '+value);
            setFirst(Math.ceil(Math.random()*9));
            setSecond(Math.ceil(Math.random()*9));
            setValue('');
            //setState모아서 한번에 처리(비동기) -> rendering 한번.
        }
        else{
            setResult('땡');
            setValue('');
        }
        inputRef.current.focus();
    }

    console.log('rendering'); //state바뀔때마다 Gugudan 함수 통째로 실행.

    return (
        <React.Fragment>
        <div>{first} 곱하기 {second}는?</div>
        <form ref={inputRef} onSubmit={onSubmitForm}>
            <input onChange={onChangeInput} value={value}/>
            <button className="" htmlFor="">입력!</button>
        </form>
        <div id="result">{result}</div>
        </React.Fragment>
    )
    //class -> className, for -> htmlFor
}
```
<br/><br/>
#### State : (setState(Class) useState(Hook))  
#### 속도 : Class > Hook (Hook은 State가 바뀔 시 위의 예시 코드에서 함수 전체가 실행이 된다.)  
#### 코드 : 길이 Class < Hook (위의 예시코드에서도 Hook 코드가 짧으며, 코드의 양이 많아질수록 Hook의 코드가 짧아진다.)  
<br/><br/><br/><br/><br/><br/>
##### 참조 : [인프런 웹 게임을 만들며 배우는 React](https://www.inflearn.com/course/web-game-react) 
