---
title: "Architectural Style: Monolith, Layered and Microservices"
date: 2026-04-13
tags:
  - module5
  - architecture
  - canvas-note
aliases:
  - Monolith Architecture
  - Architectural Styles
cssclasses:
  - canvas-note
---

# Architectural Style: Monolith, Layered and Microservices

> [!note] Overview
> An ==architectural style== defines the high-level organization of a software system — how parts are split, how they communicate, and how they are deployed. The three foundational styles covered here are **Monolith**, **Layered**, and **Microservices**.

## 1. Monolithic Architecture

A software system is called ==monolithic== when different system parts — data input/output, processing, error handling, and the user interface — are **not built as separate components** but combined into a single unified unit.

A monolith is an architectural style where the whole application is designed and run as **one cohesive system**.

### Levels of a Monolith

The monolithic style can be described at several levels, which together explain how it is built and organized:

- **Modules (Repository, Project)**
  At the module level, a monolith is a cohesive collection of components that usually live in a shared repository or project. These modules encapsulate related functionality, forming a comprehensive codebase.

- **Component**
  On a finer scale, a monolith can be viewed as a single component that integrates diverse functionalities. Different parts of the application are intricately interconnected within the same codebase.

- **Runtime (Infrastructure Components)**
  The monolithic style extends to the runtime environment — servers, databases, and other infrastructure elements function as a unified whole that supports the entire application.

### Key Characteristics

> [!info] Defining Traits of a Monolith
> - **Single codebase, repository, and team** — development teams collaborate within the same codebase, fostering shared ownership and collective responsibility.
> - **Single component and unit of deployment** — the monolith is treated as one indivisible unit; updates and releases involve the entire application, ensuring consistency across all features.
> - **Single database** — all components and modules share one centralized data store, simplifying data management and access.

### Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Simple to develop and deploy at small scale | Hard to scale individual parts independently |
| One codebase = easy debugging and tracing | Codebase grows complex over time |
| Strong consistency, single transaction boundary | A single bug can bring down the whole app |
| Low operational overhead | Releases are coupled — slower delivery cycles |

## 2. Layered Architecture

A ==layered architecture== organizes the system into horizontal layers, each with a clear responsibility. A typical stack:

- **Presentation Layer** — UI and user interaction
- **Application / Business Logic Layer** — domain rules and orchestration
- **Data Access Layer** — persistence and queries
- **Database Layer** — storage

> [!tip] Rule of Dependency
> Higher layers depend on lower layers, **never the reverse**. This separation makes each layer replaceable and testable in isolation.

Layered architecture is often implemented **inside** a monolith, but it is conceptually independent — microservices can also use layering internally.

## 3. Microservices Architecture

==Microservices== break the application into small, independently deployable services, each owning a focused business capability and (usually) its own data store. Services communicate over the network — typically via HTTP/REST, gRPC, or asynchronous messaging.

### Key Characteristics

> [!info] Defining Traits of Microservices
> - **Independent deployment** — each service is released on its own schedule.
> - **Decentralized data** — every service owns its database; no shared schema.
> - **Polyglot freedom** — services can use different languages or stacks.
> - **Team autonomy** — small teams own services end-to-end.
> - **Failure isolation** — a failing service should not take down the whole system.

### Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Independent scaling per service | High operational complexity (orchestration, observability) |
| Faster, isolated deployments | Distributed transactions are hard |
| Technology diversity | Network latency and partial-failure handling |
| Strong service boundaries | Requires mature DevOps and monitoring |

## Comparison at a Glance

| Aspect | Monolith | Layered | Microservices |
|---|---|---|---|
| Deployment unit | Single | Single (usually) | Many small services |
| Codebase | One | One | Many |
| Database | One shared | One shared | One per service |
| Scaling | Whole app | Whole app | Per service |
| Team structure | Shared | Shared | Autonomous teams |
| Best for | Small/medium apps, MVPs | Apps with clear functional layers | Large, evolving systems with multiple teams |

## When to Choose Which

> [!example] Decision Hints
> - Start with a **monolith** when the domain is small or unclear — it is the fastest path to working software.
> - Use a **layered** approach inside any style to keep responsibilities separated.
> - Move to **microservices** only when scaling, team autonomy, or independent release cycles become real bottlenecks — not before.

## Summary

Looking at these styles side by side shows that there is no universally "best" architecture: each is a trade-off between **simplicity, scalability, and autonomy**. The monolith favors simplicity and consistency, the layered style favors separation of concerns, and microservices favor independence and scale at the cost of operational complexity.

## Related Notes

- [[Architectural Style and Pattern]]
- [[Architectural Design Principles]]
- [[Coupling and Cohesion]]
- [[Stateful vs Stateless]]


![[Pasted image 20260413124548.png]]