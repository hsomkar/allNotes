==We have seen so far that React web apps are actually a collection of independent components that run according to the interactions made with them. Every React Component has a lifecycle of its own, lifecycle of a component can be defined as the series of methods that are invoked in different stages of the component’s existence. The definition is pretty straightforward but what do we mean by different stages? A React Component can go through four stages of its life as follows.==   
 

- **Initialization:** ==This is the stage where the component is constructed with the given Props and default state. This is done in the constructor of a Component Class.==
- **Mounting:** ==Mounting is the stage of rendering the JSX returned by the render method itself.==
- **Updating:** ==Updating is the stage when the state of a component is updated and the application is repainted.==
- **Unmounting:** ==As the name suggests Unmounting is the final step of the component lifecycle where the component is removed from the page.==

==React provides the developers a set of predefined functions that if present is invoked around specific events in the lifetime of the component. Developers are supposed to override the functions with desired logic to execute accordingly. We have illustrated the gist in the following diagram.==  
 

![Initialization Set Props and Initial State of the component in the constructor Mounting componentWillMount( ) render( ) co mpo nentDidMo unt( ) Updation For Props Unmounting For State React Methods ReactDOM Methods setState( ) componentWill'Jrmount( ) componentWiIIUpdat* render( componentDidLDdate( GeeksforGeeks A c science pottal geeks ](Exported%20image%2020250408214238-0.jpeg)

==Now let us describe each phase and its corresponding functions.==  
**Functions of each Phase of Lifecycle**

- **Initialization**==: In this phase, the developer has to define the props and initial state of the component this is generally done in the constructor of the component. The following code snippet describes the initialization process.==
- Javascript 
```
class Clock extends React.Component {

    
constructor(props)

    
{

        
// Calling the constructor of

        
// Parent Class React.Component

        
super
(props);

        
 

        
// Setting the initial state

        
this
.state = { date : 
new
 
Date() };

    
}

}



componentWillRecieveProps(newProps)

{

    
if
 
(
this
.props !== newProps) {

        
console.log(
" New Props have been assigned "
);

        
// Use this.setState() to rerender the page.

    
}

}



import React from 
'react'
;

import ReactDOM from 
'react-dom'
;

 

class Test extends React.Component {

    
constructor(props)

    
{

        
super
(props);

        
this
.state = { hello : 
"World!"
 
};

    
}

 

    
componentWillMount()

    
{

        
console.log(
"componentWillMount()"
);

    
}

 

    
componentDidMount()

    
{

        
console.log(
"componentDidMount()"
);

    
}

 

    
changeState()

    
{

        
this
.setState({ hello : 
"Geek!"
 
});

    
}

 

    
render()

    
{

        
return
 
(

            
<div>

            
<h1>GeeksForGeeks.org, Hello{ 
this
.state.hello }</h1>

            
<h2>

            
<a onClick={
this
.changeState.bind(
this
)}>Press Here!</a>

            
</h2>

            
</div>);

    
}

 

    
shouldComponentUpdate(nextProps, nextState)

    
{

        
console.log(
"shouldComponentUpdate()"
);

        
return
 
true
;

    
}

 

    
componentWillUpdate()

    
{

        
console.log(
"componentWillUpdate()"
);

    
}

 

    
componentDidUpdate()

    
{

        
console.log(
"componentDidUpdate()"
);

    
}

}

 

ReactDOM.render(

    
<Test />,

    
document.getElementById(
'root'
));





```
     constructor(props)  
    {  
        // Calling the constructor of  
        // Parent Class React.Component  
        super(props);  
           
        // Setting the initial state  
        this.state = { date : new Date() };  
    }  
}  
     
 
   ==2==**. Mounting**==: Mounting is the phase of the component lifecycle when the initialization of the component is completed and the component is mounted on the DOM and rendered for the first time on the webpage. Now React follows a default procedure in the Naming Conventions of these predefined functions where the functions containing “Will” represents before some specific phase and “Did” represents after the completion of that phase. The mounting phase consists of two such predefined functions as described below.==

- **componentWillMount() Function**==: As the name clearly suggests, this function is invoked right before the component is mounted on the DOM i.e. this function gets invoked once before the render() function is executed for the first time.==
- **componentDidMount() Function**==: Similarly as the previous one this function is invoked right after the component is mounted on the DOM i.e. this function gets invoked once after the render() function is executed for the first time==

       ==3==**. Updation**==:== ==React is a JS library that helps create Active web pages easily. Now active web pages are specific pages== ==that behave according to== ==their== ==user. For example, let’s take the GeeksforGeeks {IDE} webpage, the webpage acts== ==differently with each user. User A might write some code in C in the Light Theme while another User may write a Python code in the Dark Theme all at the same time. This dynamic behavior that partially depends upon the user itself makes the webpage an Active webpage. Now how can this be related to Updation? Updation is the phase where the states and props of a component are updated followed by some user events such as clicking, pressing a key on== ==the== ==keyboard====,== ==etc. The following are the descriptions of functions that are invoked at different points of Updation phase.==

- **componentWillRecieveProps() Function**==: This is a Props exclusive Function and is independent of States. This function is invoked before a mounted component gets its props reassigned. The function is passed the new set of Props which may or may not be identical to the original Props. Thus checking is a mandatory step in this regard. The following code snippet shows a sample use-case.==
- Javascript 
componentWillRecieveProps(newProps)  
{  
    if (this.props !== newProps) {  
        console.log(" New Props have been assigned ");  
        // Use this.setState() to rerender the page.  
    }  
}

- **setState() Function**==: This is not particularly a Lifecycle function and can be invoked explicitly at any instant. This function is used to update the state of a component. You may refer to== ==this article== ==for detailed information.==
- **shouldComponentUpdate() Function**==: By default, every state or props update re-render the page but this may not always be the desired outcome, sometimes it is desired that updating the page will not be repainted. The shouldComponentUpdate() Function fulfills the requirement by letting React know whether the component’s output will be affected by the update or not. shouldComponentUpdate() is invoked before rendering an already mounted component when new props or state are being received. If returned false then the subsequent steps of rendering will not be carried out. This function can’t be used in the case of forceUpdate(). The Function takes the new Props and new State as the arguments and returns whether to re-render or not.==
- **componentWillUpdate() Function**==: As the name clearly suggests, this function is invoked before the component is rerendered i.e. this function gets invoked once before the render() function is executed after the updation of State or Props.==
- **componentDidUpdate() Function**==: Similarly this function is invoked after the component is rerendered i.e. this function gets invoked once after the render() function is executed after the updation of State or Props.==

      ==4==**. Unmounting**==: This is the final phase of the lifecycle of the component that is the phase of unmounting the component              from the DOM. The following function is the sole member of this phase.==

- **componentWillUnmount() Function**==: This function is invoked before the component is finally unmounted from the DOM i.e. this function gets invoked once before the component is removed from the page and this denotes the end of the lifecycle.==

==We have so far discussed every predefined function there was in the lifecycle of the component, and we have also specified the order of execution of the function. Let us now see one final example to finish the article while revising what’s discussed above.==  
==First====,== ==create a react app and edit your== **index.js** ==file from the src folder.==  
**src index.js:**

- Javascript 
import React from 'react';  
import ReactDOM from 'react-dom';  
   
class Test extends React.Component {  
    constructor(props)  
    {  
        super(props);  
        this.state = { hello : "World!" };  
    }  
   
    componentWillMount()  
    {  
        console.log("componentWillMount()");  
    }  
   
    componentDidMount()  
    {  
        console.log("componentDidMount()");  
    }  
   
    changeState()  
    {  
        this.setState({ hello : "Geek!" });  
    }  
   
    render()  
    {  
        return (  
            <div>  
            <h1>GeeksForGeeks.org, Hello{ this.state.hello }</h1>  
            <h2>  
            <a onClick={this.changeState.bind(this)}>Press Here!</a>  
            </h2>  
            </div>);  
    }  
   
    shouldComponentUpdate(nextProps, nextState)  
    {  
        console.log("shouldComponentUpdate()");  
        return true;  
    }  
   
    componentWillUpdate()  
    {  
        console.log("componentWillUpdate()");  
    }  
   
    componentDidUpdate()  
    {  
        console.log("componentDidUpdate()");  
    }  
}  
   
ReactDOM.render(  
    <Test />,  
    document.getElementById('root'));  
**Output:**

![React App C O localhost:3000 Chapter 1. Intr... co Exercise (Vide... GeeksForGeeks.org, HelloWorld! Press 1--11re! Elements Console Sources S top [HA] Waiting for update signal from componen ) Network nos. Performance Memory Application Security Default levels Lighthouse ](Exported%20image%2020250408214240-1.gif)
