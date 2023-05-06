# SQL Commands and CRUD operations
- Use 'mysql -u root -p' log into your mysql service 
    - Make sure to have mysql added to your environment variables or the command may not work
- SHOW DATABASES;
    - Used to show all created databases
- CREATE DATABASES \<name>;
    - Used to create a database with a valid name
- USE \<name>;
    - Used to start using a database for the following commands
- SHOW TABLES;
    - Used to show all tables of the current database (selected)
- CREATE TABLE \<name> ( 
    1. id INT(11) NOT NULL AUTO_INCREMENT,
    2. name VARCHAR(60) NOT NULL,
    3. price DECIMAL(#, #) NOT NULL,
    4. PRIMARY KEY (id)
    5.   );
    - Used to create a table on the current database
- DESCRIBE \<name> 
    - Show details of a table