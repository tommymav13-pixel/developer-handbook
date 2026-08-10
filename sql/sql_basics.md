# SQL Basics

This document contains basic SQL commands and relational database concepts encountered during study and practice.

## SQL

SQL stands for **Structured Query Language**.

It is used to interact with relational database management systems such as MySQL.

SQL can be used to:

* retrieve data;
* filter and sort data;
* insert data;
* update data;
* delete data;
* define database structures.

This document should grow as these concepts are encountered in practice.

## Databases and tables

A relational database organizes data primarily into tables.

A table consists of rows and columns.

Conceptually:

```text id="y76qcm"
Table: actor

+----------+------------+-----------+
| actor_id | first_name | last_name |
+----------+------------+-----------+
| 1        | PENELOPE   | GUINESS   |
| 2        | NICK       | WAHLBERG  |
+----------+------------+-----------+
```

A column represents an attribute or field.

A row represents an individual record.

## List databases

To inspect the databases available on a MySQL server:

```sql id="xj0is6"
SHOW DATABASES;
```

## Select a database

Before querying tables, select the database to work with:

```sql id="yok2tu"
USE sakila;
```

The selected database becomes the current database for subsequent statements.

## List tables

Display the tables in the current database:

```sql id="dyab6m"
SHOW TABLES;
```

This is useful when exploring an unfamiliar database.

## Query data

The `SELECT` statement retrieves data from a table.

Basic structure:

```sql id="2d49og"
SELECT column_name
FROM table_name;
```

For example:

```sql id="ctybz2"
SELECT first_name
FROM actor;
```

Multiple columns can be requested:

```sql id="wog1rp"
SELECT first_name, last_name
FROM actor;
```

## Select all columns

The `*` wildcard represents all columns:

```sql id="tkn8gc"
SELECT *
FROM actor;
```

This is useful for exploring a table, although explicitly selecting required columns is generally clearer for production queries.

## Statement terminator

SQL statements are commonly terminated with a semicolon:

```sql id="5vckne"
SHOW DATABASES;
```

The MySQL command-line client can wait for additional input when a statement has not yet been terminated.

## Keywords and capitalization

SQL keywords are generally case-insensitive in MySQL.

For example:

```sql id="txhks6"
select * from actor;
```

and:

```sql id="scygbs"
SELECT * FROM actor;
```

can represent the same query.

Using uppercase SQL keywords is a common readability convention:

```sql id="3yxzxm"
SELECT first_name, last_name
FROM actor;
```

## Current practice database

The current practice database is:

```text id="p1k8ji"
sakila
```

Sakila provides interconnected tables containing sample data and can be used to practice relational queries.

## Current mental model

At the current stage:

```text id="htp2yv"
MySQL Server
    ↓
Database
    ↓
Table
    ↓
Rows and columns
    ↓
SQL query
    ↓
Result set
```

More advanced topics such as filtering, joins, aggregation, keys, constraints, normalization, transactions, indexes, and database design should be added after they are encountered and practiced.

## Related documentation

* `mysql_setup.md` — installing, connecting to, and troubleshooting MySQL
