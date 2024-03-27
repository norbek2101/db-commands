
# Basic Cassandra Commands Guide

This guide provides a quick reference to basic Cassandra commands that you can use in the Ubuntu terminal.

## Connecting to Cassandra

To connect to a Cassandra database, use the `cqlsh` command. If Cassandra is running on your local machine with the default settings, simply run:

```bash
cqlsh
```

## Creating a Keyspace (Database)

To create a new keyspace, use the `CREATE KEYSPACE` command. Replace `YourKeyspaceName` with your desired keyspace name:

```cql
CREATE KEYSPACE YourKeyspaceName WITH replication = {'class':'SimpleStrategy', 'replication_factor' : 3};
```

## Creating a User

Cassandra uses roles for authentication. To create a new user, you actually create a role with login privileges:

```cql
CREATE ROLE username WITH PASSWORD = 'password' AND LOGIN = true;
```

## Changing a User's Password

To change a user's password, use the `ALTER ROLE` command:

```cql
ALTER ROLE username WITH PASSWORD = 'newpassword';
```

## Granting Permissions to a User

To grant all permissions on a keyspace to a user, use the `GRANT` command:

```cql
GRANT ALL PERMISSIONS ON KEYSPACE YourKeyspaceName TO username;
```

## Creating a Table

To create a new table within a keyspace, first, make sure you're using the correct keyspace:

```cql
USE YourKeyspaceName;
```

Then, use the `CREATE TABLE` command:

```cql
CREATE TABLE yourTableName (
  column1_name column1_type PRIMARY KEY,
  column2_name column2_type,
  column3_name column3_type
);
```

## Deleting a Table

To delete a table, use the `DROP TABLE` command:

```cql
DROP TABLE yourTableName;
```

## Inserting Data into a Table

To insert data into a table, use the `INSERT INTO` command:

```cql
INSERT INTO yourTableName (column1, column2, column3) VALUES (value1, value2, value3);
```

## Updating Data in a Table

To update data in a table, use the `UPDATE` command:

```cql
UPDATE yourTableName SET column1 = value1 WHERE column2 = value2;
```

## Common Queries

- **Selecting Data**

  To select data from a table:

  ```cql
  SELECT * FROM yourTableName;
  ```

- **Selecting Specific Columns**

  To select specific columns:

  ```cql
  SELECT column1, column2 FROM yourTableName WHERE column3 = value3;
  ```

This README provides a brief overview of basic commands and operations in Cassandra. For more detailed information, refer to the official Cassandra documentation.
