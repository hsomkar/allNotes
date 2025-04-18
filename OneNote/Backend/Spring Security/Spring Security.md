- **Spring Security** is one of the modules of spring - Standard for securing the Spring based application - We can easily provide login and logout module - It also have default login page - We can make password encryptions - It has default encryption library, which is 'Bcrypt' - Easily provide authentication and authorization like admin privileges user privileges - "**Authentication**" is the assurance that the user is actually the user he is claiming to be, and it is done through Username and Password. - "**Authorization**" is the assurance that the user is allowed to access only those resources that he is authorized to use. - Spring security internally makes use of 'Servlet Filetrs', which intecepts all the requests and validates them - Spring Security default behavior
    
    - Adds mandatory authentication for URLs
    - Adds login form
    - Handles login error
    - Creates a user and sets a default password
-   
    
- Dependency required: 'spring-boot-starter-security'

## @Concepts
- [[Adding spring security]]
- [[Bcrypt]]
- [[Change username and password]]
- [[Custom login and logout page]]
- [[Spring Boot Security Authentication with JPA, Hibernate and MySQL]]

#backend 