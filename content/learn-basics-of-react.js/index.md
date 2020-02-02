---
title: "Learn Basics of React.js"
description: "Information that gets passed from one component to another is known as ‘props’."
date: "2018-06-02T23:55:29.000Z"
categories: []
published: true
canonical_link: https://medium.com/@akashmishra291997/learn-basics-of-react-js-2189960c995e
redirect_from:
  - /learn-basics-of-react-js-2189960c995e
---

-   Information that gets passed from one component to another is known as ‘_props_’.
-   A component’s props is an object. It holds information about that component. To see a component’s props object, you use the expression this.props as shown in the code below:

```
import React from 'react';
import ReactDOM from 'react-dom';
class Greeting extends React.Component {
 render() {
 return <h1>My name is {this.props.firstName}!</h1>;
 }
} 
ReactDOM.render(<Greeting firstName='Thanos'/>,document.getElementById('app'));
```

Lets import Something :-

```
import React from 'react';
export class Button extends React.Component {
 render() {
 return (
 <button onClick={this.props.talk}> me! </button> 
); 
}
}
```

Lets import Button class:

```
import React from 'react';
import ReactDOM from 'react-dom';
import {Button} from './Button';
talk() {
 alert('Hello!!!');
 } 
class App extends React.Component {
 render() { 
return <Button talk={this.talk}/>; 
}
}
ReactDOM.render(Talker />, document.getElementById('app'));
```

**What is a State?**

-   A React component can access dynamic information in two ways: props and state.
-   Unlike props, a component’s state is not passed in from the outside. A component decides its own state.
-   To make a component have state, give the component a state property. This property should be declared inside of a constructor method, like this:
-   _this.state_ should be equal to an object.
-   To read a component’s state, use the expression _this.state.name-of-property_.
-   The most common way to call _this.setState()_ is to call a custom function that wraps a _this.setState()._ As shown in below example:
-   There is a stateful component, and a stateless component. “Stateful” describes any component that has a state property; “Stateless” describes any component that does not. Pretty simple, eh!
-   Example of passing component from stateful component to stateless component:
-   Stateless components updating their parents state is a React pattern that you’ll see alot.
-   A component can change its state by calling _this.setState()_ but a component should never update _this.props_. A React component should use props to store information that can be changed, but can only be changed by a different component. A React component should use state to store information that the component itself can change.
-   Child component can update the parent’s state as shown in below example, by passing a function down to child that can change parent’s state. Please note: binding at constructor level to make sure the method always refers to the instance of parent.

```
import React from "react";

import ReactDOM from "react-dom";

import { Child } from "./Child";

class Parent extends React.Component {

constructor(props) {

super(props);

this.state = { name: "Frarthur" };

}

render() {

return <Child name={this.state.name} />;

}

}

ReactDOM.render(<Parent />, document.getElementById("app"));
```

Lets import to a stateless component:

-   So stateful parent component passes prop to stateless child component, stateful parent component passes event handler to stateless child component and the child component uses event handler to update parents state. We can also update sibling components.
-   An uncontrolled component is a component that maintains its own internal state. A controlled component is a component that does not maintain any internal state. Since a controlled component has no state, it must be controlled by someone else.
-   Stateless functional component example:

```
import React from 'react'; constructor(props) { super(props); this.handleChange=this.handleChange.bind(this); } // When a user selects a new dropdown item, it will invoke handleChange(e) { const name = e.target.value; this.props.onChange(name); }
// changeName, but it won't pass the correct argument! Instead of 
// passing a new name, it will pass an event object, as all event 
// listeners do. This is a common problem when passing down an event // handler in React! The solution is to define another function that // can extract the name from the event object. export class Child extends React.Component { render() { return ( <div> <h1>Hey my name is {this.props.name}!h1> <select id="great-names" onChange={thi.handleChange }> <option value="Frarthur">Amazonoption> <option value="Gromulus">Google</option> </div> ); }}
```
