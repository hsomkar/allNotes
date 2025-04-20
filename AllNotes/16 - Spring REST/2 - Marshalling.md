- **JAXB** stands for Java for XML Binding, Use annotation pattern to convert java object to xml or vice-versa. - Here the two terms mostly used are Marshalling and Unmarshalling. - ![jaxb](Exported%20image%2020250408212939-0.png)
- **Marshalling:** By use of java object create xml file or convert java object to xml. - Dependencies needed:
    
    - jackson-core
    - jackson-databind
    - jackson-dataformat-xml - Steps to convert java object into XML document.
    
    - Create a bean class
    - Create the JAXBContext object
    - Create the Marshaller objects
    - Create the content tree by using set methods
    - Call the marshal method
      
    
- Example for Marshalling from object to xml:
    
    - Bean class:
    - Main method:
    - Output:
- Example for Marshalling from object to json:
    
    - Main method:
    - Output:
    -   
        
- List of JAXB Annotations:
         

```
@Data

@XmlRootElement
(name = 
"employee-info"
)

@JsonRootName
(
"employeeinfo"
)

@XmlAccessorType
(XmlAccessType.
FIELD
)

@JsonPropertyOrder
({
"empId"
 , 
"name"
})

public class 
EmployeeInfo 
implements
 Serializable {

 

@JsonProperty
(
"empId"
)

@XmlElement
(name = 
"emp-id"
)

//    @XmlAttribute

private int 
id
;

 

@XmlElement

private
 String 
name
;

 

@XmlElement
(name = 
"employee-dob"
)

private
 Date 
dob
;

 

@XmlElement

private long 
phone
;

 

@XmlElement

private
 String 
role
;

//    @XmlElement

@XmlTransient 
//ignore

@JsonIgnore

private
 String 
pwd
;

}

public class
 EmployeeMarshallingTest {

 

public static void
 main(String[] 
args
) {

EmployeeInfo 
info
 = 
new
 EmployeeInfo();

info
.setId(100);

info
.setName(
"abc"
);

info
.setDob(
new
 Date());

info
.setPhone(9009009009l);

info
.setRole(
"Dev"
);

info
.setPwd(
"abc"
);

try
 {

JAXBContext 
context
 = 
JAXBContext
.
newInstance
(EmployeeInfo.
class
);

Marshaller 
marshaller
 = 
context
.createMarshaller();

// output pretty printed

marshaller
.setProperty(Marshaller.
JAXB_FORMATTED_OUTPUT
, 
true
);

// to show out put in console

marshaller
.marshal(
info
, System.
out
);

marshaller
.marshal(
info
, 
new
 File(
"employee.xml"
));

} 
catch
 (Exception 
e
) {

e
.printStackTrace();

}

}

}










public class
 EmployeeJSONMarshalling {

 

public static void
 main(String[] 
args
) {

EmployeeInfo 
info
 = 
new
 EmployeeInfo();

info
.setId(100);

info
.setName(
"abc"
);

info
.setDob(
new
 Date());

info
.setPhone(9009009009l);

info
.setRole(
"Dev"
);

info
.setPwd(
"abc"
);

try
 {

ObjectMapper 
mapper
 =  
new
 ObjectMapper();

mapper
.writeValue(
new
 File(
"emp.json"
), 
info
);

} 
catch
 (Exception 
e
) {

e
.printStackTrace();

}

}

}



```
 @XmlRootElement(name = "employee-info")  
@JsonRootName("employeeinfo")  
@XmlAccessorType(XmlAccessType.FIELD)  
@JsonPropertyOrder({"empId" , "name"})  
public class EmployeeInfo implements Serializable {  
   
@JsonProperty("empId")  
@XmlElement(name = "emp-id")  
// @XmlAttribute  
private int id;  
   
@XmlElement  
private String name;  
   
@XmlElement(name = "employee-dob")  
private Date dob;  
   
@XmlElement  
private long phone;  
   
@XmlElement  
private String role;  
// @XmlElement  
@XmlTransient //ignore  
@JsonIgnore  
private String pwd;  
}
 
public class EmployeeMarshallingTest {  
   
public static void main(String[] args) {  
EmployeeInfo info = new EmployeeInfo();  
info.setId(100);  
info.setName("abc");  
info.setDob(new Date());  
info.setPhone(9009009009l);  
info.setRole("Dev");  
info.setPwd("abc");  
try {  
JAXBContext context = JAXBContext.newInstance(EmployeeInfo.class);  
Marshaller marshaller = context.createMarshaller();  
// output pretty printed  
marshaller.setProperty(Marshaller.JAXB_FORMATTED_OUTPUT, true);  
// to show out put in console  
marshaller.marshal(info, System.out);  
marshaller.marshal(info, new File("employee.xml"));  
} catch (Exception e) {  
e.printStackTrace();  
}  
}  
}
 
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
<employee-info>  
<emp-id>100</emp-id>  
<name>abc</name>  
<employee-dob>2021-06-09T23:00:46.709+05:30</employee-dob>  
<phone>9009009009</phone>  
<role>Dev</role>  
</employee-info>
   

public class EmployeeJSONMarshalling {  
   
public static void main(String[] args) {  
EmployeeInfo info = new EmployeeInfo();  
info.setId(100);  
info.setName("abc");  
info.setDob(new Date());  
info.setPhone(9009009009l);  
info.setRole("Dev");  
info.setPwd("abc");  
try {  
ObjectMapper mapper = new ObjectMapper();  
mapper.writeValue(new File("emp.json"), info);  
} catch (Exception e) {  
e.printStackTrace();  
}  
}  
}
 
{"empId":100,"name":"abc","dob":1623260371825,"phone":9009009009,"role":"Dev"}
   

|
|
==ANNOTATION== ==SCOPE== ==DESCRIPTION==
|[@XmlRootElement](https://howtodoinjava.com/jaxb/jaxb-annotations/#XmlRootElement)|\|<br>\|<br>==Class, Enum==|\|<br>\|<br>==Defines the XML root element. Root Java classes need to be registered with the JAXB context when it is created.==|
|[@XmlAccessorType](https://howtodoinjava.com/jaxb/jaxb-annotations/#XmlAccessorType)|Package, Class|\|<br>\|<br>==Defines the fields and properties of your Java classes that the JAXB engine uses for binding. It has four values: PUBLIC_MEMBER, FIELD, PROPERTY and NONE.==|
|[@XmlAccessorOrder](https://howtodoinjava.com/jaxb/jaxb-annotations/#XmlAccessorOrder)|Package, Class|\|<br>\|<br>==Defines the sequential order of the children.==|
|[@XmlType](https://howtodoinjava.com/jaxb/jaxb-annotations/#XmlType)|Class, Enum|\|<br>\|<br>==Maps a Java class to a schema type. It defines the type name and order of its children.==|
|[@XmlElement](https://howtodoinjava.com/jaxb/jaxb-annotations/#XmlElement)|Field|\|<br>\|<br>==Maps a field or property to an XML element==|
|[@XmlAttribute](https://howtodoinjava.com/jaxb/jaxb-annotations/#XmlAttribute)|Field|\|<br>\|<br>==Maps a field or property to an XML attribute==|
|[@XmlTransient](https://howtodoinjava.com/jaxb/jaxb-annotations/#XmlTransient)/@JsonIgnore|Field|\|<br>\|<br>==Prevents mapping a field or property to the XML Schema==|
|[@XmlValue](https://howtodoinjava.com/jaxb/jaxb-annotations/#XmlValue)|Field|\|<br>\|<br>==Maps a field or property to the text value on an XML tag.==|
|[@XmlList](https://howtodoinjava.com/jaxb/jaxb-annotations/#XmlList)|Field, Parameter|\|<br>\|<br>==Maps a collection to a list of values separated by space.==|
|[@XmlElementWrapper](https://howtodoinjava.com/jaxb/jaxb-annotations/#XmlElementWrapper)|Field|\|<br>\|<br>==Maps a Java collection to an XML wrapped collection==|
