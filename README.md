### Install SQL Server Database Engine

Go here to instal SQL Server Database Engine and Management studio: https://www.microsoft.com/en-gb/sql-server/sql-server-downloads

### Why use cloud based system:

- You don't have to install and patch your server - saves you time as cloud based system do this.
- Automated backup/ snapshots placed online so can roll back you system
- They are available so you can always online
- Can monitor your system using online tools

### Creating a database on RDS: 
1. Login into your aws management console and search RDS
2. Click create database and chose standard create (to ensure that you dont have to pay, you can click on easy create and amend database settings once it has set up)

<img width="568" alt="image" src="https://github.com/MutiatOba/aws_rds/assets/118978642/995ca911-3bfd-43be-8e7d-172fa622e6b7">

3. Engine option

<img width="574" alt="image" src="https://github.com/MutiatOba/aws_rds/assets/118978642/5ded90ea-2074-4970-ba2c-69b9f51f8066">

<img width="454" alt="image" src="https://github.com/MutiatOba/aws_rds/assets/118978642/295a6991-0873-4820-bb5f-092b00656e6f">

4. select default engine option 
5. insert the database information

<img width="473" alt="image" src="https://github.com/MutiatOba/aws_rds/assets/118978642/2e83ebce-4a1f-4fc7-8a4e-b77cc2ed5bd7">

6. instance configuration

<img width="462" alt="image" src="https://github.com/MutiatOba/aws_rds/assets/118978642/893ffed6-1372-4bab-bac3-f558a3d65569">

7. allocate storage

<img width="464" alt="image" src="https://github.com/MutiatOba/aws_rds/assets/118978642/077def97-dfb5-497c-a26c-df68f7758985">

8. connectivity - keep everything as default save for channging public access to Yes.
9. Turn off monitoring and monthly backup

If you do set up as easy create, then make sure you do the following to amend your database:

<img width="570" alt="image" src="https://github.com/MutiatOba/aws_rds/assets/118978642/2c8c2924-f42a-40aa-b5c5-ab873a7095ad">

### Connect to RDS with SQL Management studio

1. click on your RDS database indentifier and then copy endpoint under connectivity section

<img width="711" alt="image" src="https://github.com/MutiatOba/aws_rds/assets/118978642/15e1fc4b-7184-4130-97e7-5af3810b4968">

2. go to your server management studio, click on connect, database engine, paste in your server then click on connect

<img width="544" alt="image" src="https://github.com/MutiatOba/aws_rds/assets/118978642/f709933d-a283-420b-aeac-14fec7eed558">

[if it does not connect, check the VPC security group allows traffic from port 1433 from 0.0.0.0/0]


### Creating an SQL server databse on RDS using CLI

1. make sure aws cli is installed
2. Go to GitBash and login as a user using your secret key and access key
3. type the following into your GitBash: ```aws rds create-db-instance --db-instance-identifier "mutidb" --db-instance-class "db.t3.small" --engine "sqlserver-ex" --master-username "admin" --master-user-password "Hello1234Hello" --publicly-accessible --port 1433 --allocated-storage 20```
4. 

