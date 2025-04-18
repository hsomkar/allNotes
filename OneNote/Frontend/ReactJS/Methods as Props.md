- We know that everything in ReactJS is a component and to pass in data to these components, props are used. 
- Although passing in props like this is great, it surely lacks flexibility in an application. 
- For example, we cannot let the child communicate with the parent in this way. 
- This, nonetheless, can be done by passing methods as props in ReactJS. 
- To use a method as a props all the steps are 
- Now let’s set a state to greet our parent whenever this component is rendered, setting a state is not necessary, but we will do it just to make an application more dynamic. Also, let’s make an event that gives an alert whenever the parent component is rendered. Do not forget to bind the event so that the this keyword won’t return “undefined“. 
- ParentComponent.js: 
```
import React, { Component } from 'react'; 

import ChildComponent from './ChildComponent'; 

class ParentComponent extends Component { 

    constructor(props) { 

        super(props); 

        this.state = { 

            parentName:'Parent' 

        } 

        this.greetParent = this.greetParent.bind(this) 

    } 

    greetParent() { 

        alert(`Hello ${this.state.parentName}`) 

    } 

    render() { 

        return ( 

            <div> 

                <ChildComponent greetHandler={this.greetParent}/> 

            </div> 

        ) 

    } 

} 

export default ParentComponent;
```
- Now let’s make a new component. Let’s call this **ChildComponent**_._**js**, and make a simple functional component. Let’s make a simple button, and then pass the method **greetParent()** as a property. Essentially, the button must greet the parent when it is clicked.
- ChildComponent.js: 
```
import React from 'react'; 

function ChildComponent(props) { 

    return ( 

        <div> 

            <button onClick={() => props.greetHandler()}> 

             Greet Parent 

            </button>    

        </div> 

    ) 

} 

export default ChildComponent;
```
- Let’s not forget to import this into our **App.js** file.
-  App.js : 
```
import './App.css'; 

import React from 'react'; 

// imports component 

import ParentComponent from './components/ParentComponent'; 

function App() { 

  return ( 

    <div className="App"> 

      <h1>-----------METHODS AS PROPS-------------</h1> 

      <ParentComponent /> 

    </div> 

  ); 

} 

export default App;
```

