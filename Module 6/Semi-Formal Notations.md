---
title: "Semi-Formal Notations"
date: 2026-04-25
tags:
  - module6
  - architecture
  - notation
  - canvas-note
cssclasses:
  - canvas-note
---

# Semi-Formal Notations

> [!note] Overview
> ==Semi-formal notations== use standard symbols and rules for building diagrams but do not fully define the meaning of every element. They are more structured than informal notations yet less mathematically rigorous than formal ones. Each symbol carries a ==built-in meaning==, enabling basic structural checks and making diagrams easier to analyze — but their use requires knowledge of specific rules and dedicated software.

## Key Characteristics

> [!info] Defining Traits
> - **Standardized symbols** — each element has a predefined, agreed-upon meaning within the notation
> - **Rule-governed structure** — diagrams must follow specific construction rules, enabling basic validity checks
> - **Partial formality** — elements are defined, but the full semantics of the diagram are not mathematically proven
> - **Tool-dependent** — creating diagrams requires specialized software (e.g., Visual Paradigm, Enterprise Architect, Camunda Modeler)
> - **Less common than informal** — used primarily by technical professionals familiar with the notation standard

![[Pasted image 20260425223141.png]]

![[Pasted image 20260425223147.png]]

### Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Symbols carry built-in meaning — less ambiguity than informal | Requires learning the notation's rules and conventions |
| Enables basic structural/consistency checks | Requires specialized software to create diagrams |
| Promotes consistency across teams and projects | Less accessible to non-technical stakeholders |
| Widely adopted industry standards (UML, BPMN, ERD) | Each notation has scope limits — may not cover all use cases |
| Supports documentation, communication, and analysis | Choosing the wrong notation for the purpose reduces effectiveness |

---

## 1. UML — Unified Modeling Language

==UML (Unified Modeling Language)== is the most widely known semi-formal notation. It provides a family of diagram types to model different aspects of a software system.

### Key UML Diagram Types

> [!info] Common UML Diagrams
> - **Class Diagram** — structure of classes, attributes, methods, and their relationships
> - **Sequence Diagram** — interactions between objects over time (message passing)
> - **Use Case Diagram** — system functionality from the user's perspective
> - **Component Diagram** — high-level architecture: modules and their dependencies
> - **Activity Diagram** — workflow and process flow within a system
> - **State Machine Diagram** — object lifecycle and state transitions

> [!warning] UML Limitations
> UML was designed for object-oriented software modeling. It has notable limitations:
> - **Not ideal for database relationships** — entity-relationship modeling is better served by ERD
> - **Verbose for process flows** — BPMN is more expressive for business workflows
> - **Tool fragmentation** — different UML tools may render the same diagram slightly differently
>
> Always choose the right diagram type for the specific modeling goal.

---

## 2. BPMN — Business Process Model and Notation

==BPMN (Business Process Model and Notation)== is designed specifically to represent business processes and workflows. It bridges the gap between business stakeholders and technical implementers.

> [!info] Key BPMN Elements
> - **Events** — start, intermediate, and end events that trigger or result from a process
> - **Activities** — tasks and sub-processes representing units of work
> - **Gateways** — decision points (exclusive, inclusive, parallel)
> - **Sequence flows** — ordered connections showing the flow of control
> - **Pools and Lanes** — boundaries representing participants and their responsibilities

> [!tip] When BPMN Shines
> BPMN is most effective for:
> - Modeling end-to-end business workflows
> - Communicating process logic between business analysts and developers
> - Designing integration flows and orchestration logic
> - Process automation documentation (e.g., for BPMS/workflow engines like Camunda)

---

## 3. ERD — Entity-Relationship Diagram

==ERD (Entity-Relationship Diagram)== is used to model data structures — specifically, how entities (objects or concepts) relate to each other within a system or database.

> [!info] Key ERD Elements
> - **Entities** — objects or concepts (e.g., Customer, Order, Product)
> - **Attributes** — properties of an entity (e.g., Customer Name, Order Date)
> - **Relationships** — associations between entities (e.g., Customer *places* Order)
> - **Cardinality** — the numeric nature of a relationship (one-to-one, one-to-many, many-to-many)

> [!tip] When ERD Shines
> - Designing or documenting relational database schemas
> - Communicating data models between architects, developers, and DBAs
> - Capturing domain entities during early requirements modeling

---

## Comparison at a Glance

| Aspect | UML | BPMN | ERD |
|---|---|---|---|
| **Primary purpose** | Software system modeling | Business process modeling | Data/entity relationship modeling |
| **Audience** | Software engineers, architects | Business analysts, developers | DBAs, data architects, developers |
| **Diagram types** | 14+ diagram types | Process/workflow diagrams | Entity-relationship diagrams |
| **Best for** | Class structure, behavior, components | Workflows, orchestration, automation | Database schemas, data models |
| **Limitations** | Poor for process flows and DB relations | Not designed for software structure | Focused on data only — not behavior |

---

## Limitations of Semi-Formal Notations for Architecture

> [!warning] Known Limits
> Semi-formal notations face three recurring constraints when used for architecture documentation:
> 1. **Rule knowledge required** — authors must understand the notation's conventions; errors are harder to spot than in informal diagrams
> 2. **Special software required** — diagrams cannot be drawn on a whiteboard or in PowerPoint without losing notation fidelity
> 3. **Scope awareness required** — each notation has a specific domain; misapplying one (e.g., using UML for DB relationships) yields incomplete or misleading results

---

## When to Choose Semi-Formal Notations

> [!example] Decision Hints
> - **Choose UML** when modeling object-oriented software structure, behavior, or component architecture for a technical audience
> - **Choose BPMN** when documenting or designing business processes, integration workflows, or automation logic
> - **Choose ERD** when designing or communicating relational database schemas or domain data models
> - **Avoid semi-formal when** the audience is non-technical and accessibility matters more than precision — use informal instead
> - **Avoid semi-formal when** you need provable correctness or formal verification — use formal notation instead

---

## Summary

Semi-formal notations occupy the middle ground between informal flexibility and formal rigor. Their standardized symbols and rule-governed structure make them more consistent and analyzable than informal diagrams, while remaining more approachable than formal mathematical notations. ==UML==, ==BPMN==, and ==ERD== are the three most commonly used standards, each optimized for a different modeling domain. Effective use requires choosing the right notation for the purpose, learning its rules, and using appropriate tooling.

## Related Notes

- [[Notation in Solution Architecture - Types of Notation]]
- [[Informal Notations]]
- [[Formal Notations]]
