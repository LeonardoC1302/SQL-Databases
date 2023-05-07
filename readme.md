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

# CRUD Operations (Create, Read, Update, Delete)
### Insert
- INSERT INTO \<name> (\<columns>) VALUES (\<values>);
### Select
- SELECT * from \<name>;
- Select \<column> from \<name>;
- SELECT * FROM \<name> ORDER BY \<column> ASC/DESC;
- SELECT * FROM \<name> LIMIT \<quantity>;
- SELECT * FROM \<name> WHERE \<condition>;
- SELECT * FROM \<name> WHERE \<column> BETWEEN \<values>;
### Update
- UPDATE \<table> SET \<column> = \<value> WHERE \<condition>;
### Modify or delete
- ALTER TABLE \<table> ADD \<column> \<dataType> \<moreInfo>;
- ALTER TABLE \<table> CHANGE \<column> \<newName> \<newDataSize> \<newInfo>;
- ALTER TABLE \<table> DROP COLUMN \<column>;
- DELETE from \<table> WHERE \<condition>;
- DROP TABLE \<name>; 
### Aggregate functions (with real examples)
- SELECT COUNT(id), date FROM reservations GROUP BY date ORDER BY COUNT(id) DEC;
- SELECT SUM(price) AS totalServices FROM services;
- SELECT MIN(price) AS minPrice FROM services;
- SELECT MAX(price) AS minPrice FROM services;
### Search in SQL (with real examples)
- SELECT * FROM services WHERE serviceName LIKE 'Hair%'
    - %word : The word is at the end of the name
    - word% : The word is at the beginning of the name
    - %word% : The word is somewhere in the name
### CONCAT (with real examples)
- SELECT CONCAT(name, ' ', lastName) AS fullName FROM reservations;
- SELECT * FROM reservations WHERE CONCAT(name, ' ', lastName) LIKE '%John Doe';
- SELECT hour, date, CONCAT(name, ' ', lastName) AS 'Full Name' FROM reservations WHERE CONCAT(name, ' ', lastName) LIKE '%John Doe';
### Multiple Conditions
- SELECT * FROM reservations WHERE id IN(1,3);
- SELECT * FROM reservations WHERE date='2021-06-28' AND id=1