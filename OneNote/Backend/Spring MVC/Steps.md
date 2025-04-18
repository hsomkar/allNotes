## web.xml:

## web.xml:
 - First configure web.xml, which is also called as deployment descriptor, sample is as follows, 
```
   
http://java.sun.com/xml/ns/j2ee/web-app_2_4.xsd
"
>

 

</
web-app
>


<?
xml
 
version
=
"1.0"
 
encoding
=
"UTF-8"
?>

</
beans
>



</
servlet
>




















<
web-app
 
id
=
"WebApp_ID"
 
version
=
"2.4"

xmlns
=
"http://java.sun.com/xml/ns/j2ee"

xmlns:xsi
=
"http://www.w3.org/2001/XMLSchema-instance"

xsi:schemaLocation
=
"http://java.sun.com/xml/ns/j2ee 

 

<
display-name
>
emp-springmvc
</
display-name
>

<
servlet
>

<
servlet-name
>
dispatcher
</
servlet-name
>

<
servlet-class
>
org.springframework.web.servlet.DispatcherServlet
</
servlet-class
>

</
servlet
>

<
servlet-mapping
>

<
servlet-name
>
dispatcher
</
servlet-name
>

<
url-pattern
>
/
</
url-pattern
>

</
servlet-mapping
>


<
beans
 
xmlns
=
"http://www.springframework.org/schema/beans"

xmlns:context
=
"http://www.springframework.org/schema/context"

xmlns:mvc
=
"http://www.springframework.org/schema/mvc"

xmlns:xsi
=
"http://www.w3.org/2001/XMLSchema-instance"

xsi:schemaLocation
=
"http://www.springframework.org/schema/beans

http://www.springframework.org/schema/beans/spring-beans.xsd

http://www.springframework.org/schema/context

http://www.springframework.org/schema/context/spring-context-3.0.xsd

http://www.springframework.org/schema/mvc

http://www.springframework.org/schema/mvc/spring-mvc-3.0.xsd
"
>

<
context:component-scan

base-package
=
"com.testyantra.emp"
></
context:component-scan
>

<
bean

class
=
"org.springframework.web.servlet.view.InternalResourceViewResolver"
>

<
property
 
name
=
"prefix"
 
value
=
"/WEB-INF/views/"
></
property
>

<
property
 
name
=
"suffix"
 
value
=
".jsp"
></
property
>

</
bean
>



<
servlet
>

<
servlet-name
>
dispatcher
</
servlet-name
>

<
servlet-class
>
org.springframework.web.servlet.DispatcherServlet
</
servlet-class
>

<
init-param
>

<
param-name
>
contextConfigLocation
</
param-name
>

<
param-value
>
/WEB-INF/applicationRoot.xml
</
param-value
>

</
init-param
>




















```

[http://java.sun.com/xml/ns/j2ee/web-app_2_4.xsd](http://java.sun.com/xml/ns/j2ee/web-app_2_4.xsd)">  
   
</web-app>

## dispatcher-servlet.xml:
 - Then we need to set-up dispatcher-servlet which is ‘Front controller’ in MVC architecture. 
<?xml version="1.0" encoding="UTF-8"?>  
</beans>
 - This file name must be – <servlet-name>-servlet.xml - If you want to give different name for this file, then you will have to configure <init-param> for ‘DispatcherServlet’ in “web.xml”. E.g.- If you want file name as “applicationRoot.xml” then – 
</servlet>
 
## Controller:
 - The DispatcherServlet delegates the request to the controllers to execute the functionality specific to it. - **@Controller** annotation indicates that a particular class serves the role of a controller. - We can write multiple controllers. - **@RequestMapping** annotation is used to map a URL to either an entire class or a particular handler method. - Sending data from Controller to view:
    
    - String – We can return only View name of String return type.
      
    - Model – this object can return data need to be rendered on view page.
        
        - On Model object we will use addAttribute to add data.
          
        
    - ModelMap – Is similar to Model but it extends Map and contains all methods of it.
      
    - ModelAndView - this object can return data and view-name.
        
        - On ModelAndView object we will use addObject to add data and setViewName to set view name.
        -   
            
    - @ResponseBody –binds the method return value to the web response body. It is not interpreted as a view name but same is printed on the web page.
      
    
- Getting form data from view to Controller:
    
    - Using HttpServletRequest Object –
        
        - req.getParameter("userId")
        - req.setAttribute("userId", userId)
          
        
    - Using @RequestParam –
        
        - public String submitFrom (@RequestParam (name = "userId") int id, ModelMap modelMap)
        - modelMap.addAttribute("userId", id)
          
        
    - By Giving parameter name same as of <input> tag name –
        
        - public String submitForm (int userId, String password, ModelMap modelMap)
        - modelMap.addAttribute("userId", id)
          
        
    - Using DTO / Bean Object –
        
        - class UserBean {private … //setters and getters}
        - public String submitForm(UserBean userBean, ModelMap modelMap) { modelMap.addAttribute("userBean", userBean);}
          
        
    - Using @ModelAttribute –
        
        - class UserBean {private … //setters and getters}
        - public String submitForm(@ModelAttribute UserBean userBean, Model model) {return “viewName”;}
        - If we want to display common data on all pages, then we will write one method with ‘@ModelAttribute’ on it. This method will be called before calling any handler method.
          
        

## View:
 - Create view pages using html or jsp. - If you want to send data from view to controller, make sure to write form tag, action, method, field name, etc.
   

<web-app id="WebApp_ID" version="2.4"  
xmlns="http://java.sun.com/xml/ns/j2ee"  
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
xsi:schemaLocation="http://java.sun.com/xml/ns/j2ee  
   
<display-name>emp-springmvc</display-name>  
<servlet>  
<servlet-name>dispatcher</servlet-name>  
<servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>  
</servlet>  
<servlet-mapping>  
<servlet-name>dispatcher</servlet-name>  
<url-pattern>/</url-pattern>  
</servlet-mapping>

## dispatcher-servlet.xml:
   

<beans xmlns="http://www.springframework.org/schema/beans"  
xmlns:context="http://www.springframework.org/schema/context"  
xmlns:mvc="http://www.springframework.org/schema/mvc"  
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
xsi:schemaLocation="http://www.springframework.org/schema/beans  
[http://www.springframework.org/schema/beans/spring-beans.xsd](http://www.springframework.org/schema/beans/spring-beans.xsd)  
[http://www.springframework.org/schema/context](http://www.springframework.org/schema/context)  
[http://www.springframework.org/schema/context/spring-context-3.0.xsd](http://www.springframework.org/schema/context/spring-context-3.0.xsd)  
[http://www.springframework.org/schema/mvc](http://www.springframework.org/schema/mvc)  
[http://www.springframework.org/schema/mvc/spring-mvc-3.0.xsd](http://www.springframework.org/schema/mvc/spring-mvc-3.0.xsd)">  
<context:component-scan  
base-package="com.testyantra.emp"></context:component-scan>  
<bean  
class="org.springframework.web.servlet.view.InternalResourceViewResolver">  
<property name="prefix" value="/WEB-INF/views/"></property>  
<property name="suffix" value=".jsp"></property>  
</bean>
    
<servlet>  
<servlet-name>dispatcher</servlet-name>  
<servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>  
<init-param>  
<param-name>contextConfigLocation</param-name>  
<param-value>/WEB-INF/applicationRoot.xml</param-value>  
</init-param>
 
## Controller:
                         
## View:


