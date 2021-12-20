# HHA504_Database_e2e_Final

## **OBJECTIVE:** To use Microsoft Azure by creatung a virtual machine and using terminal to connect to database e2e, using mysql to create usersand to grant permissions to set users. Using Google Colab to connect to MS Azure virtual machine and to upload H1N1 dataset to e2e database. Using Mysql Workbench to create triggers for e2e database;

## *Following steps are*

## Step 1: Setup and deploy EC2:
### Launch Azure Virtual Machine:
#### - Use Ubuntu Gen1
#### - Create username and password
#### - Inbound rule for MySQL by adding port 3306 under networking
#### - Review configs and Create the Virtual Machine

## Step 2: Connect to Virtual Machine via Terminal:
### Open Windows Terminal and connect to VM
#### o	Terminal Command: ssh e2e@ 20.127.54.159
####  - Username and password
#### o	IP address on the Azure overview page for the instance.
#### -	Update UBUNTU server
#### o	Terminal Command: sudo apt-get update

