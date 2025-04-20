### Annotations:
 
- **@Entity:** To specify the entity bean. It is mapped to database - **@Id:** To specify primary key and id - **@GeneratedValue:** To auto generate id
    
    - strategy=DEFAULT
      
    
- **@Column:** We can provide column level constraints
    
    - Attributes:
    - name="__" --> explicitly provide column name
    - updateable=false --> to avoid update
        
        - True(default)
    - nullable=false --> not null
        
        - True(default)
    - ColumnDefinition="TEXT" --> to change data explicitly
    - unique=true --> to make unique
        
        - false(default)
          
        
- **@Table:** We can provide table level constraints
    
    - Attributes:
    - name="__" --> explicitly provide table name
    - uniqueConstraint --> to make unique
        
        - name="__" --> constraint name
        - columnNames={"__","__"} --> array which accepts column names to make it unique - **Mapping** annotations:
    
    - @OneToOne
    - @OneToMany
    - @ManyToOne
    - @ManyToMany
      
    
         
_Note: 

_Choose all from javax.persistence_ _We should either specify constraint name in table level or column level_
