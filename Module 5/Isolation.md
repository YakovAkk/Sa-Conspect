---
title: Isolation
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

# Isolation

> [!note] Overview
> The ==Isolation pattern== protects a system from cascading failures by dividing it into separate, independent parts. If one part fails, the failure is contained and cannot spread to the rest of the system. Isolation is achieved through two complementary techniques: ==Bulkheads== (structural separation) and ==Loose Coupling== (minimal dependencies).

## The Core Idea

**Isolation** means that each part of the system can fail independently without taking down the whole. This is especially critical in complex, interconnected systems where one failure could propagate across many components.

> [!info] Context / Risk
> A failure in one part of a tightly integrated system can cascade across the entire system. The goal is to contain failures to their origin.

## Bulkheads

==Bulkheads== — also called **Units of Failure** or **Units of Mitigation** — are named after the watertight compartments in a ship's hull that prevent the vessel from sinking when one section is breached.

In software architecture, a bulkhead is a segregated section of the system that limits the impact of faults to that specific area. If one bulkhead fails, the others continue operating normally.

### Bulkheads in Microservices

In a ==microservices architecture==, each microservice acts as a natural bulkhead. Each service operates independently; if one microservice fails, it does not compromise the functionality of the other services or the system as a whole.

## Loose Coupling

==Loose coupling== minimizes dependencies between system components. Complete isolation of components ensures that a failure in one does not directly affect others.

**Asynchronous communication** further enhances fault tolerance by decoupling the timing of interactions — components can operate independently and do not need to wait for each other, reducing the risk of cascading failures.

### Loose Coupling in Distributed Systems

Systems designed with loose coupling and asynchronous communication — especially in distributed environments — are more resilient to faults. If one component fails or experiences delays, it does not impede the overall system's performance.

## Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Prevents cascading failures | Adds architectural complexity |
| Each unit can fail and recover independently | Asynchronous communication harder to reason about |
| Enables graceful degradation | More components to monitor and operate |
| Natural fit for microservices architecture | Inter-service communication overhead |

## When to Use

> [!example] Decision Hints
> - Use Isolation in any system where a ==single component failure== must not bring down the whole system.
> - Apply Bulkheads when you can clearly define independent units of functionality (e.g., per service, per tenant, per feature).
> - Apply Loose Coupling when you want to decouple timing — use async messaging between components.
> - Combine with [[Circuit Breaker]] to stop calls to an already-failing isolated component.

## Related Notes

- [[Fault Tolerance Patterns]]
- [[Circuit Breaker]]
- [[Redundancy]]
- [[Heartbeat]]
