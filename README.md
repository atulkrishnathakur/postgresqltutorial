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
- command: $ pg_dump -U [username] --column-inserts [database_name] > /path/dir/filename.sql

  ```
  atul@atul-Lenovo-G570:~$ pg_dump -U postgres --column-inserts fprofile_db > mydb/mydatasql.sql

  ```

# Export single table of postgresql database
- command: $ pg_dump -U [username] --table [tablename] --column-inserts [database_name] > /path/dir/filename.sql
  ```
   atul@atul-Lenovo-G570:~$ pg_dump -U postgres --table users --column-inserts fprofile_db > mydb/user.sql
  
  ```
