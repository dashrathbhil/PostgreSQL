## Commands for SQL

>   This Query used in PostgreSQL to list the names of all databases currently available on the server.

```bash
 SELECT datname FROM pg_database; 
 ```

# CREATE DATABASE

``` bash 
CREATE DATABASE DATABASENAME; 
```
# CONNECT TO DATABASE

1. IN terminal 
```bash
 \c DATABASENAME; 
 ```

# DELET DATABASE 

* first disconnect database
``` bash
 DROP DATABASE DATABASENAME; 
 ```
# Some Important Queries in starting
```bash
\l         - list all databases

\q         - quit

\c db_name - connect to database

\dt        - list all tables

\d tb_name - desc a table

\d+ tb_name- list all column

\! cls.    - list all column
```

# CREATE TABLE

```bash
 CREATE TABlE person (
id INT,
name VARCHAR(225),
city VARCHAR(225)
); 
``` 

> check if the table with name <bold> person</bold> created or not?
```bash
\d person
``` 

# INSERTING DATA IN TABLE 
- **INSERT QUERY** - 
```bash 
INSERT INTO person(id,name,city )
VALUES (101,'dashrath','ahmedabad' );
```
- **INSERT Multiple data**-
```bash
INSERT INTO person(id,name,city)
VALUES (102,'raju','surat'),(103,'jay','jamanagar')
```
- **INSERT Without field** -
``` bash 
INSERT INTO person
VALUES (104,'alex','ahmedabad');
```
- **READING DATA FROM TABLE -** 
``` bash
SELECT * FROM person;
SELECT <column_name> from person;
SELECT name from person;
SELECT city from person;
SELECT name,city from person;

```
- **MODIFY/UPDATING DATA FROM TABLE -**
1. 
``` bash
UPDATE person
SET city = 'banglore'
WHERE name = 'raju';
```
2. 
``` bash
UPDATE person
SET city = 'banglore'
WHERE id = '102';
```
-**DELET DATA FROM TABLE -**
```bash
DELETE FROM person
WHERE name = 'alex';
```
```bash
DELETE FROM person
WHERE id = 102;
```

-**HOW TO AVOID NULL OR DUBLICATE ID IN  TABLE -**

# CONSTRAINE 

> A constraint in PostgreSQL is a rule applied to column.

## PRIMARY KEY 
- The PRIMARY KEY constraint uniquely identifies each record in a table
- primary keys must contain UNIQUE values,and cannot contain NULL values.
- A table have only ONE primary key

# NOT NULL
```bash
CREATE TABLE customers
(
    id INT NOT NULL,
    name VARCHAR(100)NOT NULL
);
```
# PRIMARY KEY & DEFAULT VALUE
```bash
CREATE TABLE customers
(
    acc_no INT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    acc_type VARCHAR(50) NOT NULL DEFAULT 'savings'
);
```
# AUTO_INCREAMENT
```bash
CREATE TABLE employees(
    id SERIAL PRIMARY KEY,
    firstname VARCHAR(50),
    lastname VARCHAR(50)
);
```
# TASK-1
>create a employees table with unique id , fname,lname,email(uniqe), department,salary(default 30000),
hire_date.
- ans.
``` bash
CREATE TABLE employees(
    emp_id SERIAL PRIMARY KEY,
    fname VARCHAR(100) NOT NULL,
    lname VARHCAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE,
    dept VARCHAR(50),
    salary DECIMAL(10,2) DEFAULT 30000.00,
    hire_date DATE NOT NULL DEFAULT CURRENT_DATE 
);
```
# DATA FILL
```bash

INSERT INTO staff (emp_id, fname, lname, email, dept, salary, hire_date) 
VALUES
(1, 'Raj', 'Sharma', 'raj.sharma@example.com', 'IT', 50000.00, '2020-01-15'),
(2, 'Priya', 'Singh', 'priya.singh@example.com', 'HR', 45000.00, '2019-03-22'),
(3, 'Arjun', 'Verma', 'arjun.verma@example.com', 'IT', 55000.00, '2021-06-01'),
(4, 'Suman', 'Patel', 'suman.patel@example.com', 'Finance', 60000.00, '2018-07-30'),
(5, 'Kavita', 'Rao', 'kavita.rao@example.com', 'HR', 47000.00, '2020-11-10'),
(6, 'Amit', 'Gupta', 'amit.gupta@example.com', 'Marketing', 52000.00, '2020-09-25'),
(7, 'Neha', 'Desai', 'neha.desai@example.com', 'IT', 48000.00, '2019-05-18'),
(8, 'Rahul', 'Kumar', 'rahul.kumar@example.com', 'IT', 53000.00, '2021-02-14'),
(9, 'Anjali', 'Mehta', 'anjali.mehta@example.com', 'Finance', 61000.00, '2018-12-03'),
(10, 'Vijay', 'Nair', 'vijay.nair@example.com', 'Marketing', 50000.00, '2020-04-19');

```
- so if u add new emplooyes like this 
```bash
INSERT INTO staff ( fname, lname, email, dept) 
VALUES
( 'Vijay', 'Nair', 'vijay.naeeir@example.com', 'Marketing');

```
- it will generate error bcz we dont set  value its try to start from 1 which already user define so for this we have to set  value with this query
``` bash
 SELECT setval('employees_emp_id_seq',10);
 
```

## Section-4
# DATA REFINING
### Clauses
- Where
- Distinct
- Order By
- Limit
- Like  

```bash
 SELECT  * from staff  where emp_id=5
```
```bash
 SELECT  * from staff  where dept='HR'
```
``` bash
SELECT * from staff WHERE salary >= 50000;
```
```bash
 SELECT  * from staff  where dept='HR' or dept='IT';
 ```
 