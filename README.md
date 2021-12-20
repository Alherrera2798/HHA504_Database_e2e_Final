# HHA504_Database_e2e_Final

## **OBJECTIVE:** To use Microsoft Azure by creatung a virtual machine and using terminal to connect to database e2e, using mysql to create usersand to grant permissions to set users. Using Google Colab to connect to MS Azure virtual machine and to upload H1N1 dataset to e2e database. Using Mysql Workbench to create triggers for e2e database;

## *Following steps are*

## Step 1: Setup and deploy EC2:
### Launch Azure Virtual Machine:
#### - Use Ubuntu Gen1
#### - Create username and password
#### - Add Inbound rule for MySQL by adding port 3306 under networking
#### - Review configs and Create the Virtual Machine

## Step 2: Connect to Virtual Machine via Terminal:
### Open Windows Terminal and connect to VM
#### o	Terminal Command: ssh e2e@ 20.127.54.159
####    - Username and password
#### o	IP address on the Azure overview page for the instance.
####  -	Update UBUNTU server
#### o	Terminal Command: sudo apt-get update

## Step 3: Installing MySQL to terminal 
#### o	Terminal Command: sudo apt-get mysql-client mysql-server
#### o	Enter to mysql server via terminal command
####  - Terminal Command: sudo mysql
#### o	Show any available databases 
####  - Terminal Commmand: sudo mysql
####  - MySQL Command Via Terminal: SHOW DATABASES;

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

