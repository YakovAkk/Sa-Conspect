---
title: "Microservice Architecture"
date: 2026-04-13
tags:
  - module5
  - architecture
  - microservices
  - canvas-note
aliases:
  - Microservices
  - MSA
cssclasses:
  - canvas-note
---

# Microservice Architecture

> [!note] Overview
> ==Microservices== are a way of building software based on the ==service-oriented architecture (SOA)== style. There is no single universal definition, but microservices are generally understood as **independent units that handle specific business functions** and expose clear interfaces. They are commonly used in cloud-native and serverless applications.

## What are Microservices

Microservices break an application into **separate, independently deployable services**, each with a focused responsibility and its own lifecycle. The system becomes more complex as the number of services grows, but each individual service remains small, clearly scoped, and loosely connected to others.

> [!tip] Key Idea
> Rather than one large deployable unit, you have **many small services** — each owning its own data, logic, and deployment pipeline. The whole system emerges from their collaboration.

## Core Attributes

### Lightweight Service-Oriented Architecture

Microservices can be thought of as a ==lightweight SOA==: they follow the same principle of exposing services through defined interfaces, but without the heavy enterprise middleware (ESB, orchestration engines) that traditional SOA often requires.

### Compact and Easy to Comprehend

> [!info] Compactness
> - Each service is small enough that a single developer or small team can understand it fully.
> - Smaller scope means faster to test, deploy, and reason about.
> - New versions of a service can be deployed ==swiftly== without touching the rest of the system.

### Loose Coupling, High Cohesion

> [!info] Coupling and Cohesion in Microservices
> - **==Loose coupling==**: services interact through well-defined interfaces (APIs, events). Changing the internals of one service does not break others.
> - **==High cohesion==**: each service groups related functionality together. Everything inside a service serves a single business capability.

### Autonomy

Each service is **autonomous** — it can be:
- Developed independently by a dedicated team.
- Deployed on its own schedule without coordinating with other services.
- Scaled independently based on its own load.

This autonomy ==facilitates frequent deployment of new service versions== without system-wide releases.

### Fault Isolation

> [!tip] Resilience Through Isolation
> A failure in one microservice **should not cascade** to bring down the entire system. Services are designed to handle partial failures gracefully — through circuit breakers, retries, and fallbacks — so the rest of the application continues to function.

### Communication Protocols

Microservices can be accessed and communicate through several protocols:

| Protocol | Style | When Used |
|---|---|---|
| ==REST== (HTTP/HTTPS) | Synchronous | Simple request-response between services |
| ==SOAP== | Synchronous | Legacy integrations, strict contracts |
| ==Event-driven / Message queues== | Asynchronous | Decoupled updates, high-throughput pipelines |
| gRPC | Synchronous (binary) | High-performance internal service calls |

## Challenges

### Scale of Services

> [!warning] N Monoliths → N × M Services
> Migrating from monolithic applications to microservices multiplies the number of deployable units. N apps may become N × M services. Each service has its own build, deploy, monitor, and on-call responsibility.

### System Partitioning

Deciding **how to split** the system into microservices is non-trivial. Poor boundaries (too fine-grained or misaligned with business domains) lead to chatty services, distributed monoliths, or shared databases — defeating the purpose of the architecture.

### Infrastructure Requirements

> [!warning] Operational Overhead
> A production microservices system typically requires:
> - **API Gateway** — single entry point for clients; handles routing, auth, rate limiting.
> - **Service Registry** — keeps track of where each service instance is running.
> - **Load Balancer** — distributes traffic across service instances.
> - **Fault Tolerance / Monitoring** — circuit breakers, health checks, distributed tracing, alerting.
> - **Configuration / Properties Management** — centralized config (e.g., Consul, Spring Cloud Config) so each service does not hard-code its settings.

### Technology Stack Selection

With polyglot freedom comes the risk of fragmentation. Each team may choose different languages, databases, and frameworks. Without governance, operational complexity grows — more toolchains to maintain, more expertise required across the organization.

## Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Independent scaling per service | High operational and infrastructure complexity |
| Autonomous teams and deployments | Distributed transactions are hard to manage |
| Technology diversity (polyglot) | Network latency between services |
| Fault isolation | Requires mature DevOps, observability, CI/CD |
| Easier to understand each service | Hard to understand the system as a whole |
| Frequent, low-risk releases | Service discovery, API versioning overhead |

## When Microservices Make Sense

> [!example] Good Fit Scenarios
> - Large organizations where **team autonomy** and independent release cycles matter.
> - Systems with **significantly different scaling needs** per component (e.g., a video processing service vs. an auth service).
> - **Cloud-native and serverless** environments where infrastructure management is abstracted.
> - Products that have already **proven their domain model** — microservices before clarity leads to expensive re-partitioning.

> [!warning] Anti-Pattern: Premature Microservices
> Starting with microservices on a new, unclear domain often produces a **distributed monolith**: many services that are still tightly coupled, sharing databases and releasing together. Start with a monolith, extract services only when the boundaries become obvious.

## Summary

Microservice architecture trades the simplicity of a single deployable unit for the autonomy, resilience, and scalability of many small independent services. The core attributes — loose coupling, high cohesion, fault isolation, and autonomous deployment — make it powerful for large-scale, evolving systems. The challenges — operational complexity, service partitioning, and infrastructure overhead — mean it should be adopted deliberately, not as a default starting point.

## Related Notes

- [[Architectural Style - Monolith, Layered and Microservices]]
- [[Layered Architecture]]
- [[Coupling and Cohesion]]
- [[Stateful vs Stateless]]
- [[Architectural Design Principles]]