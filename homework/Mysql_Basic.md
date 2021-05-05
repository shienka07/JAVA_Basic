# 과제

0. database 이름 : testDB
1. pokemon 테이블 만들기 
   항목 : 번호(no),  이름(name), 레벨(level), 등록일자(regdate, 기본값:현재시간)
2. 최소 5개 레코드 추가
3. 모두 조회



```mysql
MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| test               |
+--------------------+
4 rows in set (0.001 sec)

MariaDB [(none)]> CREATE DATABASE testDB; -- 0번문제
Query OK, 1 row affected (0.679 sec)

MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| test               |
| testdb             |
+--------------------+
5 rows in set (0.001 sec)

MariaDB [(none)]> use testdb;
Database changed
MariaDB [testdb]> CREATE TABLE pokemon( -- 1번문제
    -> no INT AUTO_INCREMENT PRIMARY KEY,
    -> name VARCHAR(40),
    -> `level` INT,
    -> regdate DATETIME DEFAULT CURRENT_TIMESTAMP
    -> );
Query OK, 0 rows affected (0.351 sec)

MariaDB [testdb]> desc pokemon;
+---------+-------------+------+-----+---------------------+----------------+
| Field   | Type        | Null | Key | Default             | Extra          |
+---------+-------------+------+-----+---------------------+----------------+
| no      | int(11)     | NO   | PRI | NULL                | auto_increment |
| name    | varchar(40) | YES  |     | NULL                |                |
| level   | int(11)     | YES  |     | NULL                |                |
| regdate | datetime    | YES  |     | current_timestamp() |                |
+---------+-------------+------+-----+---------------------+----------------+
4 rows in set (0.025 sec)

MariaDB [testdb]> INSERT INTO pokemon -- 2번문제
    -> VALUES (null, '피카츄', 30, DEFAULT);
Query OK, 1 row affected (0.328 sec)

MariaDB [testdb]> INSERT INTO pokemon
    -> VALUES (null, '님피아', 40, DEFAULT);
Query OK, 1 row affected (0.001 sec)

MariaDB [testdb]> INSERT INTO pokemon
    -> VALUES (null, '따라큐', 38, DEFAULT);
Query OK, 1 row affected (0.325 sec)

MariaDB [testdb]> INSERT INTO pokemon
    -> VALUES (null, '메타몽', 29, DEFAULT);
Query OK, 1 row affected (0.001 sec)

MariaDB [testdb]> INSERT INTO pokemon
    -> VALUES (null, '갸라도스', 50, DEFAULT);
Query OK, 1 row affected (0.001 sec)

MariaDB [testdb]> select * from pokemon; -- 3번문제
+----+----------+-------+---------------------+
| no | name     | level | regdate             |
+----+----------+-------+---------------------+
|  1 | 피카츄   |    30 | 2021-05-05 18:09:18 |
|  2 | 님피아   |    40 | 2021-05-05 18:09:35 |
|  3 | 따라큐   |    38 | 2021-05-05 18:10:20 |
|  4 | 메타몽   |    29 | 2021-05-05 18:10:37 |
|  5 | 갸라도스 |    50 | 2021-05-05 18:10:50 |
+----+----------+-------+---------------------+
5 rows in set (0.000 sec)
```

