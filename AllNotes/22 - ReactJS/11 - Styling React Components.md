==There are about eight different ways to styling React Js components, there names and explanations of some of them are mentioned below.==

1. ==Inline CSS==
2. ==Normal CSS==
3. ==CSS in JS==
4. ==Styled Components==
5. ==CSS module==
6. ==Sass & SCSS==
7. ==Less==
8. ==Stylable==

**Inline CSS:** ==In inline styling basically we create objects of style. And render it inside the components in style attribute using the React technique to incorporate JavaScript variable inside the JSX (Using ‘{ }’ )==  
**Example 1:** ==This example illustrates how to use inline styling to style react components.==  
**index.js:**
 
```
import React from 
'react'

import ReactDOM from 
'react-dom'

import App from 
'./App'

 

ReactDOM.render(<App />, document.querySelector(
'#root'
))



import React, { Component } from 
'react'

import StudentList from 
'./StudentList'

 

const App = () => {

  
return
 
(

    
<div>

      
<StudentList

        
name=
'Ashank'

        
classNo=
'X'

        
roll=
'05'

        
addr=
'Kolkata, West Bengal'

      
/>

      
<StudentList

        
name=
'Samir'

        
classNo=
'Xi'

        
roll=
'09'

        
addr=
'Jalpaiguri, West Bengal'

      
/>

      
<StudentList

        
name=
'Tusar'

        
classNo=
'Xii'

        
roll=
'02'

        
addr=
'Howrah, West Bengal'

      
/>

      
<StudentList

        
name=
'Karishma'

        
classNo=
'ix'

        
roll=
'08'

        
addr=
'Mednipur, West Bengal'

      
/>

    
</div>

  
)

}

 

export 
default
 
App



import React, { Component } from 
'react'

 

class StudentList extends Component{

  
render(){

    
const {name, classNo, roll, addr} = 
this
.props

    
const ulStyle = {border: 
'2px solid green'
, width:
'40%'
, listStyleType:
'none'
}

    
const liStyle = {color : 
'blue'
, fontSize:
'23px'
}

    
return
(

      
<ul style={ulStyle}>

        
<li style={liStyle}>Name : {name}</li>

        
<li style={liStyle}>Class: {classNo}</li>

        
<li style={liStyle}>Roll: {roll}</li>

        
<li style={liStyle}>Address : {addr}</li>

      
</ul>

    
)

  
}

}

 

export 
default
 
StudentList






import React from 
'react'

import ReactDOM from 
'react-dom'

import App from 
'./App'

 

ReactDOM.render(<App />, document.querySelector(
'#root'
))



import React from 
'react'
;

import Lottery from 
'./Lottery'

 

function
 
App() {

  
return
 
(

    
<div>

      
<Lottery />

      
<Lottery title=
'Mini Daily'
/>

    
</div>

  
);

}

 

export 
default
 
App;



import React, { Component } from 
'react'

 

class Ball extends Component{

  
render(){

    
const ballStyle = {

      
backgroundColor: 
'tomato'
,

      
borderRadius: 
'50%'
,

      
width:
'3em'
,

      
height:
'2.25em'
,

      
textAlign:
'center'
,

      
paddingTop: 
'0.75em'
,

      
display:
'inline-block'
,

      
marginRight: 
'0.5em'
,

      
marginTop: 
'1em'
,

      
color:
'white'
,

      
fontWeight: 
'bold'
,

      
fontSize: 
'1.5em'

    
}

    
return
(

      
<div style={ballStyle}>

        
{
this
.props.num}

      
</div>

    
)

  
}

}

 

export 
default
 
Ball



import React,{ Component } from 
'react'

import Ball from 
'./Ball'

 

class Lottery extends Component{

  
static defaultProps = {

    
title : 
'lotto'
,

    
numbers : [1,2,3,4,5,6]

  
}

 

  
render(){

    
const lotteryStyle={

      
border: 
'2px solid grey'
,

      
borderRadius: 
'10px'
,

      
width:
'40em'
,

      
textAlign:
'center'
,

      
margin: 
'1em auto auto'
,

      
padding: 
'1em 0 2em 0'

    
}

    
return
(

      
<div style={lotteryStyle}>

        
<h3>{
this
.props.title}</h3>

        
<div>

          
{
this
.props.numbers.map(n => (

            
<Ball num={n} />

          
))}

        
</div>

      
</div>

    
)

  
}

}

 

export 
default
 
Lottery







import React from 
'react'

import ReactDOM from 
'react-dom'

import App from 
'./App'

 

ReactDOM.render(<App />, document.querySelector(
'#root'
))



import React, { Component } from 
'react'

import StudentList from 
'./StudentList'

 

const App = () => {

  
return
 
(

    
<div>

      
<StudentList

        
name=
'Ashank'

        
classNo=
'X'

        
roll=
'05'

        
addr=
'Kolkata, West Bengal'

      
/>

      
<StudentList

        
name=
'Samir'

        
classNo=
'Xi'

        
roll=
'09'

        
addr=
'Jalpaiguri, West Bengal'

      
/>

      
<StudentList

        
name=
'Tusar'

        
classNo=
'Xii'

        
roll=
'02'

        
addr=
'Howrah, West Bengal'

      
/>

      
<StudentList

        
name=
'Karishma'

        
classNo=
'ix'

        
roll=
'08'

        
addr=
'Mednipur, West Bengal'

      
/>

    
</div>

  
)

}

 

export 
default
 
App



import React, { Component } from 
'react'

 

class StudentList extends Component{

  
render(){

    
const {name, classNo, roll, addr} = 
this
.props

    
return
(

      
<ul className=
'StudentList'
>

        
<li className=
'StudentList-details'
>Name : {name}</li>

        
<li className=
'StudentList-details'
>Class: {classNo}</li>

        
<li className=
'StudentList-details'
>Roll: {roll}</li>

        
<li className=
'StudentList-details'
>Address : {addr}</li>

      
</ul>

    
)

  
}

}

 

export 
default
 
StudentList



.StudentList{

    
border
: 
2px
 
solid
 
green
;

    
width
: 
40%
:

    
list-style-type
: 
none
;

    
}

 

.StudentList-details{

    
color
: 
blue
;

    
font-size
: 
23px
;

    
}






npm install react-jss



import React from 
'react'

import ReactDOM from 
'react-dom'

import App from 
'./App'

 

ReactDOM.render(<App />, document.querySelector(
'#root'
))



import React, { Component } from 
'react'

import StudentList from 
'./StudentList'

 

const App = () => {

  
return
 
(

    
<div>

      
<StudentList

        
name=
'Ashank'

        
classNo=
'X'

        
roll=
'05'

        
addr=
'Kolkata, West Bengal'

      
/>

      
<StudentList

        
name=
'Samir'

        
classNo=
'Xi'

        
roll=
'09'

        
addr=
'Jalpaiguri, West Bengal'

      
/>

      
<StudentList

        
name=
'Tusar'

        
classNo=
'Xii'

        
roll=
'02'

        
addr=
'Howrah, West Bengal'

      
/>

      
<StudentList

        
name=
'Karishma'

        
classNo=
'ix'

        
roll=
'08'

        
addr=
'Mednipur, West Bengal'

      
/>

    
</div>

  
)

}

 

export 
default
 
App



import React, { Component } from 
'react'

import {createUseStyles} from 
'react-jss'

 

const styles = createUseStyles({

  
student : {

    
border : 
'2px solid green'
,

    
width: 
'40%'
,

    
listStyleType:
'none'

  
},

 

  
studentDetails : {

    
color : 
'blue'
,

    
fontSize : 
'23px'

  
}

})

 

const StudentList = (props) => {

  
const classes = styles()

  
const {name, classNo, roll, addr} = props

  
return
(

    
<ul className={classes.student}>

      
<li className={classes.studentDetails}>Name : {name}</li>

      
<li className={classes.studentDetails}>Class: {classNo}</li>

      
<li className={classes.studentDetails}>Roll: {roll}</li>

      
<li className={classes.studentDetails}>Address : {addr}</li>

    
</ul>

  
)

}

 

export 
default
 
StudentList






npm install --save styled-components



import React from 
'react'

import ReactDOM from 
'react-dom'

import App from 
'./App'

 

ReactDOM.render(<App />, document.querySelector(
'#root'
))



import React, { Component } from 
'react'

import StudentList from 
'./StudentList'

 

const App = () => {

  
return
 
(

    
<div>

      
<StudentList

        
name=
'Ashank'

        
classNo=
'X'

        
roll=
'05'

        
addr=
'Kolkata, West Bengal'

      
/>

      
<StudentList

        
name=
'Samir'

        
classNo=
'Xi'

        
roll=
'09'

        
addr=
'Jalpaiguri, West Bengal'

      
/>

      
<StudentList

        
name=
'Tusar'

        
classNo=
'Xii'

        
roll=
'02'

        
addr=
'Howrah, West Bengal'

      
/>

      
<StudentList

        
name=
'Karishma'

        
classNo=
'ix'

        
roll=
'08'

        
addr=
'Mednipur, West Bengal'

      
/>

    
</div>

  
)

}

 

export 
default
 
App



import React, { Component } from 
'react'

import styled from 
'styled-components'

 

//styled component Li

const Li = styled.li`

  
color : blue;

  
font-size : 23px

`

 

//Styled component Ul

const Ul = styled.ul`

  
border : 2px solid green;

  
width: 40%;

  
list-style-type:none

`

 

const StudentList = (props) => {

  
const {name, classNo, roll, addr} = props

  
return
(

    
<Ul>

      
<Li>Name : {name}</Li>

      
<Li>Class: {classNo}</Li>

      
<Li>Roll: {roll}</Li>

      
<Li>Address : {addr}</Li>

    
</Ul>

  
)

}

 

export 
default
 
StudentList






import styles from './filename.module.css



import React from 
'react'

import ReactDOM from 
'react-dom'

import App from 
'./App'

 

ReactDOM.render(<App />, document.querySelector(
'#root'
))



import React, { Component } from 
'react'

import StudentList from 
'./StudentList'

 

const App = () => {

  
return
 
(

    
<div>

      
<StudentList

        
name=
'Ashank'

        
classNo=
'X'

        
roll=
'05'

        
addr=
'Kolkata, West Bengal'

      
/>

      
<StudentList

        
name=
'Samir'

        
classNo=
'Xi'

        
roll=
'09'

        
addr=
'Jalpaiguri, West Bengal'

      
/>

      
<StudentList

        
name=
'Tusar'

        
classNo=
'Xii'

        
roll=
'02'

        
addr=
'Howrah, West Bengal'

      
/>

      
<StudentList

        
name=
'Karishma'

        
classNo=
'ix'

        
roll=
'08'

        
addr=
'Mednipur, West Bengal'

      
/>

    
</div>

  
)

}

 

export 
default
 
App



import React, { Component } from 
'react'

import style from 
'./StudentList.module.css'

 

const StudentList = (props) => {

  
const {name, classNo, roll, addr} = props

  
return
(

    
<ul className={style.list}>

      
<li className={style.details}>Name : {name}</li>

      
<li className={style.details}>Class: {classNo}</li>

      
<li className={style.details}>Roll: {roll}</li>

      
<li className={style.details}>Address : {addr}</li>

    
</ul>

  
)

}

 

export 
default
 
StudentList



.list{

    
border
: 
2px
 
solid
 
green
;

    
width
: 
40%
:

    
list-style-type
: 
none
;

    
}

 

.details{

    
color
: 
blue
;

    
font-size
: 
23px
;

    
}







npm install node-sass





import './ StudentList.scss';




import React from 
'react'

import ReactDOM from 
'react-dom'

import App from 
'./App'

 

ReactDOM.render(<App />, document.querySelector(
'#root'
))


import React, { Component } from 
'react'

import StudentList from 
'./StudentList'

 

const App = () => {

  
return
 
(

    
<div>

      
<StudentList

        
name=
'Ashank'

        
classNo=
'X'

        
roll=
'05'

        
addr=
'Kolkata, West Bengal'

      
/>

      
<StudentList

        
name=
'Samir'

        
classNo=
'Xi'

        
roll=
'09'

        
addr=
'Jalpaiguri, West Bengal'

      
/>

      
<StudentList

        
name=
'Tusar'

        
classNo=
'Xii'

        
roll=
'02'

        
addr=
'Howrah, West Bengal'

      
/>

      
<StudentList

        
name=
'Karishma'

        
classNo=
'ix'

        
roll=
'08'

        
addr=
'Mednipur, West Bengal'

      
/>

    
</div>

  
)

}

 

export 
default
 
App


import React, { Component } from 
'react'

import 
'./StudentList.scss'

 

const StudentList = (props) => {

  
const {name, classNo, roll, addr} = props

  
return
(

    
<ul className=
'list'
>

      
<li className=
'details'
>Name : {name}</li>

      
<li className=
'details'
>Class: {classNo}</li>

      
<li className=
'details'
>Roll: {roll}</li>

      
<li className=
'details'
>Address : {addr}</li>

    
</ul>

  
)

}

 

export 
default
 
StudentList


&blue-shade: 
#264BC4
;

&pale-green-
color
: 
#3CC27F
;

 

.list{

    
border
: 
2px
 
solid
 
&pale-green-color;

    
width
: 
40%
:

    
list-style-type
: 
none
;

    
}

 

.details{

    
color
: &blue-shade;

    
font-size
: 
23px
;

    
}

```

'react'  
import ReactDOM from 'react-dom'  
import App from './App'  
   
ReactDOM.render(<App />, document.querySelector('#root'))  
 ==￼==   
**App.js**
 
import React, { Component } from 'react'  
import StudentList from './StudentList'  
   
const App = () => {  
  return (  
    <div>  
      <StudentList  
        name='Ashank'  
        classNo='X'  
        roll='05'  
        addr='Kolkata, West Bengal'  
      />  
      <StudentList  
        name='Samir'  
        classNo='Xi'  
        roll='09'  
        addr='Jalpaiguri, West Bengal'  
      />  
      <StudentList  
        name='Tusar'  
        classNo='Xii'  
        roll='02'  
        addr='Howrah, West Bengal'  
      />  
      <StudentList  
        name='Karishma'  
        classNo='ix'  
        roll='08'  
        addr='Mednipur, West Bengal'  
      />  
    </div>  
  )  
}  
   
export default App  
 ==￼==   
**StudentList.js:** ==It is a studentList component rendered by the App component. It displays details of each student.==
 
import React, { Component } from 'react'  
   
class StudentList extends Component{  
  render(){  
    const {name, classNo, roll, addr} = this.props  
    const ulStyle = {border: '2px solid green', width:'40%', listStyleType:'none'}  
    const liStyle = {color : 'blue', fontSize:'23px'}  
    return(  
      <ul style={ulStyle}>  
        <li style={liStyle}>Name : {name}</li>  
        <li style={liStyle}>Class: {classNo}</li>  
        <li style={liStyle}>Roll: {roll}</li>  
        <li style={liStyle}>Address : {addr}</li>  
      </ul>  
    )  
  }  
}  
   
export default StudentList  
 ==￼==   
**Output:**  
 

![Name : Ashank Class: X Roll: 05 Address : Kolkata, West Bengal Name : Samir Class: Xi Roll: 09 Address : Jalpaiguri, West Bengal Name : Tusar Class: Xii Roll: 02 Address : Howrah, West Bengal Name : Karishma Class: ix Roll: 08 Address : Mednipur, West Bengal ](Exported%20image%2020250408214204-0.png)

_Styling using inline styles_  
**Example 2:**  
**index.js :** 
 
import React from 'react'  
import ReactDOM from 'react-dom'  
import App from './App'  
   
ReactDOM.render(<App />, document.querySelector('#root'))  
 ==￼==   
**App.js**
 
import React from 'react';  
import Lottery from './Lottery'  
   
function App() {  
  return (  
    <div>  
      <Lottery />  
      <Lottery title='Mini Daily'/>  
    </div>  
  );  
}  
   
export default App;  
 ==￼==   
**Ball.js:** ==Ball component responsible to design each ball==
 
import React, { Component } from 'react'  
   
class Ball extends Component{  
  render(){  
    const ballStyle = {  
      backgroundColor: 'tomato',  
      borderRadius: '50%',  
      width:'3em',  
      height:'2.25em',  
      textAlign:'center',  
      paddingTop: '0.75em',  
      display:'inline-block',  
      marginRight: '0.5em',  
      marginTop: '1em',  
      color:'white',  
      fontWeight: 'bold',  
      fontSize: '1.5em'  
    }  
    return(  
      <div style={ballStyle}>  
        {this.props.num}  
      </div>  
    )  
  }  
}  
   
export default Ball  
 ==￼==   
**Lottery.js:** ==Lottery component responsible to render a single lottery card consists of six ball components.==
 
import React,{ Component } from 'react'  
import Ball from './Ball'  
   
class Lottery extends Component{  
  static defaultProps = {  
    title : 'lotto',  
    numbers : [1,2,3,4,5,6]  
  }  
   
  render(){  
    const lotteryStyle={  
      border: '2px solid grey',  
      borderRadius: '10px',  
      width:'40em',  
      textAlign:'center',  
      margin: '1em auto auto',  
      padding: '1em 0 2em 0'  
    }  
    return(  
      <div style={lotteryStyle}>  
        <h3>{this.props.title}</h3>  
        <div>  
          {this.props.numbers.map(n => (  
            <Ball num={n} />  
          ))}  
        </div>  
      </div>  
    )  
  }  
}  
   
export default Lottery  
 ==￼==   
**Output:**  
 

![lotto ооооэо Mini DaiIy ](Exported%20image%2020250408214206-1.png)

_Inline Styling_  
**Normal CSS:** ==In the external CSS styling technique, we basically create an external CSS file for each component and do the required styling of classes. and use those class names inside the component. It is a convention that name of the external CSS file same as the name of the component with ‘.css’ extension. It is better if the name of the classes used, follow the format== **‘componentName-context’** ==(here context signifies where we use this classname). For example, if we style the header of a component called ‘Box’, a better classname should style this element should be== **‘Box-header’.**  
**Example:** ==This example illustrates how to style react components with external stylesheets.==
 
**index.js:**
 
import React from 'react'  
import ReactDOM from 'react-dom'  
import App from './App'  
   
ReactDOM.render(<App />, document.querySelector('#root'))  
 ==￼==   
**App.js :**
 
import React, { Component } from 'react'  
import StudentList from './StudentList'  
   
const App = () => {  
  return (  
    <div>  
      <StudentList  
        name='Ashank'  
        classNo='X'  
        roll='05'  
        addr='Kolkata, West Bengal'  
      />  
      <StudentList  
        name='Samir'  
        classNo='Xi'  
        roll='09'  
        addr='Jalpaiguri, West Bengal'  
      />  
      <StudentList  
        name='Tusar'  
        classNo='Xii'  
        roll='02'  
        addr='Howrah, West Bengal'  
      />  
      <StudentList  
        name='Karishma'  
        classNo='ix'  
        roll='08'  
        addr='Mednipur, West Bengal'  
      />  
    </div>  
  )  
}  
   
export default App  
 ==￼==   
**StudentList.js:** ==It is a studentList component rendered by the App component. It displays details of each student.==
 
import React, { Component } from 'react'  
   
class StudentList extends Component{  
  render(){  
    const {name, classNo, roll, addr} = this.props  
    return(  
      <ul className='StudentList'>  
        <li className='StudentList-details'>Name : {name}</li>  
        <li className='StudentList-details'>Class: {classNo}</li>  
        <li className='StudentList-details'>Roll: {roll}</li>  
        <li className='StudentList-details'>Address : {addr}</li>  
      </ul>  
    )  
  }  
}  
   
export default StudentList  
 ==￼==   
**StudentList.CSS:** ==Since there is no place to add CSS code externally, Here I add a screenshot of the CSS code.==
 
.StudentList{  
    border: 2px solid green;  
    width: 40%:  
    list-style-type: none;  
    }  
   
.StudentList-details{  
    color: blue;  
    font-size: 23px;  
    }  
 ==￼==   
**Output:**  
 

![Name : Ashank Class: X Roll: 05 Address : Kolkata, West Bengal Name : Samir Class: Xi Roll: 09 Address : Jalpaiguri, West Bengal Name : Tusar Class: Xii Roll: 02 Address : Howrah, West Bengal Name : Karishma Class: ix Roll: 08 Address : Mednipur, West Bengal ](Exported%20image%2020250408214208-2.png)

_External CSS styling_  
**CSS in JS:** ==The’react-jss’ integrates JSS with react app to style components. It helps to write CSS with Javascript and allows us to describe styles in a more descriptive way. It uses javascript objects to describe styles in a declarative way using ‘createUseStyles’ method of react-jss and incorporate those styles in functional components using className attribute.==
 
==Command to install third-party react-jss package==  
npm install react-jss  
**Example :**  
**index.js:**
 
import React from 'react'  
import ReactDOM from 'react-dom'  
import App from './App'  
   
ReactDOM.render(<App />, document.querySelector('#root'))  
 ==￼==   
**App.js**
 
import React, { Component } from 'react'  
import StudentList from './StudentList'  
   
const App = () => {  
  return (  
    <div>  
      <StudentList  
        name='Ashank'  
        classNo='X'  
        roll='05'  
        addr='Kolkata, West Bengal'  
      />  
      <StudentList  
        name='Samir'  
        classNo='Xi'  
        roll='09'  
        addr='Jalpaiguri, West Bengal'  
      />  
      <StudentList  
        name='Tusar'  
        classNo='Xii'  
        roll='02'  
        addr='Howrah, West Bengal'  
      />  
      <StudentList  
        name='Karishma'  
        classNo='ix'  
        roll='08'  
        addr='Mednipur, West Bengal'  
      />  
    </div>  
  )  
}  
   
export default App  
 ==￼==   
**StudentList.js:** ==It is a studentList component rendered by the App component. It displays the details of each student.==
 
import React, { Component } from 'react'  
import {createUseStyles} from 'react-jss'  
   
const styles = createUseStyles({  
  student : {  
    border : '2px solid green',  
    width: '40%',  
    listStyleType:'none'  
  },  
   
  studentDetails : {  
    color : 'blue',  
    fontSize : '23px'  
  }  
})  
   
const StudentList = (props) => {  
  const classes = styles()  
  const {name, classNo, roll, addr} = props  
  return(  
    <ul className={classes.student}>  
      <li className={classes.studentDetails}>Name : {name}</li>  
      <li className={classes.studentDetails}>Class: {classNo}</li>  
      <li className={classes.studentDetails}>Roll: {roll}</li>  
      <li className={classes.studentDetails}>Address : {addr}</li>  
    </ul>  
  )  
}  
   
export default StudentList  
 ==￼==   
**Output:**  
 

![Name : Ashank Class: X Roll: 05 Address : Kolkata, West Bengal Name : Samir Class: Xi Roll: 09 Address : Jalpaiguri, West Bengal Name : Tusar Class: Xii Roll: 02 Address : Howrah, West Bengal Name : Karishma Class: ix Roll: 08 Address : Mednipur, West Bengal ](Exported%20image%2020250408214211-3.png)

_Styling with CSS in JS_  
**Styled Components:** ==The styled-components allows us to style the CSS under the variable created in JavaScript. style components is a third party package using which we can create a component as a JavaScript variable that is already styled with CSS code and used that styled component in our main component. styled-components allow us to create custom reusable components which can be less of a hassle to maintain.==
 
==Command to install third-party styled-components package==  
npm install --save styled-components  
**Example:**  
**index.js:**
 
import React from 'react'  
import ReactDOM from 'react-dom'  
import App from './App'  
   
ReactDOM.render(<App />, document.querySelector('#root'))  
 ==￼==   
**App.js**
 
import React, { Component } from 'react'  
import StudentList from './StudentList'  
   
const App = () => {  
  return (  
    <div>  
      <StudentList  
        name='Ashank'  
        classNo='X'  
        roll='05'  
        addr='Kolkata, West Bengal'  
      />  
      <StudentList  
        name='Samir'  
        classNo='Xi'  
        roll='09'  
        addr='Jalpaiguri, West Bengal'  
      />  
      <StudentList  
        name='Tusar'  
        classNo='Xii'  
        roll='02'  
        addr='Howrah, West Bengal'  
      />  
      <StudentList  
        name='Karishma'  
        classNo='ix'  
        roll='08'  
        addr='Mednipur, West Bengal'  
      />  
    </div>  
  )  
}  
   
export default App  
 ==￼==   
**StudentList.js:** ==It is a studentList component rendered by the App component. It displays details of each student.==
 
import React, { Component } from 'react'  
import styled from 'styled-components'  
   
//styled component Li  
const Li = styled.li`  
  color : blue;  
  font-size : 23px  
`  
   
//Styled component Ul  
const Ul = styled.ul`  
  border : 2px solid green;  
  width: 40%;  
  list-style-type:none  
`  
   
const StudentList = (props) => {  
  const {name, classNo, roll, addr} = props  
  return(  
    <Ul>  
      <Li>Name : {name}</Li>  
      <Li>Class: {classNo}</Li>  
      <Li>Roll: {roll}</Li>  
      <Li>Address : {addr}</Li>  
    </Ul>  
  )  
}  
   
export default StudentList  
 ==￼==   
**Output :**  
 

![Name : Ashank Class: X Roll: 05 Address : Kolkata, West Bengal Name : Samir Class: Xi Roll: 09 Address : Jalpaiguri, West Bengal Name : Tusar Class: Xii Roll: 02 Address : Howrah, West Bengal Name : Karishma Class: ix Roll: 08 Address : Mednipur, West Bengal ](Exported%20image%2020250408214214-4.png)

_Styling with styled components_  
**CSS Modules:** ==A CSS module is a simple CSS file but a key difference is by default when it is imported every class name and animation inside the CSS module is scoped locally to the component that is importing it also CSS file name should follow the format== **‘filename.module.css’**==. This allows us to use a valid name for CSS classes without worrying about conflicts with other class names in your application.==
 
==To use CSS modules create a normal CSS file, import the module you have created from within your component using the syntax==  
import styles from './filename.module.css  
**Example :**  
**ndex.js:**
 
import React from 'react'  
import ReactDOM from 'react-dom'  
import App from './App'  
   
ReactDOM.render(<App />, document.querySelector('#root'))  
 ==￼==   
**App.js**
 
import React, { Component } from 'react'  
import StudentList from './StudentList'  
   
const App = () => {  
  return (  
    <div>  
      <StudentList  
        name='Ashank'  
        classNo='X'  
        roll='05'  
        addr='Kolkata, West Bengal'  
      />  
      <StudentList  
        name='Samir'  
        classNo='Xi'  
        roll='09'  
        addr='Jalpaiguri, West Bengal'  
      />  
      <StudentList  
        name='Tusar'  
        classNo='Xii'  
        roll='02'  
        addr='Howrah, West Bengal'  
      />  
      <StudentList  
        name='Karishma'  
        classNo='ix'  
        roll='08'  
        addr='Mednipur, West Bengal'  
      />  
    </div>  
  )  
}  
   
export default App  
 ==￼==   
**StudentList.js :**
 
import React, { Component } from 'react'  
import style from './StudentList.module.css'  
   
const StudentList = (props) => {  
  const {name, classNo, roll, addr} = props  
  return(  
    <ul className={style.list}>  
      <li className={style.details}>Name : {name}</li>  
      <li className={style.details}>Class: {classNo}</li>  
      <li className={style.details}>Roll: {roll}</li>  
      <li className={style.details}>Address : {addr}</li>  
    </ul>  
  )  
}  
   
export default StudentList  
 ==￼==   
**StudentList.module.css:** ==Since there is no place to add CSS code externally, Here I add a screenshot of the CSS code.==
 
.list{  
    border: 2px solid green;  
    width: 40%:  
    list-style-type: none;  
    }  
   
.details{  
    color: blue;  
    font-size: 23px;  
    }  
   
**Output :**  
 

![Name : Ashank Class: X Roll: 05 Address : Kolkata, West Bengal Name : Samir Class: Xi Roll: 09 Address : Jalpaiguri, West Bengal Name : Tusar Class: Xii Roll: 02 Address : Howrah, West Bengal Name : Karishma Class: ix Roll: 08 Address : Mednipur, West Bengal ](Exported%20image%2020250408214217-5.png)

_Styling with CSS modules_  
**Sass and SCSS:** ==Sass is the most stable, powerful, professional-grade CSS extension language. It’s a CSS preprocessor that adds special features such as variables, nested rules, and mixins or syntactic sugar in regular CSS. The aim is to make the coding process simpler and more efficient.==  
**Installation:**  
**Step 1:** ==Before moving further, firstly we have to install node-sass , by running the following command in your project directory, with the help of terminal in your SRC folder or you can also run this command in Visual Studio Code’s terminal in your project folder.== ==￼==   
npm install node-sass  
**Step 2 :** ==After the installation is complete we create a file name StudentList.scss .==  
**Step 3:** ==Now include the necessary CSS effects in your CSS file.==  
**Step 4:** ==Now we import our file the same way we import a CSS file in React.==  
**Step 5:** ==In your app.js file, add this code snippet to import  StudentList.scss.==  
import './ StudentList.scss';  
==Below is a sample program to illustrate the above approach :==  
**Example:**  
**index.js :**
 
import React from 'react'  
import ReactDOM from 'react-dom'  
import App from './App'  
   
ReactDOM.render(<App />, document.querySelector('#root'))  
**App.js :**
 
import React, { Component } from 'react'  
import StudentList from './StudentList'  
   
const App = () => {  
  return (  
    <div>  
      <StudentList  
        name='Ashank'  
        classNo='X'  
        roll='05'  
        addr='Kolkata, West Bengal'  
      />  
      <StudentList  
        name='Samir'  
        classNo='Xi'  
        roll='09'  
        addr='Jalpaiguri, West Bengal'  
      />  
      <StudentList  
        name='Tusar'  
        classNo='Xii'  
        roll='02'  
        addr='Howrah, West Bengal'  
      />  
      <StudentList  
        name='Karishma'  
        classNo='ix'  
        roll='08'  
        addr='Mednipur, West Bengal'  
      />  
    </div>  
  )  
}  
   
export default App  
**StudentList.js :**
 
import React, { Component } from 'react'  
import './StudentList.scss'  
   
const StudentList = (props) => {  
  const {name, classNo, roll, addr} = props  
  return(  
    <ul className='list'>  
      <li className='details'>Name : {name}</li>  
      <li className='details'>Class: {classNo}</li>  
      <li className='details'>Roll: {roll}</li>  
      <li className='details'>Address : {addr}</li>  
    </ul>  
  )  
}  
   
export default StudentList  
**StudentList.scss :** ==Since there is no place to add CSS code externally, Here I add a screenshot of the CSS code.==
 
&blue-shade: '#264BC4';  
&pale-green-color: '#3CC27F';  
   
.list{  
    border: 2px solid &pale-green-color;  
    width: 40%:  
    list-style-type: none;  
    }  
   
.details{  
    color: &blue-shade;  
    font-size: 23px;  
    }
 
**Output :**

![Name : Ashank Class: X Roll: 05 Address : Kolkata, West Bengal Name : Samir Class: Xi Roll: 09 Address : Jalpaiguri, West Bengal Name : Tusar Class: Xii Roll: 02 Address : Howrah, West Bengal Name : Karishma Class: ix Roll: 08 Address : Mednipur, West Bengal ](Exported%20image%2020250408214223-6.png)

_Styling using Sass_
