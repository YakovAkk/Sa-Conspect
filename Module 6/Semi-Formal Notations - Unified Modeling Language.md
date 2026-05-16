---
title: "Semi-Formal Notations: Unified Modeling Language"
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

# Semi-Formal Notations: Unified Modeling Language

> [!note] Overview
> The ==Unified Modeling Language (UML)== is a generic developmental modeling language used to analyze, design, and implement software systems. Its purpose is to provide a simple and common method to visualize a software system's inherent architectural properties. UML is a ==semi-formal notation==: it uses standardized symbols with defined meaning, enabling basic structural checks, while remaining accessible to technical teams without requiring mathematical expertise.

## 1. What Is UML

==UML== is a visual modeling language that standardizes the way software systems are described, documented, and communicated across teams. It defines a set of diagram types, symbols, and rules that represent components, interactions, behaviors, and data flows in a consistent, tool-agnostic way.

### Key Characteristics

> [!info] Defining Traits
> - **Generic** — applicable across domains and programming paradigms
> - **Developmental** — used throughout the full software lifecycle (analysis → design → implementation)
> - **Visual** — communicates system structure and behavior through diagrams
> - **Standardized** — governed by the Object Management Group (OMG)
> - **Semi-formal** — symbols carry defined meaning; supports basic structural analysis without full mathematical rigor

### Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Common visual language understood across teams | Diagrams require maintenance as the system evolves |
| Covers both structural and behavioral views | Value is limited in fast-moving Agile projects |
| Supported by a wide range of tools | Learning curve for teams unfamiliar with notation |
| OMG-standardized — enables interoperability | Can become overly complex for simple systems |

---

## 2. History and Evolution

### 1994 — Evolution of Object-Oriented Methods

In 1994, ==Rational Software Corporation== hired ==James Rumbaugh==, who had developed the ==OMT (Object Modeling Technique)== approach for object-oriented analysis (OOA). ==Grady Booch==, already at Rational, had elaborated the ==Booch method== for object-oriented design (OOD). The two began combining their approaches into a **Unified Method**.

### 1995 — Birth of UML

==Ivar Jacobson==, creator of the ==OOSE (Object-Oriented Software Engineering)== method, joined Rational in 1995. The three became collectively known as the **Three Amigos** — noted for frequent methodological debates. UML was formally developed in response to the ==Object Management Group (OMG) Request For Proposal (RFP)==.

> [!info] The Three Amigos
> - **Grady Booch** — Booch method (OOD)
> - **James Rumbaugh** — OMT method (OOA)
> - **Ivar Jacobson** — OOSE method (use cases)

### 1997 — Standardization by OMG

The collaboration produced ==UML 1.0== — a well-defined, expressive, and generally applicable modeling language. In 1997, UML was adopted as a standard by the OMG, with members including Hewlett-Packard and Apple Computer. The adoption was driven by the goal of ensuring ==interoperability== and establishing UML as the common visual language for software development.

### 1997–2005 — UML 1.x: Integration of Notations

UML 1.x integrated notations to support all object-oriented methods. The ==OMT notation== had the dominant influence — using rectangles for classes and objects. The **UML 1.1** release focused on enhancing the clarity of UML 1.0 semantics and incorporating contributions from new partners. The specification underwent further improvements through ==version 1.5==.

### 2005 — UML 2.0

==UML 2.0== was a major revision that introduced significant new diagram types, including object, package, and composite structure diagrams. The ==UML 2.x specification== covers four areas:

> [!info] UML 2.x Specification Areas
> - **Superstructure** — diagram and notation definitions
> - **Infrastructure** — foundational meta-model
> - **OCL (Object Constraint Language)** — formal constraint expressions
> - **UML Diagram Interchange** — standardized diagram interchange format

### 2005 — ISO Publication

In 2005, UML was published by the ==International Organization for Standardization (ISO)== as ==ISO/IEC 19501:2005==, marking it as an internationally recognized standard. UML has since been revised to keep it current.

### Current Versions

| Version | Year | Key Change |
|---|---|---|
| UML 1.0 | 1997 | Initial OMG standard |
| UML 1.5 | ~2003 | Incremental clarity improvements |
| UML 2.0 | 2005 | Major revision — new diagram types |
| UML 2.5 | 2015 | Reorganized into Superstructure/Infrastructure |
| UML 2.5.1 | 2017 | Most recent update |

> [!tip] UML in Agile Contexts
> While UML remains relevant, its value in ==Agile environments== is limited. Continuously updating diagrams as the project progresses may not justify the effort. Teams often use UML selectively — for key architectural views — rather than maintaining a full model.

---

## 3. UML Diagram Types (Overview)

UML defines two broad categories of diagrams:

> [!info] Structural Diagrams (what the system is)
> - **Class Diagram** — classes, attributes, relationships
> - **Object Diagram** — instances at a point in time
> - **Component Diagram** — system components and interfaces
> - **Package Diagram** — groupings and dependencies
> - **Composite Structure Diagram** — internal structure of a component
> - **Deployment Diagram** — hardware/software deployment

> [!info] Behavioral Diagrams (how the system behaves)
> - **Use Case Diagram** — actor-system interactions
> - **Sequence Diagram** — message flow over time
> - **Activity Diagram** — workflows and processes
> - **State Machine Diagram** — state transitions
> - **Interaction Overview Diagram** — overview of interactions
> - **Timing Diagram** — time-constrained behavior
> - **Communication Diagram** — collaboration between objects

---

## When to Choose UML

> [!example] Decision Hints
> - Use UML when teams need a **shared visual language** for software structure and behavior
> - Use **class diagrams** to model domain models or code structure
> - Use **sequence diagrams** to document API interactions or complex flows
> - Use **use case diagrams** for stakeholder communication around system scope
> - Prefer informal notations when speed and accessibility matter more than precision
> - Prefer ArchiMate when modeling enterprise architecture (not just software)

---

## Summary

UML was born in 1994–1995 through the collaboration of Booch, Rumbaugh, and Jacobson at Rational Software. Standardized by the OMG in 1997 and published by ISO in 2005, it became the dominant semi-formal notation for software systems. UML 2.0 (2005) introduced new diagram types that remain the standard today. The latest version is UML 2.5.1 (2017). While powerful, UML is most valuable when selectively applied — maintaining a complete model in fast-moving Agile projects is often impractical.

---

## Related Notes

- [[Semi-Formal Notations]]
- [[Notation in Solution Architecture - Types of Notation]]
- [[Formal Notations - Architecture Analysis and Design Language]]
