- To inject bean normally to another bean, elements <constructor-arg> and <property> are used. - But spring container can auto-wire the injection without <constructor-arg> and <property> elements. - Auto-wiring is configured in <bean> element in xml file. 
```
</
bean
>



</
bean
>


</
bean
>


</
bean
>

}

</
bean
>

}

 

@
Configuration

}
}

 

@
Configuration

}



<
bean
 
id
=
“----”
 
class
=
“----”
>

<
property
 
name
=
“----”
 
value
=
“----”
 
/>

<
property
 
name
=
“----”
 
ref
=
“----”
 
/>




<
bean
 
id
=
“----”
 
class
=
“----”
 
autowire
=
"byName"
>

<
property
 
name
=
“----”
 
value
=
“----”
 
/>


<
bean
 
id
=
“----”
 
class
=
“----”
 
autowire
=
"byType"
>

<
property
 
name
=
“----”
 
value
=
“----”
 
/>


<
bean
 
id
=
“----”
 
class
=
“----”
 
autowire
=
"constructor"
>

<
constructor-arg
 
name
=
“----”
 
value
=
“----”
 
/>

// for other properties


public class
 MyClass {

@
Autowired

private
 DependentClass ref;

<
bean
 id
=
“----”
 
class
=
“----”
 
primary
=
"true"
>

<
property
 
name
=
“----”
 
value
=
“----”
 
/>

public class
 MyClass {

@
Autowired

@
Qualifier(“d1”)

private
 DependentClass ref;

public class
 MyConfig {

@
Bean(name = “d1”)

public
 DependentClass getDependentBean1() 

{

// …

}

@
Bean(name = “d2”)

public
 DependentClass getDependentBean2() 

{

// …

}

public
 
class
 MyClass {

@
Autowired

private
 DependentClass 
ref
;

public
 
class
 MyConfig {

@
Bean(name = “d1”)

@
Component

public
 DependentClass getDependentBean1() 

{

// …

}

@
Bean(name = “d2”)

public
 DependentClass getDependentBean2() 

{

// …

}
```

bean>
 - No auto-wiring (default) using “ref” – - There are 3 modes in auto-wiring in xml based –
    
    1. byName
      
    
    </bean>
    
      
    5. byType
      
    
    </bean>
    
      
    9. Constructor
      
    
    </bean>
     - Auto-Wiring Using Annotation –
    
    - using “primary” attribute in xml
    
    }
    
      
    
    </bean>  
     
    
    - using @Qualifier
    
    }  
       
    @Configuration  
    }
    
    - using @Component
    
    }  
       
    @Configuration  
    }
    
    
<bean id=“----” class=“----”>  
<property name=“----” value=“----” />  
<property name=“----” ref=“----” />
      

<bean id=“----” class=“----” autowire="byName">  
<property name=“----” value=“----” />
   

<bean id=“----” class=“----” autowire="byType">  
<property name=“----” value=“----” />
   

<bean id=“----” class=“----” autowire="constructor">  
<constructor-arg name=“----” value=“----” />  
// for other properties
   

public class MyClass {  
@Autowired  
private DependentClass ref;
 
<bean id=“----” class=“----” primary="true">  
<property name=“----” value=“----” />  
public class MyClass {  
@Autowired  
@Qualifier(“d1”)  
private DependentClass ref;  
public class MyConfig {  
@Bean(name = “d1”)  
public DependentClass getDependentBean1()  
{  
// …  
}  
@Bean(name = “d2”)  
public DependentClass getDependentBean2()  
{  
// …  
}  
public class MyClass {  
@Autowired  
private DependentClass ref;  
public class MyConfig {  
@Bean(name = “d1”)  
@Component  
public DependentClass getDependentBean1()  
{  
// …  
}  
@Bean(name = “d2”)  
public DependentClass getDependentBean2()  
{  
// …  
}


