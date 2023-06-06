ubu8@ubu8Virt:~$ sudo mysql
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 9
Server version: 8.0.33-0ubuntu0.22.04.2 (Ubuntu)

Copyright (c) 2000, 2023, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> CREATE DATABASE Human_friends;
Query OK, 1 row affected (3,73 sec)

mysql> USE Human_friends;
Database changed
mysql> CREATE TABLE animal_classes (Id INT AUTO_INCREMENT PRIMARY KEY, Class_name VARCHAR(20));
Query OK, 0 rows affected (0,82 sec)

mysql> INSERT INTO animal_classes (Class_name) VALUES ('pack'),('pets');
Query OK, 2 rows affected (0,36 sec)
Records: 2  Duplicates: 0  Warnings: 0

mysql> CREATE TABLE paked_animals (Id INT AUTO_INCREMENT PRIMARY KEY, Genus_name VARCHAR(20), Class_id INT, FOREIGN KEY (Class_id) REFERENCES animal_classes (Id) ON DELETE CASCADE ON UPDATE CASCADE);
Query OK, 0 rows affected (0,74 sec)

mysql> INSERT INTO packed_animals (Genus_name, Class_id) VALUES ('Horses',1),('Donkey',1),('Camels',1);
ERROR 1146 (42S02): Table 'Human_friends.packed_animals' doesn't exist
mysql> INSERT INTO paked_animals (Genus_name,Class_id) VALUES ('Horses',1),('Donkey',1),('Camels',1);
Query OK, 3 rows affected (0,05 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> CREATE TABLE home_animals (Id INT AUTO)INCREMENT PRIMARY KEY, Genus_name VARCHAR(20), Class_id INT, FOREIGN KEY (Class_id) REFERENCES animal_classes(Id) ON DELETE CASCADE ON UPDATE CASCADE);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'AUTO)INCREMENT PRIMARY KEY, Genus_name VARCHAR(20), Class_id INT, FOREIGN KEY (C' at line 1
mysql> CREATE TABLE home_animals (Id INT AUTO_INCREMENT PRIMARY KEY, Genus_name VARCHAR(20), Class_id INT, FOREIGN KEY (Class_id) ON DELETE CASCADE ON UPDATE CASCADE);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'ON DELETE CASCADE ON UPDATE CASCADE)' at line 1
mysql> 2~^X
[1]+  Stopped                 sudo mysql
ubu8@ubu8Virt:~$ sudo mysql
[sudo] password for ubu8:
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 10
Server version: 8.0.33-0ubuntu0.22.04.2 (Ubuntu)

Copyright (c) 2000, 2023, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql>