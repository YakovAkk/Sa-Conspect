---
title: "CQRS: Traditional CRUD Architecture"
date: 2026-04-20
tags:
  - module5
  - cqrs
  - crud
  - patterns
  - canvas-note
cssclasses:
  - canvas-note
---
![[Pasted image 20260420190249.png]]
# CQRS: Traditional CRUD Architecture

> [!note] Overview
> ==CRUD== (Create, Read, Update, Delete) maps to standard HTTP actions and underpins most application data models. In traditional architecture, a ==single data model== handles both reading from and writing to the database. This works for simple applications but breaks down under complexity, scale, and varied access patterns.

## Traditional CRUD Model

**CRUD** is a standard way to use HTTP actions in many systems. In traditional architecture, a single data model is used to read from and write to the database. This works well for basic tasks, but can become difficult in more complex applications.

In complex cases, the system may need many different types of read queries that return data in various formats, making object mapping harder. The model might include detailed validation and business logic, making it too complex because it's trying to do too much. Also, reading and writing often have different performance and scaling needs, which causes an imbalance in the system.

## Four CRUD Drawbacks

### Mismatch Between Read and Write Representations

> [!warning] Data Model Mismatch
> Discrepancies frequently arise between the read and write representations of data, introducing challenges in correctly updating additional columns or properties not part of a given operation.

### Data Contention

==Data contention== arises from the locking of records in the data store, particularly in collaborative domains where multiple actors operate concurrently on the same dataset.

### Update Conflicts

==Update conflicts== can be attributable to concurrent updates with optimistic locking. As the system's complexity and throughput grow, the risks increase. The traditional approach can harm performance due to the load on the data store and data access layer and the complexity of queries required to retrieve information.

### Complexity in Managing Security

Handling security and permissions becomes more intricate as each entity is subject to read and write operations. This complexity exposes data in potentially inappropriate contexts.

## Why CQRS Addresses These Problems

> [!tip] Key Insight
> Using ==separate models for reading and writing== can better meet changing demands and help manage complexity more effectively. CQRS explicitly separates the **command** path (writes, updates, deletes) from the **query** path (reads), resolving all four CRUD drawbacks.

| CRUD Problem | CQRS Solution |
|---|---|
| Read/write model mismatch | Dedicated read model (optimized for queries) |
| Data contention | Write model handles commands independently |
| Update conflicts | Commands are processed sequentially per aggregate |
| Security complexity | Different permissions per model |

## Related Notes

- [[Performance and Scalability Patterns]]
- [[CQRS Requirements]]
- [[CQRS Use Cases]]
