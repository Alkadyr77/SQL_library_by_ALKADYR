# Д/З
1) Создать базу данных library
2) Создать таблицу books
3) Добавить как минимум 3 записи
4) выполнить:
   4.1) select
   4.2) update
   4.3) delete

# 1) Создать базу данных library
mysql> CREATE DATABASE `library`;
Query OK, 1 row affected (0.003 sec)

mysql> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| courses            |
| information_schema |
| library            |
| mysql              |
| performance_schema |
| school             |
| sys                |
+--------------------+
7 rows in set (0.001 sec)

# 2) Создать таблицу books
mysql> CREATE TABLE books ( 
    id INT PRIMARY KEY, 
    name_of_book VARCHAR(100), 
    count_pages INT, 
    year_of_book INT 
    );
Query OK, 0 rows affected (0.007 sec)

# 3) Добавить как минимум 3 записи
mysql> INSERT INTO books VALUE (1, 'Learn PYTHON easy', 200, 1999);
Query OK, 1 row affected (0.003 sec)

mysql> INSERT INTO books VALUE (2, 'Brother 2', 510, 2015);
Query OK, 1 row affected (0.001 sec)

mysql> INSERT INTO books VALUE (3, 'Brain', 237, 2024);
Query OK, 1 row affected (0.001 sec)

# 4.1 select
mysql> SELECT * FROM books;
+----+-------------------+-------------+--------------+
| id | name_of_book      | count_pages | year_of_book |
+----+-------------------+-------------+--------------+
|  1 | Learn PYTHON easy |         200 |         1999 |
|  2 | Brother 2         |         510 |         2015 |
|  3 | Brain             |         237 |         2024 |
+----+-------------------+-------------+--------------+
3 rows in set (0.000 sec)

#   4.2) update 
mysql> UPDATE books SET count_pages = 300 WHERE id=1;
Query OK, 1 row affected (0.001 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> SELECT * FROM books;
+----+-------------------+-------------+--------------+
| id | name_of_book      | count_pages | year_of_book |
+----+-------------------+-------------+--------------+
|  1 | Learn PYTHON easy |         300 |         1999 |
|  2 | Brother 2         |         510 |         2015 |
|  3 | Brain             |         237 |         2024 |
+----+-------------------+-------------+--------------+
3 rows in set (0.000 sec)

#   4.3) delete
mysql> DELETE FROM books WHERE id=2;
Query OK, 1 row affected (0.001 sec)

mysql> SELECT * FROM books;
+----+-------------------+-------------+--------------+
| id | name_of_book      | count_pages | year_of_book |
+----+-------------------+-------------+--------------+
|  1 | Learn PYTHON easy |         300 |         1999 |
|  3 | Brain             |         237 |         2024 |
+----+-------------------+-------------+--------------+
2 rows in set (0.000 sec)