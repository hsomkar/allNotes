SQL constraints are used to specify rules for the data in a table
 
Constraints are divided into two level-
 
Column Level Constraints – limits only Column data
 
Table Level Constraints – limits whole table data.
 
1. NOT NULL :

Constraints restricts a column from having a NULL value . Once you applied NOT NULL Constraints to a column you can not pass NULL value to that column.
 
It can not be applicable on table level.
 
2. UNIQUE:
 
Unique constraints ensure that a field or column will only have unique values . will not have duplicate data.  
Can be applied at column level or table level.
 
3. PRIMARY KEY:
 
We can have ONLY ONE primary in a table.  
Primary Key cannot accept DUPLICATE value.  
Primary Key is always a combination of UNIQUE & NOT NULL.  
Primary Key is not MANDATORY but it is HIGHLY RECCOMENDED.
 
4.FOREIGN KEY :
 
We can have ANY NUMBER of FOREIGN KEY.  
It can accept DUPLICATE VALUES and can be NULL.  
It is present in CHILD table but actually belongs to the PARENT table.  
An attribute defined as Primary Key in its table can only become Foreign Key in other table
 
5. CHECK :
 
This constraints is used to restrict the value of a column between a range.  
Its like a condition checking before saving data into a column.  
It can be applied Table level as well as Column level.
 
6.Default:
 
The DEFAULT constraint is used to provide a default value for a column.  
The default value will be added to all new records IF no other value is specified
