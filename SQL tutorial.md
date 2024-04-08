
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

  
