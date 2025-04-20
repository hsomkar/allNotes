There are five SQL Statements(Subsets):
 
- Data Definition Language.(DDL)
- Data Manipulation Language.(DML)
- Data Control Language.(DCL)
- Transactional Control Language.(TCL)
- Data Query Language.(DQL)
 
- Data Definition Language(DDL): 
Data Definition Language consist of statement used to define the database schema.
 
DDL includes statements Like – Create , Drop, Alter, Truncate, Rename.
 
**CREATE** – is used to create the database or its objects (like table, index, function, views, store procedure and triggers).  
SYNTAX: create <table|database> <object_name>
 
**DROP** – is used to delete objects from the database.  
SYNTAX: drop <table|database> <object_name>
 
**ALTER** - is used to alter the structure of the database.  
SYNTAX:
 
**TRUNCATE**–is used to remove all records from a table, including all spaces allocated for the records are removed  
SYNTAX: truncate table <table_name>
 
**RENAME** –is used to rename an object existing in the database.  
SYNTAX: rename table from <old_table_name> to <new_table_name> 
 - Data Manipulation Language(DML): 
The SQL Statement that deals with the manipulation of data present in database
 
DML includes statements like – Insert, Update, Delete
 
**INSERT** – is used to insert data into a table.  
SYNTAX: INSERT INTO table_name (field1, field2,…fieldN) VALUES ( value1, value2,…valueN);
 
**UPDATE** – is used to update existing data within a table.  
SYNTAX: UPDATE table_name SET field1=new_value1, field2=new_value2 [WHERE Clause];
 
**DELETE** – is used to delete records from a database table  
SYNTAX: DELETE FROM table_name [WHERE Clause];
 - Data Control Language(DCL): 
DCL Commands mainly deals with the rights , permissions and other controls of other database system.
 
DCL includes statements like - Grant and Invoke.
 
**GRANT**- gives user’s access privileges to database.  
SYNTAX:
 
**REVOKE**- withdraw user’s access privileges given by using the GRANT command  
SYNTAX:
 - Transactional Control Language(TCL): 
Transaction Control Language(TCL) commands are used to manage transactions in the database.
 
These are used to manage the changes made to the data in a table by DML statements.
 
The DDL changes cannot be undone as they are implicitly saved.
 
Various commands in TCL are:
                                     

**COMMIT** – commits a Transaction.  
**ROLLBACK** – rollbacks a transaction in case of any error occurs.  
**SAVEPOINT** – sets a savepoint within a transaction.
 _Note: 
In MySql autocommit is by default on. As a result, TCL commands are not runnable_  

- Data Query Language(DQL): 
The SQL Statements used to retrieve the data from database is known as Data Query Language (DQL).
 
Only one command to retrieve the data from database is:  
**Select**
 
With the help of select we can perform retrieval from the table in the three different ways:
 
Projection  
Selection  
Joins
