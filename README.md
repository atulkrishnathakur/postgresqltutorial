# Connect pgadmin4 with postgresql for localhost
- install pgadmin4
- Right click on Severs
- Click on Register
- Click on Server
- General Tab
  - name: server1
- Connection Tab
  - Host name/address: localhost
  - Port: 5432
  - Maintenance Database: postgres
  - Username: postgres
  - Password: ******
  - Click on Save button
- Click on Server1
  - to show all localhost database
- Right click on server1
  - Click on Create
  - Click on Database (note: you can create database)
   
# Connect pgadmin4 with postgresql for AWS RDS
- Right click on Severs
- Click on Register
- Click on Server
- General Tab
  - name: postgrerds
- Connection Tab
  - Host name/address: type endpoint like tefdafdastpfdadfdadfaostfdafdaresfdadfaql.ctk6csmmwzzi.us-east-1.rds.amazonaws.com
  - Port: 5432
  - Maintenance Database: postgres
  - Username: postgres
  - Password: ******
  - Click on Save button
- Click on postgrerds
  - to show all rds database
- Right click on postgrerds
  - Click on Create
  - Click on Database (note: you can create database)

# Export full postgresql database
- use the pg_dump command
- command: $ pg_dump -h [hostname/endpoint] -p [port] -U [username] --column-inserts [database_name] > /path/dir/filename.sql

  ```
  atul@atul-Lenovo-G570:~$ pg_dump -h localhost -p 5432 -U postgres --column-inserts fprofile_db > mydb/mydatasql.sql

  ```
# Export only data of postgressql database

```
atul@atul-Lenovo-G570:~$ pg_dump -h localhost -p 5432 -U postgres --data-only --column-inserts fprofile_db > mydb/mydatasql1.sql

```

# Export single table of postgresql database
- command: $ pg_dump -h [hostname/endpoint] -p [port] -U [username] --table [tablename] --column-inserts [database_name] > /path/dir/filename.sql
  ```
   atul@atul-Lenovo-G570:~$ pg_dump -h localhost -p 5432 -U postgres --table users --column-inserts fprofile_db > mydb/user.sql
  
  ```
# Export only data of single table of postgresql database

  ```
   atul@atul-Lenovo-G570:~$ pg_dump -h localhost -p 5432 -U postgres --table users --data-only --column-inserts fprofile_db > mydb/users1.sql

  ```
# Import database

command: $ psql -h [hostname/endpoint] -p [port]  -U [username] [databasename] -f /path/dir/filename.sql

```
atul@atul-Lenovo-G570:~$ psql -h localhost -p 5432  -U postgres fprofile_test1 -f mydb/mydatasql.sql

```
# Schema in database
reference: https://neon.tech/postgresql/postgresql-administration/postgresql-schema
1. In PostgreSQL, a schema is a named collection of database objects, including tables, views, indexes, data types, functions, stored procedures, and operators.
2. A database may contain one or more schemas. However, a schema belongs to only one database. Additionally, two schemas can have different objects that share the same name. For example, you may have sales schema that has staff table and the public schema which also has the staff table.

