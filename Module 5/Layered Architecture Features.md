---
title: "Layered Architecture Features"
date: 2026-04-13
tags:
  - module5
  - architecture
  - layered
  - canvas-note
aliases:
  - Layered Architecture Characteristics
cssclasses:
  - canvas-note
---

# Layered Architecture Features

> [!note] Overview
> The ==layered architectural style== organizes components into separate horizontal layers, each with a specific role such as managing presentation or business logic. This separation clearly divides responsibilities between layers and components, making the system easier to understand and evolve.

## Key Features

### Logical and Physical Separation

> [!info] Two Forms of Layering
> Layered architecture can exist in two forms:
> - **Logical layers** — a conceptual separation in the codebase. Layers are distinct modules but may run on the same machine.
> - **Physical layers (tiers)** — a deployment separation. Layers run on separate machines or infrastructure (e.g., a web server, an application server, a database server).
>
> Logical and physical layering can be combined: logically separated layers are also physically deployed to different tiers when scalability or security requires it.

### Stacking — Each Layer on Top of Another

Components are stacked vertically: each layer sits on top of the layer it depends on. The flow of control moves **top-down** (from user-facing layers toward data storage), while data flows back **bottom-up** in responses.

```
Presentation Layer
      ↓
Business Layer
      ↓
Persistence Layer
      ↓
Database Layer
```

### Well-Defined Interfaces Between Layers

> [!tip] Interface Contract
> Each layer exposes a ==well-defined interface== to the layer above it. This contract means:
> - The layer above does not need to know how the layer below is implemented.
> - Layers can be replaced or refactored independently as long as the interface stays the same.
> - Testing each layer in isolation becomes practical.

### Modularity, Reusability, and Maintainability

> [!info] Development Benefits
> - **Reduces complexity** — developers can focus on one layer without understanding the full system.
> - **Improves modularity** — each layer is a self-contained unit with a clear responsibility.
> - **Reusability** — a well-defined business or persistence layer can be reused across different presentation interfaces (web, mobile, API).
> - **Maintainability** — changes in one layer do not cascade to unrelated layers, reducing the risk of introducing bugs.

Developers can work on one part of the application without understanding the details of other layers. This ==separation of concerns== improves code readability, reusability, and overall system flexibility.

### Performance Trade-off

> [!warning] Performance Impact
> Each layer adds a level of indirection. In a strict layered architecture, every request must pass through all intermediate layers — even if a layer does nothing useful for that request. This is known as the ==sinkhole anti-pattern==.
>
> **Impact**: more layers = more function calls, more object mapping, and more latency per request. This is a known trade-off accepted in exchange for clean separation.

### Criteria for Layering: Abstraction

> [!example] Abstraction as the Primary Criterion
> The most common criterion for deciding how to divide layers is ==abstraction level==:
> - Higher layers operate at a **higher level of abstraction** (user-facing concepts, domain logic).
> - Lower layers operate at a **lower level of abstraction** (database queries, file I/O, network calls).
>
> Other criteria can include: security boundary, team ownership, rate of change, or deployment unit.

## Feature Summary

| Feature | Benefit |
|---|---|
| Logical and physical separation | Flexibility to co-locate or distribute layers |
| Stacked hierarchy | Clear, predictable flow of control |
| Well-defined interfaces | Independent development and testing per layer |
| Separation of concerns | Easier to understand, modify, and maintain |
| Modularity and reusability | Layers can be reused across different interfaces |
| Abstraction-driven design | High-level logic stays separate from low-level details |
| Performance cost | Known trade-off — accept it consciously |

## Summary

Layered architecture's defining features — stacked layers, well-defined interfaces, and abstraction-driven separation — make it one of the most maintainable styles for building structured applications. These features support modularity and allow teams to work independently on different parts of the system. The main trade-off is performance overhead, which is worth understanding before committing to a strictly layered design.

## Related Notes

- [[Layered Architecture]]
- [[Architectural Style - Monolith, Layered and Microservices]]
- [[Coupling and Cohesion]]
- [[Architectural Design Principles]]