---
title: Circuit Breaker
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

# Circuit Breaker

> [!note] Overview
> The ==Circuit Breaker pattern== wraps a potentially failing operation in a state machine that monitors for repeated failures. When failures exceed a threshold, the breaker **trips** — blocking further calls and returning errors immediately instead of waiting for timeouts. This protects system resources and provides stability during recovery.

## The Core Idea

A function that might fail is wrapped in a **circuit breaker object**. The object watches for repeated failures. If the failure count exceeds a set limit within a defined period, the circuit breaker trips and blocks more calls, returning an error immediately. The Circuit Breaker acts as a ==middle layer== for risky operations — it checks recent failure patterns and decides whether to allow or stop the operation.

> [!info] Context / Risk
> Repeated calls to a failing service waste resources and increase latency for the caller. Without a circuit breaker, a slow or dead dependency can cascade into a full system slowdown.

## Three States

<picture>

### Closed State

==Normal operation.== Incoming requests pass through to the service. The circuit breaker monitors recent failures, and if a specified threshold is exceeded within a defined period, it transitions to the **Open** state.

### Open State

==Failure mode.== Incoming requests are instantly returned with an error — no calls reach the service. A ==cooldown timer== starts, and when it expires the breaker transitions to the **Half-Open** state.

### Half-Open State

==Recovery probe.== A limited number of requests are allowed through to test the service. If they succeed (fault is assumed fixed), the breaker transitions back to **Closed** and resets all counters. If any request fails, the breaker reverts to **Open** and the timeout timer restarts.

## State Transition Summary

| From | To | Condition |
|---|---|---|
| Closed | Open | Failure count exceeds threshold within period |
| Open | Half-Open | Cooldown timer expires |
| Half-Open | Closed | Test requests succeed |
| Half-Open | Open | Test request fails |

## Observability

> [!tip] Event Emission
> If the circuit breaker emits events when its state changes, administrators can track the health of the protected system in real time — state transitions become observable signals of dependency health.

## Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Prevents resource exhaustion from failing dependencies | Adds complexity to call paths |
| Reduces latency by failing fast instead of timing out | Cooldown period must be carefully tuned |
| Provides stability during system recovery | Half-Open state requires careful request limiting |
| State changes are observable health signals | False positives can block a recovering service |

## When to Use

> [!example] Decision Hints
> - Use Circuit Breaker when calling ==external services or dependencies== that can fail or become slow.
> - Combine with [[Isolation]] to stop calls propagating into an already-isolated failing component.
> - Combine with [[Leaky Bucket Counter]] to feed failure counts into the trip threshold.
> - Use in microservices to prevent a slow downstream service from degrading an entire request chain.

## Related Notes

- [[Fault Tolerance Patterns]]
- [[Isolation]]
- [[Leaky Bucket Counter]]
- [[Heartbeat]]
