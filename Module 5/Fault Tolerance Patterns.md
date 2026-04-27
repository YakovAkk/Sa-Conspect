---
title: Fault Tolerance Patterns
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

# Fault Tolerance Patterns

> [!note] Overview
> ==Fault tolerance== is the ability of a system to keep working — or recover — when some of its components fail. Building it requires a structured approach to the full fault lifecycle: detection, recovery, mitigation, and treatment. Six patterns — Redundancy, Voting, Heartbeat, Leaky Bucket Counter, Isolation, and Circuit Breaker — together form a complete toolkit for resilient system design.

## Fault Lifecycle

**Fault tolerance** reduces the impact of errors or failures, ensuring the system can keep working or recover without affecting overall performance or reliability.

![[Fault Tolerance lifecycle diagram]]

| Phase | Purpose |
|---|---|
| ==Error Detection== | Detect error states, root faults, and failures via audit checks or detection components |
| ==Error Recovery== | Substitute the erroneous state with a new error-free state; continue execution |
| ==Error Mitigation== | Remove errors without changing state — fix the data value and continue, no rollback |
| ==Fault Treatment== | Prevent recurrence: verify fault still exists → diagnose nature/location → correct |

> [!warning] Safety-Critical Context
> Fault tolerance is especially critical in safety-critical systems, where failures can lead to serious harm or damage. A reliable system must be deliberately designed — it does not emerge from unreliable parts by accident.

## Six Patterns at a Glance

| Pattern | Context/Risk | Solution |
|---|---|---|
| ==Redundancy== | Component failure makes the system unavailable | Add spatial, temporal, or informational copies |
| ==Voting== | Redundant components give different answers — which is correct? | Majority vote, median vote, or plurality vote |
| ==Heartbeat== | Components can become unavailable; must minimize Mean Time To Repair | Regular health signals from/to a monitor |
| ==Leaky Bucket Counter== | Not all errors are critical; need to distinguish transient from permanent | Counter that increments on error, decrements over time; threshold = permanent |
| ==Isolation== | A failure in one part can cascade across the system | Divide into independent units; use bulkheads and loose coupling |
| ==Circuit Breaker== | Repeated calls to a failing service waste resources | Wrap in a state machine: Closed → Open → Half-Open |

The ==Isolation== and ==Circuit Breaker== patterns are especially important for keeping failures from spreading across the system.

## Related Notes

- [[Redundancy]]
- [[Voting]]
- [[Heartbeat]]
- [[Leaky Bucket Counter]]
- [[Isolation]]
- [[Circuit Breaker]]
