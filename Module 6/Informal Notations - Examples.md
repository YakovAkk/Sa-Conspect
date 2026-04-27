---
title: "Informal Notations: Examples"
date: 2026-04-25
tags:
  - module6
  - architecture
  - notation
  - canvas-note
cssclasses:
  - canvas-note
---

# Informal Notations: Examples

> [!note] Overview
> Informal notation diagrams appear across a wide range of contexts — from enterprise web hosting diagrams to Android platform architecture and whiteboard sketches. A common thread across all examples is the importance of a ==key (legend)==: without one, even experienced readers may misinterpret shapes, colors, and line styles. With proper explanation, nearly anyone can interpret these diagrams.

## The Role of a Key (Legend)

Including a ==key== in an informal notation diagram is critical. It defines the meaning of:

> [!info] What a Key Should Explain
> - **Shapes** — what each box, circle, cylinder, or icon represents
> - **Colors** — whether color encodes type, layer, status, or redundancy
> - **Borders and line styles** — solid vs. dashed, thick vs. thin
> - **Arrow types** — direction of data flow, dependency, or communication

> [!warning] Without a Key
> A diagram that uses shapes, colors, and lines without a key leaves room for ambiguity. Readers may understand the structure but remain unclear on the specific meaning behind each visual element.

---

## Example 1 — Shapes, Colors, and Lines Without a Key

This example uses semantics encoded through shapes, colors, and lines to represent an architecture. However, the ==absence of a key== leaves ambiguity: readers familiar with architecture visualizations may infer meaning, but those without context cannot be certain.

![[Pasted image 20260425222552.png]]
> [!example] Lesson
> Even experienced architects may disagree on interpretation without a key. Always pair a diagram with a legend or written explanation.

---

## Example 2 — Web Hosting Architecture

A diagram illustrating web hosting architecture using informal notations. Two notable patterns are visible:

> [!info] Key Elements in This Diagram
> - **Special cubes** — used to encode specific types of storage; a corresponding note explains what each cube means
> - **Redundancy indicators** — duplicate components shown explicitly to communicate fault tolerance
> - **Recognizable conventions** — elements that are familiar to people with architecture experience, even without a formal key


![[Pasted image 20260425222607.png]]

> [!tip] Takeaway
> When the audience is technically literate, informal diagrams can rely on ==domain conventions== (e.g., cylinder for database, cloud shape for internet) as a lightweight substitute for a full key.

---

## Example 3 — Context-Dependent Diagram

This diagram may appear ==cryptic== to someone lacking context. However, with a proper verbal or written explanation, even individuals without specialized training can interpret it effortlessly.

> [!example] Lesson
> Informal notations are presentation-dependent. The diagram itself is only half the communication — the accompanying explanation is equally important. This makes informal notation well-suited for live presentations or workshops, less so for asynchronous documentation.

![[Pasted image 20260425222617.png]]
---

## Example 4 — Android Platform Architecture

Sourced from the Android developer website, this diagram visualizes a ==platform architecture== using simple shapes and colors. It demonstrates that informal notation can scale to real-world, production-grade documentation.

> [!info] What This Diagram Communicates
> - **Layers** — horizontal bands separating system levels (hardware, kernel, middleware, application)
> - **Components** — named boxes within each layer representing distinct modules or subsystems
> - **Implicit interactions** — visual proximity and layout imply relationships without explicit arrows
> - **Established rules** — consistent use of color and shape across the diagram creates implicit conventions

> [!tip] Takeaway
> Large organizations (like Google) use informal notation for public developer documentation precisely because it is ==accessible without prerequisites==. The diagram communicates structure to a broad developer audience without requiring knowledge of UML or ArchiMate.



![[Pasted image 20260425222627.png]]

## Example 5 — Whiteboard Diagram

Even a diagram drawn on a ==whiteboard with a single-color marker== qualifies as informal notation.

### Application Overview as a Whiteboard Test

An ==application overview== is a lightweight informal diagram that makes architecture tangible by connecting it to real-world constraints and decisions. Building one involves:

> [!info] Steps to Create an Application Overview
> 1. **Determine the application type** — web, mobile, desktop, service, embedded
> 2. **Understand deployment constraints** — cloud, on-premise, hybrid, edge
> 3. **Identify key architectural styles** — monolith, layered, microservices, event-driven
> 4. **Select relevant technologies** — frameworks, databases, messaging systems

> [!example] The Whiteboard Litmus Test
> A useful application overview should be ==explainable on a whiteboard==. If a diagram cannot be conveyed in a 5-minute whiteboard sketch, it may be too complex or insufficiently distilled. This test ensures the architecture is understood — not just documented.

![[Pasted image 20260425222836.png]]


## Tooling and Sharing

> [!tip] Why Informal Diagrams Work Well with Presentation Tools
> - **PowerPoint / Google Slides** are available on all major platforms (PC and Mac), making diagrams easy to share, view, and present without specialized software
> - **No viewer installation required** — recipients can open files immediately
> - **Editable by anyone** — no notation expertise needed to update or annotate
>
> **Key limitation**: without a legend, the meaning of visual elements may not be clear to readers who were not present during the original presentation.

---

## Summary

Informal notation examples span from whiteboard sketches to production Android architecture documentation. Across all five examples, two principles hold:
1. ==A key (legend) is essential== — without it, even well-structured diagrams invite misinterpretation.
2. ==Context and explanation matter== — informal diagrams are best paired with verbal or written descriptions, especially for asynchronous audiences.

The whiteboard litmus test is a practical tool: if an architecture overview cannot be sketched and explained on a whiteboard in minutes, it likely needs further simplification before being communicated to a broader audience.

## Related Notes

- [[Informal Notations]]
- [[Notation in Solution Architecture - Types of Notation]]
