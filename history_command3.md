ubu8@ubu8Virt:~$ ubu8@ubu8Virt:~$ sudo apt-get install mysql-workbench-community libmysqlclient18
E: Could not get lock /var/lib/dpkg/lock-frontend. It is held by process 4315 (unattended-upgr)
N: Be aware that removing the lock file is not a solution and may break your system.
E: Unable to acquire the dpkg frontend lock (/var/lib/dpkg/lock-frontend), is another process using it?
ubu8@ubu8Virt:~$
==============
oops
mysql was installed earlier with :

sudo apt install mysql-server-8.0

as it was recommended by Acopyan at the seminar
================
ubu8@ubu8Virt:~$ sudo mysql
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 8
Server version: 8.0.33-0ubuntu0.22.04.2 (Ubuntu)

Copyright (c) 2000, 2023, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql>