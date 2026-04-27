---
title: "Notations Selection"
date: 2026-04-25
tags:
  - module6
  - architecture
  - notation
  - canvas-note
cssclasses:
  - canvas-note
---

# Notations Selection

> [!note] Overview
> Choosing the right notation is as important as understanding each notation type. A solution architect must weigh ==three key factors== before selecting a notation: the viewpoints of all stakeholders, the organization's or project's preferences and tooling constraints, and the specific capabilities and limitations of each notation type. Getting this choice right ensures architectural diagrams communicate clearly to the right audience at the right level of detail.

## 1. Stakeholders' Viewpoints

==Stakeholders' viewpoints== are the first and most critical factor. Every stakeholder group has different needs and different expectations from an architectural diagram.

> [!info] Key Stakeholder Groups and Their Needs
> - **Developers** — need technical depth: component interactions, interfaces, data flows, deployment topology
> - **Project managers** — prefer high-level overviews: scope, major components, dependencies, timelines
> - **End-users** — need to understand what the system does, not how it is built: use case or process flow views
> - **Business stakeholders / clients** — want to see how the system addresses business needs, not implementation details
> - **Operations / DevOps** — need deployment and infrastructure views: environments, scaling, failure paths

> [!tip] Architect's Role
> A solution architect must identify ==who reads the diagram== and tailor the notation to that audience. A single diagram rarely serves all stakeholders — different views for different audiences is the norm, not the exception.

### Practical Guidance

| Audience | Preferred Notation Style | Example |
|---|---|---|
| Non-technical stakeholders | Informal (boxes, arrows, plain labels) | Whiteboard sketch, PowerPoint diagram |
| Business analysts | Semi-formal (process-focused) | BPMN workflow diagram |
| Developers / architects | Semi-formal (structure-focused) | UML class, component, or sequence diagram |
| Data teams | Semi-formal (data-focused) | Entity-Relationship Diagram (ERD) |
| Hardware / safety engineers | Formal | AADL, Z Notation |

---

## 2. Organization / Project Preferences

==Organization or project preferences== define the standards and constraints within which the architect must work. Ignoring these leads to diagrams that are rejected, ignored, or require rework.

> [!info] What to Consider
> - **Mandatory standards** — some organizations require UML; others have corporate notation guidelines
> - **Team familiarity** — the notation is only useful if the team can read and maintain it
> - **Tooling compatibility** — the chosen notation must work with available software (e.g., Confluence, Jira, draw.io, Enterprise Architect)
> - **Integration with existing documentation** — new diagrams should align with existing notation used in the project
> - **Client expectations** — external clients may specify a notation format in contracts or RFPs

> [!warning] Notation Mismatch Risk
> A technically superior notation that no one on the team can read — or that doesn't render in the organization's documentation platform — adds friction rather than clarity. ==Adoption matters as much as precision==.

### Practical Guidance

> [!example] Questions to Ask Before Choosing
> - Does our organization have a formal notation policy?
> - What diagramming tools are already licensed and in use?
> - Can the target audience read and maintain diagrams in this notation?
> - Does the client or project standard specify a notation type?
> - Will this notation integrate with our documentation system (Confluence, Notion, etc.)?

---

## 3. Notation Type Specifics

==Notation type specifics== refer to the inherent capabilities and limitations of each notation family. Matching the notation's strengths to the task's requirements is the technical dimension of the selection decision.

### Formal Notations

> [!info] When Formal Fits
> - Mathematical precision is required
> - Automated verification of correctness is needed
> - Domain: hardware, avionics, medical devices, safety-critical embedded systems
> - Trade-off: complex, slow to produce, inaccessible to non-specialists

### Semi-Formal Notations

> [!info] When Semi-Formal Fits
> - Structure and consistency matter, but mathematical proof is not required
> - Technical audience is familiar with the notation standard (UML, BPMN, ERD)
> - Need to generate artifacts from diagrams (code skeletons, DB schemas)
> - Trade-off: requires tool knowledge, less accessible to non-technical readers

### Informal Notations

> [!info] When Informal Fits
> - Speed and accessibility are the priority
> - Audience is non-technical or mixed
> - Early-stage exploration: whiteboard sessions, workshops, stakeholder presentations
> - Trade-off: ambiguity risk without a legend; not suitable for rigorous analysis

---

## Decision Framework

> [!example] Notation Selection Decision Guide
> **Step 1 — Identify the primary audience:**
> - Non-technical → lean Informal
> - Mixed technical/business → lean Semi-Formal (process-focused)
> - Technical only → Semi-Formal or Formal depending on precision needed
>
> **Step 2 — Check organizational constraints:**
> - Mandatory standard? Follow it.
> - No standard? Choose what the team can read and maintain.
> - Tool constraints? Choose a notation supported by available software.
>
> **Step 3 — Match notation to purpose:**
> - Quick idea sharing → Informal
> - Software structure documentation → UML (Semi-Formal)
> - Business process documentation → BPMN (Semi-Formal)
> - Data model documentation → ERD (Semi-Formal)
> - Safety-critical system specification → Formal (AADL, Z Notation, TLA+)

---

## Comparison at a Glance

| Factor | Informal | Semi-Formal | Formal |
|---|---|---|---|
| **Best audience** | Non-technical, mixed | Technical teams | Specialists |
| **Organizational fit** | No tools needed | Standard tools (Visio, draw.io, EA) | Specialized tools (OSATE, Alloy Analyzer) |
| **Precision** | Low | Medium | High |
| **Speed to produce** | Fast | Moderate | Slow |
| **Analysis support** | None | Basic structural checks | Automated formal verification |
| **Adoption barrier** | Very low | Medium | High |

---

## Summary

Selecting the right notation requires balancing three forces: what ==stakeholders need to understand==, what the ==organization expects and supports==, and what the ==notation type is capable of==. No single notation is universally best — informal diagrams excel at stakeholder communication, semi-formal notations serve technical documentation, and formal notations guarantee correctness in safety-critical systems. A skilled solution architect chooses the notation that best serves the specific communication goal in context.

## Related Notes

- [[Notation in Solution Architecture - Types of Notation]]
- [[Informal Notations]]
- [[Semi-Formal Notations]]
- [[Formal Notations]]
