- Props short for properties is the optional input that your component can accept it also allows the component to be dynamic
- They are immutable
- App.js:
- Greet.js (using Function component)
- Welcome.js ( using Class component)
- Output:

Hello Diana a.k.a Wonder Woman
 
![class App extends Component { render() { return ( <div className="App"> <Greet name: "Bruce" heroName="Batman"> <p>This is children props<./p> </Greet> <Greet name: "Clark" heroName="Superman"> <button>Action</button> </Greet> <Greet name: "Diana" heroName= "Wonder Woman" <Welcome */EI {/* <Hello */} ](Exported%20image%2020250408214056-0.png) ![props { const Greet = console. log( props) return ( <div> <hl> Hello {props. name} </hl> Uprops . children!] </div> a.k.a {props.heroName} ](Exported%20image%2020250408214102-1.png) ![class Welcome extends Component { render() { return <h1>Welcome {this. props. name} a.k.a {this. props.heroName}J/h1El ](Exported%20image%2020250408214105-2.png)

Hello Bruce a.k.a Batman  
This is children props  
Hello Clark a.k.a Superman  
Action
 
# Destructuring props

### Function Component

![import React from 'react' ( {name, heroName}) { const Greet = console. log(props) return ( <div> <hl> Hello {name} a.k.a fflheroNameE] q/hl> </div> export default Greet ](Exported%20image%2020250408214108-3.png)

OR

![import React from .'.yeact ' const Greet = props { const {name, heroName} "oÅ return ( Hello {name} a.k.a {heroName} export default Greet ](Exported%20image%2020250408214111-4.png)

### Class Component

![import React, { Component } from 'react ' class Welcome extends Component { render() { const {name, return ( <hl> Welcome heroName} = this. props {name} a.k.a ßheroName export default Welcome ](Exported%20image%2020250408214114-5.png)
