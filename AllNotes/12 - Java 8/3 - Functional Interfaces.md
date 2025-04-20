- Functional interfaces are those interfaces which can have only one abstract method .
- It can have any number of static method, default methods. No restriction on that
- There are many functional interfaces already present in java such as eg : Comparable, Runnable
   

## Q) How lambda expression and functional Interfaces are related?
 
- Functional Interface is used to provide reference to lambda expressions. --> This is the relation
- Comparator<String> c= (s1,$2) > s1.compareTo(s2);
- |   |   |
    |---|---|
    |(s1,s2) > sl.compareTo(s2)|: This is lambda Expression|
    |Comparator<String> c|: This is Functional Interface|
    
- Thus you can see , To call lambda expressions we need Functional Interfaces.
   

## Q) Can you create your own functional interface?
 
- As we know Functional interface is an interface with Exactly One Single Abstract method and can have multiple Static or default methods.
- To create our own Functional interface, You can do following steps:
    
    - Create An interface
    - Annotate that with @FunctionalInterface.
    - Define exactly one Abstract method.
    - There is no restriction on number of static and default methods defined in such and interface.
- Java can implicitly identify functional interface but still you can also annotate it with @FunctionalInterface . It just give you the security that in case if u by mistake add 2 abstract methods then Compiler will throw compile time error.
