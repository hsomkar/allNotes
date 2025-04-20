- When the user interacts with your application events are fired
### In Function component
- ![import React from 'react ' function FunctionClick() { function clickHand1er() { console. tog( 'Button clicked' ) return ( <div> <button </div> export default FunctionClick ](Exported%20image%2020250408214137-0.png)
### In Class component
- ![import React, { Component } from '.yeact ' class ClassClick extends Component { clickHandler() { console. log( 'Clicked the buttonl• render() { return ( <div> <button me</button> </div> export default ClassClick ](Exported%20image%2020250408214139-1.png)

 
# Binding Event Handlers
 
- In ReactJS, we need to bind events so that the this keyword would not return an “undefined“.
- Let’s write an event that changes the state of message from ‘Welcome‘ to ‘Farewell‘ whenever the button is clicked. So let’s define an onClick method to the button and write an event handler clickHandler().
```
import React, { Component } from 'react'; 

class EventBind extends Component { 

    constructor(props) { 

        super(props) 

        this.state = { 

            message: 'Welcome' 

        } 

    } 

    clickHandler() { 

        this.setState({ 

            message:'Farewell' 

        }) 

    } 

    render() { 

        return ( 

            <div> 

                <h3>{this.state.message}</h3> 

                <button onClick={this.clickHandler}>Click</button>  

            </div> 

        ) 

    } 

} 

export default EventBind;
```
- **Output:** Now if we run the application and click on the button, we get an error. This is because _this_ returns an _“undefined”_. This is why we need to bind our events.
- Binding Event Handler in Render Method: We can bind the handler when it is called in the render method using bind() method.
```
import React, { Component } from 'react'; 

class EventBind extends Component { 

    constructor(props) { 

        super(props) 

        this.state = { 

            message: 'Welcome' 

        } 

    } 

    clickHandler() { 

        this.setState({ 

            message:'Farewell' 

        }) 

    } 

    render() { 

        return ( 

            <div> 

                <h3>{this.state.message}</h3> 

                <button onClick={this.clickHandler.bind(this)}> 

                         Click</button>  

            </div> 

        ) 

    } 

} 

export default EventBind;
```
- **Binding Event Handler using Arrow Function:** This is pretty much the same approach as above, however, in this approach we are binding the event handler implicitly. This approach is the best if you want to pass parameters to your event. 
```
import React, { Component } from 'react'; 

class EventBind extends Component { 

    constructor(props) { 

        super(props) 

        this.state = { 

            message: 'Welcome' 

        } 

    } 

    clickHandler() { 

        this.setState({ 

            message:'Farewell' 

        }) 

    } 

    render() { 

        return ( 

            <div> 

                <h3>{this.state.message}</h3> 

                <button onClick={() => this.clickHandler()}> 

                  Click 

                </button>  

            </div> 

        ) 

    } 

} 

export default EventBind;
```
- **Binding Event Handler in the Constructor:** In this approach, we are going to bind the event handler inside the constructor. This is also the approach that is mentioned in **ReactJS** **documentation**. This has performance benefits as the events aren’t binding every time the method is called, as opposed to the previous two approaches. Just add the following line in the constructor for this approach,
	- `this.clickHandler = this.clickHandler.bind(this)`
- **Binding Event Handler using Arrow Function as a Class Property:** This is probably the best way to bind the events and still pass in parameters to the event handlers easily.
 
```
import React, { Component } from 'react'; 

class EventBind extends Component { 

    constructor(props) { 

        super(props) 

        this.state = { 

            message: 'Welcome' 

        } 

    } 

    clickHandler = () => { 

        this.setState({ 

            message:'Farewell' 

        }) 

    } 

    render() { 

        return ( 

            <div> 

                <h3>{this.state.message}</h3> 

                <button onClick={this.clickHandler}> 

                  Click 

                </button>  

            </div> 

        ) 

    } 

} 

export default EventBind;
```

