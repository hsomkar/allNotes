- It is possible to influence what is rendered on the screen using props and State  
## props vs state
 
### Props:

- props get passed to the component
- Function parameters
- props are immutable
- props - Functional Components
- this.props - Class Components  
### State:
- state is managed within the component
- Variables declared in the function body
- state can be changed
- useState Hook - Functional Components
- this.state - Class Components
 
```
      
import
 React, { Component } 
from
 
" react
'

      
class
 Message 
extends
 Component {

        
constructor
() {

          
super
()

          
this
 . state = {

              message: 
'Welcome visitor'

          }

        }

        changeMessage(){

            
this
.setState({

                message: 
'Thank you for Subscribing'

            })

        }

      render() {

      
return
 (

          
<div>

          
<h1>
{this
.state.message
}
</h1>

          
<button
 
onClick
=
{
()
=>this
.changeMessage()
}
>
Subscribe
</button>

          
</div>

      )

          }

      }

      
export
 
default
 Message







```

import React, { Component } from " react'  
      class Message extends Component {  
        constructor() {  
          super()  
          this . state = {  
              message: 'Welcome visitor'  
          }  
        }  
        changeMessage(){  
            this.setState({  
                message: 'Thank you for Subscribing'  
            })  
        }  
      render() {  
      return (  
          <div>  
          <h1>{this.state.message}</h1>  
          <button onClick={()=>this.changeMessage()}>Subscribe</button>  
          </div>  
      )  
          }  
      }  
      export default Message
 
- Output: welcome visitor with Subscribe button, if we click on button Thank you for subscribing is displayed
 
## setState
 
- Always make use of setState and never modify the state directly.
- Code has to be executed after the state has been updated ? Place that code in the call back function which is the second argument to the setState method.
- ![increment() { this.setState( count: this. state. count + 1 console. log('Catlback value' , console. log(this.state. count) this . state. count) ](Exported%20image%2020250408214120-0.png) - When you have to update state based on the previous state value, pass in a function as an argument instead of the regular object.
- ![this.setstate(prevstate ( { count: prevState.count + 1 D) console. log(this . state. count) ](Exported%20image%2020250408214123-1.png)
- OR we can use props
- ![this.setState((prevState, props) ( { count: prevState.count + props.addValue D) console. log(this . state. count) ](Exported%20image%2020250408214131-2.png)
   

## Destructuring states
 ![class Welcome extends Component { render() { const {name, heroName} const {statel, state2} return ( <hl> = this.props = this. state Welcome {name} a.k.a {heroName} </hl> export default Welcome ](Exported%20image%2020250408214133-3.png)
