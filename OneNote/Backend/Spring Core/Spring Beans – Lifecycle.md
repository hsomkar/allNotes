- There are 2 phases:
    
    - Initialization phase and Destroy phase.
      
    
- For initialization and destroy phase there are 3 ways to implement. - Implementing InitializingBean and DisposableBean for initialization and destroy phase respectively for the bean class. - Providing attributes init-method and destroy-method for <bean> element in the xml file. - Provide @PostConstruct and @PreDestroy for the init method and destroy method respectively.
    
```
public
 
class
 MyBean 
implements
 InitializingBean, DisposableBean {

// …

@Override

public
 
void
 afterPropertiesSet() 
throws
 Exception {

// initialization phase

}

 

@Override

public
 
void
 destroy() 
throws
 Exception {

// Destroy Phase

}

}


public
 
class
 MyBean {

// …

public
 
void
 init() 
throws
 Exception {

// initialization phase

}

 

public
 
void
 destroy() 
throws
 Exception {

// Destroy Phase

}

}


public
 
class
 MyBean {

// …

@
PostConstruct

public
 
void
 init() 
throws
 Exception {

// initialization phase

}

 

@
PreDestroy

public
 
void
 destroy() 
throws
 Exception {

// Destroy Phase

}

}
```

class MyBean implements InitializingBean, DisposableBean {  
// …  
@Override  
public void afterPropertiesSet() throws Exception {  
// initialization phase  
}  
   
@Override  
public void destroy() throws Exception {  
// Destroy Phase  
}  
}
 
- beans.xml <bean id=“----” class=“----” init-method=“init“ destroy-method=“destroy“ />
 
public class MyBean {  
// …  
public void init() throws Exception {  
// initialization phase  
}  
   
public void destroy() throws Exception {  
// Destroy Phase  
}  
}
   

public class MyBean {  
// …  
@PostConstruct  
public void init() throws Exception {  
// initialization phase  
}  
   
@PreDestroy  
public void destroy() throws Exception {  
// Destroy Phase  
}  
}
