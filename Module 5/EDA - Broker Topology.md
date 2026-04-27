---
title: "Event-Driven Architecture: Broker Topology"
date: 2026-04-13
tags:
  - module5
  - architecture
  - eda
  - canvas-note
aliases:
  - EDA Broker
  - Broker Topology
  - EDA Choreography
cssclasses:
  - canvas-note
---

# Event-Driven Architecture: Broker Topology

> [!note] Overview
> Unlike the mediator topology, the ==broker topology== does **not use a central event mediator**. Instead, messages flow **between event processors in a chain**, using a ==lightweight message broker== (e.g., ActiveMQ, HornetQ).
>
> This setup works well for **simple event-processing flows** that do not need central coordination.

## The Three Main Actors

```
Event Producer  →  [Broker]  →  Event Consumer(s)
```

![[Pasted image 20260413140903.png]]

### 1. Event Producer

> [!info] Event Producer
> The ==event producer== is responsible for **creating and sending the event**.
> - It triggers the chain by publishing an event to the broker.
> - The producer does not know which consumers will receive the event or how they will process it.
> - Completely decoupled from downstream components.

### 2. Event Broker

> [!info] Event Broker
> The ==event broker== acts as the **middle layer** between producers and consumers.
> - Receives the event from the producer.
> - **Delivers it to all interested consumers** (subscribers).
> - Does **not** control the overall processing flow — it only routes and delivers.
> - Implemented using lightweight message brokers such as **ActiveMQ** or **HornetQ**.

> [!tip] Key Difference from Mediator
> The broker has no knowledge of the workflow logic. It simply delivers events — the intelligence is in the producers and consumers, not in the broker itself.

### 3. Event Consumer

> [!info] Event Consumer
> The ==event consumer== is the **final actor** in the chain.
> - Receives the event from the broker.
> - Processes it **according to its own purpose**.
> - May itself produce a new event that triggers the next step in the chain, creating a reactive flow.

## How the Flow Works

> [!example] Real-World Example: Elevator
> You are on the ground floor and want to go to the 20th floor.
>
> | Role | Component |
> |---|---|
> | **Event** | Pressing the elevator button |
> | **Event Producer** | You (the person pressing the button) |
> | **Event Broker** | The elevator control system — receives the event and delivers it |
> | **Event Consumer** | The elevator car — receives the request and takes action |
>
> The process starts **only after the button is pressed**, showing how the system reacts to an event rather than polling or waiting.

## Broker vs Mediator at a Glance

| Dimension | Broker (Choreography) | Mediator (Orchestration) |
|---|---|---|
| Central coordinator | None | Yes — the mediator |
| Flow control | Distributed — consumers decide | Centralized — mediator orchestrates |
| Complexity | Low — lightweight pipes | Higher — mediator manages ordering |
| Traceability | Harder | Easier from one place |
| Resilience | Higher — no single point of failure | Lower — mediator is a risk |
| Best for | Simple, reactive flows | Complex, ordered multi-step workflows |

## Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| No single point of failure | Hard to trace the full workflow |
| Highly decoupled components | No centralized error handling |
| Simple, lightweight infrastructure | Difficult to enforce step ordering |
| Easy to add new consumers | Debugging distributed chains is complex |
| Scales well horizontally | Logic scattered across many consumers |

## When to Use Broker Topology

> [!example] Good Fit
> - **Simple, linear event flows** where each event triggers one reaction.
> - Systems where **components must remain fully autonomous** and independent.
> - When there is **no need for conditional branching, parallel steps, or complex ordering**.
> - High-throughput systems where **decoupling and resilience** matter more than workflow visibility.

## Summary

The broker topology removes the central coordinator entirely, letting events flow through a chain of loosely connected producers, a lightweight broker, and independent consumers. This makes it simpler and more resilient than the mediator approach, but at the cost of visibility and control over the overall workflow. It is the right choice when simplicity and decoupling outweigh the need for orchestration.

## Related Notes

- [[Event-Driven Architecture]]
- [[EDA - Mediator Topology]]
- [[Architectural Style and Pattern]]
- [[Microservice Architecture]]