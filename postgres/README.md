# Basic PostgreSQL Commands

This document provides an overview of basic PostgreSQL commands and their brief descriptions.

## Connecting to a PostgreSQL Database

- `psql -U username -d database_name`: Connects to a PostgreSQL database with the specified username and database.

## Creating Database and Table

- `CREATE DATABASE database_name;`: Creates a new PostgreSQL database.
- `CREATE TABLE table_name(column1 datatype1, column2 datatype2, ...);`: Creates a new table in the database.

## Inserting Data

- `INSERT INTO table_name(column1, column2, ...) VALUES(value1, value2, ...);`: Inserts new data into a table.

## Selecting Data

- `SELECT * FROM table_name;`: Selects all data from a table.
- `SELECT column1, column2 FROM table_name;`: Selects specific columns from a table.

## Updating Data

- `UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;`: Updates data in a table based on a condition.

## Deleting Data

- `DELETE FROM table_name WHERE condition;`: Deletes data from a table based on a condition.

## Dropping Table and Database

- `DROP TABLE table_name;`: Deletes a table from the database.
- `DROP DATABASE database_name;`: Deletes a database.

Remember, it's important to always back up your data before performing operations that modify or delete data.
"""
