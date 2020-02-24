**Select * From Customers;**

**SELECT * FROM Customers
WHERE Country='Germany' AND City='Berlin';**


**INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES ('Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway');**


**UPDATE Customers
SET ContactName = 'Alfred Schmidt', City= 'Frankfurt'
WHERE CustomerID = 1;**


**DELETE FROM Customers WHERE CustomerName='Alfreds Futterkiste';**


to Create database   **Create Database testDb;**
to Delete   **Drop Database testDb;**
for backup  **BACKUP DATABASE testDB TO DISK = 'D:\backups\testDB.bak';**


to create table  

**CREATE TABLE Persons (
    PersonID int,
    LastName varchar(255),
    FirstName varchar(255),
    Address varchar(255),
    City varchar(255)
);**

to delete complete table with values 
   ** DROP TABLE Shippers;**
   
to delete values of the table:
  ** TRUNCATE TABLE table_name;**
  
to alter table - ADD,Delete,Alter the column in existing table

ALTER TABLE Customers
ADD Email varchar(255);

ALTER TABLE Customers
DROP COLUMN Email;

ALTER TABLE table_name
MODIFY COLUMN column_name datatype;

How to create **primary key:**

The PRIMARY KEY constraint uniquely identifies each record in a table.

Primary keys must contain UNIQUE values, and cannot contain NULL values.

A table can have only ONE primary key; and in the table, this primary key can consist of single or multiple columns (fields).


**CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    PRIMARY KEY (ID)
);**

**Foreign key**
A FOREIGN KEY is a key used to link two tables together.

A FOREIGN KEY is a field (or collection of fields) in one table that refers to the PRIMARY KEY in another table.

The table containing the foreign key is called the child table, and the table containing the candidate key is called the referenced or parent table.

**CREATE TABLE Orders (
    OrderID int NOT NULL,
    OrderNumber int NOT NULL,
    PersonID int,
    PRIMARY KEY (OrderID),
    FOREIGN KEY (PersonID) REFERENCES Persons(PersonID)
);**



 

















to get all the columns from the Customers table.
**SELECT * FROM table_name;**



SELECT * FROM Customers;

Inside a table, a column often contains many duplicate values; and someAND Syntax
SELECT column1, column2, ...
FROM table_name
WHERE condition1 AND condition2 AND condition3 ...;times you only want to list the different (distinct) values.

SELECT DISTINCT column1, column2, ...
FROM table_name;

**SELCT DISTICT City from Cusomers;**

The following SQL statement lists the number of different (distinct) customer countries:

**SELECT COUNT(DISTINCT Country) FROM Customers;**

The WHERE clause is used to extract only those records that fulfill a specified condition.
** SELECT column1, column2, ...
FROM table_name
WHERE condition;**

AND Syntax
**SELECT column1, column2, ...
FROM table_name
WHERE condition1 AND condition2 AND condition3 ...;**

SELECT * FROM Customers
WHERE Country='Germany' AND City='Berlin';


OR Syntax
**SELECT column1, column2, ...
FROM table_name
WHERE condition1 OR condition2 OR condition3 ...;**
e.g.

SELECT * FROM Customers
WHERE City='Berlin' OR City='München';


NOT Syntax

**SELECT column1, column2, ...
FROM table_name
WHERE NOT condition;**

SELECT * FROM Customers
WHERE NOT Country='Germany';


The ORDER BY keyword is used to sort the result-set in ascending or descending order.

**SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC;**


SELECT * FROM Customers
ORDER BY Country ASC, CustomerName DESC;


Insert 
1)into all columns
2)into specific columns

**INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES ('Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway');**


**INSERT INTO Customers (CustomerName, City, Country)
VALUES ('Cardinal', 'Stavanger', 'Norway');**



Update

**UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;**


e.g.

UPDATE Customers
SET ContactName = 'Alfred Schmidt', City= 'Frankfurt'
WHERE CustomerID = 1;

**Be careful when updating records. If you omit the WHERE clause, ALL records will be updated!**



Delete:

**DELETE FROM table_name WHERE condition;**
e.g.
DELETE FROM Customers WHERE CustomerName='Alfreds Futterkiste';


Delete All Records:
**DELETE FROM Customers;**

Select top or Limit clause or rownum(in oracle) and select top percent

SELECT TOP 3 * FROM Customers;

    or
    
SELECT * FROM Customers LIMIT 3;

      or
SELECT * FROM Customers WHERE ROWNUM <= 3;


SELECT TOP 50 PERCENT * FROM Customers;

**Sql Functions:**
min,max,count,avg


Select all records where the first letter of the City is an "a" or a "c" or an "s".


SELECT * FROM Customers
WHERE City LIKE '
[acs]%';

Select all records where the first letter of the City is NOT an "a" or a "c" or an "f".


SELECT * FROM Customers
WHERE City LIKE '[^acf]%';


The IN operator is a shorthand for multiple OR conditions.

**SELECT * FROM Customers
WHERE Country IN ('Germany', 'France', 'UK');**


**SELECT * FROM Customers
WHERE Country NOT IN ('Germany', 'France', 'UK');**


**SELECT * FROM Customers
WHERE Country IN (SELECT Country FROM Suppliers);**


**SQL JOIN**
A JOIN clause is used to combine rows from two or more tables, based on a related column between them.

**(INNER) JOIN:** Returns records that have matching values in both tables
**LEFT (OUTER) JOIN:** Returns all records from the left table, and the matched records from the right table
**RIGHT (OUTER) JOIN:** Returns all records from the right table, and the matched records from the left table
**FULL (OUTER) JOIN:** Returns all records when there is a match in either left or right table

e.g.

SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate
FROM Orders
INNER JOIN Customers ON Orders.CustomerID=Customers.CustomerID;


**Group by**

The following SQL statement lists the number of customers in each country:

Example

SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country;









