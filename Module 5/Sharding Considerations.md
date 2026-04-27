---
title: Sharding Considerations
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

# Sharding Considerations

> [!note] Overview
> The ==Sharding pattern== allows systems to scale beyond what a single storage node can handle by distributing data across commodity hardware. However, sharding should only be applied after other performance improvements are exhausted, and it requires careful design to avoid hotspots, rebalancing issues, and cross-shard consistency problems.

## Benefits of Sharding

**The Sharding pattern** brings many benefits. Adding more shards to extra storage nodes allows the system to ==scale easily== without needing expensive, high-performance machines for every node. However, sharding should only be used when other performance improvement methods no longer work. It also comes with challenges that must be carefully planned for.

## Seven Design Considerations

### 1. Complementary to Other Partitioning Forms

==Sharding can be used in conjunction with other forms of partitioning==. For example, a single shard can contain entities that have been divided ==vertically==, and a functional partition can be implemented as multiple shards.

### 2. Balanced Shards

It is necessary to ==periodically rebalance== the shards in cases if the data was deleted or inserted. It helps to ensure an even distribution and reduce the likelihood of ==hotspots==. Plan the operation to ensure that each shard has enough free space to handle the changes.

### 3. Stable Data for Key Shards

When selecting a shard key, it is essential to use ==stable data==. If the shard key changes, the corresponding data item may have to move between shards, which could increase the amount of work required by update operations.

### 4. Unique Sharding Keys

Ensure that ==shard keys are unique==. It is recommended to avoid using ==auto-incrementing fields== since they cannot be coordinated across shards in some systems. This could result in different shards having the same shard key.

### 5. Complex Queries

It is not always possible to design a shard key that matches all the query requirements. For this reason, share the data to support the ==most frequently performed queries==. If necessary, create ==secondary index tables== to support queries that retrieve data.

### 6. Reference Data Replication

Consider ==replicating reference data to all shards==. If an operation that retrieves data also mentions static or slow-moving data as part of the same query, add it to the shard. The application can easily convey all of it, without returning to a separate data store.

### 7. Referential Integrity and Consistency

Minimize operations that affect data in multiple shards. If an application must modify data across shards, evaluate whether complete data consistency is required. Instead, a common approach in the cloud is to implement ==eventual consistency==.

## Considerations Summary

| Consideration | Key Rule |
|---|---|
| Complementary Partitioning | Can combine vertical + functional partitioning within shards |
| Balanced Shards | Rebalance periodically to prevent hotspots |
| Stable Keys | Avoid keys that change; moving data is expensive |
| Unique Keys | Don't use auto-increment across shards |
| Complex Queries | Design around most frequent queries; use secondary indexes |
| Reference Data | Replicate static data to avoid cross-shard lookups |
| Consistency | Prefer eventual consistency for cross-shard writes |

## When to Use Sharding

> [!tip] Decision Guidance
> Sharding allows systems to use ==standard, low-cost hardware== instead of expensive machines. Spreading the workload across shards reduces conflicts and improves overall performance. In cloud environments, shards can also be placed closer to the users who need the data, which helps with speed and efficiency.

Sharding should be used when the system needs to grow beyond what a ==single storage node== can handle or when you want to reduce contention in the data store to improve performance. Its success depends on doing it correctly, with good planning and the right tools. When managed well, sharding can deliver strong scalability and better system performance.

## Related Notes

- [[Performance and Scalability Patterns]]
- [[Sharding]]
