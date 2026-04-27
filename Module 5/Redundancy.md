---
title: Redundancy
date: 2026-04-20
tags:
  - module5
  - fault-tolerance
  - patterns
  - resilience
  - canvas-note
cssclasses:
  - canvas-note
---

# Redundancy

> [!note] Overview
> ==Redundancy== is a core fault tolerance pattern that creates copies of key components so that if one fails, another can take over without interrupting service. It is the foundational idea behind fault tolerance itself — the belief that many separate faults are unlikely to happen simultaneously.

## The Core Idea

**Redundancy** means making copies of critical components — hardware, software, or data — so the system can continue working when one of them fails. A fault-tolerant system must be built to avoid any ==single point of failure==. If one part might fail, a backup should be ready to take over.

> [!info] Context / Risk
> In case of errors, a system composed of many software and hardware components can become unavailable.

**Intention**: Reduce the amount of time between error detection and the resumption of normal operation after error recovery.

## Three Types of Redundancy

### Spatial Redundancy

==Spatial redundancy== means multiple copies of the system exist in different physical or logical locations. This is especially relevant in ==virtualized systems==, where copies of components may end up on the same physical host — a problem addressed using **anti-affinity rules** that force replicas apart.

### Temporal Redundancy

==Temporal redundancy== repeats the same calculations over time and compares the results to detect faults. This approach can also bring parallelism and improve overall system performance.

### Informational Redundancy

==Informational redundancy== is used to fix mistakes in data. Failures can arise when data is transferred between systems or stored in a memory unit; extra information (such as checksums or error-correcting codes) allows detection and correction of these errors.

## Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Eliminates single points of failure | Increases infrastructure cost |
| Minimizes downtime after component failure | Redundant copies add operational complexity |
| Enables transparent failover | Virtualized environments need anti-affinity rules |
| Supports all layers: hardware, software, data | Temporal redundancy adds latency per operation |

## When to Use

> [!example] Decision Hints
> - Use Redundancy when ==availability== is a primary requirement and any downtime is unacceptable.
> - Use Spatial Redundancy when geographic isolation or host-level failure is a concern.
> - Use Temporal Redundancy when computational accuracy must be verified over repeated execution.
> - Use Informational Redundancy when data integrity during storage or transfer is critical.
> - Combine with [[Voting]] to resolve conflicts between redundant components that give different answers.

## Related Notes

- [[Fault Tolerance Patterns]]
- [[Voting]]
- [[Heartbeat]]
- [[Leaky Bucket Counter]]
- [[Isolation]]
- [[Circuit Breaker]]
