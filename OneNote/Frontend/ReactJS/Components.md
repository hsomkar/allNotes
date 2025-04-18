![Root (App) Component SIDENAV HEADER MAIN CONTENT FOOTER ](Exported%20image%2020250408214033-0.png)

- **Components** describe a part of the user interface
- App component encloses all other components
- They are re-usable and can be nested inside other components
- Two Types -
    - Stateless Functional Components
    - Stateful Class Components
- A component code is generally placed in js file, App component is placed in App.js
 
# Function Component
 
![(xsr) (sdoad) uou.ung Idy.sener sapaadoad ](Exported%20image%2020250408214037-1.png)- Functional component is a JavaScript function that accepts an input of properties and returns HTML that describes the UI
- ![import React from 'react' // function Greet() { return <h1>Hello Vishwas</hl> const Greet = export default Greet ](Exported%20image%2020250408214040-2.png)
- We need to export component by,
    
    - export default <component_name>
    - In App.js we need to import it by using any variable name
- (OR) Named export,
    
    - `export const Greet = () => <h1>Hello Vishwas</h1>`
    - In App.js we need to import it by using same component name
 
# Class Component
 
![Properties (props) ES6 class State HTML (JSX) ](Exported%20image%2020250408214044-3.png)- Class component is a ES6 class that accepts an input of properties and returns HTML that describes the UI
- And it also maintains state
- Steps to write Component:
    
    - Import React and Component class from react library
    - Write class which extends Component class
    - Write a render method which returns null or some html
    - We should export in to App.js
 
# Functional vs Class component

### Functional component:

- Simple functions
- Use Functional components as much as possible
- Absence of 'this' keyword
- Solution without using state
- Mainly responsible for the UI
- Dumb/ Presentational

### Class component:

- More feature rich
- Maintain their own private data - state
- Complex Ul logic
- Provide lifecycle hooks
- Smart/ Container

