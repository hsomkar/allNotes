## Spring Boot annotations:
 
- **@Repository**
    
    - It is a Data Access Object (DAO) that accesses the database directly. It indicates that the annotated class is a repository.
      
    
- **@Service**
    
    - It is used at the class level. It shows that the annotated class is a service class, such as business basic logic, and call external APIs.
      
    
- **@Bean**
    
    - The @Bean annotations are used at the method level and indicate that a method produces a bean that is to be managed by Spring container. It is an alternative to the XML<bean> tag.
      
    
- **@SpringBootApplication**
    
    - We use this annotation to mark the main class of a Spring Boot application.
    - @SpringBootApplication encapsulates @Configuration, @EnableAutoConfiguration, and @ComponentScan annotations with their default attributes.
      
    
- **@EnableAutoConfiguration**
    
    - @EnableAutoConfiguration, as its name says, enables auto-configuration. It means that Spring Boot looks for auto-configuration beans on its classpath and automatically applies them.
      
    
- **@ComponentScan**
    
    - This annotation is used with @Configuration annotation to allow Spring to know the packages to scan for annotated components. @ComponentScan is also used to specify base packages using basePackageClasses or basePackage attributes to scan.
      
    
- **@Configuration**
    
    - It is used as a source of bean definitions. It is a class-level annotation.
