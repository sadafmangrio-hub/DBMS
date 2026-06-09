# DBMS
# Denormalizing and Introducing Controlled Redundancy

## Introduction

Denormalization is a database optimization technique in which controlled redundancy is introduced into a normalized database to improve system performance. Although normalization reduces redundancy and maintains data integrity, highly normalized databases may require many join operations, which can slow down query processing. Denormalization helps overcome this issue by reducing the number of joins.

## Technique 1: Duplicating Non-Key Attributes in One-to-Many Relationships

### Definition

This technique involves copying a non-key attribute from a parent table into a child table to reduce the need for join operations.

### Purpose

The main purpose is to improve query performance when data from both tables is frequently accessed together.

### Process

* Identify frequently executed queries.
* Determine which non-key attribute is repeatedly retrieved through joins.
* Duplicate that attribute in the child table.
* Maintain consistency whenever the original data changes.

### Example

In the DreamHome database, the owner's last name can be copied from the **PrivateOwner** table into the **PropertyForRent** table. This removes the need to join the two tables every time property information is retrieved.

### Use Cases

* Frequently accessed reporting systems.
* Applications with high read operations and low update rates.
* Performance-critical database systems.

## Technique 2: Partitioning Relations

### Definition

Partitioning divides a large relation into smaller and more manageable parts called partitions.

### Purpose

It improves performance, load balancing, and data management for very large databases.

### Types of Partitioning

#### Horizontal Partitioning

Rows (tuples) are divided into separate partitions based on specific criteria.

#### Vertical Partitioning

Columns (attributes) are divided into separate partitions while duplicating the primary key to reconstruct the original relation.

### Process

* Analyze large tables and access patterns.
* Divide data into smaller partitions.
* Store partitions separately for faster access and processing.

### Use Cases

* Data warehouses.
* Large-scale enterprise databases.
* Systems storing millions of records.

## Advantages of Denormalization

* Faster query execution.
* Reduced join operations.
* Improved reporting performance.
* Better response time for frequent transactions.

## Disadvantages of Denormalization

* Increased data redundancy.
* Higher storage requirements.
* More complex updates.
* Risk of data inconsistency.

## Conclusion

Denormalization and controlled redundancy are important database optimization techniques used when performance becomes a critical requirement. Techniques such as duplicating non-key attributes and partitioning relations help reduce query processing time and improve efficiency. However, these benefits must be balanced against the increased complexity and potential redundancy introduced into the database.
