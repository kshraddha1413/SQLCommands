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






