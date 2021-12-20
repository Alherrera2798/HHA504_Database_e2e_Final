# HHA504_Database_e2e_Final

## **OBJECTIVE:** To use Microsoft Azure by creatung a virtual machine and using terminal to connect to database e2e, using mysql to create usersand to grant permissions to set users. Using Google Colab to connect to MS Azure virtual machine and to upload H1N1 dataset to e2e database. Using Mysql Workbench to create triggers for e2e database;

## *Following steps are*

Step 1: Setup and deploy EC2
Launch Azure Virtual Machine:
-	Use Ubuntu Gen1
-	Create username and password
-	Inbound rule for MySQL by adding port 3306 under networking
-	Review configs and Create the Virtual Machine

Step 2: Connect to Virtual Machine via Terminal
-	Open Windows Terminal and connect to VM
o	Terminal Command: ssh e2e@ 20.127.54.159
	Username and password
o	IP address on the Azure overview page for the instance.
o	Password: Appliedhealth2021!
o	Yes
-	Update UBUNTU server
o	Terminal Command: sudo apt-get update

Step 3: Installing MySQL to terminal 
o	Terminal Command: sudo apt-get mysql-client mysql-server
o	Yes
o	Enter to mysql server via terminal command
	Terminal Command: sudo mysql
o	Show any available databases 
	Terminal Commmand: sudo mysql
	MySQL Command Via Terminal: SHOW DATABASES;

Step 4: Create a MySQL User and Granting permissions
-	Creating a new user via Terminal 
o	Terminal Command: CREATE USER 'DBA' IDENTIFIED BY 'ahi2021';
-	Confirm USER via Terminal
o	Terminal Command: SELECT USER FROM mysql.user;
-	Grant permissions via terminal for user
o	Terminal Command: GRANT ALL PRIVILEGES ON *.* TO 'DBA'@'%' WITH GRANT OPTION;
-	Confirm granted permissions via terminal
o	Terminal Command: SHOW GRANTS FOR DBA;
-	Confirm user via terminal
o	Terminal Command: mysql -u DBA -p *****

Step 5: Create a new database
-	Create a database via terminal
o	Terminal Command: CREATE DATABASE e2e;
-	Confirm database via terminal
o	Terminal Command: SHOW DATABASES;

Step 6: Python that connects to your SQL instance
Open Google Colab or preferred python IDE
-	Import necessary packages using the import command
-	Install any packages using the !pip install command
-	Update SQL configs to ensure python code works. 
o	Terminal Command: sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf
-	Update blind-address to 0.0.0.0 Ctrl + O to save changes and Ctrl + X to exit config menu
-	Restart mysql 
o	Terminal Command: /etc/init.d/mysql restart 

Step 7: Create a dump (.sql) file
-	Create dump via terminal 
o	Terminal Command: sudo mysqldump e2e > backup_e2e.sql
o	Terminal Command: ls – to confirm

Step 8: Using the SCP command from your terminal, move that file to your own local computer:
Launch AZURE to create a replica instance
IP Address for replica: 13.82.195.157
In current terminal (Primary e2e) use scp terminal command
-	Terminal Command: scp backup_e2e.sql replica@52.179.23.94:/home/replica

Step 9: Create a trigger
-	Refer to the sql file HHA_504_Trigger_final.sql
