- ![Conn on Your Objects The Sprülg Container CHgured SS'Stern for use ](Exported%20image%2020250408212812-0.octet-stream) - We know that, IoC Container needs some configuration data to know what objects it has to instantiate, configure and how to inject the dependencies. - This data is called as Configuration Metadata. - In other words, we can say that, the Configuration Metadata represents the way an application developer tells the Spring container, nothing but IoC container, that how to instantiate, configure and assemble the objects in his application. - But XML is not the only way to supply configuration metadata to IoC Container. - We can provide this configuration metadata using annotations. - Sample of the XML-Based Configuration Metadata –
         

```
<?xml version="1.0" encoding="UTF-8"?>

<
beans
 
xmlns
=
"http://www.springframework.org/schema/beans"

    
xmlns:xsi
=
"http://www.w3.org/2001/XMLSchema-instance"

    
xsi:schemaLocation
=
"http://www.springframework.org/schema/beans

        
https://www.springframework.org/schema/beans/spring-beans.xsd
"
>

 

    
<
bean
 
id
=
"..."
 
class
=
"..."
> 
        
<!-- collaborators and configuration for this bean go here -->

    
</
bean
>

 

    
<
bean
 
id
=
"..."
 
class
=
"..."
>

        
<!-- collaborators and configuration for this bean go here -->

    
</
bean
>

 

    
<!-- more bean definitions go here -->

 

</
beans
>






```
 <beans xmlns="http://www.springframework.org/schema/beans"  
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
xsi:schemaLocation="http://www.springframework.org/schema/beans  
[https://www.springframework.org/schema/beans/spring-beans.xsd](https://www.springframework.org/schema/beans/spring-beans.xsd)">  
   
<bean id="..." class="...">  
<!-- collaborators and configuration for this bean go here -->  
</bean>  
   
<bean id="..." class="...">  
<!-- collaborators and configuration for this bean go here -->  
</bean>  
   
<!-- more bean definitions go here -->  
   
</beans>

- <beans> …………... </beans> is the root element of the configuration metadata. - Inside this <beans> ………. </beans> element, there is a sub-element, <bean> ……... </bean>. - Spring container / IoC container needs to know that what objects it has to manage. That information we supply in Configuration Metadata using <bean> …… </bean> element. - There may be 1 or more <bean> …… </bean> element(s) in the configuration metadata.
