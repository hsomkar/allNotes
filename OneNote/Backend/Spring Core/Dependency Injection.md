- Even the simplest application has a few objects that work together. In other words, one object working with another object is nothing but it is dependent on the other object - Dependency Injection is also known as ‘Inversion of Control (IOC)’ - It is a process whereby objects define their dependencies (i.e., the other object they work with) only through constructor arguments / arguments to a factory method or properties that are set on the object instance after it is constructed or returned from a factory method. The container then injects those dependencies when it creates the bean.  - In simple words, in Dependency Injection, the underlying container / software / framework creates the main object and dependent object and also assigns dependent object to main object. Everything is taken care by the underlying container / software / framework. - In general, if main object is dependent on some other object, then main object has to create / search the dependent object and get the things done. - But in Spring, Spring container is doing all this thing and giving object to us. It is Reverse of regular control flow. Hence, Inversion of Control. - Various ways of Dependency Injection in Spring –
    
    - Setter Injection
        
        - Dependent class object is assigned to main object by calling setter method.
        - ![}uxssep ](Exported%20image%2020250408212750-0.octet-stream)
      
    - Constructor Injection
        
        - Dependent class object is assigned to main object through parametrized constructor.
        - ![class Abc { class Xyz Abc ref; Xyx (Abc ref, m, m) this.ref ref' ](Exported%20image%2020250408212754-1.octet-stream)
      
    - Arguments to a factory method
        
        - To understand this, first we should know what is a factory method.
        - ![a•enud ) zAx ssep {()aqv mau ()a3uetsuna8 3qv 31qnd ) ()IW 31qnd } SSep SSep ](Exported%20image%2020250408212801-2.octet-stream)
