- The JavaScript this keyword refers to the object it belongs to. 
- It has different values depending on where it is used:
	- In a method, this refers to the **owner object.**
        
```
        const person = {  
        firstName: "John",  
        lastName: "Doe",  
        id: 5566,  
        fullName : function() {  
        return this.firstName + " " + this.lastName;  
        }  
        };
        
        // Display data from the object:  
        document.getElementById("demo").innerHTML = person.fullName();
```
        
- Output: John Doe
          
        
- Alone, this refers to the **global object.**
        
```
        var x = this;  
document.getElementById("demo").innerHTML = x;
```
        
- Output: [object Window]    
- In a function, this refers to the **global object.**
        
```
        document.getElementById("demo").innerHTML = myFunction();  
        function myFunction() {  
        return this;  
        }
```
        
- Output: [object Window]
- In a function, in strict mode, this is **undefined**.
        
```
        "use strict";  
        var x = this;  
document.getElementById("demo").innerHTML = x;
```
        
- Output: [object Window]
          
- In an event, this refers to the **element** that received the event.
        
```
       <button onclick="this.style.display='none'">Click to Remove Me!</button>
```
- Output: Click to Remove Me!(button, after clicking it disappears)      
- Methods like call(), and apply() can refer this to **any object.** 

