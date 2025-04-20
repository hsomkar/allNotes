> [!caution] This page contained a drawing which was not converted.   

# Ep4: Function invocation

- ![Exported image](Exported%20image%2020250408213902-0.png)
- Output:
	10  
	100  
	1
- **EXPLANATION:**
- GEC is created and pushed to Call stack, In memory phase memory is allocated to all variables
- ![Exported image](Exported%20image%2020250408213905-1.png)
- In the second phase, code is executed line by line undefined is replaced with 1, when a() is executed a new execution context is created and pushed to stack, for x it will first look in local then in global
- ![Exported image](Exported%20image%2020250408213911-2.png)
- When a() finish executing, it is cleared from the stack, when b() is called new execution context is created and pushed to stack
- ![Exported image](Exported%20image%2020250408213913-3.png)
- When a() finish executing, it is cleared from the stack, log(x) is logged to console i.e., 1
- ![Exported image](Exported%20image%2020250408213918-4.png)
- After completion of program GEC is also cleared

# Ep7: Scope

- means where we can access specific variable or a function in our code
- Scope is directly connected to Lexical environment
- ![Exported image](Exported%20image%2020250408213921-5.png)
- Output: 10
- ![Exported image](Exported%20image%2020250408213923-6.png)
- Output: b is not defined
- Lexical environment is created when the execution context is created
- Lexical environment: local memory + Lexical environment of its parent
- ![Exported image](Exported%20image%2020250408213926-7.png)
- Scope chain

# Ep8: let & const

- let and const are not hoisted in JS
- let and const are bock scoped
- let is used if we want to reinitialize
- const is used if the value is constant
- const should be initialized
- _Reference error:_ occurs If we try to print let before it is initialized
- _Type error:_ occurs If we try to reinitialize the const
- _Syntax error:_ occurs if we didn't initialize the const

# Ep9: Block scope

- let and const are bock scoped
- If we declare let and const inside the block, we can't use them outside it

# Ep10: Closures

- A function bundled together with its Lexical environment forms a Closure
- ![Exported image](Exported%20image%2020250408213928-8.png) - Function remembers variables present in there parent - ![Exported image](Exported%20image%2020250408213934-9.png)
- Output: 7

# Ep11: setTimeout

- ![Exported image](Exported%20image%2020250408213938-10.png)
- Output:
    - Namaste JavaScript
    - 1 (after 3 sec)

