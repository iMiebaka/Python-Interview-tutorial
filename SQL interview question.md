
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

