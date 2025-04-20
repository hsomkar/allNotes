- Lists are mainly used for displaying menus in a website, for example, the navbar menu. - We can use the map() function in JavaScript for traversing the lists. - Illustration of map():
- Output: [3, 4, 5, 6, 7] - Rendering List:
- Rendering lists inside Components: - Lists and Keys
   

```
<script type=
"text/javascript"
>

    
var
 
numbers = [1,2,3,4,5];

 
 

    
const updatedNums = numbers.map((number)=>{

        
return
 
(number + 2);

    
});

 
 

    
console.log(updatedNums);

</script>


import React from 
'react'
;

import ReactDOM from 
'react-dom'
;

 

const numbers = [1,2,3,4,5];

 

const updatedNums = numbers.map((number)=>{

    
return
<li>{number}</li>;

});

 

ReactDOM.render(

    
<ul>

        
{updatedNums}

    
</ul>, 

    
document.getElementById(
'root'
)

);


import React from 
'react'
;

import ReactDOM from 
'react-dom'
;

 
 

// Component that will return an

// unordered list

function
 
Navmenu(props)

{

    
const list = props.menuitems;

 
 

    
const updatedList = list.map((listItems)=>{

        
return
 
<li>{listItems}</li>;

    
});

 
 

    
return
(

        
<ul>{updatedList}</ul>

    
);

}

 
 

const menuItems = [1,2,3,4,5];

 
 

ReactDOM.render(

    
<Navmenu menuitems = {menuItems} />, 

    
document.getElementById(
'root'
)

);


import React from 
'react'
;

import ReactDOM from 
'react-dom'
;

 
 

// Component that will return an

// unordered list

function
 
Navmenu(props)

{

    
const list = props.menuitems;

 
 

    
const updatedList = list.map((listItems)=>{

        
return
(

                
<li key={listItems.toString()}>

                    
{listItems}

                
</li>

            
); 

    
});

 
 

    
return
(

        
<ul>{updatedList}</ul>

    
);

}

 
 

const menuItems = [1,2,3,4,5];

 
 

ReactDOM.render(

    
<Navmenu menuitems = {menuItems} />, 

    
document.getElementById(
'root'
)

);











```

"text/javascript">  
    var numbers = [1,2,3,4,5];  
    
    const updatedNums = numbers.map((number)=>{  
        return (number + 2);  
    });  
    
    console.log(updatedNums);  
</script>
   

import React from 'react';  
import ReactDOM from 'react-dom';  
    
const numbers = [1,2,3,4,5];  
    
const updatedNums = numbers.map((number)=>{  
    return <li>{number}</li>;  
});  
    
ReactDOM.render(  
    <ul>  
        {updatedNums}  
    </ul>,   
    document.getElementById('root')  
);
   

import React from 'react';  
import ReactDOM from 'react-dom';  
    
// Component that will return an  
// unordered list  
function Navmenu(props)  
{  
    const list = props.menuitems;  
    
    const updatedList = list.map((listItems)=>{  
        return <li>{listItems}</li>;  
    });  
    
    return(  
        <ul>{updatedList}</ul>  
    );  
}  
    
const menuItems = [1,2,3,4,5];  
    
ReactDOM.render(  
    <Navmenu menuitems = {menuItems} />,   
    document.getElementById('root')  
);
   

import React from 'react';  
import ReactDOM from 'react-dom';  
    
// Component that will return an  
// unordered list  
function Navmenu(props)  
{  
    const list = props.menuitems;  
    
    const updatedList = list.map((listItems)=>{  
        return(  
                <li key={listItems.toString()}>  
                    {listItems}  
                </li>  
            );   
    });  
    
    return(  
        <ul>{updatedList}</ul>  
    );  
}  
    
const menuItems = [1,2,3,4,5];  
    
ReactDOM.render(  
    <Navmenu menuitems = {menuItems} />,   
    document.getElementById('root')  
);
 
- We can't access the key in child component - A "key" is a special string attribute you need to include when creating lists of elements. - Keys give the elements a stable identity.
- Keys help React identify which items have changed, are added, or are removed. - Help in efficient update of the user interface.

