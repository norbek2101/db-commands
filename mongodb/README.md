# MongoDB Basic Commands Guide

This guide provides an overview of the most common commands used in MongoDB Shell (mongosh) for managing databases, users, and permissions. These commands are essential for performing routine database operations in MongoDB.

## Connecting to MongoDB

- **Connect to MongoDB on the local machine**
  ```sh
  mongosh
  ```
- **Connect to a MongoDB database**
  ```sh
  mongosh "mongodb://localhost:27017/<databaseName>"
  ```

## Managing Databases

- **Create or switch to a database**
  ```sh
  use <databaseName>
  ```
- **List all databases**
  ```sh
  show dbs
  ```
- **Delete a database**
  - First, switch to the database you want to delete, then run:
    ```sh
    db.dropDatabase()
    ```

## Managing Collections

- **Create a collection**
  ```sh
  db.createCollection("<collectionName>")
  ```
- **List all collections in the current database**
  ```sh
  show collections
  ```
- **Delete a collection**
  ```sh
  db.<collectionName>.drop()
  ```

## Managing Users

- **Create a new user**
  ```sh
  db.createUser({
    user: "<username>",
    pwd: "<password>",
    roles: [{ role: "readWrite", db: "<databaseName>" }]
  })
  ```
- **Show all users in the current database**
  ```sh
  show users
  ```
- **Update a user's password or roles**
  ```sh
  db.updateUser("<username>", {
    pwd: "<newPassword>",
    roles: [{ role: "readWrite", db: "<databaseName>" }]
  })
  ```
- **Delete a user**
  ```sh
  db.dropUser("<username>")
  ```

## Granting Permissions to Users

- **Grant roles to a user**
  ```sh
  db.grantRolesToUser("<username>", [{ role: "readWrite", db: "<databaseName>" }])
  ```
- **Revoke roles from a user**
  ```sh
  db.revokeRolesFromUser("<username>", [{ role: "readWrite", db: "<databaseName>" }])
  ```

## Executing Queries

- **Insert documents into a collection**
  ```sh
  db.<collectionName>.insertOne({ key: "value" })
  db.<collectionName>.insertMany([{ key1: "value1" }, { key2: "value2" }])
  ```
- **Find documents in a collection**
  ```sh
  db.<collectionName>.find({ key: "value" })
  ```
- **Update documents in a collection**
  ```sh
  db.<collectionName>.updateOne({ key: "value" }, { $set: { key: "new value" } })
  db.<collectionName>.updateMany({ key: "value" }, { $set: { key: "new value" } })
  ```
- **Delete documents from a collection**
  ```sh
  db.<collectionName>.deleteOne({ key: "value" })
  db.<collectionName>.deleteMany({ key: "value" })
  ```

This guide covers the basics to get you started with MongoDB. For more detailed information, consult the MongoDB documentation.

This Markdown file provides a quick reference to MongoDB basic commands for managing databases, collections, and users, as well as performing CRUD operations. Save this content as `README.md` in your project directory for easy access and reference.
