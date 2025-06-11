## Commands for SQL

>   This Query used in PostgreSQL to list the names of all databases currently available on the server.

``` SELECT datname FROM pg_database; ```

# CREATE DATABASE

``` CREATE DATABASE DATABASENAME; ```
# CONNECT TO DATABASE

1. IN terminal ``` \c DATABASENAME; ```

# DELET DATABASE 

* first disconnect database
``` DROP DATABASE DATABASENAME; ```

# CREATE TABLE

<pre> ``` CREATE TABlE person (
id INT,
name VARCHAR(225),
city VARCHAR(225)
); ``` </pre>

> check if the table with name <bold> person</bold> created or not?
<pre>```\d person``` </pre>

# INSERTING DATA IN TABLE 
- **INSERT QUERY** - 
<pre>``` 
INSERT INTO person(id,name,city )
VALUES (101,'dashrath','ahmedabad' );
```</pre>