
# Data types, primary-foreign keys


**Primary Key**:
 A primary key is unique

 **Foreign keys**

 1 ) A foreign key is a column used to link two or more tables together <br>
 2 ) A tbale can have any number of foreign key can constainer duplicate value

 **Constraints**

 1 ) Constraints are used to specify rules for data in a table <br>
 2 ) This ensures the accuracy and reliablity of the data in the table <br>
 3 ) Constraints can be specified when the table is created with the create table statement or <br> 
 4 ) After the table is created with the ALTER TABLE statement <br>
  syntax

              create table table_name (
              column1 datatype constraint,
              column2 datatype constraint,
              column3 datatype constraint,
              ....
              };

  **Commonly used constraints in SQL**

  1) Not Null - Ensures that a column cannot have a null value
  2) UNIQUE   - Ensure that all values in a column are different
  3) PRIMARY KEY -A combination of a NOT NULL and UNIQUE
  4) FOREIGN KEY - Prevents actions that would destroy links between tables (used to link multiple tables together )
  5) CHECK - Ensure that the values in a column statisfies a specific condition
  6) DEFAULT - sets a default value for a column if no values is specified
  7) CREATE INDEX - used to create and retrieve data from the database very quickly


# create table

**Create database**

      CREATE DATABASE  testdb;

**Create table**

      create table test 
      (
        "ID" int8 PRIMARY KEY,
        "Name" varchar(50) NOT NULL,
        "Age" int NOT NULL,
        "City" char(50),
        "Salaryt" numeric
        );
**select table**

        select * from test;

# Insert update, delete & alter table in SQL

**The insert into statement is used to insert new records in table**

          INSERT INTO customer
            (CustID, CustName, Age, City, Salary)
            
          VALUES
          
          (1,"sam",26,"Delhi",9000),
          (2,"Ram",19,"Pune",11000),
          (3,"Pam",31,"Nagar",6000),
          (4,"Jam",42,"Mumbai",10000);

  **The UPDATE command is used to update exising rows in a table**

  
          update customer SET CustName="sachin", City="Nagar" where CustID = 1;

  **Delete values in table**

  The DELETE statement is used to delete existing records in a table

          delete from customer where CustID = 4;

  **Alter Table**

  The ALTER TABLE  statement is used to add, delete, or modify columns in an existing table

          alter table table_name add  column column_name

  **Alter table- DROP COLUMN**

          ALTER TABLE table_name DROP COLUMN column_name
  **Alter table -ALTER/MODIFY COLUMN syntax**

          ALTER TABLE table_name ALTER COLUMN column_name datatype;

  **Drop & Truncate table**

  The DROP TABLE COMMAND DELETES A TABLE IN THE DATABSE

          DROP TABLE table_name;

  The TRUNCATE TABLE command deletes the data inside a table, but not the table itself

          TRUNCATE TABLE table_name

  # SELECT & WHERE CLAUSE

  The SELECT statement is used to select dta from a database.

          SELECT * FROM Customer;


  To select all the fields available in the table


          SELECT Age,City FROM Customer;

  To select distinct/Unique fields available in the table
  
         SELECT DISTINCT City from customer


**Where clause**

the where clause is used to filter records <br>
it is used to extract only those records that fulfill a specified condition

         select * from Customers where country="USA"


 **Operators in python**

 The SQL reserved words and characters are called operators, which are used with a where clause in a SQL Query

 1) Arithmetic operators : arithmetic operations on numeric values (ex Addition (+), Multiplication(*), Division(/), Modules(%)
 2) Comparison operator: Compare two different data of SQL table (ex Equal(=), Not Equal(!=), Greater than(>)
 3) Logical Operators: Perform the Boolean operations(ex ALL, IN, BETWEEN, LIKE, AND, OR, NOT, ANY
 4) Bitwise Operators: Perform the bit operations on the (ex Bitwise AND (& ), bitwise OR(|)


 1) select * from Customers where country="USA" and Age=22
 2) select * from Customers  order by first_name ASC limit 2;


# String functions in SQL

Function in SQL are the database objects that contains a set of SQL statements to perform actions, and then return the result

Type of function

1) System defined function : these are built-in function (ex rand(), round(), upper(), lower(), count(), sum(), max()
2) User-defined function: Once you define a function can call in the same way as the built-in functions

**Most used string function**

String functions are used to perform an operation on input string and return an output string

1) UPPER() : convert the value of a filed to uppercase
2) LOWER() : converts the value of a field to lowercase
3) LENGTH() : returns the length of the value in a text field
4) SUBSTRING() : extracts a substring from a string
5) NOW() : returns the current system date and time
6) FORMAT() : used to set the format of a field
7) CONCAT() : adds two or more strings together
8) REPLACE() : replace all occurrences of a substring within a string with a new substate
9) TRIM() : removes leading and trailing spaces ( or other specified characters) from a


          1) select UPPER(first_name) from Customers
          2) select LOWER(first_name) from Customers
          3) select LENGTH(first_name), first_name from Customers
          4) select SUBSTRING(first_name,1,3), first_name from Customers  #  it will slice name (sac)
          5) SELECT CONCAT(first_name, ' ', last_name) AS full_name FROM customers;
          6) SELECT replace(first_name, "John","sachin") FROM customers;


# Aggregate function in SQL

Aggregate function perform a calculation on multiple values and returns a single values.

Aad aggregate function are often used with Group BY & Select

and Aggreagte function are often used with group by & select statement

        1) COUNT() : returns number of values
        2) SUM() : return sum of all values
        3) AVG() : return average value
        4) MAX() : return maximum value
        5) MIN() : return minimum value
        6) ROUND() : Round a number to a specified number of decimal places
        

        1) SELECT COUNT(*) FROM Customers;
        2) SELECT SUM(age) FROM Customers;
        3) SELECT AVG(age) FROM Customers;
        4) SELECT MAX(age) FROM Customers;
        5) SELECT MIN(age) FROM Customers;
        6) SELECT ROUND(age) FROM Customers;
        7) SELECT ROUND(AVG(age), 2) FROM Customers;

 
# Group by and having clause in SQL

The GROUP BY statement group rows that have the same values into summary rows.

It is often used with aggregate functions (COUNT(), MAX(), MIN(), MIN(), SUM(), AVG()) to group the result-set by one or more columns


       SELECT item, SUM(amount) AS Total from Orders GROUP BY item


By Order

       SELECT item, SUM(amount) AS Total from Orders GROUP BY item order by amount ASC

**Having clause**

The Havign clause is used to apply a filter on the result of GROUP BY based on the specified condition

The WHERE clause places conditions on the selected columns, whereas the having clause places conditions on groups created by the GROUP BY clause




  
