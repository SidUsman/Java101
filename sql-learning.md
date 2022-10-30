

STRUCTURED QUERY LANGUAGE 
========
### Introduction:

SQL is a standard language for accessing and manipulating relational databases.

-----
#### What is SQL?  

- SQL stands for Structured Query Language 
- SQL let you access and manipulate databases
- SQL is an ANSI (American National Standards Institute ) standard
---
#### What can SQL do ?
- execute queries against a database
- retrieve data from a database
- insert records ina database
- update records in database
- delete records in database
- create new database
- create new tables in database
- create stored procedures in a database
- create views in database
- set permissions on tables, procedures and views
-----
#### SQL is Standard -BUT...

Although SQL is an ANSI standard, there are many versions of the SQL language. However, to be compliant with the ANSI standard they all support at least the major commands (SELECT, UPDATE, DELETE, INSERT, WHERE ) in a similar manner. 

---
#### Using SQL in your Website

To build a website that shows some data from a database, need the following

- An RDBMS database program (MS Access, SQL server, MySQL)
- A server-side scripting language(PHP , ASP)
- SQL
- HTML/CSS
----
### RDBMS
RDBMS stands for relational database management system .
RDBMS is the basis for SQL and all modern database systems like MS SQL server, IBM DB2, Oracle, MySQL and Microsoft Access.
The data in RDBMS is stored in database objects called **tables**.
A table is a collection of related data, and it consists of **columns** and **rows**.

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
Most of the actions you need to perform on a database are done with SQL Statements.
For example the following SQL Statement will select all the records in the "Persons" table.
````
SELECT * FROM Persons
````
Note: (SQL is not Case Senstive)

#### Semicolon ( ; ) after SQL Statement 
Some databases require a semicolon at the end of each SQL Statement .
Semicolon is a standard way to separate each SQL statement in a database system that allows more than one SQL statement to be executed in the same call to the server.

----
### SQL DML and DDL
SQL can be divided into two parts:
- DML = The Data Manipulation Language 
- DDL = The Data Definition Language 

1. The query and update commands from the **DML** part of SQL:

 - **SELECT** - extract data from databases 
 - **UPDATE** - updates data in a database
 - **DELETE** - deletes data from  a database 
 - **INSERT INTO** - inserts data into database

2. The **DDL** part of SQL permits database tables to be created or deleted. It also defines indexes(keys), specify links between tables and impose constraints between tables. The most important DDL statements in SQL are:
 - **CREATE DATABASE** - crates a new database 
 - **ALTER DATABASE** - modifies a database
 - **CREATE TABLE** -  create a new table
 - **ALTER TABLE** - modifies a table
 - **DROP TABLE** - delete a table
 - **CREATE INDEX** - create an index (search key)
 - **DROP INDEX** - delete an index 


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


##### ⇒  Select statement will be as:
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
Although Numeric values should not be enclosed in quotes.

**Operators Allowed in the WHERE Clause**

|Operators | Description |
|---|---|
| = | Equal |
|!=|Not Equal
| <>| Not Equal|
| >|Greater than  |
| <|Less than  |
|>= |Greater than or Equal |
|<=|Less than or Equal|
|BETWEEN|Between an inclusive range|
|LIKE|Search for a pattern|
|IN|If you know the exact value you want to return for at least one of the columns

#### SQL AND & OR Operators 
The AND & OR operators are used to filter records based on more than one conditions.
The AND operator displays a record if both the first condition and the second condition is true.
The OR operator displays a record if either the first or the second condition is true.

using the "Persons" table

AND Example :
````
SELECT * FROM Persons
WHERE FirstName = 'Tove'
AND LastName = 'Svendson'
````
The result-set will be like:

|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
|2 |Svendson |Tove | Borgvn 23|Sandnes|

OR Example:
````
SELECT * FROM Persons 
WHERE FirstName = 'Tove'
OR FirstName = 'Ola'
````
result-set will look like this:

|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |
|2 |Svendson |Tove | Borgvn 23|Sandnes|


### The ORDER BY Keyword
The ORDER BY Keyword is used to sort the result-set by a specified column.
The ORDER BY keyword sort the records in ascending order by default. To sort in descending order ,DESC keyword is used.

**Syntax for ORDER BY:**

````
SELECT column_name(s)
From table_name
ORDER BY column_name(s) ASC|DESC
````

"Persons" table.

|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |
|2 |Svendson |Tove | Borgvn 23|Sandnes|
|3 |Pettersen|Kari|Storgt 20|Stavanger|
|4 |Nilsen |Tom | Vingvn 23|Stavanger|

````
SELECT * 
FROM Persons
ORDER BY LastName
````

|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |
|4 |Nilsen |Tom | Vingvn 23|Stavanger|
|3 |Pettersen|Kari|Storgt 20|Stavanger|
|2 |Svendson |Tove | Borgvn 23|Sandnes|

**ORDER BY DESC Example**
````
SELECT * 
FROM Persons
ORDER BY LastName DESC
````
|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
|2 |Svendson |Tove | Borgvn 23|Sandnes|
|3 |Pettersen|Kari|Storgt 20|Stavanger|
|4 |Nilsen |Tom | Vingvn 23|Stavanger|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |

----
###The INSERT INTO Statement

The INSERT INTO Statement is used to insert a new row in a table.

It is possible to write the INSERT INTO statement in two forms.

1. This form does not specify the column names where the data will be inserted, only their values:
````
INSERT INTO table_name
VALUES(value1, value2, value3,...)
````
2. The second form specifies both the column names and the values to be inserted:
````
INSERT INTO table_name(column1, column2, column3,...)
VALUES(value1, value2, value3,...)
````
**Example:**
Persons table

|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |
|2 |Svendson |Tove | Borgvn 23|Sandnes|
|3 |Pettersen|Kari|Storgt 20|Stavanger|
Syntax:
````
INSERT INTO Persons
VALUE (4,'Nilsen','johan','Bakken 2',Stavanger')
````
result-set :

|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |
|2 |Svendson |Tove | Borgvn 23|Sandnes|
|3 |Pettersen|Kari|Storgt 20|Stavanger|
|4 |Nilsen |Tom | Vingvn 23|Stavanger|


**Insert Data Only in Specified Columns**
````
INSERT INTO Persons (P_Id,LstName,FirstName)
VALUE(5,'Tjessem','Jakob')
````
Result-set:

|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |
|2 |Svendson |Tove | Borgvn 23|Sandnes|
|3 |Pettersen|Kari|Storgt 20|Stavanger|
|4 |Nilsen |Tom | Vingvn 23|Stavanger|
|5|TJessem|Jakob|   |   |

----
### SQL UPDATE Statement
The UPDATE Statement is used to update records in a table or to update existing records in a table.
**UPDATE Syntax**
````
UPDATE table_name
SET column1 = value, column2 = value,...
WHERE some_column = some_value
````
NOTE: WHERE clause specifies which record should be updated.

Example:
Update the person "Tjessem" in the "persons" table.
````
UPDATE Persons
SET Address = 'Nissestien 67',City = 'Sandnes'
WHERE LastName = 'Tjessem' AND FirstName = 'Jakob'
````


|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |
|2 |Svendson |Tove | Borgvn 23|Sandnes|
|3 |Pettersen|Kari|Storgt 20|Stavanger|
|4 |Nilsen |Tom | Vingvn 23|Stavanger|
|5|TJessem|Jakob|Nissestien 67 |Sandnes|

Example:
Updating whole columns of Address and City
````
UPDATE Persons
SET Address = 'Nissestien 67',City = 'Sandnes'
````
|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Nissestien 67 |Sandnes |
|2 |Svendson |Tove |Nissestien 67 |Sandnes|
|3 |Pettersen|Kari|Nissestien 67 |Sandnes|
|4 |Nilsen |Tom |Nissestien 67 |Sandnes|
|5|TJessem|Jakob|Nissestien 67 |Sandnes|

----
### SQL DELETE Statement 

The DELETE statement is used to delete records(rows) in a table.
**Syntax**
````
DELETE FROM table_name
WHERE some_column = some_value
"where clause specifies which record should be deleted"
````
|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |
|2 |Svendson |Tove | Borgvn 23|Sandnes|
|3 |Pettersen|Kari|Storgt 20|Stavanger|
|4 |Nilsen |Tom | Vingvn 23|Stavanger|
|5|Tjessem|Jakob|Nissestien 67 |Sandnes|

Example:
Delete the person "Tjessesm,Jakob" in the persons table
````
DELETE FROM Persons 
WHERE LastName = 'Tjessem' AND FirstName = 'Jakob'
````
Result_set:

|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |
|2 |Svendson |Tove | Borgvn 23|Sandnes|
|3 |Pettersen|Kari|Storgt 20|Stavanger|
|4 |Nilsen |Tom | Vingvn 23|Stavanger|

**DELETE ALL ROWS**
````
DELETE FROM table_name
or
DELETE * FROM table_name
````
----
### The TOP Clause
The TOP Clause is used to specify the number of records to return.
The Top clause can be very useful on large tables with thouseds of records. Returning a large number of records can impact on performance.
Not all database system support the TOP clause.

**SQL Server Syntax**
````
SELECT TOP number|percent column_name(s)
FROM table_name
````
-------
### SQL SELECT TOP Equivalent in My SQL and Oracle
#### MySQL Syntax
````
SELECT column_name(S)
FROM table_name
LIMIT number

**Example**
SELECT *
FROM Persons
LIMIT 5
````
**Oracle Syntax**
````
SELECT column_name(s)
FROM table_name
WHERE ROWNUM <= number 

**Example**

SELECT *
FROM Person WHERE ROWNUM <= 5
````
--------
#### SQL TOP Example
|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |
|2 |Svendson |Tove | Borgvn 23|Sandnes|
|3 |Pettersen|Kari|Storgt 20|Stavanger|
|4 |Nilsen |Tom | Vingvn 23|Stavanger|
````
SELECT TOP 2 * FROM Persons
````
RESULT-SET:

|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |
|2 |Svendson |Tove | Borgvn 23|Sandnes|

-----
#### SQL TOP PERCENT Example
|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |
|2 |Svendson |Tove | Borgvn 23|Sandnes|
|3 |Pettersen|Kari|Storgt 20|Stavanger|
|4 |Nilsen |Tom | Vingvn 23|Stavanger|
````
SELECT TOP 50 PERCENT * FROM Persons
````
Result-set:

|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |
|2 |Svendson |Tove | Borgvn 23|Sandnes|
-------
### SQL LIKE Operator
The LIKE operator is used in a WHERE clause to search for a specified pattern in a column.
````
SELECT column_name(s)
FROM table_name
WHERE column_name LIKE pattern
````
Example:
persons table:

|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |
|2 |Svendson |Tove | Borgvn 23|Sandnes|
|3 |Pettersen|Kari|Storgt 20|Stavanger|
|4 |Nilsen |Tom | Vingvn 23|Stavanger|
````
SELECT * FROM persons
WHERE City LIKE 's%'

(The % sign can be used to define wildcards /missing letters in the pattern) both before and after the pattern.
````
Result-set:

|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |
|2 |Svendson |Tove | Borgvn 23|Sandnes|
|3 |Pettersen|Kari|Storgt 20|Stavanger|
|4 |Nilsen |Tom | Vingvn 23|Stavanger|

````
SELECT * FROM Persons
WHERE City LIKE '%S'
````
|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |
|2 |Svendson |Tove | Borgvn 23|Sandnes|
````
SELECT * FROM Persons
WHERE City like '%tav%'
````
Result-set:

|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
|3 |Pettersen|Kari|Storgt 20|Stavanger|
|4 |Nilsen |Tom | Vingvn 23|Stavanger|
````
SELECT *FROM Persons
WHERE City NOT LIKE '%tav%'
````
Result-set:

|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |
|2 |Svendson |Tove | Borgvn 23|Sandnes|

-----
### SQL Wildcards
SQL wildcards can be used when searching for data in a database.
SQL wildcards must be used with the SQL LIKE operator.
SQL wildcards can be substituted for one or more character when searching for a data in a database.

|Wildcard|Description|
|---|---|
|%|A substitute for a zero or more characters|
|-|a substitute for exactly one character |
|[charlist]|Any single character in charlist|
|[^charlist]|Any single character not in charlist|
|[!charlist]|Any single character not in charlist|

Persons table:

|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |
|2 |Svendson |Tove | Borgvn 23|Sandnes|
|3 |Pettersen|Kari|Storgt 20|Stavanger|
|4 |Nilsen |Tom | Vingvn 23|Stavanger|

Example syntax:
````
SELECT * FROM persons
WHERE LastName LIKE 'S_end_on'
````
|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
|2 |Svendson |Tove | Borgvn 23|Sandnes|
````
SELECT *FROM Persons
WHERE LastName LIKE '[bsp]%'
````
|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
|2 |Svendson |Tove | Borgvn 23|Sandnes|

````
SELECT *FROM Persons
WHERE LastName LIKE '[!bsp]%'
````
|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |

-----
### SQL IN Operator 
The IN operator allows you to specify multiple values in a WHERE clause.
````
SELECT colum_name(s)
FROM table_name
WHERE column_name IN (value1, value2,...)
````
Persons table:

|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |
|2 |Svendson |Tove | Borgvn 23|Sandnes|
|3 |Pettersen|Kari|Storgt 20|Stavanger|
|4 |Nilsen |Tom | Vingvn 23|Stavanger|
````
SELECT *
FROM Persons
WHERE LastName IN ('Hansen','Pettersen')
````
result-set:

|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |
|3 |Pettersen|Kari|Storgt 20|Stavanger|

-------
### SQL BETWEEN Operator
The BETWEEN Operator is used in a WHERE clause to select a range of data between two values.
The values can be numbers, text or dates.
````
SELECT colum_name(s)
FROM table_name
WHERE column_name 
BETWEEN value1 AND value2
````
Persons table:

|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |
|2 |Svendson |Tove | Borgvn 23|Sandnes|
|3 |Pettersen|Kari|Storgt 20|Stavanger|
|4 |Nilsen |Tom | Vingvn 23|Stavanger|
````
SELECT *
FROM Person
WHERE LastName 
BETWEEN 'Hansen' AND 'Pettersen'
````
Result set:

|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
| 1 |Hansen  |Ola |Timoteivn 10|Sandnes |

NOTE:-
The BETWEEN operator is treated differently in different databases.
In some databases' person with the last_name of "Hansen" or "Pettersen" will not be listed because the BETWEEN operator only selects fields that are between and excluding the test values.
In other databases' person with the LastName of "Hansen" or "Pettersen" will be listed because the BETWEEN operator selects fields that are between and including the test values.
In some databases person with the LastName of "Hansen" will be listed but "Pettersen" will not be listed like example above because the BETWEEN operator selects fields between the test values, including the first value and excluding the last test value.
Therefore, it is better to check how a database treats the BETWEEN operator.

Example:
````
SELECT * FROM Persons
WHERE LastName 
NOT BETWEEN 'Hansen' AND 'Pettersen'
````
result-set:

|P_Id  | LastName  |FirstName   | Address  | City |
|---|---|---|---|---|
|2 |Svendson |Tove | Borgvn 23|Sandnes|
|3 |Pettersen|Kari|Storgt 20|Stavanger|

-------
### SQL Alias
With SQL an alias name can be given to a table or a column. This can be a good thing to do if you have a very long or complex table name or column names. An alias name could be anything but usually it is short.
````
** Aias syntax for tables**

SELECT column_name(s)
FROM table_name
AS alias_name

**Alias syntax for cloumns**
SELECT column_name AS alias_name
FROM table_name
````

[sql joins](sql-assets/SQL_Joins.png)

