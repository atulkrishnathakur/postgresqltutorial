## Connect pgadmin4 with postgresql for localhost
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
   
## Connect pgadmin4 with postgresql for AWS RDS
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

## Export full postgresql database
- use the pg_dump command
- command: $ pg_dump -h [hostname/endpoint] -p [port] -U [username] --column-inserts [database_name] > /path/dir/filename.sql

  ```
  atul@atul-Lenovo-G570:~$ pg_dump -h localhost -p 5432 -U postgres --column-inserts fprofile_db > mydb/mydatasql.sql

  ```
## Export only data of postgressql database

```
atul@atul-Lenovo-G570:~$ pg_dump -h localhost -p 5432 -U postgres --data-only --column-inserts fprofile_db > mydb/mydatasql1.sql

```

## Export single table of postgresql database
- command: $ pg_dump -h [hostname/endpoint] -p [port] -U [username] --table [tablename] --column-inserts [database_name] > /path/dir/filename.sql
  ```
   atul@atul-Lenovo-G570:~$ pg_dump -h localhost -p 5432 -U postgres --table users --column-inserts fprofile_db > mydb/user.sql
  
  ```
## Export only data of single table of postgresql database

  ```
   atul@atul-Lenovo-G570:~$ pg_dump -h localhost -p 5432 -U postgres --table users --data-only --column-inserts fprofile_db > mydb/users1.sql

  ```
## Import database

command: $ psql -h [hostname/endpoint] -p [port]  -U [username] [databasename] -f /path/dir/filename.sql

```
atul@atul-Lenovo-G570:~$ psql -h localhost -p 5432  -U postgres fprofile_test1 -f mydb/mydatasql.sql

```
## Schema in database
reference: https://neon.tech/postgresql/postgresql-administration/postgresql-schema
1. In PostgreSQL, a schema is a named collection of database objects, including tables, views, indexes, data types, functions, stored procedures, and operators.
2. A database may contain one or more schemas. However, a schema belongs to only one database. Additionally, two schemas can have different objects that share the same name. For example, you may have sales schema that has staff table and the public schema which also has the staff table.
3. PostgreSQL automatically creates a schema called public for every new database.

## How to export postgresql database from pgadmin-4
Reference: https://www.pgadmin.org/docs/pgadmin4/8.13/backup_dialog.html
- open your pgadmin-4
- Right click on database
- Click on Backup
  - General:
    - File: enter file path like `/home/atul/mydb/mydb.sql`
    - Format: choose plan
    - Encoding: UTF-8
    - Role Name: postgres
  - Objects: From this tab you can export some specific tables
- Click on Backup button

## How to import postgresql database from directory in pgadmin-4
- open pgdadmin-4
- Right click on Databases in Server and create your database
- Right click on created database
- Click on Restore
- General:
  - Format: Directory
  - File name: choose here directory where database tables save example "/home/atul/mydb
  - Role name: postgres
  - Click on Restore button
- Right click on created database and refresh it

## How to check sequences of postgresql in pgadmin-4
- open pgadmin-4
- open database
- open schemas 
  - open public schema
  - Open Sequences

1. when you isert and you found an error then how to solve it.
   ```
   ERROR: Key (id)=(1) already exists.duplicate key value violates unique constraint "test_pkey"
   ```
2. open sequences
3. right click on `test_id_seq`
4. click on properties
5. go to Definition tab
   - Current Value: set here max value and click on save. Example if test table id field max value is 5 then here set 5 in current Value.


## How to truncate table and restart sequence
```
TRUNCATE TABLE table_name RESTART IDENTITY;
```
## How to check postgresql is active or not
```
atul@atul-Lenovo-G570:~$ sudo systemctl status postgresql

```
## How to stop postgresql
- If system reboot then postgresql will be again active
```
atul@atul-Lenovo-G570:~$ sudo systemctl stop postgresql

```
## How to disable postgresql
- Postgresql permanently stoped. If you reboot system then postgresql can not active again
```
atul@atul-Lenovo-G570:~$ sudo systemctl disable postgresql

```

## How to uninstall pgadmin4
```
atul@atul-Lenovo-G570:~$ sudo apt remove --purge pgadmin4

```

```
atul@atul-Lenovo-G570:~$ sudo apt autoremove

```

## How to enable postgresql if disabled
1. check status first
```
atul@atul-Lenovo-G570:~$ systemctl status postgresql
```

2. enable the postgresql
   ```
   atul@atul-Lenovo-G570:~$ sudo systemctl enable postgresql
   ```
3. start the postgresql
   ```
   atul@atul-Lenovo-G570:~$ sudo systemctl start postgresql

   ```
4. check the status again


## login in postgressql by command line
1. Run the command
```
atul@atul-Lenovo-G570:~$ psql -U postgres

```
2. see database list
   ```
   postgres=# \l
   ```
## how to go into database
1. command `\c <database name>`
```
postgres=# \c softbookdb
```
2. see database tables
```
softbookdb=# \dt
```
3. see database table of specific schema. command `\dt public.*`
```
softbookdb=# \dt public.*
```

## how to quite or logout from postgresql database
```
softbookdb=# \q

```
