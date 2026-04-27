---
title: Heartbeat
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

# Heartbeat

> [!note] Overview
> ==Heartbeat detection== is a fault tolerance pattern where each node in a distributed system sends regular health signals to a central monitor. If a node stops sending heartbeats, the monitor detects the failure and can take corrective action. It is especially valuable for detecting ==network failures==, which are among the most common problems in distributed systems.

## How Heartbeat Works

Each node sends a periodic signal — a **heartbeat** — to a central monitor to indicate it is active and healthy. The monitor tracks these signals and raises an alert when a node stops responding. By noticing which nodes go silent, the system can pinpoint the cause of a failure and take action to reduce its impact.

> [!info] Context / Risk
> Modules or services in distributed architectures can become unavailable at any time. Errors must be detected as quickly as possible to minimize the ==Mean Time To Repair (MTTR)==.

**Solution**: Health reports (heartbeats) occur at regular intervals. During busy periods, realistic thresholds reduce unnecessary overhead. The heartbeat can flow from the monitor to the monitored task, or from the task to the monitor.

## Heartbeat Failure Scenario

<picture>

When a network failure occurs, some nodes may stop responding or lose connection with others. The Heartbeat pattern makes this visible: the monitor notices the missing signals and can identify which part of the network is affected.

## Configuration Considerations

> [!warning] Threshold Tuning
> - Set heartbeat intervals short enough to detect failures quickly, but not so short that they create unnecessary load.
> - During busy periods, increase acceptable latency thresholds to avoid false positives.
> - The direction of heartbeats (monitor → task or task → monitor) depends on which side is more likely to fail silently.

## Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Minimizes MTTR by detecting failures early | Adds periodic network/CPU overhead |
| Localizes failures to specific nodes | Threshold tuning requires operational knowledge |
| Works for both active and passive components | False positives can trigger unnecessary failovers |
| Detects network partitions, not just process crashes | Does not distinguish between slow and dead nodes |

## When to Use

> [!example] Decision Hints
> - Use Heartbeat whenever components can fail silently and you need fast failure detection.
> - Especially important in distributed systems where ==network partitions== are a realistic failure mode.
> - Combine with [[Redundancy]] so the monitor can trigger failover when a heartbeat is missed.
> - Use [[Leaky Bucket Counter]] to filter out transient heartbeat misses before declaring a node failed.

## Related Notes

- [[Fault Tolerance Patterns]]
- [[Redundancy]]
- [[Voting]]
- [[Leaky Bucket Counter]]
- [[Isolation]]
