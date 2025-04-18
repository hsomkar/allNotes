## Interceptors

![Exported image](Exported%20image%2020250408212924-0.octet-stream)

- Spring Interceptor are used to intercept client requests and process them. Sometimes we want to intercept the HTTP Request and do some processing before handing it over to the controller handler methods. That’s where Spring MVC Interceptor come handy. - We can achieve it by either implementing ‘HandlerInterceptor’ interface or by overriding abstract class ‘HandlerInterceptorAdapter’ that provides the base implementation of HandlerInterceptor interface. - HandlerInterceptor interface contains three main methods:
    
    - prehandle() – called before the actual handler is executed, but the view is not generated yet
    - postHandle() – called after the handler is executed
    - afterCompletion() – called after the complete request has finished and view was generated
        
        - If these method s return true then only request is further passed.
          
        
- Configuration:
    
    - In xml file add
      
    

## Filters
 - Used to filter out some requests. - To use it use @WebFilter(urlpattern=”/*”) on the filter class - and we should implement Filter interface. - It has three methods:
    
    - Init
    - doFilter
    - destroy
      

```
xmlns:mvc=”…/schema/mvc”  
and  
<mvc:interceptors>  
<mvc:interceptor>  
<mvc:mapping path=”/path_Needed”/>  
<bean class="class_path"/>  
</mvc:interceptor>  
</mvc:interceptors>












@
WebFilter(
"/test/*"
)

public
 
class
 RequestFilter 
implements
 Filter {

 

@Override

public
 
void
 init(FilterConfig 
filterConfig
) 
throws
 ServletException {

}

 

@Override

public
 
void
 doFilter(ServletRequest 
request
, ServletResponse 
response
, FilterChain 
chain
)

throws
 IOException, ServletException {

}

 

@Override

public
 
void
 destroy() {

}

}
```
 
## Filters
      

@WebFilter("/test/*")  
public class RequestFilter implements Filter {  
   
@Override  
public void init(FilterConfig filterConfig) throws ServletException {  
}  
   
@Override  
public void doFilter(ServletRequest request, ServletResponse response, FilterChain chain)  
throws IOException, ServletException {  
}  
   
@Override  
public void destroy() {  
}  
}
