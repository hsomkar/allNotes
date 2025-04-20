- Singleton(default) – This scopes the bean definition to a single instance per Spring IoC container
    
    - <bean id=“----” class=“----” > ……… </bean> (OR)
    - <bean id=“----” class=“----” scope=“singleton” > ……… <bean> (OR) - Prototype – This scopes a single bean definition to have any number of object instances.
    
    - <bean id=“----” class=“----” scope=“prototype” > ……… <bean> (OR) - Request – This scopes a bean definition to an HTTP request. Only valid in the context of a web-aware Spring ApplicationContext.
    
    - <bean id=“----” class=“----” scope=“request” > ……… <bean> (OR)

- Prototype – This scopes a single bean definition to have any number of object instances.
    
    - <bean id=“----” class=“----” scope=“prototype” > ……… <bean> (OR) - Application – This scopes a bean definition to an application. Only valid in the context of a web-aware Spring ApplicationContext.
    
    - <bean id=“----” class=“----” scope=“application” > ……… <bean> (OR)
 
```
@
Configuration

public
 
class
 MessageConfig {

@
Bean

@
Scope(
"singleton"
) 
// Optional (default)

public
 MessageBean getMessageBean() {

// …

}

}


@
Configuration

public
 
class
 MessageConfig {

@
Bean

@
Scope(
"prototype"
)

public
 MessageBean getMessageBean() {

// …

}

}


@
RequestScope

@
Component

public
 
class
 MyClass {

// …

}

@
SessionScope

@
Component

public
 
class
 MyClass {

// …

}


@
ApplicationScope

@
Component

public
 
class
 MyClass {

// …

}
```

Configuration  
public class MessageConfig {  
@Bean  
@Scope("singleton") // Optional (default)  
public MessageBean getMessageBean() {  
// …  
}  
}
   

@Configuration  
public class MessageConfig {  
@Bean  
@Scope("prototype")  
public MessageBean getMessageBean() {  
// …  
}  
}
   

@RequestScope  
@Component  
public class MyClass {  
// …  
}
 
@SessionScope  
@Component  
public class MyClass {  
// …  
}
   

@ApplicationScope  
@Component  
public class MyClass {  
// …  
}
