- **Unmarshalling:** Create java object again using xml file. - Steps are similar to marshalling - Example for Unmarshalling from xml to object:
    
      
    - Bean class:
    - Main method:
    - Output:
      
    
- Example for Unmarshalling from json to object:
    
      
    - Main method:
    - Output:
      
    
- In Spring REST Marshalling and Unmarshalling is done internally.
    
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
 EmployeeUnMarshalTest {

public static void
 main(String[] 
args
) {

try
 {

JAXBContext 
context
 = JAXBContext.
newInstance
(EmployeeInfo.
class
);

Unmarshaller 
unmarshaller
 = 
context
.createUnmarshaller();

EmployeeInfo 
employeeInfo
 = (EmployeeInfo) 
unmarshaller
.unmarshal(
new
 File(
"employee.xml"
));

System.
out
.println(
employeeInfo
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



public class
 EmployeeJsonUnMarshall {

public static void
 main(String[] 
args
) 
throws 
JsonParseException, JsonMappingException, IOException {

ObjectMapper 
mapper
 = 
new
 ObjectMapper();

EmployeeInfo 
info
 = 
mapper
.readValue(
new
 File(
"emp.json"
), EmployeeInfo.
class
);

System.
out
.println(
info
);

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
 
public class EmployeeUnMarshalTest {  
public static void main(String[] args) {  
try {  
JAXBContext context = JAXBContext.newInstance(EmployeeInfo.class);  
Unmarshaller unmarshaller = context.createUnmarshaller();  
EmployeeInfo employeeInfo = (EmployeeInfo) unmarshaller.unmarshal(new File("employee.xml"));  
System.out.println(employeeInfo);  
} catch (Exception e) {  
e.printStackTrace();  
}  
}  
}
 
EmployeeInfo(id=100, name=abc, dob=Wed Jun 09 23:00:46 IST 2021, phone=9009009009, role=Dev, pwd=null)
   

public class EmployeeJsonUnMarshall {  
public static void main(String[] args) throws JsonParseException, JsonMappingException, IOException {  
ObjectMapper mapper = new ObjectMapper();  
EmployeeInfo info = mapper.readValue(new File("emp.json"), EmployeeInfo.class);  
System.out.println(info);  
}  
}
 
EmployeeInfo(id=100, name=abc, dob=Wed Jun 09 23:09:31 IST 2021, phone=9009009009, role=Dev, pwd=null)
