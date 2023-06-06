ubu8@ubu8Virt:~$ sudo mysql
[sudo] password for ubu8: 
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 13
Server version: 8.0.33-0ubuntu0.22.04.2 (Ubuntu)

Copyright (c) 2000, 2023, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> CREATE TABLE home_animals
    -> (
    ->   Id INT AUTO_INCREMENT PRIMARY KEY,
    ->     Genus_name VARCHAR (20),
    ->     Class_id INT,
    ->     FOREIGN KEY (Class_id) REFERENCES animal_classes (Id) ON DELETE CASCADE ON UPDATE CASCADE
    -> );
ERROR 1046 (3D000): No database selected
mysql> USE Human_friends;
Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A

Database changed
mysql> CREATE TABLE home_animals
    -> (
    ->   Id INT AUTO_INCREMENT PRIMARY KEY,
    ->     Genus_name VARCHAR (20),
    ->     Class_id INT,
    ->     FOREIGN KEY (Class_id) REFERENCES animal_classes (Id) ON DELETE CASCADE ON UPDATE CASCADE
    -> );
Query OK, 0 rows affected (1,15 sec)

mysql> INSERT INTO home_animals (Genus_name, Class_id)
    -> VALUES ('Кошки', 2),
    -> ('Собаки', 2),  
    -> ('Хомяки', 2); 
Query OK, 3 rows affected (0,18 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> CREATE TABLE cats 
    -> (       
    ->     Id INT AUTO_INCREMENT PRIMARY KEY, 
    ->     Name VARCHAR(20), 
    ->     Birthday DATE,
    ->     Commands VARCHAR(50),
    ->     Genus_id int,
    ->     Foreign KEY (Genus_id) REFERENCES home_animals (Id) ON DELETE CASCADE ON UPDATE CASCADE
    -> );
Query OK, 0 rows affected (0,47 sec)

mysql> INSERT INTO cats (Name, Birthday, Commands, Genus_id)
    -> VALUES ('Пупа', '2011-01-01', 'кс-кс-кс', 1),
    -> ('Олег', '2016-01-01', "отставить!", 1),  
    -> ('Тьма', '2017-01-01', "", 1);
Query OK, 3 rows affected (0,17 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> CREATE TABLE dogs 
    -> (       
    ->     Id INT AUTO_INCREMENT PRIMARY KEY, 
    ->     Name VARCHAR(20), 
    ->     Birthday DATE,
    ->     Commands VARCHAR(50),
    ->     Genus_id int,
    ->     Foreign KEY (Genus_id) REFERENCES home_animals (Id) ON DELETE CASCADE ON UPDATE CASCADE
    -> );
Query OK, 0 rows affected (0,48 sec)

mysql> INSERT INTO dogs (Name, Birthday, Commands, Genus_id)
    -> VALUES ('Дик', '2020-01-01', 'ко мне, лежать, лапу, голос', 2),
    -> ('Граф', '2021-06-12', "сидеть, лежать, лапу", 2),  
    -> ('Шарик', '2018-05-01', "сидеть, лежать, лапу, след, фас", 2), 
    -> ('Босс', '2021-05-10', "сидеть, лежать, фу, место", 2);
Query OK, 4 rows affected (0,16 sec)
Records: 4  Duplicates: 0  Warnings: 0

mysql> CREATE TABLE hamsters 
    -> (       
    ->     Id INT AUTO_INCREMENT PRIMARY KEY, 
    ->     Name VARCHAR(20), 
    ->     Birthday DATE,
    ->     Commands VARCHAR(50),
    ->     Genus_id int,
    ->     Foreign KEY (Genus_id) REFERENCES home_animals (Id) ON DELETE CASCADE ON UPDATE CASCADE
    -> );
Query OK, 0 rows affected (0,61 sec)

mysql> INSERT INTO hamsters (Name, Birthday, Commands, Genus_id)
    -> VALUES ('Малой', '2020-10-12', '', 3),
    -> ('Медведь', '2021-03-12', "атака сверху", 3),  
    -> ('Ниндзя', '2022-07-11', NULL, 3), 
    -> ('Бурый', '2022-05-10', NULL, 3);
Query OK, 4 rows affected (0,08 sec)
Records: 4  Duplicates: 0  Warnings: 0

mysql> CREATE TABLE horses 
    -> (       
    ->     Id INT AUTO_INCREMENT PRIMARY KEY, 
    ->     Name VARCHAR(20), 
    ->     Birthday DATE,
    ->     Commands VARCHAR(50),
    ->     Genus_id int,
    ->     Foreign KEY (Genus_id) REFERENCES packed_animals (Id) ON DELETE CASCADE ON UPDATE CASCADE
    -> );
ERROR 1824 (HY000): Failed to open the referenced table 'packed_animals'
mysql> CREATE TABLE horses 
    -> (       
    ->     Id INT AUTO_INCREMENT PRIMARY KEY, 
    ->     Name VARCHAR(20), 
    ->     Birthday DATE,
    ->     Commands VARCHAR(50),
    ->     Genus_id int,
    ->     Foreign KEY (Genus_id) REFERENCES packed_animals (Id) ON DELETE CASCADE ON UPDATE CASCADE
    ->  ^C 
mysql> CREATE TABLE horses 
    -> (       
    ->     Id INT AUTO_INCREMENT PRIMARY KEY, 
    ->     Name VARCHAR(20), 
    ->     Birthday DATE,
    ->     Commands VARCHAR(50),
    ->     Genus_id int,
    ->     Foreign KEY (Genus_id) REFERENCES paked_animals (Id) ON DELETE CASCADE ON UPDATE CASCADE
    -> );
Query OK, 0 rows affected (0,66 sec)

mysql> INSERT INTO horses (Name, Birthday, Commands, Genus_id)
    -> VALUES ('Гром', '2020-01-12', 'бегом, шагом', 1),
    -> ('Закат', '2017-03-12', "бегом, шагом, хоп", 1),  
    -> ('Байкал', '2016-07-12', "бегом, шагом, хоп, брр", 1), 
    -> ('Молния', '2020-11-10', "бегом, шагом, хоп", 1);
Query OK, 4 rows affected (0,15 sec)
Records: 4  Duplicates: 0  Warnings: 0

mysql> CREATE TABLE donkeys 
    -> (       
    ->     Id INT AUTO_INCREMENT PRIMARY KEY, 
    ->     Name VARCHAR(20), 
    ->     Birthday DATE,
    ->     Commands VARCHAR(50),
    ->     Genus_id int,
    ->     Foreign KEY (Genus_id) REFERENCES paked_animals (Id) ON DELETE CASCADE ON UPDATE CASCADE
    -> );
Query OK, 0 rows affected (0,52 sec)

mysql> INSERT INTO donkeys (Name, Birthday, Commands, Genus_id)
    -> VALUES ('Первый', '2019-04-10', NULL, 2),
    -> ('Второй', '2020-03-12', "", 2),  
    -> ('Третий', '2021-07-12', "", 2), 
    -> ('Четвертый', '2022-12-10', NULL, 2);
Query OK, 4 rows affected (0,38 sec)
Records: 4  Duplicates: 0  Warnings: 0

mysql> CREATE TABLE camels 
    -> (       
    ->     Id INT AUTO_INCREMENT PRIMARY KEY, 
    ->     Name VARCHAR(20), 
    ->     Birthday DATE,
    ->     Commands VARCHAR(50),
    ->     Genus_id int,
    ->     Foreign KEY (Genus_id) REFERENCES paked_animals (Id) ON DELETE CASCADE ON UPDATE CASCADE
    -> );
Query OK, 0 rows affected (0,71 sec)

mysql> INSERT INTO camels (Name, Birthday, Commands, Genus_id)
    -> VALUES ('Горбатый', '2022-04-10', 'вернись', 3),
    -> ('Самец', '2019-03-12', "остановись", 3),  
    -> ('Сифон', '2015-07-12', "повернись", 3), 
    -> ('Борода', '2022-12-10', "улыбнись", 3);
Query OK, 4 rows affected (0,07 sec)
Records: 4  Duplicates: 0  Warnings: 0

mysql> SET SQL_SAFE_UPDATES = 0;
Query OK, 0 rows affected (0,08 sec)

mysql> DELETE FROM camels;
Query OK, 4 rows affected (0,14 sec)

mysql> SELECT Name, Birthday, Commands FROM horses
    -> UNION SELECT  Name, Birthday, Commands FROM donkeys;
+--------------------+------------+----------------------------------------+
| Name               | Birthday   | Commands                               |
+--------------------+------------+----------------------------------------+
| Гром               | 2020-01-12 | бегом, шагом                           |
| Закат              | 2017-03-12 | бегом, шагом, хоп                      |
| Байкал             | 2016-07-12 | бегом, шагом, хоп, брр                 |
| Молния             | 2020-11-10 | бегом, шагом, хоп                      |
| Первый             | 2019-04-10 | NULL                                   |
| Второй             | 2020-03-12 |                                        |
| Третий             | 2021-07-12 |                                        |
| Четвертый          | 2022-12-10 | NULL                                   |
+--------------------+------------+----------------------------------------+
8 rows in set (0,24 sec)

mysql> CREATE TEMPORARY TABLE animals AS 
    -> SELECT *, 'Лошади' as genus FROM horses
    -> UNION SELECT *, 'Ослы' AS genus FROM donkeys
    -> UNION SELECT *, 'Собаки' AS genus FROM dogs
    -> UNION SELECT *, 'Кошки' AS genus FROM cats
    -> UNION SELECT *, 'Хомяки' AS genus FROM hamsters;
Query OK, 19 rows affected (0,14 sec)
Records: 19  Duplicates: 0  Warnings: 0

mysql> CREATE TABLE yang_animal AS
    -> SELECT Name, Birthday, Commands, genus, TIMESTAMPDIFF(MONTH, Birthday, CURDATE()) AS Age_in_month
    -> FROM animals WHERE Birthday BETWEEN ADDDATE(curdate(), INTERVAL -3 YEAR) AND ADDDATE(CURDATE(), INTERVAL -1 YEAR);
Query OK, 7 rows affected (0,74 sec)
Records: 7  Duplicates: 0  Warnings: 0

mysql>  
mysql> SELECT * FROM yang_animal;
+----------------+------------+----------------------------------------------+--------------+--------------+
| Name           | Birthday   | Commands                                     | genus        | Age_in_month |
+----------------+------------+----------------------------------------------+--------------+--------------+
| Молния         | 2020-11-10 | бегом, шагом, хоп                            | Лошади       |           30 |
| Третий         | 2021-07-12 |                                              | Ослы         |           22 |
| Граф           | 2021-06-12 | сидеть, лежать, лапу                         | Собаки       |           23 |
| Босс           | 2021-05-10 | сидеть, лежать, фу, место                    | Собаки       |           24 |
| Малой          | 2020-10-12 |                                              | Хомяки       |           31 |
| Медведь        | 2021-03-12 | атака сверху                                 | Хомяки       |           26 |
| Бурый          | 2022-05-10 | NULL                                         | Хомяки       |           12 |
+----------------+------------+----------------------------------------------+--------------+--------------+
7 rows in set (0,01 sec)

mysql> SELECT h.Name, h.Birthday, h.Commands, pa.Genus_name, ya.Age_in_month 
    -> FROM horses h
    -> LEFT JOIN yang_animal ya ON ya.Name = h.Name
    -> LEFT JOIN paked_animals pa ON pa.Id = h.Genus_id
    -> UNION 
    -> SELECT d.Name, d.Birthday, d.Commands, pa.Genus_name, ya.Age_in_month 
    -> FROM donkeys d 
    -> LEFT JOIN yang_animal ya ON ya.Name = d.Name
    -> LEFT JOIN paked_animals pa ON pa.Id = d.Genus_id
    -> UNION
    -> SELECT c.Name, c.Birthday, c.Commands, ha.Genus_name, ya.Age_in_month 
    -> FROM cats c
    -> LEFT JOIN yang_animal ya ON ya.Name = c.Name
    -> LEFT JOIN home_animals ha ON ha.Id = c.Genus_id
    -> UNION
    -> SELECT d.Name, d.Birthday, d.Commands, ha.Genus_name, ya.Age_in_month 
    -> FROM dogs d
    -> LEFT JOIN yang_animal ya ON ya.Name = d.Name
    -> LEFT JOIN home_animals ha ON ha.Id = d.Genus_id
    -> UNION
    -> SELECT hm.Name, hm.Birthday, hm.Commands, ha.Genus_name, ya.Age_in_month 
    -> FROM hamsters hm
    -> LEFT JOIN yang_animal ya ON ya.Name = hm.Name
    -> LEFT JOIN home_animals ha ON ha.Id = hm.Genus_id;
+--------------------+------------+--------------------------------------------------------+--------------+--------------+
| Name               | Birthday   | Commands                                               | Genus_name   | Age_in_month |
+--------------------+------------+--------------------------------------------------------+--------------+--------------+
| Гром               | 2020-01-12 | бегом, шагом                                           | Horses       |         NULL |
| Закат              | 2017-03-12 | бегом, шагом, хоп                                      | Horses       |         NULL |
| Байкал             | 2016-07-12 | бегом, шагом, хоп, брр                                 | Horses       |         NULL |
| Молния             | 2020-11-10 | бегом, шагом, хоп                                      | Horses       |           30 |
| Первый             | 2019-04-10 | NULL                                                   | Donkey       |         NULL |
| Второй             | 2020-03-12 |                                                        | Donkey       |         NULL |
| Третий             | 2021-07-12 |                                                        | Donkey       |           22 |
| Четвертый          | 2022-12-10 | NULL                                                   | Donkey       |         NULL |
| Пупа               | 2011-01-01 | кс-кс-кс                                               | Кошки        |         NULL |
| Олег               | 2016-01-01 | отставить!                                             | Кошки        |         NULL |
| Тьма               | 2017-01-01 |                                                        | Кошки        |         NULL |
| Дик                | 2020-01-01 | ко мне, лежать, лапу, голос                            | Собаки       |         NULL |
| Граф               | 2021-06-12 | сидеть, лежать, лапу                                   | Собаки       |           23 |
| Шарик              | 2018-05-01 | сидеть, лежать, лапу, след, фас                        | Собаки       |         NULL |
| Босс               | 2021-05-10 | сидеть, лежать, фу, место                              | Собаки       |           24 |
| Малой              | 2020-10-12 |                                                        | Хомяки       |           31 |
| Медведь            | 2021-03-12 | атака сверху                                           | Хомяки       |           26 |
| Ниндзя             | 2022-07-11 | NULL                                                   | Хомяки       |         NULL |
| Бурый              | 2022-05-10 | NULL                                                   | Хомяки       |           12 |
+--------------------+------------+--------------------------------------------------------+--------------+--------------+
19 rows in set (0,02 sec)

mysql> 


