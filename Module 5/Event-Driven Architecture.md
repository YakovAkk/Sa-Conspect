---
title: "Event-Driven Architecture"
date: 2026-04-13
tags:
  - module5
  - architecture
  - eda
  - canvas-note
aliases:
  - EDA
  - Event Driven Architecture
cssclasses:
  - canvas-note
---

# Event-Driven Architecture (EDA)

> [!note] Overview
> ==Event-Driven Architecture (EDA)== is based on ==loosely connected components== that handle events **asynchronously**. Each component is designed for a specific task and can work on its own, which makes the system more efficient.
>
> The main goal of EDA is to improve **scalability and performance**. It allows systems to react quickly and flexibly to different events, making them more responsive.

## Core Concepts

### What is an Event?

An ==event== is a signal that something has happened — a user action, a state change, a system notification. In EDA, components communicate by **producing** and **consuming** events rather than calling each other directly.

### Why Asynchronous?

> [!tip] Asynchronous Processing
> Because components handle events asynchronously:
> - **Producers** do not wait for consumers to finish — they fire and move on.
> - **Consumers** process events at their own pace, independently of each other.
> - The system can absorb traffic spikes by queuing events rather than blocking.
>
> This decoupling is what gives EDA its scalability and responsiveness.

## Two Topologies

EDA can be organized in two main ways, each with a different approach to control and coordination.

---

### 1. Mediator Topology (Orchestration)

> [!info] Mediator — Centralized Control
> In the ==Mediator topology==, a **central component (the mediator)** coordinates and orchestrates the flow of events.
>
> **How it works:**
> - The mediator acts as a **hub** that receives, processes, and dispatches events to the relevant components.
> - It knows the full flow: which components need to be called, in what order, and under what conditions.
> - All event routing logic lives in the mediator.
>
> **Characteristics:**
> - **Centralized** control and management of event processing.
> - Easier to understand and trace the full workflow from one place.
> - The mediator becomes a potential single point of failure and a bottleneck if not managed well.

| Aspect | Mediator |
|---|---|
| Control | Centralized |
| Workflow visibility | High — all logic in one place |
| Coupling | Mediator is coupled to all participants |
| Failure risk | Mediator is a single point of failure |
| Best for | Complex workflows with conditional branching |

---

### 2. Broker Topology (Choreography)

> [!info] Broker — Decentralized Collaboration
> In the ==Broker topology==, there is **no central coordinator**. Instead, events are **broadcast** to all interested components.
>
> **How it works:**
> - A broker (message bus or event stream) delivers events to all subscribers.
> - Each component **independently decides** how to respond to an event it receives.
> - Components collaborate based on the events they receive, without any single component directing the flow.
>
> **Characteristics:**
> - **Decentralized** and **autonomous** — each component owns its own reaction logic.
> - More resilient — no single point of failure in routing.
> - Harder to trace a full workflow across components (distributed observability is required).

| Aspect | Broker |
|---|---|
| Control | Decentralized |
| Workflow visibility | Low — logic distributed across components |
| Coupling | Components only depend on event contracts |
| Failure risk | No single routing point of failure |
| Best for | Highly distributed, autonomous systems |

---

## Mediator vs Broker at a Glance

| Dimension | Mediator (Orchestration) | Broker (Choreography) |
|---|---|---|
| Who controls the flow? | Central mediator | Each component individually |
| Communication style | Hub-and-spoke | Publish-subscribe / broadcast |
| Flexibility | Less — logic centralized | More — components act independently |
| Traceability | Easy | Hard without distributed tracing |
| Scalability | Mediator can bottleneck | Scales well horizontally |

## When to Use EDA

> [!example] Good Fit Scenarios
> - Systems that need to **react to real-time events** (user actions, sensor data, financial transactions).
> - Architectures where **services must remain decoupled** and deployable independently.
> - High-throughput systems that need to **absorb load asynchronously** (order processing, notifications, analytics pipelines).
> - When **scalability and performance** are primary concerns over strict workflow control.

> [!warning] Trade-offs to Consider
> - **Eventual consistency** — because events are processed asynchronously, data may not be immediately consistent across components.
> - **Debugging complexity** — tracing a request across many async event handlers requires strong observability tools.
> - **Event ordering** — guaranteeing the order of event processing across distributed consumers is non-trivial.

## Summary

Event-Driven Architecture decouples components by having them communicate through events rather than direct calls. The choice between the **Mediator (orchestration)** and **Broker (choreography)** topologies comes down to how much central control is needed versus how much autonomy each component should have. Together, these two approaches give architects the tools to design systems that scale, adapt, and respond to events efficiently.

## Related Notes

- [[Architectural Style - Monolith, Layered and Microservices]]
- [[Microservice Architecture]]
- [[Characteristics of Microservices Architecture]]
- [[Architectural Style and Pattern]]