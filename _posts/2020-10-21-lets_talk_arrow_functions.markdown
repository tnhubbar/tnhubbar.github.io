---
layout: post
title:      "Let's Talk Arrow Functions "
date:       2020-10-21 21:19:00 +0000
permalink:  lets_talk_arrow_functions
---


One topic that I struggled with on my final project was when to use an arrow function, vs when to use a regular function. Arrow functions were introduced in 2015 at ES6 and have become very popular. To show an example of both see below: 
Regular Function: 
``` 
import React from 'react';

export default class Arrows extends React.Component {

constructor(){
    super()
    this.handleChange3 = this.handleChange3.bind(this)
}

   
handleChange(event){
    console.log(this)
} //'this' is instance of handleChange -- this is the regular function 

handleChange1 = (event) => {
    console.log(this)
} //'this' is instance of Arrows  -- this is the arrow function 

handleChange3(event){
    console.log(this)
} //'this' is instance of Arrows -- this is the regular function using bind
 

    render(){
        return(
            <>
            <button onClick={this.handleChange}>Handle Click</button>
            <button onClick={this.handleChange1}>Handle Click 1</button>
            <button onClick={this.handleChange1}>Handle Click 3</button>
            </>
        )
    }
}


```



These 3 ways of writing functions, may look similar, but they are not. The biggest difference comes down to “this”. Which is the execution context in JavaScript (Or “self” as I like to think of it in Ruby). With an arrow function, it does not define its own execution context. “This” will always be the value from the outer function. So whatever the “this” is of the outer function, will be the “this” of your arrow function. It’s lexically bound. This prevents bugs! Also, as developers we are lazy, we don’t like to write long, repetitive code with fluff when we don’t have to. So, when writing methods it can be very annoying to write methods and then to write binding for each of them. It’s also a lot easier to read an arrow function. 

But “do” be advised, there “are” some times when you wouldn’t want to use arrow functions. For example, if this is not bound to anything, and will inherit the value of this from its parent scope. 

```
var cookieJar = {
    cookies: 10, 

    tarynEats: () => {this.tarynEats--
    }
} //the value of this is not bound to anything 
``` 
Overall, arrow functions can make your code more predictable and prevent bugs. It’s also more readable. I hope you found this article useful and hopefully it helped you out. 
