# ![Databases](https://img.shields.io/badge/Database-SQL%2FNoSQL-blue?style=for-the-badge) ![Interview](https://img.shields.io/badge/Interview-Questions-green?style=for-the-badge) ![ProductionReady](https://img.shields.io/badge/Production-Ready-orange?style=for-the-badge)

# Database Interview Questions & Answers (SQL & NoSQL)

---

## Table of Contents
<details>
<summary>Click to expand</summary>

- [Basics](#basics)
- [SQL Queries](#sql-queries)
- [Joins](#joins)
- [Indexing](#indexing)
- [Normalization & Denormalization](#normalization--denormalization)
- [Transactions & ACID](#transactions--acid)
- [Stored Procedures & Triggers](#stored-procedures--triggers)
- [Views](#views)
- [Backup & Restore](#backup--restore)
- [Performance Tuning](#performance-tuning)
- [Security](#security)
- [NoSQL Concepts](#nosql-concepts)
- [Replication & Sharding](#replication--sharding)
- [Database Design & Modeling](#database-design--modeling)
- [Monitoring & Troubleshooting](#monitoring--troubleshooting)
- [Production-Level Scenarios](#production-level-scenarios)
- [Best Practices](#best-practices)
- [Commands / Queries Cheat Sheet](#commands--queries-cheat-sheet)

</details>

---

## Basics
<details>
<summary>Click to expand</summary>

**Q:** What is a database?  
**A:** A structured collection of data stored and accessed electronically.

**Q:** Difference between SQL and NoSQL?  
**A:** SQL = relational, structured schema; NoSQL = non-relational, flexible schema.

**⚡ Q:** What is a primary key?  
**A:** Unique identifier for a table row; cannot be NULL.

**Q:** What is a foreign key?  
**A:** A field that links to the primary key of another table to enforce referential integrity.

**Q:** What are constraints in SQL?  
**A:** Rules to maintain data integrity, e.g., NOT NULL, UNIQUE, CHECK, PRIMARY KEY, FOREIGN KEY.

</details>

---

## SQL Queries
<details>
<summary>Click to expand</summary>

**⚡ Q:** How to fetch top N records in SQL?  
**A:** `SELECT * FROM table ORDER BY column DESC LIMIT N;` (MySQL/PostgreSQL)

**Q:** Difference between `WHERE` and `HAVING`?  
**A:** `WHERE` filters rows before aggregation; `HAVING` filters after aggregation.

**Q:** Difference between `DISTINCT` and `GROUP BY`?  
**A:** `DISTINCT` removes duplicates; `GROUP BY` aggregates data.

**Q:** How to update multiple rows conditionally?  
**A:** `UPDATE table SET column=value WHERE condition;`

</details>

---

## Joins
<details>
<summary>Click to expand</summary>

**Q:** Difference between INNER JOIN and LEFT JOIN?  
**A:** INNER JOIN returns matching rows only; LEFT JOIN returns all left table rows with NULL for non-matching.

**Q:** RIGHT JOIN vs FULL OUTER JOIN?  
**A:** RIGHT JOIN returns all right table rows with NULL for non-matching; FULL OUTER JOIN returns all rows from both tables.

**Q:** Self Join?  
**A:** Joining a table to itself to compare rows within the same table.

</details>

---

## Indexing
<details>
<summary>Click to expand</summary>

**⚡ Q:** What is an index?  
**A:** A database structure that speeds up data retrieval.

**Q:** Difference between clustered and non-clustered index?  
**A:** Clustered = sorts table physically; Non-clustered = separate structure pointing to rows.

**Q:** When not to use an index?  
**A:** On small tables or frequently updated columns (can slow writes).

</details>

---

## Normalization & Denormalization
<details>
<summary>Click to expand</summary>

**Q:** What is normalization?  
**A:** Process of organizing data to reduce redundancy (1NF, 2NF, 3NF, BCNF).

**Q:** What is denormalization?  
**A:** Combining tables to improve read performance at the cost of redundancy.

**Q:** ⚡ Difference between 1NF, 2NF, 3NF?  
**A:** 1NF = atomic values; 2NF = no partial dependency; 3NF = no transitive dependency.

</details>

---

## Transactions & ACID
<details>
<summary>Click to expand</summary>

**⚡ Q:** What are ACID properties?  
**A:** Atomicity, Consistency, Isolation, Durability.

**Q:** Difference between COMMIT and ROLLBACK?  
**A:** COMMIT saves changes; ROLLBACK discards changes in a transaction.

**Q:** What is isolation level?  
**A:** Defines how/when changes by one transaction are visible to others (Read Uncommitted, Read Committed, Repeatable Read, Serializable).

</details>

---

## Stored Procedures & Triggers
<details>
<summary>Click to expand</summary>

**Q:** What is a stored procedure?  
**A:** Precompiled SQL statements stored in DB for reuse.

**Q:** What is a trigger?  
**A:** Automated action executed on insert/update/delete events.

**Q:** ⚡ Difference between trigger and stored procedure?  
**A:** Trigger runs automatically on events; procedure runs manually or via call.

</details>

---

## Views
<details>
<summary>Click to expand</summary>

**Q:** What is a view?  
**A:** Virtual table based on a SELECT query.

**Q:** ⚡ Difference between a view and a table?  
**A:** View stores query logic, not data; table stores actual data.

**Q:** Updatable view?  
**A:** A view that allows INSERT, UPDATE, DELETE on underlying tables if certain conditions are met.

</details>

---

## Backup & Restore
<details>
<summary>Click to expand</summary>

**Q:** What are different backup types?  
**A:** Full, Incremental, Differential.

**⚡ Q:** How to restore a DB in SQL?  
**A:** Use `RESTORE DATABASE db_name FROM backup_file;`

**Q:** Hot vs cold backup?  
**A:** Hot = backup while DB is online; Cold = offline backup.

</details>

---

## Performance Tuning
<details>
<summary>Click to expand</summary>

**Q:** How to optimize slow queries?  
**A:** Use indexing, avoid SELECT *, use JOINs wisely, analyze execution plans.

**Q:** What is query execution plan?  
**A:** Step-by-step DB operations to execute a query.

**Q:** ⚡ How to handle large tables efficiently?  
**A:** Partitioning, indexing, denormalization, caching.

</details>

---

## Security
<details>
<summary>Click to expand</summary>

**Q:** How to secure a database?  
**A:** Use authentication, roles, permissions, encryption, and SSL connections.

**Q:** Difference between GRANT and REVOKE?  
**A:** GRANT = provide access; REVOKE = remove access.

</details>

---

## NoSQL Concepts
<details>
<summary>Click to expand</summary>

**Q:** Difference between MongoDB, Redis, Cassandra?  
**A:** MongoDB = document; Redis = key-value; Cassandra = columnar wide-table.

**Q:** ⚡ What is CAP theorem?  
**A:** Consistency, Availability, Partition tolerance — choose any 2 in distributed DB.

**Q:** MongoDB indexing?  
**A:** Supports single, compound, TTL, text, and unique indexes.

**Q:** Redis data structures?  
**A:** Strings, Hashes, Lists, Sets, Sorted Sets.

</details>

---

## Replication & Sharding
<details>
<summary>Click to expand</summary>

**Q:** What is replication?  
**A:** Copying data across multiple DB servers for redundancy.

**Q:** What is sharding?  
**A:** Splitting a DB horizontally across multiple servers for scalability.

**Q:** Master-Slave vs Master-Master replication?  
**A:** Master-Slave = one writable node, many read nodes; Master-Master = multiple writable nodes.

</details>

---

## Database Design & Modeling
<details>
<summary>Click to expand</summary>

**Q:** What is ER modeling?  
**A:** Entity-Relationship diagrams to design relational databases.

**Q:** ⚡ Difference between logical and physical design?  
**A:** Logical = abstract schema; Physical = actual implementation in DB.

**Q:** What is data modeling?  
**A:** Structuring data to define relationships, constraints, and storage.

</details>

---

## Monitoring & Troubleshooting
<details>
<summary>Click to expand</summary>

**Q:** How to monitor DB performance?  
**A:** Use metrics like queries/sec, slow queries, locks, CPU/memory usage.

**Q:** Tools for monitoring?  
**A:** Prometheus, Grafana, Datadog, native DB logs.

**Q:** How to troubleshoot deadlocks?  
**A:** Identify queries causing locks, kill/blocking sessions, optimize transactions.

</details>

---

## Production-Level Scenarios
<details>
<summary>Click to expand</summary>

**⚡ Q:** How to handle slow queries in production?  
**A:** Analyze execution plan, add indexes, rewrite queries, consider caching.

**Q:** How to fix deadlocks?  
**A:** Optimize transactions, reduce lock contention, use proper isolation levels.

**⚡ Q:** What to do if replication lag occurs?  
**A:** Check network, slave load, apply pending logs, monitor write volume.

**Q:** Backup failures?  
**A**
