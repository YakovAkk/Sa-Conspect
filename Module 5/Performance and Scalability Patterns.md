---
title: Performance and Scalability Patterns
date: 2026-04-20
tags:
  - module5
  - performance
  - scalability
  - patterns
  - canvas-note
cssclasses:
  - canvas-note
---

# Performance and Scalability Patterns

> [!note] Overview
> When designing complex software architecture, ==performance== and ==scalability== require special attention beyond basic functionality. Three patterns—CQRS, Event Sourcing, and Sharding—address these quality attributes by restructuring how data is stored, accessed, and distributed across a system.

## 1. Command and Query Responsibility Segregation (CQRS)

==CQRS== separates read and write operations into distinct models and physical stores. This solves inefficiencies in traditional CRUD, where a single model must serve all access patterns.

> [!info] Pattern Summary
> - **Context/Risk**: All CRUD operations use the same entity representation, leading to performance and modeling trade-offs.
> - **Intention**: Divide the data store into separate physical stores for read and write operations; support eventual consistency.
> - **Solution**: Segregate operations that read data from operations that update data using separate interfaces.

## 2. Event Sourcing Pattern

==Event Sourcing== replaces current-state storage with an append-only log of events. The current state is always derived by replaying these events.

> [!info] Pattern Summary
> - **Context/Risk**: Maintaining current state directly can slow performance due to processing overhead, conflicts, and history loss.
> - **Intention**: Support event consistency and provide practical ways of retrieving the object's current state.
> - **Solution**: Handle operations on data driven by a sequence of events, each recorded in an append-only store that acts as the authoritative data source.

## 3. Sharding Pattern

==Sharding== horizontally partitions a large database into smaller pieces (shards) distributed across different servers or nodes.

> [!info] Pattern Summary
> - **Context/Risk**: A single-server data store may be limited by storage space, computing resources, network bandwidth, and geography.
> - **Intention**: Store data most effectively from the performance, cost, and location points of view.
> - **Solution**: Divide a data store into a set of horizontal partitions or shards to improve scalability when storing and accessing large volumes of data.

## Comparison at a Glance

| Pattern | Core Idea | Scalability Lever | Key Trade-off |
|---|---|---|---|
| CQRS | Separate read/write models | Independent read/write scaling | Eventual consistency complexity |
| Event Sourcing | Immutable event log as state | Replay, audit, extensibility | Storage growth, query complexity |
| Sharding | Horizontal data partitioning | Distribute load across nodes | Rebalancing, cross-shard queries |

## When to Choose Which

> [!example] Decision Hints
> - Use **CQRS** when read and write loads differ greatly, domain logic is complex, or you need DDD alignment.
> - Use **Event Sourcing** when audit history, state replay, or decoupled event-driven integrations are required.
> - Use **Sharding** when a single database node can no longer handle the data volume or throughput—after simpler optimizations are exhausted.

Using these patterns helps the system meet basic needs and adapt as demands increase and operations change, making the architecture more flexible and ready for future challenges.

## Related Notes

- [[CQRS - Traditional CRUD Architecture]]
- [[CQRS Requirements]]
- [[CQRS Use Cases]]
- [[Event Sourcing]]
- [[Event Sourcing Use Cases]]
- [[Sharding]]
- [[Sharding Considerations]]
