---
title: "Informal Notations"
date: 2026-04-25
tags:
  - module6
  - architecture
  - notation
  - canvas-note
cssclasses:
  - canvas-note
---

# Informal Notations

> [!note] Overview
> ==Informal notations== use simple, free-form diagrams to show software architecture. Created with general-purpose tools, they are designed to explain ideas to a broad audience — including customers and stakeholders who may not have strong technical knowledge or need a detailed formal diagram. Their defining strength is ==accessibility==; their key limitation is potential ambiguity.

![[Pasted image 20260425220954.png]]
## 1. Free-Form Creation

==Free-form creation== means there are no rigid templates or prescribed layouts. Architects and designers can structure diagrams however best communicates the concept at hand.

> [!info] Defining Traits
> - Diagrams are shaped by the author's intent, not a formal standard
> - Layouts, groupings, and flows can be invented on the fly
> - No required tools or software — anything from a whiteboard to PowerPoint works
> - Easy to iterate rapidly during early design stages

### Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Maximum flexibility in how ideas are expressed | Different authors may produce wildly inconsistent diagrams |
| Fast to create and easy to update | Hard to enforce team-wide diagramming standards |
| No learning curve for tools or notation rules | Risk of important detail being omitted or misrepresented |

---

## 2. No Visual Conventions

Unlike formal notations, informal notations have ==no strict visual conventions== — no predefined rules govern which shapes, colors, or line styles must be used.

> [!info] Defining Traits
> - Boxes, circles, arrows, and labels are used freely without standardized meaning
> - Colors and shapes are chosen for clarity rather than specification compliance
> - The same shape may mean different things in different diagrams by different authors
> - Interpretation depends on context and accompanying explanation

### Strengths and Trade-offs

| Strengths                                                         | Trade-offs                                           |
| ----------------------------------------------------------------- | ---------------------------------------------------- |
| Authors choose symbols that feel most intuitive                   | Symbols carry no universal agreed meaning            |
| Reduces friction for stakeholders unfamiliar with formal notation | Reader may misinterpret elements without explanation |
| Encourages creative and context-specific representations          | Cannot be parsed or validated by automated tools     |

---

## 3. Lack of Formal Analysis

==Lack of formal analysis== means informal notations do not provide structured mechanisms for checking correctness, completeness, or consistency of the diagram.

> [!info] Defining Traits
> - No rules to verify architectural decisions against
> - Suitable for visual exploration and communication, not rigorous scrutiny
> - Errors, gaps, or contradictions may go undetected
> - Analysis relies entirely on human review and discussion

> [!warning] Limitation
> Because informal diagrams cannot be formally analyzed, they are not suitable for safety-critical domains, compliance documentation, or scenarios where architectural correctness must be proven.

### Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Great for exploration and "good enough" communication | Cannot catch inconsistencies or missing elements systematically |
| Low overhead — no tooling needed for analysis | Quality depends entirely on the author's expertise and diligence |
| Encourages discussion and iteration | May propagate misunderstandings if the audience misreads the diagram |

---

## 4. Accessibility to Non-Technical Audience

==Accessibility== is the primary advantage of informal notations. They are specifically designed to be understandable by non-technical individuals — facilitating communication with business stakeholders, customers, and project managers.

> [!info] Defining Traits
> - Plain language labels and intuitive shapes replace technical symbols
> - No prerequisite knowledge of notation standards required
> - Diagrams act as a conversation starter, not a formal specification
> - Work well in workshops, presentations, and stakeholder meetings

### Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Bridges the gap between technical teams and business stakeholders | May sacrifice precision needed by developers or engineers |
| Speeds up stakeholder alignment and approval | Risk of over-simplification leading to missed requirements |
| Usable in any meeting format (slide deck, whiteboard, email) | May need a companion formal diagram for technical implementation |

---

## Tooling

> [!tip] Common Tools for Informal Notations
> Simple tools are usually sufficient:
> - **PowerPoint / Google Slides** — basic shapes, lines, and text boxes
> - **Whiteboard (physical or digital)** — Miro, Mural, FigJam
> - **Draw.io / Lucidchart** — drag-and-drop without notation constraints
> - **Pen and paper** — fastest for early ideation
>
> No specialized diagramming tool is required.

---

## Summary

Informal notations are the most ==accessible== and ==widely used== type of notation in solution architecture. Their four defining characteristics — free-form creation, absence of visual conventions, lack of formal analysis, and accessibility to non-technical audiences — make them ideal for early-stage communication and stakeholder alignment. Tools as simple as PowerPoint and basic shapes are sufficient. Their main risk is ambiguity: without shared conventions, diagrams can be misread. They are best paired with more rigorous notations when technical precision is required.

## Related Notes

- [[Notation in Solution Architecture - Types of Notation]]
- [[Semi-Formal Notations]]
- [[Formal Notations]]
