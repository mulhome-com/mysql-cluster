# mysql-cluster
Build the mysql cluster which including master and slave server.

* About MySQL Replication
MySQL replication is a process that allows data to be copied/replicated from one server to the other at the same time. It is mainly done to increase the availability of data. One of the main reasons that people go for MySQL master-slave replication is for data recovery. In the case of any catastrophe or a hardware failure, MySQL replication ensures that an accurate backup exists all the time.

* About Current MySQL Cluster
This current MySQL Cluster comes from the master-slave replication, which can privide more mysql connection.

* About Prerequisites
- 2 Hosts(Personal Computer or Server) or VM(Virtual Machine)
- Linux OS running on those Hosts (master and slave), and these hosts can be login with ssh rsa key.
- MySQL Server running on those Hosts (master and slave), and these mysql servers are the same version.
- Working Internet, (eg: Master Host IP: 10.11.12.13, Slave Host IP: 10.11.12.14)

* About Process
- Configure the master server
-- Update the configure file of mysqld
-- Insert the slave user in the mysql database

- Data replication
-- Export the latest data from master sever
-- Import the current data file to slave one

- Configure the slave server
-- Update the configure file for mysql
-- Change the master information of slave server

* Example

build-sh -m 10.11.12.13 -s 10.11.12.14 -S mysql -c /etc/mysql/mysql.conf.d/mysqld.cnf -p masterrootpassword -P slaverootpassword

In the master

# create database test;

In the slave

# show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
| test               |
+--------------------+
6 rows in set (0.01 sec)
