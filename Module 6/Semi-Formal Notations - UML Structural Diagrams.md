---
title: "Semi-Formal Notations: UML Structural Diagrams"
date: 2026-04-28
tags:
  - module6
  - uml
  - structural-diagrams
  - semi-formal
  - notation
  - canvas-note
cssclasses:
  - canvas-note
---

# Semi-Formal Notations: UML Structural Diagrams

> [!note] Overview
> ==Structural diagrams== in UML clearly show how a system is built and organized. They focus on the physical parts, internal structures, and how different components are connected. The components these diagrams work with include ==classes, objects, packages/modules, physical nodes, components, and interfaces==. Structural diagrams serve as visual documentation — showing how different system parts are connected and arranged, forming the foundation and layout of a software system.

---

## 1. Composite Structure Diagram

A ==Composite Structure Diagram== illustrates the **internal structure of a component**, visualizing how classifiers interact with their environment via ==ports==. It captures a collaboration's dynamic behavior, showcasing the system's relationships and operations.

### Key Elements

> [!info] Defining Traits
> - **Components** — the enclosing classifiers being described
> - **Parts** — internal instances that make up the component
> - **Ports** — interaction points between the component and its environment
> - **Connectors** — links between parts or between parts and ports
> - **Usages** — dependencies between parts

### Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Shows internal collaboration not visible in class diagrams | Can become complex for large classifiers |
| Captures both structure and communication pathways | Requires detailed knowledge of internal design |
| Ideal for component-level design documentation | Less familiar to non-technical stakeholders |

**Use:** Ideal for visualizing complex systems and their interdependencies — especially when you need to see how elements inside a single component work together and interact with the outside world through ports.

---

## 2. Deployment Diagram

A ==Deployment Diagram== offers a **visual representation of the distribution of software artifacts across deployment targets**, providing insights into the architecture at both the specification and instance levels.

### Key Elements

> [!info] Defining Traits
> - **Nodes** — physical or virtual execution environments (servers, devices, containers)
> - **Artifacts** — deployable software units (executables, libraries, config files)
> - **Communication paths** — connections between nodes
> - **Deployment specifications** — configuration details for deploying artifacts

### Two Levels of Detail

| Level | Focus |
|---|---|
| **Specification level** | Describes the architecture in terms of node types and artifact types |
| **Instance level** | Shows specific named instances (e.g., a specific server and its deployed app) |

### Primary Utility

> [!info] What Deployment Diagrams Analyze
> - **Performance** — how distribution affects response time and throughput
> - **Availability** — redundancy and failover topology
> - **Security** — network zones, firewalls, and trust boundaries
> - **Infrastructure structure** — which software runs where

**Use:** Useful for analyzing performance, availability, security, and infrastructure structure — communicating how software components are deployed across the physical or virtual environment.

---

## 3. Package Diagram

A ==Package Diagram== provides a **visual depiction of the structural organization of a designed system at the package level**, aiding system modularization.

### Key Elements

> [!info] Defining Traits
> - **Packages** — named groupings of related model elements (classes, interfaces, sub-packages)
> - **Dependencies** — relationships showing that one package relies on another
> - **Package imports** — one package makes elements of another accessible
> - **Package merges** — content of one package is merged into another

### Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Provides high-level architectural overview | Does not show runtime behavior |
| Clarifies module boundaries and dependencies | Dependency arrows can clutter large diagrams |
| Helps manage large-scale systems | Package merges are complex and rarely used |

**Use:** Helpful for managing and visualizing the structure of large-scale systems — shows how the codebase is organized into modules and which modules depend on each other, enhancing understanding of overall architecture and its interconnections.

---

## 4. Component Diagram

A ==Component Diagram== visually represents the **components within a system**, showcasing their provided and required interfaces, ports, and the relationships that connect them.

### Key Elements

> [!info] Defining Traits
> - **Components** — modular, deployable, replaceable parts of a system
> - **Interfaces** — provided (what the component offers) and required (what it needs)
> - **Ports** — named interaction points that group interfaces
> - **Connectors** — wires linking a required interface to a provided interface
> - **Dependencies** — directional relationships between components
> - **Usages** — one component uses the services of another

### Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Shows system composition and interface contracts | Does not show internal implementation |
| Highlights coupling between components | Large systems produce visually complex diagrams |
| Supports component-based development planning | Requires agreed interface definitions upfront |

**Use:** Useful for understanding the composition and dependencies among components — aids in understanding the system's internal structure and facilitates discussions about component-based development and integration.

---

## Comparison at a Glance

| Diagram | Primary Focus | Key Elements | Typical Use |
|---|---|---|---|
| Composite Structure | Internal structure of a single classifier | Parts, ports, connectors | Modeling complex component internals |
| Deployment | Distribution of software across hardware | Nodes, artifacts, paths | Infrastructure and deployment planning |
| Package | Module organization at design level | Packages, dependencies, imports | Large-scale codebase organization |
| Component | Physical components and interface contracts | Components, interfaces, ports | Component-based architecture design |

---

## When to Choose Which

> [!example] Decision Hints
> - Use **Composite Structure** when you need to show the internal workings and port-based interactions of a specific component
> - Use **Deployment** when planning or documenting how software is distributed across servers, containers, or devices
> - Use **Package** when organizing a large design into modules and mapping build/compile-time dependencies
> - Use **Component** when designing interface contracts between replaceable system parts or planning integration

---

## Summary

Structural diagrams in UML form the backbone of architectural documentation. ==Composite Structure== reveals internal collaboration within a component. ==Deployment== maps software to its physical execution environment. ==Package== organizes the design into manageable modules with explicit dependencies. ==Component== describes the high-level architecture as a set of replaceable parts with defined interfaces. Together, these four diagrams provide a complete picture of how a system is structured — from its internal details to its physical deployment.

---

## Related Notes

- [[Semi-Formal Notations - UML Diagrams Overview]]
- [[Semi-Formal Notations - Unified Modeling Language]]
- [[Semi-Formal Notations]]
