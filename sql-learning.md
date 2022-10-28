

STRUCTURED QUERY LANGUAGE 
========
### Introdcction:

SQL is a standard language for accessing and manipulating relational databases.

-----
#### What is SQL?  

- SQL stands for Structured Query Language 
- SQL let you access and manipulate databases
- SQL is an ANSI (American National Standards Institute ) standard
---
#### What can SQL do ?
- excecuate queries against a database
- retrive data from a database
- insert records ina database
- update records in database
- delete records in database
- create new database
- create new tables in databse
- create stored procedures in a database
- creat views in database
- set permissions on tables, procedures and views
-----
#### SQL is Standard -BUT...

Although SQL is an ANSI standard, there are many different versions of the SQL language. However, to be compliant with the ANSI standard they all support at least the major commands (SELECT, UPDATE, DELETE, INSERT, WHERE ) in a similar manner. 

---
#### Using SQL in your Website

Tobuild a website that shows some data from a database, need the following

- An RDBMS database program (MS Access, SQL server, MySQL)
- A server-side scripting language(PHP , ASP)
- SQL
- HTML/CSS
----
### RDBMS
RDBMS stands for relational database management system .
RDBMS is the basis for SQL and all modern database systems like MS SQL server, IBM DB2, Oracle, MySQL and Microsoft Access.
The data in RDBMS is stored in database objects called **tables**.
A table is a collection of related data and it consists of **columns** and **rows**.

#### Database Tables:
A database most often contains one or more tables. Each table is identified by a name (e.g. "Customers" or "orders"). Tables contain records(rows) with data. Example table called "Persons" is below:

|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |
|2 |Svendson |Tove | Borgvn 23|Sandnes|
|3 |Pettersen|Kari|Storgt 20|Stavanger|

The table above contains three records, one for each person and five columns .

----
#### SQL Statements 
Most of the actions you need to perform on a data base are done with SQL Statements.
For example the following SQL Statement will select all the records in a the "Persons" table.
*SELECT * FROM Persons*
Note: (SQL is not Case Senstive)

#### Semicolon ( ; ) after SQL Statement 
Some database require a semicolon at the end of each SQL Statement .
Semicolon is a standard way to separate each SQL statement in a database system that allows more than one SQL statement to be executed in the same call to the server.

----
### SQL DML and DDL
SQL can be divided into two parts:
- DML = The Data Manipulation Language 
- DDL = The Data Definition Language 

1. The query and update commands from the DML part of SQL:

 - **SELECT** - extract data from databases 
 - **UPDATE** - updates data in a database
 - **DELETE** - deletes data from  a database 
 - **INSERT INTO** - inserts data into database

2. The DDL part of SQL permits database tables to be created or deleted. It also define indexes(keys), specify links between tables and impose constraints between tables. The most important DDL statements in SQL are:
 - CREATE DATABASE - crates a new database 
 - ALTER DATABASE - modifies a database
 - CREAT TABLE -  creat a new table
 - ALTER TABLE - modifies a table
 - DROP TABLE - delete a table
 - CREATE INDEX - creat an index (search key)
 - DROP INDEX - delete an index 


####  SQL SELECT Statement 

The SQL SELECT Statement is used to select data from a database.
The result is stored in a result table, called the result-set.
##### SQL  SELECT Syntax
SELECT column_name(s)
FROM table_name

and 

SELECT * FROM table_name (select all from table_name)

EXAMPLE: the "Persons" table

|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |
|2 |Svendson |Tove | Borgvn 23|Sandnes|
|3 |Pettersen|Kari|Storgt 20|Stavanger|


##### ⇒  Select statment will be as:
`SELECT LastName, FirstName FROM Persons` </br>
result-set will be as :

| LastName  |FirstName   |
|---|---|
|Hansen  |Ola |
|Svendson |Tove |
|Pettersen|Kari|

##### ⇒  Select * Example:

 `SELECT  *  From Persons`

 Result will be as :

 |P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |
|2 |Svendson |Tove | Borgvn 23|Sandnes|
|3 |Pettersen|Kari|Storgt 20|Stavanger|

----
#### SQL SELECT DISTINCT Example
using the "Persons" table 

SELECT DISTINCT City FROM Persons

Result-set  will be like:


|City|
|---|
| Sandnes  |
|Stavanger|

----
#### SQL WHERE Clause
**SYNTAX** :
```				
	SELECT column_name(s)
	FROM table_name 
	WHERE column_name operator value			
     
 ```
using the "Person" table
```
SELECT * FROM Persons
WHERE City  =  'Sadnes'
```
result-set :

|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |
|2 |Svendson |Tove | Borgvn 23|Sandnes|

==> Quotes Around TEXT Fields 
SQL use single quotes around text values , most database systems will also accept double quotes .
Although Numeric values should not be inclosed in quotes.

**Operators Allowed in the WHERE Clause**

|Operators | Discription |
|---|---|
| = | Equal |
|!=|Not Equal
| <>| Not Equal|
| >|Greater than  |
| <|Less than  |
|>= |Greater than or Equal |
|<=|Less than or Equal|
|BTWEEN|Between an inclusive range|
|LIKE|Search for a pattern|
|IN|If you know the exact value you want to return for at least one of the columns


### SQL Joins

![sql joins](sql-assets/SQL_Joins.png)

