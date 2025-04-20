- As we know spring boot avoids XML configuration all the configuration are present in this file - Sample Properties file:

|
|
==Properties== ==Description==
|spring.datasource.url=jdbc:mysql://localhost/db_name?createDatabaseIfNotExist=true&autoReconnect=true&useSSL=false|Database url|
|spring.datasource.username=root|Database username|
|spring.datasource.password=root|Database password|
|spring.jpa.hibernate.ddl-auto=update|To auto generate ddl commands|
|spring.jpa.show-sql=true|To show sql queries in console|
|spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect|To set dialect i.e., to generate specific SQL queries|
|spring.jpa.properties.hibernate.format_sql=true|To formate SQL queries displayed in console|
 - hbm2ddl auto all possible values and their uses
    
    - **validate**: validate the schema, makes no changes to the database.
    - **update**: update the schema.
    - **create**: creates the schema, destroying previous data.
    - **create-drop**: drop the schema when the SessionFactory is closed explicitly, typically when the application is stopped.
    - **none**: does nothing with the schema, makes no changes to the database
