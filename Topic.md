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