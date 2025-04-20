- Need: If any error comes in server side because of user then it may lead to server crash. - Using **BindingResult**
    
    - Add BindingResult result in params of handler method.
    - It is the interface which extends Errors.
    - It has one method called ‘hasErrors’ which returns Boolean result that page have errors or not.
    - if(result. hasErrors){return “samePage”;}
      
    
- Using **@ExceptionHandler**
    
    ```
    @ExceptionHandler({NullPointerException.class,NumberFormatException.class}) (OR)
    @ExceptionHandler(value=NullPointerException.class)
    
    
    
    
    @
    ExceptionHandler(value=NullPointerException.
    class
    )
    
    public
     String otherMethod(){
    
    return
     “viewName”;
    
    }
    
    
    ```
    
    - @ExceptionHandler(value=NullPointerException.class)
    - Exception handling is done only for classes which we give as param, for Generalized exception handling replace them with Exception.class
      
    
- We can send status code to client side by using **@ResponseStatus** (HttpStatus. Internal_Server_error) --> for status code 500 - Centralized Exception Handling
    
    - We can handle exception for all available controllers by using @ControllerAdvice
    - It is done by making one separate class with this annotation and writing all the exception handling methods with @ExcptionHandler.
   

@ExceptionHandler(value=NullPointerException.class)  
public String otherMethod(){  
return “viewName”;  
}
