---
title: "Notation in Solution Architecture: Types of Notation"
date: 2026-04-25
tags:
  - module6
  - architecture
  - notation
  - canvas-note
cssclasses:
  - canvas-note
---

# Notation in Solution Architecture: Types of Notation

> [!note] Overview
> ==Notation== in solution architecture is a visual language used to show parts of a system and how they connect. It helps teams and stakeholders understand and communicate complex ideas in a clear and standard way. Notations usually include ==diagrams, symbols, and rules== representing components, interactions, data flows, and other important details.

## 1. Informal Notations

==Informal notations== are the most common and accessible type of notation in solution architecture.

### Key Characteristics

> [!info] Defining Traits
> - No rigid rules for visual elements
> - Allow creative expression and flexibility
> - Prioritize clarity and simplicity over standardization
> - Accessible to non-technical audiences

### Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Easy to understand by customers and stakeholders | Lack of standardization may cause ambiguity |
| No expertise required to read or produce | Different authors may use inconsistent symbols |
| Fast to create and iterate on | Hard to enforce consistency across teams |
| Flexible — adapted to audience needs | May not convey enough precision for complex systems |

> [!example] When to Use
> Use informal notations when communicating with business stakeholders, during early ideation, or whenever clarity for a non-technical audience matters more than precision.

---

## 2. Semi-Formal Notations

==Semi-formal notations== follow standardized conventions with prescribed graphical elements and rules.

### Key Characteristics

> [!info] Defining Traits
> - Follow standardized conventions and graphical elements
> - Predefined symbols with defined meanings
> - Rules exist but some flexibility is retained
> - More commonly used among technical professionals

### Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Enhanced consistency across diagrams | Less familiar to non-technical stakeholders |
| Facilitates communication among technical teams | Requires learning the notation conventions |
| Strikes balance between formality and usability | Still allows some ambiguity compared to formal notations |
| Wide tooling support (e.g., UML, ArchiMate, C4) | May feel overly rigid for early design phases |

> [!example] When to Use
> Use semi-formal notations when collaborating with technical teams, documenting architecture for handoff, or when consistency and shared understanding across engineering roles are required.

---

## 3. Formal Notations

==Formal notations== are the most precise and rigorous type, rooted in mathematical or logical foundations.

### Key Characteristics

> [!info] Defining Traits
> - Based on strict mathematical or logical rules
> - Every element has a precise, unambiguous meaning
> - Require specialized tools and expertise to produce and read
> - Particularly valuable in hardware systems engineering and safety-critical domains

### Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Highest precision — no ambiguity | Steep learning curve and specialized expertise needed |
| Enables formal verification of system properties | Often requires specialized tooling |
| Suitable for safety-critical and hardware systems | Not accessible to non-specialist audiences |
| Machine-readable in many cases | Time-consuming to produce and maintain |

> [!example] When to Use
> Use formal notations in hardware systems engineering, safety-critical domains (avionics, medical devices), or when automated verification of system properties is required.

---

## Comparison at a Glance

| Aspect | Informal | Semi-Formal | Formal |
|---|---|---|---|
| **Rules** | None / flexible | Standardized conventions | Strict mathematical rules |
| **Audience** | Everyone, incl. non-technical | Technical professionals | Specialists |
| **Precision** | Low | Medium | High |
| **Accessibility** | Very high | Medium | Low |
| **Tooling required** | None | Optional | Often required |
| **Common examples** | Whiteboard diagrams, free-form boxes | UML, ArchiMate, C4 Model | Z notation, Petri nets |
| **Best for** | Early design, stakeholder comms | Technical documentation | Safety-critical, hardware systems |

---

## When to Choose Which

> [!example] Decision Hints
> - **Choose Informal** when speed and accessibility matter — stakeholder workshops, early brainstorming, or customer-facing presentations.
> - **Choose Semi-Formal** when collaborating with technical teams on architecture docs, API design, or system handoffs.
> - **Choose Formal** when working on safety-critical systems, hardware engineering, or when formal verification of correctness is required.

---

## Summary

Notation is the shared language of solution architecture. ==Informal notations== prioritize accessibility and flexibility; ==semi-formal notations== balance structure with usability for technical teams; ==formal notations== provide maximum precision for complex, safety-critical domains. Architects, developers, and project managers rely on these notation types to communicate requirements, decisions, and designs clearly and consistently across stakeholders.

## Related Notes

- [[Architectural Style and Pattern]]
- [[Architectural Design Principles]]
