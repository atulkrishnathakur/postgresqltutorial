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

# Export database from pgadmin4
- Launch the pgAdmin4
- Connect your PostgreSQL server
- Expand the server to locate the database that you want to export
- Right click on the database name
- Click on Backup
- Select General tab
  - Filename: Enter file path like /home/atul/myaws/fastapi_test_aws/fprofile2.sql
  - Format: plan
  - Click on Backup button
