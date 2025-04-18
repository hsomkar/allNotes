## Conditionals
  - **Elvis Operator:**
    
    - The Elvis operator ?: lets us render text within an HTML element depending on the current state of a variable.
    - <==td== ==th:text====="${teacher.additionalSkills} ?: 'UNKNOWN'"== />
    - In the upper example, if the variable is defined then only it is rendered otherwise "UNKNOWN" will be rendered.
    - <==td== ==th:text====="${teacher.active} ? 'ACTIVE' : 'RETIRED'"== />
    - In the upper example, if it is true "ACTIVE" will be rendered else "RETIRED" will be rendered.
      
    
- **If – Unless:**
    
    - The th:if and th:unless attributes allow us to render an HTML element depending on a provided condition:
    - If the content of the variable is equals to F, then only “Female” is rendered. Otherwise, “Male” is rendered.
    - Such a setup is comparable to an if-else clause.
      
    
- **Switch – Case:**
    
    - If there are more than two possible results of an expression, we can use the th:switch and th:case attributes for the conditional rendering of the HTML elements:
    - Depending on the size of theteacher.courseslist we either display a default text, the single course or all courses available. The asterisk (*)is used for the default option.
      
    
    
```
<td>  
<span th:if="${teacher.gender == 'F'}">Female</span>  
<span th:unless="${teacher.gender == 'F'}">Male</span>  
</td>
   

<td th:switch="${#lists.size(teacher.courses)}">  
<span th:case="'0'">NO COURSES YET!</span>  
<span th:case="'1'" th:text="${teacher.courses[0]}"></span>  
<div th:case="*">  
<div th:each="course:${teacher.courses}" th:text="${course}"/>  
</div>  
</td>
```
 
## Iteration
  - In Thymeleaf, iteration is achieved by using the th:each attribute. - It can iterate objects and arrays.
   
```
<tr th:each="student: ${students}">  
<td th:text="${student.id}" />  
<td th:text="${student.name}" />  
</tr>
```

