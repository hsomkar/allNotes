- **IoC container** is the one who manages the objects in our application. - ‘Manages the objects’ means IoC Container is responsible for basically three things -
    
    - Instantiate the object
    - Configure the object
    - Inject the dependencies
      
    
- What objects it needs to instantiate, how to configure them all this information will be present in an xml file and we call it as Configuration Metadata. - The IoC Container reads this Configuration Metadata and performs the operations. - ![IOC Container BeanFactory ApplicationContext ](Exported%20image%2020250408212808-0.octet-stream) - The BeanFactory interface provides configuration mechanism which is capable of managing any type of object and also provides some basic functionality. - ApplicationContext is a Sub-Interface of BeanFactory and it adds more enterprise specific functionality. - In other words, BeanFactory provides configurations and basic functionalities and ApplicationContext adds more enterprise-specific functionalities. - We can say that “ApplicationContext is a complete superset of BeanFactory”.
