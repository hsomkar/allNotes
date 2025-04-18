The **this** variable or keyword is a very puzzling and powerful feature of the JavaScript programming language. It is often dreaded by JavaScript newbies and can even pose some challenges to adept developers. This is because of the unpredictability of the object it is referencing in a given context.  
A good understanding of the **this** variable is required to accurately predict what object it is referencing in any context. Once this is acquired it becomes an invaluable tool in the hands of a JavaScript developer.  
The **this** variable in JavaScript behaves differently from other programming languages. Although it refers to an object in a given context, its behavior is not consistent. Consequently, it is hard to understand.  
In this article, we would learn about the behavior of the **this** variable in different execution contexts in JavaScript.  
However, to understand the **this** variable in JavaScript, we need an understanding of some fundamental JavaScript concepts like the execution context and the execution stack — also called the call stack.  
Let’s learn about these fundamental aspects of JavaScript in the next section:

## The Execution Context

Every bit of our code in JavaScript is executed in an execution context.  
The execution context is a wrapper around the currently executing code.  
In a nutshell, the execution context is an abstract context that contains information about the environment of the currently executing code.  
When the JavaScript engine starts executing a JavaScript file — that is as [the JavaScript engine](https://blog.sessionstack.com/how-does-javascript-actually-work-part-1-b0bacc073cf) starts to read our code, it creates an execution context — even if there is no code to execute in the JavaScript file.  
_Consider the image below:_
 ![Global Object this Variable Environment Outer Environment Your Code The Global Execution Context ](Exported%20image%2020250408213843-0.png)

The image above illustrates the global execution context. It consists of the following:

1. The global object. In the browser, this is the window object.
2. The **this** variable. Every execution context provides the **this** variable which refers to an object to which the currently executing code belongs.
3. The variable environment — a place in memory where variables live.
4. The outer environment. When we execute code within a function the outer environment is the code outside that function — at the global level, it is null.

Also, the execution context is created in two phases namely:

1. The creation phase: During this phase, the JavaScript engine goes through our code and adds all the variables and functions to memory.
2. The execution phase: During this phase values are assigned to variables and functions are invoked.

## The Execution Stack

Whenever a function is invoked, a new execution context is created and added to the top of the execution stack.  
The execution stack, is a stack with a **LIFO** (last in first out) structure, that stores all the execution contexts created during code execution.  
The execution stack allows the JavaScript engine to keep track of the order of execution.  
Let’s elaborate using some code examples.  
_Consider the code below:_  

```
      
function
 b() {

        console.log(
"function b is running"
);

        console.log(
"function b is finished"
);

      }

      
function
 a() {

        console.log(
"function a is running"
);

        b();

        console.log(
"function a finished"
);

      }

      console.log(
"hello from global"
);

      a();

      
// returns

      
// "hello from global"

      
// "function a is running"

      
// "function b is running"

      
// "function b is finished"

      
// "function a is finished"












      
// in Node

      console.log(
this
 === global); 
// true

      age = 
100
;

      console.log(global.age); 
// 100

      
this
.developer = 
"Lawrence Eagles"
;

      console.log(global.developer); 
// "Lawrence Eagles"

      
// in browser

      console.log(
this
 === window); 
// true

      age = 
100
;

      console.log(window.age); 
// 100

      
this
.developer = 
"Lawrence Eagles"
;

      console.log(window.developer); 
// "Lawrence Eagles"





      
function
 a() {

        
return
 
this
;

      }

      
function
 b() {

        
"use strict"
;

        
return
 
this
;

      }

      b() === 
undefined
; 
// true

      
// In a browser:

      a() === window; 
// true

      
// In Node:

      a() === globalThis; 
// true



      
function
 b() {

        
'use strict'
;

        
return
 
this
;

      }

      # 
in
 node

      global.b() === global 
// true

      # 
in
 the browser

      window.b() === window 
// true


      
let
 developer = {

        name: 
"Lawrence Eagles"
,

        sayName() {

          console.log(
this
.name);

        },

      };

      
const
 Person = {

        firstName: 
"Lawrence"
,

        lastName: 
"Eagles"
,

        sayName: 
function
 () {

          setTimeout(
function
 () {

            console.log(

              
"my fullname is "
 + 
this
.firstName + 
" "
 + 
this
.lastName

            );

          }, 
100
);

        },

      };

      console.log(Person.sayName()); 
// prints "my fullname is undefined undefined"





      
const
 Person = {

        firstName: 
"Lawrence"
,

        lastName: 
"Eagles"
,

        sayName: 
function
 () {

          
let
 self = 
this
; 
// saves a refrence of the this to the self variable.

          setTimeout(
function
 () {

            console.log(

              
"my fullname is "
 + self.firstName + 
" "
 + self.lastName

            );

          }, 
100
);

        },

      };

      console.log(Person.sayName()); 
// returns "my fullname is Lawrence Eagles"







      
const
 Person = {

        firstName: 
"Lawrence"
,

        lastName: 
"Eagles"
,

        sayName: 
function
 () {

          setTimeout(

            () 
=>

              console.log(

                
"my fullname is "
 + 
this
.firstName + 
" "
 + 
this
.lastName

              ),

            
100

          );

        },

      };

      console.log(Person.sayName()); 
// returns "my fullname is Lawrence Eagles"






      
const
 developer = {

        firstName: 
"John"
,

        lastName: 
"Doe"
,

        getDevName: 
function
 () {

          
let
 fullName = 
this
.firstName + 
" "
 + 
this
.lastName;

          
return
 fullName;

        },

      };

      
const
 logDevName = 
function
 () {

        console.log(
"logged: "
 + 
this
.getDevName());

      };

      
// binds the `this`in the boostedLogDevName function to the developer object.

      
const
 boostedLogDevName = logDevName.bind(developer);

      boostedLogDevName(); 
// "developer's name is:John Doe"





      
const
 Person = {

        firstName: 
"Lawrence"
,

        lastName: 
"Eagles"
,

        sayName: 
function
 () {

          setTimeout(

            
function
 () {

              console.log(

                
"my fullname is "
 + 
this
.firstName + 
" "
 + 
this
.lastName

              );

            }.bind(
this
),

            
100

          ); 
// binds this here.

        },

      };

      console.log(Person.sayName()); 
// returns "my fullname is Lawrence Eagles"



      
function
 Device(name, type) {

        
this
.name = name;

        
this
.type = type;

        console.log(
this
); 
// logs the new object to the console.

      }

      
class
 Person {

        
constructor
(name, gender) {

          
this
.name = name;

          
this
.gender = gender;

          console.log(
this
); 
// logs the new object to the console.

        }

      }

      
const
 myDevice = 
new
 Device(
"Macbook"
, 
"Laptop"
);

      
// returns {name: "Macbook", type: "Laptop"}

      
const
 Developer = 
new
 Person(
"Lawrence"
, 
"Male"
);

      
// {gender: "Male", name: "Lawrence"}



      
// without binding this

      
class
 Logger {

        printName(name = 
"Lawrence Eagles"
) {

          
this
.print(
`Hello 
${
name
}
`
);

        }

        print(text) {

          console.log(text);

        }

      }

      
const
 logger = 
new
 Logger();

      
const
 { printName } = logger;

      printName(); 
// returns: TypeError: Cannot read property 'print' of undefined


      
// bind this in the constructor

      
class
 Logger {

        
constructor
() {

          
this
.printName = 
this
.printName.bind(
this
);

        }

        printName(name = 
"Lawrence Eagles"
) {

          
this
.print(
`Hello 
${
name
}
`
);

        }

        print(text) {

          console.log(text);

        }

      }

      
const
 logger = 
new
 Logger();

      
const
 { printName } = logger;

      printName(); 
// Hello Lawrence Eagles








```

function b() {  
        console.log("function b is running");  
        console.log("function b is finished");  
      }  
      function a() {  
        console.log("function a is running");  
        b();  
        console.log("function a finished");  
      }  
      console.log("hello from global");  
      a();  
      // returns  
      // "hello from global"  
      // "function a is running"  
      // "function b is running"  
      // "function b is finished"  
      // "function a is finished"  
When the above code runs the global execution context is created and our code is executed synchronously. The **console.log** statement in the global execution context is executed and **“hello from global”** is logged to the console.  
Next, the **a()** function invocation is reached which creates a new execution context and adds to the top of the execution stack. The code in this function would now be executed synchronously.  
Here, the first **console.log** statement is reached logging **“function a is running”**. The JavaScript engine then encounters another function call — the **b()** invocation and this creates a new execution context and adds it to the top of the execution — before the code in the **a()** function is fully executed.  
Consequently, the code in the **b()** function would then be executed. Thus **“function b is running”** and **“function b() is finished”** would be logged to the console.  
When the JavaScript engine finishes executing the **b()** function, the execution context is popped off the execution stack, and the remaining code in the **a()** function is then executed, thus logging **“function a is finished”** to the console.  
The image below illustrates the flow of execution of the code sample above:
 ![Global Exectuion Context trom gu•) "hello from global" Execution Context a is Global Exectuion Context "'hello from global" "function a is running" bo Execution context loffunctim b is running-) consok b is finished-) ao Execution Context Global Exectuion Context "hello from global" "function a is running" "function b is running " "function b is finished" Execution Context a finished") Global Exectuion Context "hello from global" "function a is running" "function b is running" "function b is finished" "function a Global Exectuion "hello from global" "function a is running" "function b is running" "function b is finished" ](Exported%20image%2020250408213848-1.png)

With knowledge of these two concepts, we can now dive into the behavior of the **this** variable in different contexts in JavaScript.

# **Understanding the “this” variable**

## **The Global Execution Context:**

The global execution context is the base execution context. It refers to the execution context created by default as the JavaScript engine starts reading our code.  
When we say global we mean something not inside a function, so it is accessible everywhere in our code.  
The global execution context creates the global object and a special variable called the **this** variable.  
In the global execution context, the **this** variable refers to the global object.  
_Consider the code below:_  
      // in Node  
      console.log(this === global); // true  
      age = 100;  
      console.log(global.age); // 100  
      this.developer = "Lawrence Eagles";  
      console.log(global.developer); // "Lawrence Eagles"  
      // in browser  
      console.log(this === window); // true  
      age = 100;  
      console.log(window.age); // 100  
      this.developer = "Lawrence Eagles";  
      console.log(window.developer); // "Lawrence Eagles"

## **The Function Execution Context:**

The function execution context is just like the global execution context. It also goes through the creation and execution phase and it has its variable environment and **this** variable.  
Inside a function, the **this** variable refers to an object depending on how the function is invoked.  
If the value of **this** is not set by the call, the value of **this** refers to the global object — which is the window object in browsers.  
In strict mode, however, the value of **this** is **undefined** if it is not set when entering an execution context.  
_Consider the code below:_  
      function a() {  
        return this;  
      }  
      function b() {  
        "use strict";  
        return this;  
      }  
      b() === undefined; // true  
      // In a browser:  
      a() === window; // true  
      // In Node:  
      a() === globalThis; // true

## **A Function Method Context:**

In the example above the value of **this** in function **b()** is **undefined** because function **b()** was called directly and not as a method — a property of an object.  
When a method — a function in an object is invoked, the **this** binding is set to the object. Thus if we call function **b()** above as a property of the window object we would not get **undefined**.  
_Consider the code below:_  
      function b() {  
        'use strict';  
        return this;  
      }  
      # in node  
      global.b() === global // true  
      # in the browser  
      window.b() === window // true  
The same is true for any JavaScript object as seen below:  
      let developer = {  
        name: "Lawrence Eagles",  
        sayName() {  
          console.log(this.name);  
        },  
      };

## **A Callback:**

_Consider the code below_  
      const Person = {  
        firstName: "Lawrence",  
        lastName: "Eagles",  
        sayName: function () {  
          setTimeout(function () {  
            console.log(  
              "my fullname is " + this.firstName + " " + this.lastName  
            );  
          }, 100);  
        },  
      };  
      console.log(Person.sayName()); // prints "my fullname is undefined undefined"  
In the code above, the value of the **this** variable in the **setTimeout** callback function is **undefined**. This exposes the inconsistency in the behavior of the **this** variable in JavaScript.  
Although we have demonstrated that when a method is called, the **this** value refers to the object containing that method. This rule does not work here.  
There are three ways to access **this** in the callback function above, they are:

1. Explicitly setting this:

This is an old pro-tip. Before ES6 and arrow functions, developers stored a reference to **this** in a variable. The variable is then used in all areas where they want to access **this**. This saves them the stress of having to second guess what **this** is pointing to in any given context.  
_Consider the code below_  
      const Person = {  
        firstName: "Lawrence",  
        lastName: "Eagles",  
        sayName: function () {  
          let self = this; // saves a refrence of the this to the self variable.  
          setTimeout(function () {  
            console.log(  
              "my fullname is " + self.firstName + " " + self.lastName  
            );  
          }, 100);  
        },  
      };  
      console.log(Person.sayName()); // returns "my fullname is Lawrence Eagles"  
We have already noted that in a method, **this** points to the object containing that method. Thus in the **sayName** method, **this** points to the Person object. However, in the **setTimeout** callback, **this** is **undefined**. To access the Person object’s properties in the **setTimeout** callback, we save a reference of **this** in the **sayName** method to a variable called **self**.  
**self** is then used in the callback.  
2. Using Arrow function  
This is the easiest and recommended way to resolve the problem. The behavior of the **this** variable in ES5 function declarations can be very difficult to predict. This can result in bugs that are difficult to resolve.  
ES6 arrow — lambda functions do not have the **this** binding. The implication is that **this** is looked up in scope as a normal variable. So the solution is to use an arrow function as the [setTimeout](https://medium.com/@eaglescoder/how-javascript-works-the-this-variable-and-the-execution-context-12d8f04a40d3) callback.  
_Consider the code below_  
      const Person = {  
        firstName: "Lawrence",  
        lastName: "Eagles",  
        sayName: function () {  
          setTimeout(  
            () =>  
              console.log(  
                "my fullname is " + this.firstName + " " + this.lastName  
              ),  
            100  
          );  
        },  
      };  
      console.log(Person.sayName()); // returns "my fullname is Lawrence Eagles"  
3. Using bind  
This is the most technical of the three solutions.  
Introduced in ES 5, the [](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind)**.bind()** method is a very powerful JavaScript method, especially in the functional programming paradigm.  
Before solving the problem using this method, we will take a look at **.bind()**.  
Let’s start by considering the code below:  
      const developer = {  
        firstName: "John",  
        lastName: "Doe",  
        getDevName: function () {  
          let fullName = this.firstName + " " + this.lastName;  
          return fullName;  
        },  
      };  
      const logDevName = function () {  
        console.log("logged: " + this.getDevName());  
      };  
      // binds the `this`in the boostedLogDevName function to the developer object.  
      const boostedLogDevName = logDevName.bind(developer);  
      boostedLogDevName(); // "developer's name is:John Doe"  
The **bind()** method enables us to explicitly bind **this**. When called on a function, it binds the value of **this** to its first argument and returns a new copy of that function.  
In the above code, **bind()** binds the value of **this** to the developer object and returns a new function stored in the **boostedLogDevName** variable.  
Thus we could access the **getDevName** method from the **boostedLogDevName** function.  
Similarly, we can solve our callback challenge by explicitly binding **this** to the Person object as seen below:  
      const Person = {  
        firstName: "Lawrence",  
        lastName: "Eagles",  
        sayName: function () {  
          setTimeout(  
            function () {  
              console.log(  
                "my fullname is " + this.firstName + " " + this.lastName  
              );  
            }.bind(this),  
            100  
          ); // binds this here.  
        },  
      };  
      console.log(Person.sayName()); // returns "my fullname is Lawrence Eagles"

## **A Function Constructor**

When the **new** operator is used in front of a function it turns that function into a constructor.  
Also, the **new** operator creates a new object and binds the **this** variable to the object.  
_Consider the code below:_  
      function Device(name, type) {  
        this.name = name;  
        this.type = type;  
        console.log(this); // logs the new object to the console.  
      }  
      class Person {  
        constructor(name, gender) {  
          this.name = name;  
          this.gender = gender;  
          console.log(this); // logs the new object to the console.  
        }  
      }  
      const myDevice = new Device("Macbook", "Laptop");  
      // returns {name: "Macbook", type: "Laptop"}  
      const Developer = new Person("Lawrence", "Male");  
      // {gender: "Male", name: "Lawrence"}

## **Classes**

Similar to regular functions — since a JavaScript class is a special function, the value of **this** in a method depends on how it is invoked.  
However, to always refer to the class instance, a common pattern is to bind the class method in the constructor.  
_Consider the code below:_  
      // without binding this  
      class Logger {  
        printName(name = "Lawrence Eagles") {  
          this.print(`Hello ${name}`);  
        }  
        print(text) {  
          console.log(text);  
        }  
      }  
      const logger = new Logger();  
      const { printName } = logger;  
      printName(); // returns: TypeError: Cannot read property 'print' of undefined  
And  
      // bind this in the constructor  
      class Logger {  
        constructor() {  
          this.printName = this.printName.bind(this);  
        }  
        printName(name = "Lawrence Eagles") {  
          this.print(`Hello ${name}`);  
        }  
        print(text) {  
          console.log(text);  
        }  
      }  
      const logger = new Logger();  
      const { printName } = logger;  
      printName(); // Hello Lawrence Eagles  
In the above examples, we see that without explicitly binding **this**, the context of the **printName** method changes. Consequently, our code throws an error.  
The behavior of the **this** variable in JavaScript is quite puzzling. Consequently, it is an aspect of JavaScript that is difficult to master. Notwithstanding by following the guidelines from our discourse above, a developer should be able to use **this** with little or no hassle.  
Also, below are some guidelines to follow when using **this** in JavaScript.  
It has different values depending on where it is used:

- In a method, **this** refers to the owner object.
- Alone, **this** refers to the global object.
- In a function, **this** refers to the global object.
- In a function, in strict mode, **this** is undefined.
- In an event, **this** refers to the element that received the event.
- Methods like call(), and apply() can refer **this** to any object.

It’s quite common that bugs related to a misuse of the **this** variable end up in production. Especially in cases where the code is heavily [asynchronous](https://blog.sessionstack.com/how-javascript-works-event-loop-and-the-rise-of-async-programming-5-ways-to-better-coding-with-2f077c4438b5?source=collection_category---4------3-----------------------). These bugs are often very difficult to troubleshoot as they can be very context-specific and the stack traces can be quite limited in such scenarios.  
In cases like these, a solution like [SessionStack](https://www.sessionstack.com/?utm_source=medium&utm_medium=blog&utm_content=js-series-the-this-variable) could save you tons of troubleshooting time. SessionStack allows you to replay user journeys and interactions as videos allowing you to see exactly where they clicked and what happened on their screen. This visual context combined with all of the output from the browser’s console gives you all of the context needed to easily replicate the problem and resolve it in a timely manner.  
There is a free trial if you’d like to [give SessionStack a try](https://www.sessionstack.com/?utm_source=medium&utm_medium=blog&utm_content=js-series-the-this-variable).
 ![54% 13% sales 21 $1,435 ](Exported%20image%2020250408213854-2.png)

SessionStack replaying a session  
If you missed the previous chapters of the series, you can find them here:
