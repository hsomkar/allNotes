- Variables are containers that you can store values in it.
    
    - Syntax :- var name(identifier) = ‘Raj’;(value)
      
    
- Primitive variables –
    
    - Number
    - String
    - Boolean
    - null
    - Undefined
      
    
- Reference variables –
    
    - Object
    - Arrays
    - Date
    - Math
    - Function
      
    
- All primitives are immutable, i.e., they cannot be altered. It is important not to confuse a primitive itself with a variable assigned a primitive value. The variable may be reassigned a new value, but the existing value can not be changed in the ways that objects, arrays, and functions can be altered which are mutable. 
- Eg.  

```
// Using a string method doesn't mutate the string

var bar = "baz";

console.log(bar);               
// baz

bar.toUpperCase();

console.log(bar);               
// baz

// Using an array method mutates the array

var foo = [];

console.log(foo);               
// []

foo.push(
"plugh"
);

console.log(foo);               
// ["plugh"]

// Assignment gives the primitive a new (not a mutated) value

bar = bar.toUpperCase();       
// BAZ
 var bar = "baz";  
console.log(bar);               // baz  
bar.toUpperCase();  
console.log(bar);               // baz  
// Using an array method mutates the array  
var foo = [];  
console.log(foo);               // []  
foo.push("plugh");  
console.log(foo);               // ["plugh"]  
// Assignment gives the primitive a new (not a mutated) value  
bar = bar.toUpperCase();       // BAZ
```

