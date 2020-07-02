<!-- TOC -->

- [1. SQL](#1-sql)
    - [1.1. SQL Operators](#11-sql-operators)
    - [1.2. SQL Data Types](#12-sql-data-types)
        - [1.2.1. MySQL Data Types (Version 8.0)](#121-mysql-data-types-version-80)
    - [1.3. SQL Syntax](#13-sql-syntax)
    - [1.4. SELECT Statement](#14-select-statement)
    - [1.5. WHERE Clause](#15-where-clause)
    - [1.6. AND, OR and NOT Operators](#16-and-or-and-not-operators)
    - [1.7. ORDER BY Keyword](#17-order-by-keyword)
    - [1.8. INSERT INTO Statement](#18-insert-into-statement)
    - [1.9. NULL Values](#19-null-values)
    - [1.10. UPDATE & DELETE Statement](#110-update--delete-statement)
    - [1.11. Select TOP, LIMIT or ROWNUM Clause](#111-select-top-limit-or-rownum-clause)
    - [1.12. Min, Max, Count, Avg, Sum Functions](#112-min-max-count-avg-sum-functions)
    - [1.13. LIKE Operator](#113-like-operator)
        - [1.13.1. Wildcard Characters](#1131-wildcard-characters)
    - [1.14. IN Operator](#114-in-operator)
    - [1.15. BETWEEN Operator](#115-between-operator)
    - [1.16. SQL Aliases](#116-sql-aliases)
    - [1.17. SQL Joins](#117-sql-joins)
        - [1.17.1. Self JOIN](#1171-self-join)
    - [1.18. UNION Operator](#118-union-operator)
    - [1.19. GROUP BY Statement](#119-group-by-statement)
    - [1.20. HAVING Clause](#120-having-clause)
    - [1.21. EXISTS Operator](#121-exists-operator)
    - [1.22. ANY and ALL Operators](#122-any-and-all-operators)
    - [1.23. SELECT INTO Statement](#123-select-into-statement)
    - [1.24. INSERT INTO SELECT Statement](#124-insert-into-select-statement)
    - [1.25. CASE Statement](#125-case-statement)
    - [1.26. NULL Functions -- IFNULL(), ISNULL(), COALESCE(), NVL()](#126-null-functions----ifnull-isnull-coalesce-nvl)
    - [1.27. Stored Procedures for SQL Server](#127-stored-procedures-for-sql-server)
    - [1.28. Comments](#128-comments)
- [2. SQL Database](#2-sql-database)
    - [2.1. Create DB, Drop DB, Backup DB](#21-create-db-drop-db-backup-db)
    - [2.2. Create Table, Drop Table, Alter Table](#22-create-table-drop-table-alter-table)
    - [2.3. SQL Constraints](#23-sql-constraints)
        - [2.3.1. NOT NULL](#231-not-null)
        - [2.3.2. UNIQUE](#232-unique)
        - [2.3.3. PRIMARY KEY](#233-primary-key)
        - [2.3.4. FOREIGN KEY](#234-foreign-key)
        - [2.3.5. CHECK](#235-check)
        - [2.3.6. DEFAULT](#236-default)
        - [2.3.7. INDEX](#237-index)
    - [2.4. SQL Auto Increment](#24-sql-auto-increment)
    - [2.5. SQL Dates](#25-sql-dates)
    - [2.6. SQL Views](#26-sql-views)
    - [2.7. SQL Injection](#27-sql-injection)
        - [2.7.1. SQL in Web Pages](#271-sql-in-web-pages)
        - [2.7.2. Use SQL Parameters for Protection](#272-use-sql-parameters-for-protection)
    - [2.8. SQL Hosting](#28-sql-hosting)
- [3. SQL Keywords](#3-sql-keywords)
- [4. Functions](#4-functions)
    - [4.1. MySQL Functions](#41-mysql-functions)
    - [4.2. SQL Server Functions](#42-sql-server-functions)
    - [4.3. MS Access Functions](#43-ms-access-functions)

<!-- /TOC -->

# SQL
SQL is a standard language for accessing and manipulating databases.
SQL stands for Structured Query Language.
SQL lets you access and manipulate databases.
SQL became a standard of the American National Standards Institute (ANSI) in 1986, and of the International Organization for Standardization (ISO) in 1987.

SQL can execute queries against a database
SQL can retrieve data from a database
SQL can insert records in a database
SQL can update records in a database
SQL can delete records from a database
SQL can create new databases
SQL can create new tables in a database
SQL can create stored procedures in a database
SQL can create views in a database
SQL can set permissions on tables, procedures, and views

Although SQL is an ANSI/ISO standard, there are different versions of the SQL language.
However, to be compliant with the ANSI standard, they all support at least the major commands (such as SELECT, UPDATE, DELETE, INSERT, WHERE) in a similar manner.

Note: Most of the SQL database programs also have their own proprietary extensions in addition to the SQL standard!

To build a web site that shows data from a database, you will need:
- An RDBMS database program (i.e. MS Access, SQL Server, MySQL)
- To use a server-side scripting language, like PHP or ASP
- To use SQL to get the data you want
- To use HTML / CSS to style the page

Relational Database Management System (RDBMS) is the basis for SQL, and for all modern database systems such as MS SQL Server, IBM DB2, Oracle, MySQL, and Microsoft Access.

The data in RDBMS is stored in database objects called tables. A table is a collection of related data entries and it consists of columns and rows.

Every table is broken up into smaller entities called fields. 
A field is a column in a table that is designed to maintain specific information about every record in the table.
A record, also called a row, is each individual entry that exists in a table.
A column is a vertical entity in a table that contains all information associated with a specific field in a table.

## SQL Operators
* SQL Arithmetic Operators
    + Add
    - Subtract
    * Multiply
    / Divide
    % Modulo
* SQL Bitwise Operators
    & Bitwise AND
    | Bitwise OR
    ^ Bitwise exclusive OR
* SQL Comparison Operators
    = Equal to
    > Greater than
    < Less than
    >= Greater than or equal to
    <= Less than or equal to
    <> Not equal to
* SQL Compound Operators
    += Add equals
    -= Subtract equals
    *= Multiply equals
    /= Divide equals
    %= Modulo equals
    &= Bitwise AND equals
    ^-= Bitwise exclusive equals
    |*= Bitwise OR equals
* SQL Logical Operators
    ALL   TRUE if all of the subquery values meet the condition
    AND   TRUE if all the conditions separated by AND is TRUE
    ANY   TRUE if any of the subquery values meet the condition
    BETWEEN   TRUE if the operand is within the range of comparisons
    EXISTS    TRUE if the subquery returns one or more records
    IN     TRUE if the operand is equal to one of a list of expressions
    LIKE   TRUE if the operand matches a pattern
    NOT    Displays a record if the condition(s) is NOT TRUE
    OR     TRUE if any of the conditions separated by OR is TRUE
    SOME   TRUE if any of the subquery values meet the condition

## SQL Data Types
The data type of a column defines what value the column can hold: integer, character, money, date and time, binary, and so on.

Each column in a database table is required to have a name and a data type.

An SQL developer must decide what type of data that will be stored inside each column when creating a table. The data type is a guideline for SQL to understand what type of data is expected inside of each column, and it also identifies how SQL will interact with the stored data.

Note: Data types might have different names in different database. And even if the name is the same, the size and other details may be different!

### MySQL Data Types (Version 8.0)
In MySQL there are three main data types: string, numeric, and date and time.
1. String data types:
    * CHAR(size)	A FIXED length string (can contain letters, numbers, and special characters). The size parameter specifies the column length in characters - can be from 0 to 255. Default is 1
    * VARCHAR(size)	A VARIABLE length string (can contain letters, numbers, and special characters). The size parameter specifies the maximum column length in characters - can be from 0 to 65535
    * BINARY(size)	Equal to CHAR(), but stores binary byte strings. The size parameter specifies the column length in bytes. Default is 1
    * VARBINARY(size)	Equal to VARCHAR(), but stores binary byte strings. The size parameter specifies the maximum column length in bytes.
    * TINYBLOB	For BLOBs (Binary Large OBjects). Max length: 255 bytes
    * TINYTEXT	Holds a string with a maximum length of 255 characters
    * TEXT(size)	Holds a string with a maximum length of 65,535 bytes
    * BLOB(size)	For BLOBs (Binary Large OBjects). Holds up to 65,535 bytes of data
    * MEDIUMTEXT	Holds a string with a maximum length of 16,777,215 characters
    * MEDIUMBLOB	For BLOBs (Binary Large OBjects). Holds up to 16,777,215 bytes of data
    * LONGTEXT	Holds a string with a maximum length of 4,294,967,295 characters
    * LONGBLOB	For BLOBs (Binary Large OBjects). Holds up to 4,294,967,295 bytes of data
    * ENUM(val1, val2, val3, ...)	A string object that can have only one value, chosen from a list of possible values. You can list up to 65535 values in an ENUM list. If a value is inserted that is not in the list, a blank value will be inserted. The values are sorted in the order you enter them
    * SET(val1, val2, val3, ...)	A string object that can have 0 or more values, chosen from a list of possible values. You can list up to 64 values in a SET list

2. Numeric data types:
    * BIT(size)	A bit-value type. The number of bits per value is specified in size. The size parameter can hold a value from 1 to 64. The default value for size is 1.
    * TINYINT(size)	A very small integer. Signed range is from -128 to 127. Unsigned range is from 0 to 255. The size parameter specifies the maximum display width (which is 255)
    * BOOL	Zero is considered as false, nonzero values are considered as true.
    * BOOLEAN	Equal to BOOL
    * SMALLINT(size)	A small integer. Signed range is from -32768 to 32767. Unsigned range is from 0 to 65535. The size parameter specifies the maximum display width (which is 255)
    * MEDIUMINT(size)	A medium integer. Signed range is from -8388608 to 8388607. Unsigned range is from 0 to 16777215. The size parameter specifies the maximum display width (which is 255)
    * INT(size)	A medium integer. Signed range is from -2147483648 to 2147483647. Unsigned range is from 0 to 4294967295. The size parameter specifies the maximum display width (which is 255)
    * INTEGER(size)	Equal to INT(size)
    * BIGINT(size)	A large integer. Signed range is from -9223372036854775808 to 9223372036854775807. Unsigned range is from 0 to 18446744073709551615. The size parameter specifies the maximum display width (which is 255)
    * FLOAT(size, d)	A floating point number. The total number of digits is specified in size. The number of digits after the decimal point is specified in the d parameter. This syntax is deprecated in MySQL 8.0.17, and it will be removed in future MySQL versions
    * FLOAT(p)	A floating point number. MySQL uses the p value to determine whether to use FLOAT or DOUBLE for the resulting data type. If p is from 0 to 24, the data type becomes FLOAT(). If p is from 25 to 53, the data type becomes DOUBLE()
    * DOUBLE(size, d)	A normal-size floating point number. The total number of digits is specified in size. The number of digits after the decimal point is specified in the d parameter
    * DOUBLE PRECISION(size, d)	 
    * DECIMAL(size, d)	An exact fixed-point number. The total number of digits is specified in size. The number of digits after the decimal point is specified in the d parameter. The maximum number for size is 65. The maximum number for d is 30. The default value for size is 10. The default value for d is 0.
    * DEC(size, d)	Equal to DECIMAL(size,d)

Note: All the numeric data types may have an extra option: UNSIGNED or ZEROFILL. If you add the UNSIGNED option, MySQL disallows negative values for the column. If you add the ZEROFILL option, MySQL automatically also adds the UNSIGNED attribute to the column.

3. Date and Time data types:
    * DATE	A date. Format: YYYY-MM-DD. The supported range is from '1000-01-01' to '9999-12-31'
    * DATETIME(fsp)	A date and time combination. Format: YYYY-MM-DD hh:mm:ss. The supported range is from '1000-01-01 00:00:00' to '9999-12-31 23:59:59'. Adding DEFAULT and ON UPDATE in the column definition to get automatic initialization and updating to the current date and time
    * TIMESTAMP(fsp)	A timestamp. TIMESTAMP values are stored as the number of seconds since the Unix epoch ('1970-01-01 00:00:00' UTC). Format: YYYY-MM-DD hh:mm:ss. The supported range is from '1970-01-01 00:00:01' UTC to '2038-01-09 03:14:07' UTC. Automatic initialization and updating to the current date and time can be specified using DEFAULT CURRENT_TIMESTAMP and ON UPDATE CURRENT_TIMESTAMP in the column definition
    * TIME(fsp)	A time. Format: hh:mm:ss. The supported range is from '-838:59:59' to '838:59:59'
    * YEAR	A year in four-digit format. Values allowed in four-digit format: 1901 to 2155, and 0000. 
            MySQL 8.0 does not support year in two-digit format.

[SQL Server Data Types, Microsoft Access Data Types (略)](https://www.w3schools.com/sql/sql_datatypes.asp)

## SQL Syntax
A database most often contains one or more tables. Each table is identified by a name. Tables contain records (rows) with data.

Most of the actions you need to perform on a database are done with **SQL statements**.

SQL keywords are NOT case sensitive: select is the same as SELECT
Some database systems require a semicolon at the end of each SQL statement.
Semicolon is the standard way to separate each SQL statement in database systems that allow more than one SQL statement to be executed in the same call to the server.

Some of The Most Important SQL Commands:
    SELECT - extracts data from a database
    UPDATE - updates data in a database
    DELETE - deletes data from a database
    INSERT INTO - inserts new data into a database
    CREATE DATABASE - creates a new database
    ALTER DATABASE - modifies a database
    CREATE TABLE - creates a new table
    ALTER TABLE - modifies a table
    DROP TABLE - deletes a table
    CREATE INDEX - creates an index (search key)
    DROP INDEX - deletes an index

## SELECT Statement
The SELECT statement is used to select data from a database.
The data returned is stored in a result table (result-set).
```sql
SELECT column1, column2, ...   -- field names of the table you want to select data from; * to select all the fields available in the table
FROM table_name;
```

The SELECT DISTINCT statement is used to return only distinct (different) values.
Inside a table, a column often contains many duplicate values; and sometimes you only want to list the different (distinct) values.
```sql
SELECT DISTINCT column1, column2, ...
FROM table_name;
```

## WHERE Clause
The WHERE clause is used to filter records.
The WHERE clause is used to extract only those records that fulfill a specified condition.
```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```
Note: The WHERE clause is not only used in SELECT statement, it is also used in UPDATE, DELETE statement, etc.!

SQL requires single quotes around text values (most database systems will also allow double quotes), numeric fields should not be enclosed in quotes.

Operators in The WHERE Clause:
* =, <>  Equal/Not equal (In some versions of SQL this operator may be written as !=)
* >, <  Greater than/Less than
* >=, <=  Greater than or equal/Less than or equal
* BETWEEN  Between a certain range
* LIKE  Search for a pattern
* IN  To specify multiple possible values for a column

## AND, OR and NOT Operators
The WHERE clause can be combined with AND, OR, and NOT operators.
The AND and OR operators are used to filter records based on more than one condition:
    The AND operator displays a record if all the conditions separated by AND are TRUE.
    The OR operator displays a record if any of the conditions separated by OR is TRUE.
The NOT operator displays a record if the condition(s) is NOT TRUE.

```sql
SELECT column1, column2, ...
FROM table_name

WHERE condition1 AND condition2 AND condition3 ...;

WHERE condition1 OR condition2 OR condition3 ...;

WHERE NOT condition;
```
You can combine the AND, OR and NOT operators. (use parenthesis to form complex expressions)

## ORDER BY Keyword
The ORDER BY keyword is used to sort the result-set in ascending or descending order.
The ORDER BY keyword sorts the records in ascending order by default. To sort the records in descending order, use the DESC keyword.

```sql
SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC;  
-- ORDER BY Several Columns  e.g. ORDER BY column1 DESC, column2 ASC;
```

## INSERT INTO Statement
The INSERT INTO statement is used to insert new records(row) in a table.

```sql
-- The first way specifies both the column names and the values to be inserted:
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);
    -- auto-increment field: the field without specification will be generated automatically (as null) when a new record is inserted into the table 

-- If you are adding values for all the columns of the table, no need to specify the column names in the SQL query. However, make sure the order of the values is in the same order as the columns in the table.
INSERT INTO table_name
VALUES (value1, value2, value3, ...);
```

## NULL Values
A field with a NULL value is a field with no value.

If a field in a table is optional, it is possible to insert a new record or update a record without adding a value to this field. Then, the field will be saved with a NULL value.

Note: A NULL value is different from a zero value or a field that contains spaces. A field with a NULL value is one that has been left blank during record creation!

It is not possible to test for NULL values with comparison operators, such as =, <, or <>.
We will have to use the IS NULL and IS NOT NULL operators instead.
    The IS NULL operator is used to test for empty values (NULL values).
    The IS NOT NULL operator is used to test for non-empty values (NOT NULL values).
```sql
SELECT column_names
FROM table_name

WHERE column_name IS NULL;

WHERE column_name IS NOT NULL;
```

## UPDATE & DELETE Statement
The UPDATE statement is used to modify the existing records in a table.
The DELETE statement is used to delete existing records in a table.

```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;

DELETE FROM table_name WHERE condition;
```
Note: The WHERE clause specifies which record(s) that should be updated/deleted. If you omit the WHERE clause, all records in the table will be updated/deleted!

It is possible to delete all rows/records in a table without deleting the table. This means that the table structure, attributes, and indexes will be intact: ```DELETE FROM table_name; ```

## Select TOP, LIMIT or ROWNUM Clause
The SELECT TOP clause is used to specify the number of records to return. It is useful on large tables with thousands of records. Returning a large number of records can impact performance.

Note: Not all database systems support the SELECT TOP clause. MySQL supports the LIMIT clause to select a limited number of records, while Oracle uses ROWNUM.

```sql
-- SQL Server / MS Access Syntax:
SELECT TOP number | percent column_name(s)  -- select number of rows or percentage
FROM table_name
WHERE condition;
-- MySQL Syntax:
SELECT column_name(s)
FROM table_name
WHERE condition
LIMIT number;
-- Oracle Syntax:
SELECT column_name(s)
FROM table_name
WHERE ROWNUM <= number;
```

The following SQL statement selects the first 50% of the records from the "Customers" table (for SQL Server/MS Access):
SELECT TOP 50 PERCENT * FROM Customers;

## Min, Max, Count, Avg, Sum Functions
The MIN()/MAX() function returns the smallest/largest value of the selected column.
```sql
SELECT MIN(column_name)  -- SELECT MAX(column_name)
FROM table_name
WHERE condition;
```
The COUNT() function returns the number of rows that matches a specified criterion.
The AVG() function returns the average value of a numeric column.
The SUM() function returns the total sum of a numeric column.

```sql
SELECT COUNT(column_name) -- SELECT AVG(column_name)   SELECT SUM(column_name)
FROM table_name
WHERE condition;
```
Note: NULL values are ignored.

## LIKE Operator
The LIKE operator is used in a WHERE clause to search for a specified pattern in a column.

There are two wildcards often used in conjunction with the LIKE operator:
* %  The percent sign represents zero, one, or multiple characters
* _  The underscore represents a single character
Note: MS Access uses an asterisk (*) instead of the percent sign (%), and a question mark (?) instead of the underscore (_).

```sql 
SELECT column1, column2, ...
FROM table_name
WHERE columnN LIKE pattern;
```

### Wildcard Characters
A wildcard character is used to substitute one or more characters in a string.
Wildcard characters are used with the SQL LIKE operator. The LIKE operator is used in a WHERE clause to search for a specified pattern in a column.
All the wildcards can also be used in combinations!

Wildcard Characters in MS Access
    *	Represents zero or more characters	bl* finds bl, black, blue, and blob
    ?	Represents a single character	h?t finds hot, hat, and hit
    []	Represents any single character within the brackets	h[oa]t finds hot and hat, but not hit
    !	Represents any character not in the brackets	h[!oa]t finds hit, but not hot and hat
    -	Represents a range of characters	c[a-b]t finds cat and cbt
    #	Represents any single numeric character	2#5 finds 205, 215, 225, 235, 245, 255, 265, 275, 285, and 295

Wildcard Characters in SQL Server
    %	Represents zero or more characters	bl% finds bl, black, blue, and blob
    _	Represents a single character	h_t finds hot, hat, and hit
    []	Represents any single character within the brackets	h[oa]t finds hot and hat, but not hit
    ^	Represents any character not in the brackets	h[^oa]t finds hit, but not hot and hat
    -	Represents a range of characters	c[a-b]t finds cat and cbt

Here are some examples showing different LIKE operators with '%' and '_' wildcards:
WHERE CustomerName LIKE 'a%'	Finds any values that start with "a"
WHERE CustomerName LIKE '%a'	Finds any values that end with "a"
WHERE CustomerName LIKE '%or%'	Finds any values that have "or" in any position
WHERE CustomerName LIKE '_r%'	Finds any values that have "r" in the second position
WHERE CustomerName LIKE 'a_%'	Finds any values that start with "a" and are at least 2 characters in length
WHERE CustomerName LIKE 'a__%'	Finds any values that start with "a" and are at least 3 characters in length
WHERE ContactName LIKE 'a%o'	Finds any values that start with "a" and ends with "o"

## IN Operator
The IN operator allows you to specify multiple values in a WHERE clause.
The IN operator is a shorthand for multiple OR conditions.

```sql
SELECT column_name(s)
FROM table_name
WHERE column_name IN (value1, value2, ...);
-- or:
SELECT column_name(s)
FROM table_name
WHERE column_name IN (SELECT STATEMENT);
```

Example:
SELECT * FROM Customers 
WHERE Country NOT IN ('Germany', 'France', 'UK');

SELECT * FROM Customers
WHERE Country IN (SELECT Country FROM Suppliers);

## BETWEEN Operator
The BETWEEN operator selects values within a given range. The values can be numbers, text, or dates.
The BETWEEN operator is inclusive: begin and end values are included. 
```sql
SELECT column_name(s)
FROM table_name
WHERE column_name BETWEEN value1 AND value2;
```

## SQL Aliases
SQL aliases are used to give a table, or a column in a table, a temporary name.
Aliases are often used to make column names more readable.
An alias only exists for the duration of the query.

```sql
-- Alias Column Syntax
SELECT column_name AS alias_name
FROM table_name;
-- Alias Table Syntax
SELECT column_name(s)
FROM table_name AS alias_name;
```

## SQL Joins
A JOIN clause is used to combine rows from two or more tables, based on a related column between them.

Different Types of SQL JOINs
* (INNER) JOIN: Returns/Selects records that have matching values in both tables
    ```sql
    SELECT column_name(s)
    FROM table1
    INNER JOIN table2
    ON table1.column_name = table2.column_name;
    ```
* LEFT (OUTER) JOIN: Returns all records from the left table, and the matched records from the right table
    The LEFT JOIN keyword returns all records from the left table (table1), and the matched records from the right table (table2). The result is NULL from the right side, if there is no match.
    ```sql
    SELECT column_name(s)
    FROM table1
    LEFT JOIN table2
    ON table1.column_name = table2.column_name;
    ```
    Note: In some databases LEFT/RIGHT JOIN is called LEFT/RIGHT OUTER JOIN.
* RIGHT (OUTER) JOIN: Returns all records from the right table, and the matched records from the left table
    The RIGHT JOIN keyword returns all records from the right table (table2), and the matched records from the left table (table1). The result is NULL from the left side, when there is no match.
* FULL (OUTER) JOIN: Returns all records when there is a match in either left or right table
    Note: FULL OUTER JOIN can potentially return very large result-sets! FULL OUTER JOIN and FULL JOIN are the same.

![](.picture/JOINs)

### Self JOIN
A self JOIN is a regular join, but the table is joined with itself.
```sql
SELECT column_name(s)
FROM table1 T1, table1 T2
WHERE condition;
```
T1 and T2 are different table aliases for the same table.

## UNION Operator
The UNION operator is used to combine the result-set of two or more SELECT statements.
- Each SELECT statement within UNION must have the same number of columns
- The columns must also have similar data types
- The columns in each SELECT statement must also be in the same order
```sql
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2;

-- The UNION operator selects only distinct values by default. To allow duplicate values, use UNION ALL.
SELECT column_name(s) FROM table1
UNION ALL
SELECT column_name(s) FROM table2;
```
Note: The column names in the result-set are usually equal to the column names in the first SELECT statement in the UNION.

## GROUP BY Statement
The GROUP BY statement groups rows that have the same values into summary rows.
The GROUP BY statement is often used with aggregate functions (COUNT, MAX, MIN, SUM, AVG) to group the result-set by one or more columns.

```sql
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
ORDER BY column_name(s);
```

## HAVING Clause
The HAVING clause was added to SQL because the WHERE keyword could not be used with aggregate functions.
```sql
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
HAVING condition
ORDER BY column_name(s);
```

## EXISTS Operator
The EXISTS operator is used to test for the existence of any record in a subquery.
The EXISTS operator returns true if the subquery returns one or more records.

```sql
SELECT column_name(s)
FROM table_name
WHERE EXISTS
(SELECT column_name FROM table_name WHERE condition);
```
Example:
```sql
-- Return TRUE and list the suppliers with a product price less than 20:
SELECT SupplierName
FROM Suppliers
WHERE EXISTS (SELECT ProductName FROM Products WHERE Products.SupplierID = Suppliers.supplierID AND Price < 20);
```

## ANY and ALL Operators
The ANY and ALL operators are used with a WHERE or HAVING clause.
The ANY operator returns true if any of the subquery values meet the condition.
The ALL operator returns true if all of the subquery values meet the condition.

```sql
SELECT column_name(s)
FROM table_name
WHERE column_name operator ANY  -- WHERE column_name operator ALL
(SELECT column_name FROM table_name WHERE condition);
```
Note: The operator must be a standard comparison operator (=, <>, !=, >, >=, <, or <=).

## SELECT INTO Statement
The SELECT INTO statement copies data from one table into a new table.

```sql
-- Copy all columns into a new table:
SELECT *
INTO newtable [IN externaldb]
FROM oldtable
WHERE condition;

-- Copy only some columns into a new table:
SELECT column1, column2, column3, ...
INTO newtable [IN externaldb]
FROM oldtable
WHERE condition;
```
The new table will be created with the column-names and types as defined in the old table. You can create new column names using the AS clause.

## INSERT INTO SELECT Statement
The INSERT INTO SELECT statement copies data from one table and inserts it into another table.
- INSERT INTO SELECT requires that data types in source and target tables match
- The existing records in the target table are unaffected
```sql
-- Copy all columns from one table to another table:
INSERT INTO table2
SELECT * FROM table1
WHERE condition;
-- Copy only some columns from one table into another table:
INSERT INTO table2 (column1, column2, column3, ...)
SELECT column1, column2, column3, ...
FROM table1
WHERE condition;
```

## CASE Statement
The CASE statement goes through conditions and returns a value when the first condition is met (like an IF-THEN-ELSE statement). So, once a condition is true, it will stop reading and return the result. If no conditions are true, it returns the value in the ELSE clause.

If there is no ELSE part and no conditions are true, it returns NULL.

```sql 
CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    WHEN conditionN THEN resultN
    ELSE result
END;
```

## NULL Functions -- IFNULL(), ISNULL(), COALESCE(), NVL()

The MySQL IFNULL() function lets you return an alternative value if an expression is NULL:
```sql
IFNULL(Field, value)    -- returns value if Field is Null
COALESCE(Field, value)  -- returns value if Field is Null
```
The SQL Server ISNULL() function lets you return an alternative value when an expression is NULL.
The MS Access IsNull() function returns TRUE (-1) if the expression is a null value, otherwise FALSE (0).
The Oracle NVL() function achieves the same result.

## Stored Procedures for SQL Server
A stored procedure is a prepared SQL code that you can save, so the code can be reused over and over again.
So if you have an SQL query that you write over and over again, save it as a stored procedure, and then just call it to execute it.
You can also pass parameters to a stored procedure, so that the stored procedure can act based on the parameter value(s) that is passed.

```sql
-- Stored Procedure Syntax
CREATE PROCEDURE procedure_name
AS
sql_statement
GO;

-- Execute a Stored Procedure
EXEC procedure_name;
```

```sql
-- Stored Procedure With One Parameter
CREATE PROCEDURE SelectAllCustomers @City nvarchar(30)
AS
SELECT * FROM Customers WHERE City = @City
GO;

EXEC SelectAllCustomers @City = 'London';

-- Stored Procedure With Multiple Parameters
CREATE PROCEDURE SelectAllCustomers @City nvarchar(30), @PostalCode nvarchar(10)
AS
SELECT * FROM Customers WHERE City = @City AND PostalCode = @PostalCode
GO;

EXEC SelectAllCustomers @City = 'London', @PostalCode = 'WA1 1DP';
```

## Comments
Comments are used to explain sections of SQL statements, or to prevent execution of SQL statements.
* Single line comments start with --. Any text between -- and the end of the line will be ignored (will not be executed).
* Multi-line comments start with /* and end with */. Any text between /* and */ will be ignored.
    uses a multi-line comment to ignore many statements, part of a line, or part of a statement


---

# SQL Database

## Create DB, Drop DB, Backup DB
The CREATE DATABASE statement is used to create a new SQL database.
```sql
CREATE DATABASE databasename;

-- Once a database is created, you can check it in the list of databases with the following SQL command: 
SHOW DATABASES;
```

The DROP DATABASE statement is used to drop an existing SQL database.
```sql
DROP DATABASE databasename;
```
Note: Be careful before dropping a database. Deleting a database will result in loss of complete information stored in the database!


The BACKUP DATABASE statement is used in SQL Server to create a full back up of an existing SQL database.
```sql
BACKUP DATABASE databasename
TO DISK = 'filepath';    -- e.g. filepath can be 'D:\backups\testDB.bak'

-- A differential back up only backs up the parts of the database that have changed since the last full database backup.
BACKUP DATABASE databasename
TO DISK = 'filepath'
WITH DIFFERENTIAL;
```
Note: Always back up the database to a different drive than the actual database. Then, if you get a disk crash, you will not lose your backup file along with the database.
Note: A differential back up reduces the back up time (since only the changes are backed up).

## Create Table, Drop Table, Alter Table
The CREATE TABLE statement is used to create a new table in a database.

```sql
CREATE TABLE table_name (
    column1 datatype,   -- The column parameters specify the names of the columns of the table
    column2 datatype,   -- The datatype parameter specifies the type of data the column can hold (e.g. varchar, integer, date)
    column3 datatype,
   ....
);
```

Create Table Using Another Table
A copy of an existing table can also be created using CREATE TABLE.
The new table gets the same column definitions. All columns or specific columns can be selected.
If you create a new table using an existing table, the new table will be filled with the existing values from the old table.

```sql
CREATE TABLE new_table_name AS
    SELECT column1, column2, ...
    FROM existing_table_name
    WHERE ....;
```

The DROP TABLE statement is used to drop an existing table in a database.
The TRUNCATE TABLE statement is used to delete the data inside a table, but not the table itself.
```sql
DROP TABLE table_name;

TRUNCATE TABLE table_name;
```
Note: Be careful before dropping a table. Deleting a table will result in loss of complete information stored in the table!

The ALTER TABLE statement is used to add, delete, or modify columns in an existing table.
The ALTER TABLE statement is also used to add and drop various constraints on an existing table.
* ADD a Column
    ```sql
    ALTER TABLE table_name
    ADD column_name datatype;
    ```
* DROP/DELETE COLUMN, note that some database systems don't allow deleting a column
    ```sql
    ALTER TABLE table_name
    DROP COLUMN column_name;
    ```
* change the data type of a column in a table
    ```sql
    -- SQL Server / MS Access:
    ALTER TABLE table_name
    ALTER COLUMN column_name datatype;
    -- My SQL / Oracle (prior version 10G):
    ALTER TABLE table_name
    MODIFY COLUMN column_name datatype;
    -- Oracle 10G and later:
    ALTER TABLE table_name
    MODIFY column_name datatype;
    ```

## SQL Constraints
SQL constraints are used to specify rules for data in a table.

SQL Create Constraints
Constraints can be specified when the table is created with the CREATE TABLE statement, or after the table is created with the ALTER TABLE statement.
```sql
CREATE TABLE table_name (
    column1 datatype constraint,
    column2 datatype constraint,
    column3 datatype constraint,
    ....
);
```

Constraints are used to limit the type of data that can go into a table. This ensures the accuracy and reliability of the data in the table. If there is any violation between the constraint and the data action, the action is aborted.
Constraints can be column level or table level. Column level constraints apply to a column, and table level constraints apply to the whole table.

Common Constraints in SQL:
* NOT NULL   Ensures that a column cannot have a NULL value
* UNIQUE   Ensures that all values in a column are different
* PRIMARY KEY   A combination of a NOT NULL and UNIQUE. Uniquely identifies each row in a table
* FOREIGN KEY   Uniquely identifies a row/record in another table
* CHECK   Ensures that all values in a column satisfies a specific condition
* DEFAULT   Sets a default value for a column when no value is specified
* INDEX   Used to create and retrieve data from the database very quickly


### NOT NULL
By default, a column can hold NULL values. The NOT NULL constraint enforces a column to NOT accept NULL values.
This enforces a field to always contain a value, which means that you cannot insert a new record, or update a record without adding a value to this field.
- SQL NOT NULL on CREATE TABLE
    ```sql
    CREATE TABLE Persons (
        ID int NOT NULL,
        Name varchar(255) NOT NULL,
        Age int
    );
    ```
- NOT NULL on ALTER TABLE
    ```sql
    ALTER TABLE Persons
    MODIFY Age int NOT NULL;
    ```
### UNIQUE
The UNIQUE constraint ensures that all values in a column are different.
Both the UNIQUE and PRIMARY KEY constraints provide a guarantee for uniqueness for a column or set of columns.
A PRIMARY KEY constraint automatically has a UNIQUE constraint.
However, you can have many UNIQUE constraints per table, but only one PRIMARY KEY constraint per table.

- SQL UNIQUE Constraint on CREATE TABLE
    ```sql
    -- create a UNIQUE constraint on the "ID" column when the "Persons" table is created
    -- SQL Server / Oracle / MS Access:
    CREATE TABLE Persons (
    ID int NOT NULL UNIQUE,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int);
    -- MySQL:
    CREATE TABLE Persons (
        ID int NOT NULL,
        LastName varchar(255) NOT NULL,
        FirstName varchar(255),
        Age int,
        UNIQUE (ID));

    -- To name a UNIQUE constraint, and to define a UNIQUE constraint on multiple columns:
    -- MySQL / SQL Server / Oracle / MS Access:
    CREATE TABLE Persons (
        ID int NOT NULL,
        LastName varchar(255) NOT NULL,
        FirstName varchar(255),
        Age int,
        CONSTRAINT UC_Person UNIQUE (ID, LastName)
    );
    ```
- SQL UNIQUE Constraint on ALTER TABLE
    ```sql
    -- create a UNIQUE constraint on the "ID" column when the table is already created
    -- MySQL / SQL Server / Oracle / MS Access:
    ALTER TABLE Persons
    ADD UNIQUE (ID);

    -- To name a UNIQUE constraint, and to define a UNIQUE constraint on multiple columns :
    -- MySQL / SQL Server / Oracle / MS Access:
    ALTER TABLE Persons
    ADD CONSTRAINT UC_Person UNIQUE (ID, LastName);
    ```
- DROP a UNIQUE Constraint
    ```sql
    -- MySQL:
    ALTER TABLE Persons
    DROP INDEX UC_Person;
    -- SQL Server / Oracle / MS Access:
    ALTER TABLE Persons
    DROP CONSTRAINT UC_Person;
    ```

### PRIMARY KEY
The PRIMARY KEY constraint uniquely identifies each record in a table.
Primary keys must contain UNIQUE values, and cannot contain NULL values.
A table can have only ONE primary key; and in the table, this primary key can consist of single or multiple columns (fields).

- SQL PRIMARY KEY on CREATE TABLE
    ```sql
    -- create a PRIMARY KEY on the "ID" column when the "Persons" table is created
    -- MySQL:
    CREATE TABLE Persons (
        ID int NOT NULL,
        LastName varchar(255) NOT NULL,
        FirstName varchar(255),
        Age int,
        PRIMARY KEY (ID)
    );
    -- SQL Server / Oracle / MS Access:
    CREATE TABLE Persons (
        ID int NOT NULL PRIMARY KEY,
        LastName varchar(255) NOT NULL,
        FirstName varchar(255),
        Age int
    );

    -- To allow naming of a PRIMARY KEY constraint (for defining a PRIMARY KEY constraint on multiple columns)
    -- MySQL / SQL Server / Oracle / MS Access:
    CREATE TABLE Persons (
        ID int NOT NULL,
        LastName varchar(255) NOT NULL,
        FirstName varchar(255),
        Age int,
        CONSTRAINT PK_Person PRIMARY KEY (ID, LastName)
    );
    -- Note: there is only ONE PRIMARY KEY (PK_Person). However, the VALUE of the primary key is made up of TWO COLUMNS (ID + LastName).
    ```

- SQL PRIMARY KEY on ALTER TABLE
    ```sql
    -- create a PRIMARY KEY constraint on the "ID" column when the table is already created
    -- MySQL / SQL Server / Oracle / MS Access:
    ALTER TABLE Persons
    ADD PRIMARY KEY (ID);
    -- To allow naming of a PRIMARY KEY constraint, and for defining a PRIMARY KEY constraint on multiple columns:
    -- MySQL / SQL Server / Oracle / MS Access:
    ALTER TABLE Persons
    ADD CONSTRAINT PK_Person PRIMARY KEY (ID,LastName);
    ```
Note: If you use the ALTER TABLE statement to add a primary key, the primary key column(s) must already have been declared to not contain NULL values (when the table was first created).

- DROP a PRIMARY KEY Constraint
    ```sql
    -- MySQL:
    ALTER TABLE Persons
    DROP PRIMARY KEY;
    -- SQL Server / Oracle / MS Access:
    ALTER TABLE Persons
    DROP CONSTRAINT PK_Person;
    ```

### FOREIGN KEY
A FOREIGN KEY is a key used to link two tables together.
A FOREIGN KEY is a field (or collection of fields) in one table that refers to the PRIMARY KEY in another table.
The table containing the foreign key is the child table, and the table containing the candidate key is the referenced/parent table.

The FOREIGN KEY constraint is used to prevent actions that would destroy links between tables.
The FOREIGN KEY constraint also prevents invalid data from being inserted into the foreign key column, because it has to be one of the values contained in the table it points to.


- SQL FOREIGN KEY on CREATE TABLE
    ```sql
    -- create a FOREIGN KEY on the "PersonID" column when the "Orders" table is created:
    -- MySQL:
    CREATE TABLE Orders (
        OrderID int NOT NULL,
        OrderNumber int NOT NULL,
        PersonID int,
        PRIMARY KEY (OrderID),
        FOREIGN KEY (PersonID) REFERENCES Persons(PersonID)
    );
    -- SQL Server / Oracle / MS Access:
    CREATE TABLE Orders (
        OrderID int NOT NULL PRIMARY KEY,
        OrderNumber int NOT NULL,
        PersonID int FOREIGN KEY REFERENCES Persons(PersonID)
    );
    -- To allow naming of a FOREIGN KEY constraint, and for defining a FOREIGN KEY constraint on multiple columns:
    -- MySQL / SQL Server / Oracle / MS Access:
    CREATE TABLE Orders (
        OrderID int NOT NULL,
        OrderNumber int NOT NULL,
        PersonID int,
        PRIMARY KEY (OrderID),
        CONSTRAINT FK_PersonOrder FOREIGN KEY (PersonID)
        REFERENCES Persons(PersonID)
    );
    ```

- SQL FOREIGN KEY on ALTER TABLE
    ```sql
    -- create a FOREIGN KEY constraint on the "PersonID" column when the "Orders" table is already created:
    -- MySQL / SQL Server / Oracle / MS Access:
    ALTER TABLE Orders
    ADD FOREIGN KEY (PersonID) REFERENCES Persons(PersonID);

    -- To allow naming of a FOREIGN KEY constraint, and for defining a FOREIGN KEY constraint on multiple columns:
    -- MySQL / SQL Server / Oracle / MS Access:
    ALTER TABLE Orders
    ADD CONSTRAINT FK_PersonOrder
    FOREIGN KEY (PersonID) REFERENCES Persons(PersonID);
    ```
- DROP a FOREIGN KEY Constraint
    ```sql
    -- To drop a FOREIGN KEY constraint:
    -- MySQL:
    ALTER TABLE Orders
    DROP FOREIGN KEY FK_PersonOrder;
    -- SQL Server / Oracle / MS Access:
    ALTER TABLE Orders
    DROP CONSTRAINT FK_PersonOrder;
    ```

### CHECK
The CHECK constraint is used to limit the value range that can be placed in a column.
If you define a CHECK constraint on a single column it allows only certain values for this column.
If you define a CHECK constraint on a table it can limit the values in certain columns based on values in other columns in the row.

- SQL CHECK on CREATE TABLE
    ```sql
    -- create a CHECK constraint on the "Age" column when the "Persons" table is created. The CHECK constraint ensures that the age of a person must be 18 or older:
    -- MySQL:
    CREATE TABLE Persons (
        ID int NOT NULL,
        LastName varchar(255) NOT NULL,
        FirstName varchar(255),
        Age int,
        CHECK (Age>=18)
    );
    -- SQL Server / Oracle / MS Access:
    CREATE TABLE Persons (
        ID int NOT NULL,
        LastName varchar(255) NOT NULL,
        FirstName varchar(255),
        Age int CHECK (Age>=18)
    );
    -- To allow naming of a CHECK constraint, and for defining a CHECK constraint on multiple columns:
    -- MySQL / SQL Server / Oracle / MS Access:
    CREATE TABLE Persons (
        ID int NOT NULL,
        LastName varchar(255) NOT NULL,
        FirstName varchar(255),
        Age int,
        City varchar(255),
        CONSTRAINT CHK_Person CHECK (Age>=18 AND City='Sandnes')
    );
    ```

- SQL CHECK on ALTER TABLE
    ```sql
    -- To create a CHECK constraint on the "Age" column when the table is already created:
    -- MySQL / SQL Server / Oracle / MS Access:
    ALTER TABLE Persons
    ADD CHECK (Age>=18);
    -- To allow naming of a CHECK constraint, and for defining a CHECK constraint on multiple columns :
    -- MySQL / SQL Server / Oracle / MS Access:
    ALTER TABLE Persons
    ADD CONSTRAINT CHK_PersonAge CHECK (Age>=18 AND City='Sandnes');
    ``` 
- DROP a CHECK Constraint
    ```sql
    -- To drop a CHECK constraint:
    -- SQL Server / Oracle / MS Access:
    ALTER TABLE Persons
    DROP CONSTRAINT CHK_PersonAge;
    -- MySQL:
    ALTER TABLE Persons
    DROP CHECK CHK_PersonAge;
    ```

### DEFAULT
The DEFAULT constraint is used to provide a default value for a column.
The default value will be added to all new records IF no other value is specified.

- SQL DEFAULT on CREATE TABLE
    ```sql
    -- set a DEFAULT value for the "City" column when the "Persons" table is created:
    -- My SQL / SQL Server / Oracle / MS Access:
    CREATE TABLE Persons (
        ID int NOT NULL,
        LastName varchar(255) NOT NULL,
        FirstName varchar(255),
        Age int,
        City varchar(255) DEFAULT 'Sandnes'
    );
    -- The DEFAULT constraint can also be used to insert system values:
    CREATE TABLE Orders (
        ID int NOT NULL,
        OrderNumber int NOT NULL,
        OrderDate date DEFAULT GETDATE()
    );
    ```
- SQL DEFAULT on ALTER TABLE
    ```sql
    -- To create a DEFAULT constraint on the "City" column when the table is already created, use the following SQL:
    -- MySQL:
    ALTER TABLE Persons
    ALTER City SET DEFAULT 'Sandnes';
    -- SQL Server:
    ALTER TABLE Persons
    ADD CONSTRAINT df_City 
    DEFAULT 'Sandnes' FOR City;
    -- MS Access:
    ALTER TABLE Persons
    ALTER COLUMN City SET DEFAULT 'Sandnes';
    -- Oracle:
    ALTER TABLE Persons
    MODIFY City DEFAULT 'Sandnes';
    ```
- DROP a DEFAULT Constraint
    ```sql
    -- To drop a DEFAULT constraint, use the following SQL:
    -- MySQL:
    ALTER TABLE Persons
    ALTER City DROP DEFAULT;
    -- SQL Server / Oracle / MS Access:
    ALTER TABLE Persons
    ALTER COLUMN City DROP DEFAULT;
    ```
### INDEX

- CREATE INDEX Statement
    The CREATE INDEX statement is used to create indexes in tables.
    Indexes are used to retrieve data from the database more quickly than otherwise. The users cannot see the indexes, they are just used to speed up searches/queries.
    Note: Updating a table with indexes takes more time than updating a table without (because the indexes also need an update). So, only create indexes on columns that will be frequently searched against.

    ```sql
    -- Creates an index on a table. Duplicate values are allowed
    CREATE INDEX index_name
    ON table_name (column1, column2, ...);
    CREATE UNIQUE INDEX Syntax

    -- Creates a unique index on a table. Duplicate values are not allowed:
    CREATE UNIQUE INDEX index_name
    ON table_name (column1, column2, ...);
    ```
- DROP INDEX Statement
    ```sql
    -- The DROP INDEX statement is used to delete an index in a table.
    -- MS Access:
    DROP INDEX index_name ON table_name;
    -- SQL Server:
    DROP INDEX table_name.index_name;
    -- DB2/Oracle:
    DROP INDEX index_name;
    -- MySQL:
    ALTER TABLE table_name
    DROP INDEX index_name;
    ```

## SQL Auto Increment

AUTO INCREMENT Field
Auto-increment allows a unique number to be generated automatically when a new record is inserted into a table.
Often this is the primary key field that we would like to be created automatically every time a new record is inserted.


- Syntax for MySQL
    ```sql
    CREATE TABLE Persons (
        Personid int NOT NULL AUTO_INCREMENT, -- "Personid" column to be an auto-increment primary key field in the "Persons" table
        LastName varchar(255) NOT NULL,
        FirstName varchar(255),
        Age int,
        PRIMARY KEY (Personid)
    );
    ```
    MySQL uses the AUTO_INCREMENT keyword to perform an auto-increment feature.
    By default, the starting value for AUTO_INCREMENT is 1, and it will increment by 1 for each new record.
    ```sql
    -- To let the AUTO_INCREMENT sequence start with another value, use the following SQL statement:
    ALTER TABLE Persons AUTO_INCREMENT=100;
    ```

- Syntax for SQL Server
    ```sql
    CREATE TABLE Persons (
        Personid int IDENTITY(1,1) PRIMARY KEY,
        LastName varchar(255) NOT NULL,
        FirstName varchar(255),
        Age int
    );
    ```
    The MS SQL Server uses the IDENTITY keyword to perform an auto-increment feature.
    In the example above, the starting value for IDENTITY is 1, and it will increment by 1 for each new record.
    To specify that the "Personid" column should start at value 10 and increment by 5, change it to IDENTITY(10, 5).

- Syntax for Access
    ```sql
    CREATE TABLE Persons (
        Personid AUTOINCREMENT PRIMARY KEY,
        LastName varchar(255) NOT NULL,
        FirstName varchar(255),
        Age int
    );
    ```
    The MS Access uses the AUTOINCREMENT keyword to perform an auto-increment feature.
    By default, the starting value for AUTOINCREMENT is 1, and it will increment by 1 for each new record.
    To specify that the "Personid" column should start at value 10 and increment by 5, change the autoincrement to AUTOINCREMENT(10, 5).

- Syntax for Oracle
    In Oracle the code is a little bit more tricky.
    You will have to create an auto-increment field with the sequence object (this object generates a number sequence).
    ```sql
    CREATE SEQUENCE seq_person
    MINVALUE 1
    START WITH 1
    INCREMENT BY 1
    CACHE 10;
    ```
    It creates a sequence object called seq_person, that starts with 1 and will increment by 1. It will also cache up to 10 values for performance. The cache option specifies how many sequence values will be stored in memory for faster access.

    To insert a new record into the "Persons" table, we will have to use the nextval function (this function retrieves the next value from seq_person sequence):
    ```sql
    INSERT INTO Persons (Personid,FirstName,LastName)
    VALUES (seq_person.nextval,'Lars','Monsen');
    ```

## SQL Dates
Note: the most difficult part when working with dates is to be sure that the format of the date you are trying to insert, matches the format of the date column in the database.

As long as your data contains only the date portion, your queries will work as expected. However, if a time portion is involved, it gets more complicated.

SQL Date Data Types:
- MySQL comes with the following data types for storing a date or a date/time value in the database:
    * DATE - format YYYY-MM-DD
    * DATETIME - format: YYYY-MM-DD HH:MI:SS
    * TIMESTAMP - format: YYYY-MM-DD HH:MI:SS
    * YEAR - format YYYY or YY
- SQL Server comes with the following data types for storing a date or a date/time value in the database:
    * DATE - format YYYY-MM-DD
    * DATETIME - format: YYYY-MM-DD HH:MI:SS
    * SMALLDATETIME - format: YYYY-MM-DD HH:MI:SS
    * TIMESTAMP - format: a unique number
Note: The date types are chosen for a column when you create a new table in your database!

You can compare two dates easily if there is no time component involved!

To select the records with an OrderDate of "2008-11-11" from the table.
SELECT * FROM Orders WHERE OrderDate='2008-11-11'  
This query is looking only for dates with no time portion. If the column contains time portion, this query will return no result.

## SQL Views
In SQL, a view is a virtual table based on the result-set of an SQL statement.
A view contains rows and columns, just like a real table. The fields in a view are fields from one or more real tables in the database.
You can add SQL functions, WHERE, and JOIN statements to a view and present the data as if the data were coming from one single table.

* SQL CREATE VIEW Statement
    ```sql
    CREATE VIEW view_name AS
    SELECT column1, column2, ...
    FROM table_name
    WHERE condition;

    -- query the view
    SELECT * FROM [view_name];
    ```
    Note: A view always shows up-to-date data! The database engine recreates the data, using the view's SQL statement, every time a user queries a view.

Example: creates a view that selects every product in the "Products" table with a price higher than the average price
```sql
CREATE VIEW [Products Above Average Price] AS
SELECT ProductName, Price
FROM Products
WHERE Price > (SELECT AVG(Price) FROM Products);

SELECT * FROM [Products Above Average Price];
```

* SQL Updating a View
    A view can be updated with the CREATE OR REPLACE VIEW command.
    ```sql
    CREATE OR REPLACE VIEW view_name AS
    SELECT column1, column2, ...
    FROM table_name
    WHERE condition;
    ```
* SQL Dropping a View
    A view is deleted with the DROP VIEW command.
    ```sql
    DROP VIEW view_name;
    ```

## SQL Injection
SQL injection is a code injection technique that might destroy your database.
SQL injection is one of the most common web hacking techniques.
SQL injection is the placement of malicious code in SQL statements, via web page input.

### SQL in Web Pages
SQL injection usually occurs when you ask a user for input, like their username/userid, and instead of a name/id, the user gives you an SQL statement that you will unknowingly run on your database.

The following example creates a SELECT statement by adding a variable (txtUserId) to a select string. The variable is fetched from user input (getRequestString):
```java
txtUserId = getRequestString("UserId");
txtSQL = "SELECT * FROM Users WHERE UserId = " + txtUserId;
```
The original purpose of the code was to create an SQL statement to select a user, with a given user id.

- SQL Injection Based on 1=1 is Always True
    If there is nothing to prevent a user from entering "wrong" input, the user can enter some "smart" input like this:
    ```UserId: 105 OR 1=1```
    Then, the SQL statement will look like this: 
    ```sql 
    SELECT * FROM Users WHERE UserId = 105 OR 1=1; 
    ```
    The SQL above is valid and will return ALL rows from the "Users" table, since OR 1=1 is always TRUE.
    If the "Users" table contains names and passwords, the SQL statement above is much the same as this:
    ```sql
    SELECT UserId, Name, Password FROM Users WHERE UserId = 105 or 1=1;
    ```
    A hacker might get access to all the user names and passwords in a database, by simply inserting 105 OR 1=1 into the input field.

- SQL Injection Based on ""="" is Always True
    ```java
    sql = 'SELECT * FROM Users WHERE Name ="' + uName + '" AND Pass ="' + uPass + '"'
    ```
    A hacker might get access to user names and passwords in a database by simply inserting " OR ""=" into the user name or password text box:
    ```User Name: " OR ""=" ```
    ```Password: " OR ""=" ```
    The code at the server will create a valid SQL statement like this:
    ```sql
    SELECT * FROM Users WHERE Name ="" or ""="" AND Pass ="" or ""=""
    ```
    The SQL above is valid and will return all rows from the "Users" table, since OR ""="" is always TRUE.
- SQL Injection Based on Batched SQL Statements 
    Most databases support batched SQL statement.
    A batch of SQL statements is a group of two or more SQL statements, separated by semicolons.

    ```java
    txtUserId = getRequestString("UserId");
    txtSQL = "SELECT * FROM Users WHERE UserId = " + txtUserId;
    ```
    With the following input:
    ```User id: 105; DROP TABLE Suppliers```

    The valid SQL statement would look like this:
    ```sql
    SELECT * FROM Users WHERE UserId = 105; DROP TABLE Suppliers;
    ```
    The SQL statement will return all rows from the "Users" table, then delete the "Suppliers" table.

### Use SQL Parameters for Protection
To protect a web site from SQL injection, you can use SQL parameters.
SQL parameters are values that are added to an SQL query at execution time, in a controlled manner.

Parameters are represented in the SQL statement by a @ marker.
The SQL engine checks each parameter to ensure that it is correct for its column and are treated not as part of the SQL to be executed.

## SQL Hosting
If you want your web site to be able to store and retrieve data from a database, your web server should have access to a database-system that uses the SQL language.
If your web server is hosted by an Internet Service Provider (ISP), you will have to look for SQL hosting plans.
The most common SQL hosting databases are MS SQL Server, Oracle, MySQL, and MS Access.

MS SQL Server
Microsoft's SQL Server is a popular database software for database-driven web sites with high traffic.
SQL Server is a very powerful, robust and full featured SQL database system.

Oracle
Oracle is also a popular database software for database-driven web sites with high traffic.
Oracle is a very powerful, robust and full featured SQL database system.

MySQL
MySQL is also a popular database software for web sites.
MySQL is a very powerful, robust and full featured SQL database system.
MySQL is an inexpensive alternative to the expensive Microsoft and Oracle solutions.

Access
When a web site requires only a simple database, Microsoft Access can be a solution.
Access is not well suited for very high-traffic, and not as powerful as MySQL, SQL Server, or Oracle.


# [SQL Keywords](https://www.w3schools.com/sql/sql_ref_keywords.asp)
| Keyword                | Description                                                                                                  |
|------------------------|--------------------------------------------------------------------------------------------------------------|
| ADD                    | Adds a column in an existing table                                                                           |
| ADD CONSTRAINT         | Adds a constraint after a table is already created                                                           |
| ALTER                  | Adds, deletes, or modifies columns in a table, or changes the data type of a column in a table               |
| ALTER COLUMN           | Changes the data type of a column in a table                                                                 |
| ALTER TABLE            | Adds, deletes, or modifies columns in a table                                                                |
| ALL                    | Returns true if all of the subquery values meet the condition                                                |
| AND                    | Only includes rows where both conditions is true                                                             |
| ANY                    | Returns true if any of the subquery values meet the condition                                                |
| AS                     | Renames a column or table with an alias                                                                      |
| ASC                    | Sorts the result set in ascending order                                                                      |
| BACKUP DATABASE        | Creates a back up of an existing database                                                                    |
| BETWEEN                | Selects values within a given range                                                                          |
| CASE                   | Creates different outputs based on conditions                                                                |
| CHECK                  | A constraint that limits the value that can be placed in a column                                            |
| COLUMN                 | Changes the data type of a column or deletes a column in a table                                             |
| CONSTRAINT             | Adds or deletes a constraint                                                                                 |
| CREATE                 | Creates a database, index, view, table, or procedure                                                         |
| CREATE DATABASE        | Creates a new SQL database                                                                                   |
| CREATE INDEX           | Creates an index on a table (allows duplicate values)                                                        |
| CREATE OR REPLACE VIEW | Updates a view                                                                                               |
| CREATE TABLE           | Creates a new table in the database                                                                          |
| CREATE PROCEDURE       | Creates a stored procedure                                                                                   |
| CREATE UNIQUE INDEX    | Creates a unique index on a table (no duplicate values)                                                      |
| CREATE VIEW            | Creates a view based on the result set of a SELECT statement                                                 |
| DATABASE               | Creates or deletes an SQL database                                                                           |
| DEFAULT                | A constraint that provides a default value for a column                                                      |
| DELETE                 | Deletes rows from a table                                                                                    |
| DESC                   | Sorts the result set in descending order                                                                     |
| DISTINCT               | Selects only distinct (different) values                                                                     |
| DROP                   | Deletes a column, constraint, database, index, table, or view                                                |
| DROP COLUMN            | Deletes a column in a table                                                                                  |
| DROP CONSTRAINT        | Deletes a UNIQUE, PRIMARY KEY, FOREIGN KEY, or CHECK constraint                                              |
| DROP DATABASE          | Deletes an existing SQL database                                                                             |
| DROP DEFAULT           | Deletes a DEFAULT constraint                                                                                 |
| DROP INDEX             | Deletes an index in a table                                                                                  |
| DROP TABLE             | Deletes an existing table in the database                                                                    |
| DROP VIEW              | Deletes a view                                                                                               |
| EXEC                   | Executes a stored procedure                                                                                  |
| EXISTS                 | Tests for the existence of any record in a subquery                                                          |
| FOREIGN KEY            | A constraint that is a key used to link two tables together                                                  |
| FROM                   | Specifies which table to select or delete data from                                                          |
| FULL OUTER JOIN        | Returns all rows when there is a match in either left table or right table                                   |
| GROUP BY               | Groups the result set (used with aggregate functions: COUNT, MAX, MIN, SUM, AVG)                             |
| HAVING                 | Used instead of WHERE with aggregate functions                                                               |
| IN                     | Allows you to specify multiple values in a WHERE clause                                                      |
| INDEX                  | Creates or deletes an index in a table                                                                       |
| INNER JOIN             | Returns rows that have matching values in both tables                                                        |
| INSERT INTO            | Inserts new rows in a table                                                                                  |
| INSERT INTO SELECT     | Copies data from one table into another table                                                                |
| IS NULL                | Tests for empty values                                                                                       |
| IS NOT NULL            | Tests for non-empty values                                                                                   |
| JOIN                   | Joins tables                                                                                                 |
| LEFT JOIN              | Returns all rows from the left table, and the matching rows from the right table                             |
| LIKE                   | Searches for a specified pattern in a column                                                                 |
| LIMIT                  | Specifies the number of records to return in the result set                                                  |
| NOT                    | Only includes rows where a condition is not true                                                             |
| NOT NULL               | A constraint that enforces a column to not accept NULL values                                                |
| OR                     | Includes rows where either condition is true                                                                 |
| ORDER BY               | Sorts the result set in ascending or descending order                                                        |
| OUTER JOIN             | Returns all rows when there is a match in either left table or right table                                   |
| PRIMARY KEY            | A constraint that uniquely identifies each record in a database table                                        |
| PROCEDURE              | A stored procedure                                                                                           |
| RIGHT JOIN             | Returns all rows from the right table, and the matching rows from the left table                             |
| ROWNUM                 | Specifies the number of records to return in the result set                                                  |
| SELECT                 | Selects data from a database                                                                                 |
| SELECT DISTINCT        | Selects only distinct (different) values                                                                     |
| SELECT INTO            | Copies data from one table into a new table                                                                  |
| SELECT TOP             | Specifies the number of records to return in the result set                                                  |
| SET                    | Specifies which columns and values that should be updated in a table                                         |
| TABLE                  | Creates a table, or adds, deletes, or modifies columns in a table, or deletes a table or data inside a table |
| TOP                    | Specifies the number of records to return in the result set                                                  |
| TRUNCATE TABLE         | Deletes the data inside a table, but not the table itself                                                    |
| UNION                  | Combines the result set of two or more SELECT statements (only distinct values)                              |
| UNION ALL              | Combines the result set of two or more SELECT statements (allows duplicate values)                           |
| UNIQUE                 | A constraint that ensures that all values in a column are unique                                             |
| UPDATE                 | Updates existing rows in a table                                                                             |
| VALUES                 | Specifies the values of an INSERT INTO statement                                                             |
| VIEW                   | Creates, updates, or deletes a view                                                                          |
| WHERE                  | Filters a result set to include only records that fulfill a specified condition                              |

# Functions
## MySQL Functions
MySQL String Functions
MySQL Numeric Functions
MySQL Date Functions
MySQL Advanced Functions

## SQL Server Functions
SQL Server String Functions
SQL Server Math/Numeric Functions
SQL Server Date Functions
SQL Server Advanced Functions

## MS Access Functions
MS Access String Functions
MS Access Numeric Functions
MS Access Date Functions
MS Access Some Other Functions