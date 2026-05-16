---
title: "Semi-Formal Notations: UML Diagrams Overview"
date: 2026-04-28
tags:
  - module6
  - uml
  - semi-formal
  - notation
  - canvas-note
cssclasses:
  - canvas-note
---

# Semi-Formal Notations: UML Diagrams Overview

> [!note] Overview
> ==UML (Unified Modeling Language)== provides a standard way to represent complex system designs visually. It includes different types of diagrams, each designed to show specific aspects of a system. UML diagrams fall into two broad categories: ==Structural== (what the system is made of) and ==Behavioral== (how the system works and how its parts interact).

---

## Structural Diagrams

==Structural diagrams== show the detailed structure of a system's architecture — its components, their organization, and their relationships.

### 1. Composite Structure Diagram

A ==Composite Structure Diagram== illustrates the **internal structure of a classifier**, showcasing how various elements collaborate within it.

> [!info] Key Facts
> - Shows internal parts and their connectors
> - Emphasizes collaboration between elements within a single component
> - Useful for modeling complex components with sub-parts

**Use:** Ideal for visualizing complex systems and their interdependencies — especially when you need to show how internal elements of a single class or component work together.

---

### 2. Package Diagram

A ==Package Diagram== represents the **organization and arrangement of model elements into packages**, aiding system modularization.

> [!info] Key Facts
> - Groups related classes, interfaces, and other elements into named packages
> - Shows dependencies between packages
> - Supports high-level system decomposition

**Use:** Helpful for managing and visualizing the structure of large-scale systems — shows how the codebase or model is organized into modules and what depends on what.

---

### 3. Component Diagram

A ==Component Diagram== depicts the **components of a system, their interactions, and relationships**, emphasizing the physical aspects of the architecture.

> [!info] Key Facts
> - Shows replaceable, deployable parts of a system
> - Highlights interfaces (provided and required)
> - Emphasizes composition and physical boundaries

**Use:** Useful for understanding the composition and dependencies among components — particularly for system deployment planning and interface design.

---

## Behavioral Diagrams

==Behavioral diagrams== focus on how the system works — the dynamic aspects: how objects interact, change state, and flow through processes.

### 4. State Machine Diagram

A ==State Machine Diagram== illustrates the **dynamic behavior of an object over time**, portraying various states and transitions between them.

> [!info] Key Facts
> - Models objects that have distinct states (e.g., Order: pending → confirmed → shipped → delivered)
> - Shows events (triggers), guards (conditions), and actions
> - Captures lifecycle of a single object or component

**Use:** Valuable for modeling complex systems with distinct operational states — especially order management, device lifecycles, or protocol behavior.

---

### 5. Use Case Diagram

A ==Use Case Diagram== represents the **interactions between external actors and a system**, focusing on its functionalities from the user's perspective.

> [!info] Key Facts
> - Shows actors (users, systems) and their goals (use cases)
> - Captures system boundary and scope
> - Does not show implementation details

**Use:** Excellent for capturing and communicating system requirements from a user's perspective — often used in early requirements gathering and stakeholder communication.

---

### 6. Activity Diagram

An ==Activity Diagram== describes the **flow of activities within a system**, emphasizing the sequence and conditions of actions.

> [!info] Key Facts
> - Similar to a flowchart, but richer (supports parallel flows, swimlanes, forks/joins)
> - Shows decision points, loops, and concurrent paths
> - Can model both business processes and software algorithms

**Use:** Useful for modeling dynamic aspects of a system, especially business processes, workflows, and complex multi-step operations.

---

### 7. Sequence Diagram

A ==Sequence Diagram== illustrates the **interactions and order of messages between objects over time**, focusing on time-based relationships.

> [!info] Key Facts
> - Shows objects as vertical lifelines
> - Messages are horizontal arrows ordered top-to-bottom (time flows downward)
> - Highlights the chronological sequence of method calls or events

**Use:** Essential for visualizing the chronological flow of processes and communication among objects — commonly used to document API interactions, service calls, and complex flows.

---

## Comparison at a Glance

| Diagram | Category | Primary Focus | Typical Use |
|---|---|---|---|
| Composite Structure | Structural | Internal structure of a component | Complex internal collaboration |
| Package | Structural | Module organization and dependencies | Large-scale system decomposition |
| Component | Structural | Physical components and interfaces | Deployment and interface planning |
| State Machine | Behavioral | Object lifecycle and state transitions | Order management, device lifecycle |
| Use Case | Behavioral | Actor-system interactions | Requirements gathering, stakeholder docs |
| Activity | Behavioral | Workflow and process flow | Business processes, algorithms |
| Sequence | Behavioral | Chronological message order | API flows, service interactions |

---

## When to Choose Which

> [!example] Decision Hints
> - Use **Composite Structure** when you need to show how the internals of a single complex component collaborate
> - Use **Package** when organizing a large codebase into modules and mapping dependencies
> - Use **Component** when planning deployment units or designing interface contracts between parts
> - Use **State Machine** when an entity has a well-defined lifecycle with distinct states
> - Use **Use Case** in early requirements phases to align with stakeholders on system scope
> - Use **Activity** to model business processes, workflows, or multi-path algorithms
> - Use **Sequence** to document step-by-step flows between services or objects

---

## Summary

UML diagrams are divided into ==structural== (what the system is) and ==behavioral== (how the system works) categories. Structural diagrams — Composite Structure, Package, Component — describe architecture and organization. Behavioral diagrams — State Machine, Use Case, Activity, Sequence — describe dynamics and interactions. Over the years, UML has developed by adding clarity and consistency improvements while still supporting older versions. Choosing the right diagram type depends on the aspect of the system you need to communicate.

---

## Related Notes

- [[Semi-Formal Notations - Unified Modeling Language]]
- [[Semi-Formal Notations]]
- [[Notation in Solution Architecture - Types of Notation]]
