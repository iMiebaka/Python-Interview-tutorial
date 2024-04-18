
# what is DBMS

DBMS stands for database management system. DBMS is a system software responsible for the creation, retrieval, updating and management of the database. it ensures that our data <br>
is consistent, organized and is easily accessible by serving as an interface between the database and end user

# why do we use DBMS and not files systems

1) Complex process to retrieve data
2) Loss of data on concurrent access
3) data redundancy
4) data isolation is not there

# what is RDBMS

Relational database management system. it stores data in the form of a collection of tables and relations can be defined between the common fields of these table
e.g MySQL, Microsoft SQL server, Oracle, IBM DB2 and Amazon redshift

# what are the different database management systems other than RDBMS

1) Distributed database: Amazon redshift, TeraData, Netezza
2) NoSQL database: MongoDM, Cassandra
3) Graph databases: Amazon Neptune
4) Cloud database: AWS, Azur, oracle cloud

# what is entity integrity

it ensures table must have a column or set of column which uniquely identify a row <br>
Enfored through: **primary key**

# what is referential integrity

it is specified between two table and it ensures every value of a column in a table must come from the column value of another table <br>
Enforced through: Foreign key

# what is domain integrity

it ensures that the column values should be defined. i.e can pick value from a finite value. <br>
e.g M or F in Gender <br>
Enforced through: DATA TYPES and CHECK, NOT NULL, UNIQUE

# what are constraints in SQL

constraints are used to specify the rules concerning data in the table

1) NOT NULL :- Restricts NULL value from being inserted into a column
2) CHECK :- verify that all values in a field satisfy a condition
3) DEFAULT :- Automatically assigns a default valu if no value has been specified for the field
4) UNIQUE :- Ensures unique values to be inserted into the field
5) PRIMARY KEY :- Uniquely identifies each record in a tabl
6) FOREIGN KEY :- Ensure referential integrity for a record in another table

# what are the various levels of constraints

There are two levels of a constraint

1) Column level constraint
2) table level constraint

# how can we select unique records from a table

using **DISTINCT** keywork

# what is primary key

The PRIMARY KEY constraint uniquely identifies each row in a table <br>
it has 2 property i.e UNIQUE and NOT NULL <br>
A table in SQL is strictly restricted to have one an only one primary key, which is comprised of single or multiple columns

# what is a Foreign key

a **FOREIGN KEY** comprises of single or collection of fields in a table that essentially refer to the **PRIMARY KEY** in another table <br>
it ensures referential integrity between 2 table

# type of relationshis in SQL

1) **one-to-one** :- This can be defined as the relationship between tow tables where each record in one table is associated with the maximum of one record in the other table
2) **one-to-many & many-to-one** : This is the most commonly used relationship where a record in a table is associated with multiple records in the other table
3) **Many-to-Many** :- this is used in cases when multiple instances on both sides are needed for defining a relationship
4) **self referencing relationship** :- This is used when a table needs to define a relationship with itself

# different types of SQL Commands

1) **DDL** -: Data definition language
2) **DML** :- Data manipulation language
3) **DCL** :- Data control language
4) **TCL** :- Transaction control Language

# what is DDL Command

Data defination language used to define the database schema

1) Create
2) .Alter
3) .Drop
4) .Truncate

# what is DML command

SQL commands that deals with the manupulation of data present in the database

1) insert
2) update
3) delete
4) select

# what is DCL command

command which deals with the rights, permissions and other controls of the database system

1) Grant
2) .Revoke

# what is TCL command

commands deal with the transaction within the database

1) Commit
2) Rollback

# diffrence between delete, drop and truncate

<br>

# Are NULL values same as that of zero or a blank space

A NULL value is not at all same as that of zero or a blank space <br>
NULL value represent a vlue which is unavailable or a garbage value

# what is the difference between NVL and NVL2

**NVL(expr1, expr2)** :- converts a null value to an actual value <br>
**NVL2(expr1, expr2, expr3)** :- if the first expression is not null, then the NVL2 function returns the second expression. if the first expression is null, <br> then the third expression is returned

# Difference between UNION and UNION ALL

**UNION** :- only keeps unique records <br>
**UNION ALL** :- keeps all records, including duplicates

# what is an Alias

Alias is a temporary name assigned to the table coulmn for the purpose of a perticular SQL query 

      SELECT A.empname AS "Employee" B.empname AS "Manager" FROM employee A, employee B 
      WHERE A.empid = B.empid

# what is join 

<br>

# what is self join 

A SELF JOIN is a case of regular join where a table is joined to itself based on same relation between its own column(s). Self-join uses the INNER JOIN or LEFT JOIN <br>
clause and a table alias is used to assign diffrent names to the table within the query

      SELECT A.emp_id AS "Emp_ID", A.emp_name AS "Employee",
      B.emp_id AS "Sup_ID", B.emp_name AS "Manager"
      FROM employee A, employee B
      WHERE A.emp_sup = B.emp_id;

# what are the different operators available in SQL

1) Arithmetic Operators
2) Logical Operators
3) Comparison Operators


# what is stored procedures

website madhe multiple pages ahe ani tya pages var same report generate kartoy tya condition apan ak code lihu shakto ani tyala multiple page var call karu shakto  <br>
ya madhe appan ak store procedures banavto ani tyala call karto


# what is aggregate function

Aggregate function performs a calculation on multiple alues and returns a single value.

and aggregate function are often used with GROUP BY & SELECT statemnet

1) COUNT() : return number of values
2) SUM() : returns sum of all values
3) AVG() : returns average value
4) MAX() : returns maximum value
5) MIN() : returns minimum value
6) ROUND() : round a number to a specified number of decimal place

# What is an ALIAS command

SQL is used to give a temprary name of table or column


**Column Alias**

            select item, amount as prod, amount as price from Orders


# What are Union commands

**Union** : Union combines the result of two or more quires into one table

he aka row madhe join karel

            select age from customers
            UNION
            select amount from orders

# How to copy tables in SQL

            create table sachin as select * from Contractors;

# What is the difference between BETWEEN and IN operators in SQL

**Between**

The BETWEEN operator is used to fetch rows based on a range of values. 

            select * from customers where age between 22 and 25


**IN**

The IN operator is used to check for values contained in specific sets

      select * from customers where age in (31,25,22)

# what is clause in sql

clause is a specific part of a SQL statement that provides additional instructions or conditions to the query

1) select
2) from
3) where
4) order by
5) JOIN Clause

# what is with clause

WITH clause, also known as Common Table Expressions (CTEs), is a powerful feature in SQL that allows you to define temporary result sets (subqueries) <br> that can be referenced within the main query.

            WITH employee_sales AS (
                SELECT employee_id, SUM(sales_amount) AS total_sales
                FROM sales
                GROUP BY employee_id
            )
            SELECT * FROM employee_sales;

# What is a Cursor

Oracle creates a memory area, know as the context area, for processing an sql statement, which contains all the information needed for <br> processing the statement for example, the number of rows processed 
a cursor is a pointer to this context area. PL/SQL controls the context area through a cursor. a cursor holds the row returned by a SQL statement. <br> the set of rows the cursor holds is referred to as  active set


# Write down various types of relationships in SQL

1) One-to-One Relationship.
2) One to Many Relationships.
3) Many to One Relationship
4) Self-Referencing Relationship


# What is a trigger

The trigger is a statement that a system executes automatically when there is any modification to the database. In a trigger, we first specify when the trigger is to be
executed and then the action to be performed when the trigger executes. Triggers are used to specify certain integrity constraints and referential constraints that cannot
be specified using the constraint mechanism of SQL.



