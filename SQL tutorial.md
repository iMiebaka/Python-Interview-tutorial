
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



# TimeStamp and Extract Function | Date Time Function

The TIMESTAM data type is used for values that contain both date and time parts

1) TIME : contains only time, format HH:MI:SS
2) DATE : contains on date, format YYYY-MM-DD
3) YEAR : contains on year, format YYYY or YY
4) TIMESTAMP : contains date and time, format YYYY-MM-DD HH:MI:SS
5) TIMESTAMPTZ : contains date, time and timezone



**TIMESTAMP functions/Operators**

1) SHOW TIMEZONE
2) SELECT NOW()
3) SELECT TIMEOFDAY()
4) SELECT CURRENT_TIME
5) CURRENT_DATE

          SHOW TIMEZONE
          SELECT NOW()
          SELECT TIMEOFDAY()
          SELECT CURRENT_TIME()
          SELECT CURRENT_DATE
  

**Extract Function**

The EXTRACT() function extracts a part from a given date value. 

Syntax: SELECT EXTRACT(MONTH FROM date_field) FROM Table

1) YEAR
2) QUARTER
3) MONTH
4) WEEK
5) DAY
6) HOUR
7) MINUTE
8) DOW - day of week
9) DOY - Day of year

             SELECT strftime('%m', payment_date) AS payment_month, payment_date 
            FROM Payment;


filter by day


           SELECT strftime('%d', payment_date) AS payment_month, payment_date FROM Payment;




# SQL join

1) JOIN means to combine something
2) A JOIN clause is used to combine data from two or more tables, based on a related column between them
3) Let's understand the join

**Types of JOINS**

1) INNER JOIN
2) LEFT JOIN
3) RIGHT JOIN
4) FULL JOIN

**Inner JOIN**

Returns records that having matching values in both tables

<img src="https://lh4.googleusercontent.com/ZaF77tpvsDLgQgWHqOdbzJVPDJ2EAmp4OSSmbk0sSFe4TcsS3jtxY7EmyfMQ3ta6WIs7bg_ZvKsUZOHkXETHRltRXC5YNi4brzpchn4HBzq4dThms2jAyU9E2KohfEL7j0fOevT5PeMdOdKEJj24C1Y" >


        SELECT * 
        FROM customers AS c
        INNER JOIN payment AS p
        ON c.customer_id = p.customer_id

get specific field


        SELECT c.first_name, p.amount, p.mode 
        FROM customers AS c
        INNER JOIN payment AS p
        ON c.customer_id = p.customer_id

**Left JOIN**

Retrun all records from the left table, and matched records from the right table

<img src="https://lh6.googleusercontent.com/I7BWNmU-rtwMozqKzbWBRgnk2sIv1a1FGElwOheS4ybu8o8erqvNR8Z57CsHndxMpdKlUq8jqaDqyUt7pR775-lSupnm_Cqe5nyncxH3eh0MTf3IA2cWz_8rnMWyDXFIrf-z_MM18zMVs_rQuiIigOw" >

       SELECT c.first_name, p.amount, p.mode 
       FROM customers AS c
       LEFT JOIN payment AS p
       ON c.customer_id = p.customer_id

**Right JOIN**

Return all records from the right table, and the matched records from the left table

<img src="https://lh4.googleusercontent.com/klmC4Kg_LYE9Ic7TO7Yw8IBJMHAx9GBeBm2RU2w3lUM_-TtHUfqYOXgDzoQMCGFLmBVhSeaauM9gUhQUwbt9IZvW7zy1TwLGGONoq8Kn0rPeZmR4txw2LfBctj2TNCPAYUrxe3IgWudpI5FOZ8EWrX-yMa-aVR12tNLX9e_4ggagP1lYGwxA1w-B">


       SELECT c.first_name, p.amount, p.mode 
       FROM customers AS c
       RIGHT JOIN payment AS p
       ON c.customer_id = p.customer_id


 **Full JOIN**

 Return all records when there is a match in either left or right table

 <img src="https://learn.microsoft.com/en-us/power-query/media/merge-queries-full-outer/full-outer-join-operation.png" >

         SELECT c.first_name, p.amount, p.mode 
        FROM customers AS c
        FULL OUTER JOIN payment AS p
        ON c.customer_id = p.customer_id



**Self JOIN**

1) A self join is a regular join in which a table is joined to itself
2) SELF JOIN are powerful for comparing values in a column of row with the same table

   <img src="https://cdn.educba.com/academy/wp-content/uploads/2020/03/student-id.jpg" />




           SELECT Employee.empid, Employee.empname, Manager.manager_name
        FROM Employee
        INNER JOIN Manager ON Employee.manager_id = Manager.manager_id;



**UNION**

The SQL UNION clause/operator is used to combine/concatenate the result of two or more SELECT statements without returning any duplicate row and keep unique record

To use this UNION clause, each SELECT statement must have

1) The same number of columns selected and expressions
2) The same data type and
3) Have them in the same order


         SELECT empid, empname, manager_id FROM Employee
         UNION
         SELECT customer_id, customer_name, NULL FROM Customer;


**Union All**

In UNION ALL everything is same as UNION, it combines/Concatenate two or more table but keeps all records, including duplicates

         SELECT empid, empname, manager_id FROM Employee
         UNION ALL
         SELECT customer_id, customer_name, NULL FROM Customer;


# Sub Query

A Subquery or inner query or a Nested query allows us to create complex query on the output of another query

Sub query syntax involves two SELECT statement

**Q :** Find the details of customers, whose payment amount is more than the average of total amount paid by all customers

Divide above question into two part

1) Find the average amount
2) Filter the customers whose amount  > average amount



         select * from payment where amount > (select AVG(amount) from payment)


Second

         select customer_id, amount, mode from payment
         
         where customer_id IN (select customer_id from customers)


Q) find user whose amount is more than 100 and customer id is same compare with customer table and payment table


           SELECT first_name, last_name 
           FROM customers AS c 
           WHERE EXISTS (
               SELECT customer_id, amount 
               FROM payment p 
               WHERE p.customer_id = c.customer_id 
               AND amount > 100
           );

 
# windows Function

Window functions applies aggregate, ranking and analytics function over a perticular window ( set of rows)

and over clause is used with window functions to define that window

