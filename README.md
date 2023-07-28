# mysqlcommands
Microsoft Windows [Version 10.0.22621.1992]
(c) Microsoft Corporation. All rights reserved.

C:\Users\lagad>cd\
C:\>cd xampp
C:\xampp>cd mysql
C:\xampp\mysql>cd bin
C:\xampp\mysql\bin>mysql.exe -u root

Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 8
Server version: 10.4.28-MariaDB mariadb.org binary distribution
Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.
Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| phpmyadmin         |
| test               |
+--------------------+
5 rows in set (0.001 sec)

MariaDB [(none)]> create database info;
Query OK, 1 row affected (0.001 sec)

MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| info               |
| information_schema |
| mysql              |
| performance_schema |
| phpmyadmin         |
| test               |
+--------------------+
6 rows in set (0.001 sec)

MariaDB [(none)]> use info
Database changed

MariaDB [info]> create table data(name varchar(10),rollnumber integer(6));
Query OK, 0 rows affected (0.022 sec)
MariaDB [info]> desc info;
ERROR 1146 (42S02): Table 'info.info' doesn't exist
MariaDB [info]> desc data;
+------------+-------------+------+-----+---------+-------+
| Field      | Type        | Null | Key | Default | Extra |
+------------+-------------+------+-----+---------+-------+
| name       | varchar(10) | YES  |     | NULL    |       |
| rollnumber | int(6)      | YES  |     | NULL    |       |
+------------+-------------+------+-----+---------+-------+
2 rows in set (0.004 sec)

MariaDB [info]> alter table data add(phn integer(10),address varchar(10));
Query OK, 0 rows affected (0.012 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [info]> desc data;
+------------+-------------+------+-----+---------+-------+
| Field      | Type        | Null | Key | Default | Extra |
+------------+-------------+------+-----+---------+-------+
| name       | varchar(10) | YES  |     | NULL    |       |
| rollnumber | int(6)      | YES  |     | NULL    |       |
| phn        | int(10)     | YES  |     | NULL    |       |
| address    | varchar(10) | YES  |     | NULL    |       |
+------------+-------------+------+-----+---------+-------+
4 rows in set (0.005 sec)

MariaDB [info]> alter table data modify address varchar(15);
Query OK, 0 rows affected (0.013 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [info]> desc data;
+------------+-------------+------+-----+---------+-------+
| Field      | Type        | Null | Key | Default | Extra |
+------------+-------------+------+-----+---------+-------+
| name       | varchar(10) | YES  |     | NULL    |       |
| rollnumber | int(6)      | YES  |     | NULL    |       |
| phn        | int(10)     | YES  |     | NULL    |       |
| address    | varchar(15) | YES  |     | NULL    |       |
+------------+-------------+------+-----+---------+-------+
4 rows in set (0.003 sec)

MariaDB [info]> alter table data drop column phn;
Query OK, 0 rows affected (0.016 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [info]> desc data;
+------------+-------------+------+-----+---------+-------+
| Field      | Type        | Null | Key | Default | Extra |
+------------+-------------+------+-----+---------+-------+
| name       | varchar(10) | YES  |     | NULL    |       |
| rollnumber | int(6)      | YES  |     | NULL    |       |
| address    | varchar(15) | YES  |     | NULL    |       |
+------------+-------------+------+-----+---------+-------+
3 rows in set (0.005 sec)

MariaDB [info]> alter table data change column rollnumber roll int(8);
Query OK, 0 rows affected (0.013 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [info]> desc data;
+---------+-------------+------+-----+---------+-------+
| Field   | Type        | Null | Key | Default | Extra |
+---------+-------------+------+-----+---------+-------+
| name    | varchar(10) | YES  |     | NULL    |       |
| roll    | int(8)      | YES  |     | NULL    |       |
| address | varchar(15) | YES  |     | NULL    |       |
+---------+-------------+------+-----+---------+-------+
3 rows in set (0.003 sec)

MariaDB [info]> alter table data rename to bio;
Query OK, 0 rows affected (0.017 sec)

MariaDB [info]> desc bio;
+---------+-------------+------+-----+---------+-------+
| Field   | Type        | Null | Key | Default | Extra |
+---------+-------------+------+-----+---------+-------+
| name    | varchar(10) | YES  |     | NULL    |       |
| roll    | int(8)      | YES  |     | NULL    |       |
| address | varchar(15) | YES  |     | NULL    |       |
+---------+-------------+------+-----+---------+-------+
3 rows in set (0.005 sec)

MariaDB [info]> create table mega(name varchar(10));
Query OK, 0 rows affected (0.021 sec)

MariaDB [info]> desc mega;
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| name  | varchar(10) | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
1 row in set (0.003 sec)

MariaDB [info]> drop table mega;
Query OK, 0 rows affected (0.014 sec)

MariaDB [info]> desc mega;
ERROR 1146 (42S02): Table 'info.mega' doesn't exist

MariaDB [info]> desc bio;
+---------+-------------+------+-----+---------+-------+
| Field   | Type        | Null | Key | Default | Extra |
+---------+-------------+------+-----+---------+-------+
| name    | varchar(10) | YES  |     | NULL    |       |
| roll    | int(8)      | YES  |     | NULL    |       |
| address | varchar(15) | YES  |     | NULL    |       |
+---------+-------------+------+-----+---------+-------+
3 rows in set (0.004 sec)

MariaDB [info]> show databases;
+--------------------+
| Database           |
+--------------------+
| info               |
| information_schema |
| mysql              |
| performance_schema |
| phpmyadmin         |
| test               |
+--------------------+
6 rows in set (0.001 sec)

MariaDB [info]> drop database test;
Query OK, 0 rows affected (0.002 sec)

MariaDB [info]> show databases;
+--------------------+
| Database           |
+--------------------+
| info               |
| information_schema |
| mysql              |
| performance_schema |
| phpmyadmin         |
+--------------------+
5 rows in set (0.001 sec)

MariaDB [info]> use database mysql;
ERROR 1049 (42000): Unknown database 'database'
MariaDB [info]> use mysql;
Database changed
MariaDB [mysql]> desc info;
ERROR 1146 (42S02): Table 'mysql.info' doesn't exist
MariaDB [mysql]> use info;
Database changed
MariaDB [info]> desc bio;
+---------+-------------+------+-----+---------+-------+
| Field   | Type        | Null | Key | Default | Extra |
+---------+-------------+------+-----+---------+-------+
| name    | varchar(10) | YES  |     | NULL    |       |
| roll    | int(8)      | YES  |     | NULL    |       |
| address | varchar(15) | YES  |     | NULL    |       |
+---------+-------------+------+-----+---------+-------+
3 rows in set (0.004 sec)
