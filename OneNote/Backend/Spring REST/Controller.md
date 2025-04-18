- Controller class should be annotated with **@RestController** annotation - To produce/consume JSON type of data add this in param of controller class:
    
    - produces/consumes={MediaType.APPLICATION_JSON_VALUE}
      
    
- To produce/consume XML type of data:
    
    - produces/consumes={MediaType.APPLICATION_XML_VALUE}
      
    
- To consume JSON type of data add this cookie in the browser:
    
    - Name=Accept
    - Value=application/JSON
      
    
- To consume xml type of data:
    
    - Name=Accept
    - Value=application/xml
      
    
- As the output we need to display status code, message and data - For that we need to create one bean class - Standard Status codes are:
    
    - 100 – 199 -> Informational
    - 200 – 299 -> Success
    - 300 – 399 -> Redirectional
    - 400 – 499 -> Client errors (observe URL)
    - 500 – 599 -> Server errors
      
    
- ```
    @JsonInclude(Include.NON_NULL) 
    
    
    
    
    
    
    
    
    
    
    
    
    ```
    
    --> To Ignore Null Fields on the Class put this - When we are using @RestController if the data is present in request body we should use @RequestBody - @ControllerAdvice is also replaced by @RestControllerAdvice
#Backend

