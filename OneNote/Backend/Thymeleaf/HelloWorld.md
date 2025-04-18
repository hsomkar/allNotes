- Create a Spring Starter Project by adding 'spring-boot-starter-thymeleaf' dependency
    
    - pom.xml: - Create a Controller class
    
    - DemoController.java: - Create a Thymeleaf HTML template
    
    - page.html: - Run the Spring boot project
    
    - Output:

```
<
dependency
>

<
groupId
>
org.springframework.boot
</
groupId
>

<
artifactId
>
spring-boot-starter-thymeleaf
</
artifactId
>

</
dependency
>

@Controller

public
 
class
 DemoController {

@GetMapping

public
 String name(Model 
model
) {

model
.addAttribute(
"msg"
,
"HelloWorld"
);

return
 
"page"
;

}

}

<!
DOCTYPE
 
html>

<
html
 
xmlns:th
=
"http://www.thymeleaf.org"
>

<
head
>

<
meta
 
charset
=
"ISO-8859-1"
>

<
title
>
Insert title here
</
title
>

</
head
>

<
body
>

<
h1
 
th:text
=
"'Thymeleaf '+${msg}+' app'"
></
h1
>

</
body
>

</
html
>

```

dependency>  
<groupId>org.springframework.boot</groupId>  
<artifactId>spring-boot-starter-thymeleaf</artifactId>  
</dependency>
 
@Controller  
public class DemoController {  
@GetMapping  
public String name(Model model) {  
model.addAttribute("msg","HelloWorld");  
return "page";  
}  
}
 
<!DOCTYPE html>  
<html xmlns:th="http://www.thymeleaf.org">  
<head>  
<meta charset="ISO-8859-1">  
<title>Insert title here</title>  
</head>  
<body>  
<h1 th:text="'Thymeleaf '+${msg}+' app'"></h1>  
</body>  
</html>
 
**Thymeleaf HelloWorld app**

