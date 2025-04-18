- Forms are really important in any website for login, signup, or whatever. It is easy to make a form but forms in React work a little differently. If you make a simple form in React it works, but it’s good to add some JavaScript code to our form so that it can handle the form submission and retrieve data that the user entered. To do this we use controlled components.  
- **Controlled Components:** In simple HTML elements like input tag, the value of the input field is changed whenever the user type. But, In React, whatever the value user types we save it in state and pass the same value to the input tag as its value, so here its value is not changed by DOM, it is controlled by react state. This may sound complicated But let’s understand with an example. 
- First, create react app, and from your project directory update your== **index.js** file from src folder. 
- **src index.js:**
 
```
import React from 
'react'
;

import ReactDOM from 
'react-dom'
;

 
 

class App extends React.Component {

   
 

    
onInputChange(event) {

        
console.log(event.target.value);

    
}

   
 

    
render() {

        
return
 
(

            
<div>

                
<form>

                    
<label>Enter text</label>

                    
<input type=
"text"

                        
onChange={
this
.onInputChange}/>

                
</form>

            
</div>

        
);

    
}

}

 
 

ReactDOM.render(<App />,

            
document.querySelector(
'#root'
));






import React from 
'react'
;

import ReactDOM from 
'react-dom'
;

 
 

class App extends React.Component {

   
 

    
state = { inputValue: 
''
 
};

   
 

    
render() {

        
return
 
(

        
<div>

            
<form>

                
<label> Enter text </label>

                
<input type=
"text"

                    
value={
this
.state.inputValue}

                    
onChange={(e) => 
this
.setState(

                    
{ inputValue: e.target.value })}/>

            
</form>

            
<br/>

            
<div>

                
Entered Value: {
this
.state.inputValue}

            
</div>

        
</div>

        
);

    
}

}

 
 

ReactDOM.render(<App />,

            
document.querySelector(
'#root'
));


import React from 
'react'
;

import ReactDOM from 
'react-dom'
;

 
 

class App extends React.Component {

   
 

    
state = { inputValue: 
''
 
};

 
 

    
onFormSubmit = (event) => {

        
event.preventDefault();

        
this
.setState({ inputValue: 
'Hello World!'
});

    
}

   
 

    
render() {

   
 

        
return
 
(

        
<div>

            
<form onSubmit={
this
.onFormSubmit}>

                
<label> Enter text </label>

                
<input type=
"text"

                
value={
this
.state.inputValue}

                
onChange={(e) => 
this
.setState(

                
{ inputValue: e.target.value })}/>

            
</form>

            
<br/>

            
<div>

                
Entered Value: {
this
.state.inputValue}

            
</div>

        
</div>

        
);

    
}

}

 
 

ReactDOM.render(<App />,

        
document.querySelector(
'#root'
));

```

'react';  
import ReactDOM from 'react-dom';  
    
class App extends React.Component {  
      
    onInputChange(event) {  
        console.log(event.target.value);  
    }  
      
    render() {  
        return (  
            <div>  
                <form>  
                    <label>Enter text</label>  
                    <input type="text"  
                        onChange={this.onInputChange}/>  
                </form>  
            </div>  
        );  
    }  
}  
    
ReactDOM.render(<App />,  
            document.querySelector('#root'));

![React App C G Search Google or type a URL M Gmail YouTube Maps News Translate Enter text helll Elements top Download the Reac h he hel hell Console Geolocation Senso No ](Exported%20image%2020250408214229-0.png)  

==In the above example, the input element is uncontrolled whatever the value user type is in the DOM. We are logging that value on the console by getting it from the DOM and the method onInputChange will be called any time user type in anything so the value will be printed on the console every time (Ctrl + Shift + F11) Google chrome user to open the console.==  
==React is used to handle the value of user enters.==   
   
==Edit src/index.js with given code:==  
**Src index.js:**
 
import React from 'react';  
import ReactDOM from 'react-dom';  
    
class App extends React.Component {  
      
    state = { inputValue: '' };  
      
    render() {  
        return (  
        <div>  
            <form>  
                <label> Enter text </label>  
                <input type="text"  
                    value={this.state.inputValue}  
                    onChange={(e) => this.setState(  
                    { inputValue: e.target.value })}/>  
            </form>  
            <br/>  
            <div>  
                Entered Value: {this.state.inputValue}  
            </div>  
        </div>  
        );  
    }  
}  
    
ReactDOM.render(<App />,  
            document.querySelector('#root'));

![Enter text hello Entered Value: hello ](Exported%20image%2020250408214231-1.png)

==What will happening in the above react example, when we have made inputValue state with value null, and the value of that state is provided to the input field which means whatever the value of the inputValue is we will see it in the input box. And we are updating the value of inputValue each time user changing the value in the input by calling setState() function and dom is re-rendering because we are changing the value of inputValue using setState(). Here, we can easily get the value whatever user type in the input field and pass it to wherever we want from React state. The same happens with other elements like the text area and select. Here is another example that prevents the browser from automatically submitting the form.==  
**Edit src index.js:**
 
import React from 'react';  
import ReactDOM from 'react-dom';  
    
class App extends React.Component {  
      
    state = { inputValue: '' };  
    
    onFormSubmit = (event) => {  
        event.preventDefault();  
        this.setState({ inputValue: 'Hello World!'});  
    }  
      
    render() {  
      
        return (  
        <div>  
            <form onSubmit={this.onFormSubmit}>  
                <label> Enter text </label>  
                <input type="text"  
                value={this.state.inputValue}  
                onChange={(e) => this.setState(  
                { inputValue: e.target.value })}/>  
            </form>  
            <br/>  
            <div>  
                Entered Value: {this.state.inputValue}  
            </div>  
        </div>  
        );  
    }  
}  
    
ReactDOM.render(<App />,  
        document.querySelector('#root'));  
==Output:==

![Activities Google Chrome React App C O localhost:3000 Chapter 1. Intr... co Exercise (Vide... Enter text Entered Value: ](Exported%20image%2020250408214233-2.gif)

==Here we just add onSubmit event handler which calls the function onFormSumbit and performs the action of replacing the value of inputValue to ‘Hello World!’, and the preventDefault() function is used to prevent the browser from submitting the form and reloading the page.==
