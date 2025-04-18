## Conditional Statements
 
- **if** statement
    
    - Syntax:
- **if...else** statement
    
    - Syntax:
- **if...else if...** Statement
    
    - Syntax:
- **switch case**
    
    - Syntax:

if (expression){  
Statement(s) to be executed if expression is true  
}  
if (expression){  
Statement(s) to be executed if expression is true  
}else{  
Statement(s) to be executed if expression is false  
}  
if (expression 1){  
Statement(s) to be executed if expression 1 is true  
}else if (expression 2){  
Statement(s) to be executed if expression 2 is true  
}else{  
Statement(s) to be executed if no expression is true  
}  
switch (expression)  
{  
case condition 1: statement(s)  
break;  
case condition 2: statement(s)  
break;  
...  
case condition n: statement(s)  
break;  
default: statement(s)  
}
 
## Looping Statements
 
- **while** loop
    
    - Syntax:
- **do...while** loop
    
    - Syntax:
- **for** loop
    
    - Syntax:
- **forEach** loop
    
    - Syntax:
- **for of** loop
    
    - Syntax:
- **for...in** loop
    
    - The for-in loop is used to loop through the properties of an object.
    - Syntax:

|
|
==for loop== ==forEach== ==for of== ==for in==
|Does not work with object|Does not work with object, only use with arrays|Does not work with object|Works with object and arrays|
|Does not ignore empty elements|Ignores empty elements|Does not ignore empty elements|Ignores empty elements|
|break statement is supported|break statement is not supported coz it’s a method|break statement is supported|break statement is supported|
|Ignores extra properties which does not have index|Ignores extra properties which does not have index|Ignores extra properties which does not have index|Does not ignore extra properties which does not have index|

while (expression){  
Statement(s) to be executed if expression is true  
}  
do{  
Statement(s) to be executed;  
} while (expression);  
for (initialization; test condition; iteration statement){  
Statement(s) to be executed if test condition is true  
}  
ref.forEach(function(name){  
Statement(s) to be executed;  
});  
for (variableName of object){  
statement or block to execute  
}  
for (variableName in object){  
statement or block to execute  
}
 
## Loop Control
 
- **break** - Used to break the loop.
- **continue** - when executed, control goes to next iteration skipping the current one.
