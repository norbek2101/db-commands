# Neo4j Basic Commands Guide

This guide provides an overview of basic commands used in Cypher, Neo4j's query language, for creating, reading, updating, and deleting data in a graph database. These commands are foundational for working with Neo4j.

## Creating Data

### Create a Node
```cypher
CREATE (n:Label {propertyKey: 'propertyValue'})
```
Creates a node with a label and properties.

### Create a Relationship
```cypher
MATCH (a:Label1), (b:Label2)
WHERE a.propertyKey = 'valueA' AND b.propertyKey = 'valueB'
CREATE (a)-[:RELATIONSHIP_TYPE {propertyKey: 'propertyValue'}]->(b)
```
Creates a relationship between two nodes with properties.

## Reading Data

### Find a Node
```cypher
MATCH (n:Label {propertyKey: 'propertyValue'})
RETURN n
```
Finds nodes by label and property.

### Find a Relationship
```cypher
MATCH (a)-[r:RELATIONSHIP_TYPE]->(b)
RETURN r
```
Finds relationships by type.

### Complex Queries
```cypher
MATCH (a:Label1)-[:RELATIONSHIP_TYPE]->(b:Label2)
WHERE a.propertyKey = 'valueA'
RETURN a, b
```
Uses patterns to find nodes and relationships with certain criteria.

## Updating Data

### Update Node
```cypher
MATCH (n:Label {propertyKey: 'oldValue'})
SET n.propertyKey = 'newValue'
```
Finds a node and updates its properties.

### Update Relationship
```cypher
MATCH (a)-[r:RELATIONSHIP_TYPE]->(b)
SET r.propertyKey = 'newValue'
```
Finds a relationship and updates its properties.

## Deleting Data

### Delete Node
```cypher
MATCH (n:Label {propertyKey: 'propertyValue'})
DELETE n
```
Deletes a node with a specific property. Note: You need to delete relationships connected to this node before you can delete it.

### Delete Relationship
```cypher
MATCH (a)-[r:RELATIONSHIP_TYPE]->(b)
DELETE r
```
Deletes a relationship between two nodes.

## Special Commands

### Create an Index
```cypher
CREATE INDEX ON :Label(propertyKey)
```
Creates an index on a property of a label to improve search performance.

### Remove an Index
```cypher
DROP INDEX ON :Label(propertyKey)
```
Removes an existing index.

Remember, these commands are just the basics to get started with Neo4j. The true power of Neo4j and Cypher comes from constructing more complex queries to navigate and manipulate your graph data effectively.
