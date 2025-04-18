- Spring Boot will look all static files in /resources/static so include CSS and JS files in this folder. - and All views should be in /resources/templates - To include ==CSS== inside head add: - To include ==JS== use:
    
      
    - Now, we call our method from our template: - We can include ==Bootstrap== in 3 ways. They are:
    
    - Add Bootstrap using WebJars:
        
        - add Boostrap webjar dependency in the POM.xml
        - add Bootstrap CSS and JS files in our Thymeleaf template
            
```
            - <link th:rel="stylesheet" th:href="@{/webjars/bootstrap/4.0.0-2/css/bootstrap.min.css} "/>
            - ...
            - <script th:src="@{/webjars/jquery/3.0.0/jquery.min.js}"></script>￼<script th:src="@{/webjars/popper.js/1.12.9-1/umd/popper.min.js}"></script>￼<script th:src="@{/webjars/bootstrap/4.0.0-2/js/bootstrap.min.js}"></script>
```
              
            
    - Adding Bootstrap library using static asset files
        
        - <link th:rel="stylesheet" th:href="@{/assets/bootstrap/css/bootstrap.min.css} "/>
        - ...
        - <script th:src="@{/assets/jquery/jquery.min.js}"></script>￼<script th:src="@{/assets/popper.js/popper.min.js}"></script>￼<script th:src="@{/assets/bootstrap/js/bootstrap.min.js}"></script>
          
        
    - Add Bootstrap using CDN
        
        - <--Normal method-->
   

```
<==link== ==th:href====="@{/styles/cssandjs/main.css}"== ==rel====="stylesheet"== />
 
<script type="text/javascript" th:src="@{/js/cssandjs/actions.js}"></script>  
(OR)  
<script th:inline="javascript">  
var nameJs = /*[[${name}]]*/;  
</==script==>
 
<button type="button" th:onclick="showAlert()">Show Alert</button>
   

<dependency>￼ <groupId>org.webjars</groupId>￼ <artifactId>bootstrap</artifactId>￼ <version>4.0.0-2</version>￼</dependency>
```
