---
title: Sharding
date: 2026-04-20
tags:
  - module5
  - sharding
  - scalability
  - patterns
  - canvas-note
cssclasses:
  - canvas-note
---

# Sharding

> [!note] Overview
> ==Sharding== is a ==horizontal partitioning== technique that splits a large database into smaller, easier-to-manage pieces called ==data shards==. These shards are stored across different servers or nodes, each handling a specific data part. The key design decision is choosing the right ==shard key== and the distribution strategy.

## Sharding Fundamentals

**Sharding** is a horizontal partitioning technique that splits a large database into smaller, easier-to-manage pieces called data shards. These shards are stored across different servers or nodes, each handling a specific data part.

The most important step when planning to divide a database into shards is deciding how to group the data. This is usually done using a ==shard key== (also called a ==partition key==), which defines the range of data each shard will hold.

Choosing the right shard key and how to spread data across shards are critical decisions.

## Three Sharding Strategies

### The Lookup Strategy

In the ==Lookup Strategy==, the sharding logic employs a mapping mechanism to direct data requests to the shard containing the relevant information using the shard key.

> [!info] Lookup Strategy Details
> - For instance, in a multi-tenant application, the **tenant ID** can serve as the shard key, consolidating all tenant data within a shard.
> - This strategy offers **control over shard configuration and utilization**.
> - ==Virtual shards== mitigate the impact during data rebalancing, providing flexibility in modifying mappings without altering application code.

![[Sharding Lookup diagram]]

### The Range Strategy

The ==Range Strategy== groups related items in the same shard and orders them based on a shared key.

> [!info] Range Strategy Details
> - Ideal for applications requiring frequent retrieval of item sets through ==range queries==.
> - Exemplified by chronologically storing orders for a specific month within the same shard.
> - While efficient for range queries, achieving a balance between shards poses challenges.

![[Pasted image 20260420190436.png]]
### The Hash Strategy

The ==Hash Strategy== distributes data evenly across shards by computing the shard based on a hash of one or more data attributes.

> [!info] Hash Strategy Details
> - To address ==load disparities==, hash distributes data evenly.
> - This minimizes ==hotspots==, ensuring a balanced distribution of load.
> - While providing even data and load distribution, the hash function may introduce additional computational overhead.

![[Pasted image 20260420190446.png]]
## Strategy Comparison

| Strategy | Mechanism | Best For | Trade-off |
|---|---|---|---|
| Lookup | Mapping table | Multi-tenant, flexible config | Extra mapping overhead |
| Range | Ordered key ranges | Range queries, time-series | Risk of unbalanced shards |
| Hash | Hash function on key | Uniform load distribution | Costly range queries |

## Availability and Fault Isolation Benefits

These sharding strategies allow architects to choose the best way to divide data based on the application's needs. ==Sharded databases improve availability== and reduce the impact of outages. If a failure occurs, only the part of the system that depends on the missing data is affected, not the whole application.

Sharded systems can also ==replicate backup shards on extra nodes==, which helps protect the system even more during an outage. In contrast, an application without sharding might stop working completely if its central database goes down.

## Related Notes

- [[Performance and Scalability Patterns]]
- [[Sharding Considerations]]
