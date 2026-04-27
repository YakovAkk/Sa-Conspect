---
title: "Layered Architecture"
date: 2026-04-13
tags:
  - module5
  - architecture
  - layered
  - canvas-note
aliases:
  - Layered Style
  - N-Tier Architecture
cssclasses:
  - canvas-note
---

# Layered Architecture

> [!note] Overview
> ==Layered architecture== is one of the most common and simple styles in software development. Components are organized into ==horizontal layers==, each with a distinct responsibility. It is typically lower-cost to build than more distributed patterns and supports a clear separation of concerns.

## What is Layered Architecture

In a layered architecture, the application is divided into horizontal tiers. Each layer has a well-defined role and **only communicates with the layer directly below it** — this is the core rule of the pattern.

The design supports **independence between layers**: layers can be developed, tested, and replaced individually as long as the interface between them stays consistent.

## The Four Layers

### 1. Presentation Layer

The **presentation layer** is responsible for managing user interactions with the software.

> [!info] Presentation Layer
> - Defines the application's overall appearance and presents it to end-users.
> - Can be accessed through client devices: desktop, laptop, mobile phone, or tablet.
> - Does **not** contain business logic — it delegates processing to the layer below.

### 2. Business Layer

The **business layer** (also called the ==domain layer==) determines the behavior of the entire application.

> [!info] Business Layer
> - Contains the core logic and rules based on the organization's guidelines.
> - Acts as the brain of the application — all significant decisions happen here.
> - Sits between the presentation layer above and the persistence layer below.

### 3. Persistence Layer

The **persistence layer** (also called the ==data access layer==) acts as a protective shield between business logic and the database.

> [!info] Persistence Layer
> - Contains the code to access and communicate with the database layer.
> - Holds the code that allows manipulation of database records (create, read, update, delete).
> - Abstracts the database implementation details from the business layer.

### 4. Database Layer

The **database layer** is where the system stores all data.

> [!info] Database Layer
> - Stores indexes, tables, and application data.
> - Facilitates frequent search, insert, update, and delete operations.
> - Data may be stored in a file system or a database server.

### Layer Summary

| Layer | Also Known As | Responsibility |
|---|---|---|
| Presentation | UI layer | User interaction and display |
| Business | Domain layer | Application logic and rules |
| Persistence | Data access layer | Database communication |
| Database | Storage layer | Data storage and retrieval |

## Rules and Flexibility

### Strict Layering

In a **strictly layered** structure, each layer can **only use the services of the layer directly below it**. This enforces clean separation but can add overhead when a top layer needs data from a lower layer without involving intermediate layers.

### Open/Closed Principle

> [!tip] Open/Closed Principle in Layered Architecture
> In Solution Architecture, the ==Open/Closed Principle== means a class or module should:
> - Be **open for extension** — new features can be added.
> - Be **closed for modification** — existing code should not need to change to accommodate new features.
>
> This keeps each layer stable while allowing the system to grow.

### Layer Bridging

> [!example] SEI Layer Bridging Model
> The Software Engineering Institute (SEI) introduces a concept called ==layer bridging==: a model with **five vertical layers** that **allows skipping intermediate layers** when needed. This gives more flexibility, reducing the performance cost of passing data through layers that do not need to touch it.

In practice, most implementations **relax the strict rule** and allow some flexibility depending on the architecture's needs.

## Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Simple and well-understood pattern | Can become rigid in larger systems |
| Lower development cost than distributed styles | Risk of "sinkhole anti-pattern" (requests pass through layers with no processing) |
| Clear separation of concerns | Scaling the full stack even for one layer's bottleneck |
| Easier to test each layer in isolation | Changes in one layer can ripple upward |
| Good fit for CRUD-heavy applications | Not ideal for high-throughput or highly distributed systems |

## Summary

Layered architecture is a practical and accessible style that brings structure to an application by separating concerns into distinct horizontal tiers. The strict top-to-bottom dependency rule keeps layers decoupled, but most real implementations allow some flexibility through layer bridging or relaxed rules. It remains a solid default for applications where simplicity, maintainability, and a clear team structure matter more than fine-grained scalability.

## Related Notes

- [[Architectural Style - Monolith, Layered and Microservices]]
- [[Architectural Style and Pattern]]
- [[Architectural Design Principles]]
- [[Coupling and Cohesion]]