---
title: "Best Drawing Practices: Less is More"
date: 2026-04-29
tags:
  - module6
  - uml
  - best-practices
  - canvas-note
cssclasses:
  - canvas-note
---

# Best Drawing Practices: Less is More

> [!note] Overview
> ==UML diagrams== are powerful communication tools in software development projects. Six key practices make diagrams clearer, more consistent, and more effective for stakeholder communication. The first and most fundamental rule is **"Less is More"** — keeping diagrams focused and appropriately sized so they remain easy to read and interpret.

## 1. Why Diagram Best Practices Matter

Well-crafted diagrams serve three purposes:

- **Communicate ideas** to stakeholders clearly and efficiently
- **Save time** by highlighting the main points without unnecessary noise
- **Ensure consistency** so every reader reaches the same understanding

> [!info] Six Key Practices
> The six best practices for effective UML diagram creation are:
> 1. **Less is More** ← *this note*
> 2. Use meaningful names
> 3. Maintain consistent notation
> 4. Keep diagrams focused on a single concern
> 5. Add a legend when using custom symbols
> 6. Tailor the diagram to the audience

## 2. Less is More

==Large diagrams with too many elements can be confusing and harder to understand.== Smaller, focused diagrams are usually more effective in showing important information.

### The Core Problem

When a diagram tries to capture everything at once, it:

- Overwhelms the reader before the presentation even begins
- Forces stakeholders to search for the relevant part instead of reading naturally
- Makes it harder to identify the main point or key decision
- Becomes unreadable when printed on standard paper (A4 / Letter)

### The Practical Test

> [!tip] A4 Printability Rule
> A well-balanced diagram should remain **clear and easy to read even when printed on one A4 page**. If it does not fit legibly on a single page, it is a strong signal that the diagram needs to be split or simplified.

### Violating vs. Respecting the Rule

| Aspect | Too Much (Violates) | Balanced (Respects) |
|---|---|---|
| Element count | Dozens of classes, relationships, and notes crammed together | Only the components relevant to the current concern |
| Readability | Arrows cross, labels overlap, text is tiny | Clear spacing, labels readable at glance |
| Stakeholder reaction | Lose interest before the speaker starts | Stay engaged, follow the narrative |
| Printability | Requires A0 plotter or zoomed-in sections | Fits on one A4 page clearly |
| Focus | Everything about the system | One specific slice or decision |

### What "Focused" Means in Practice

A focused diagram answers **one question**. Examples:

- *How does the order service communicate with the payment service?* → one sequence diagram, those two components only
- *What are the core domain classes?* → class diagram with 5–8 classes, not the entire domain model
- *What are the deployment targets?* → deployment diagram showing only infrastructure nodes

> [!warning] Over-Inclusion Trap
> It is tempting to add "just one more" element for completeness. Each addition reduces the diagram's communicative power. When in doubt, leave it out — create a second diagram if needed.

## 3. Splitting vs. Simplifying

Two strategies address an overly large diagram:

**Simplify** — remove elements that are not essential to the current message. Ask: *"If I removed this, would the main point still be clear?"* If yes, remove it.

**Split** — divide the diagram into two or more focused views, each answering a different question. A high-level diagram can reference sub-diagrams for detail.

> [!example] Decision Hints
> - If the diagram shows **structure and behavior simultaneously** → split into a class/component diagram and a sequence/activity diagram
> - If the diagram shows **all layers of the system at once** → split by layer (presentation, business logic, data)
> - If you have **more than ~10–12 meaningful elements** → consider whether some elements belong in a separate, linked diagram
> - If stakeholders **regularly ask you to zoom in** → the diagram is too dense; split it

## 4. Relationship to Other Best Practices

The "Less is More" rule underpins the remaining five practices:

- **Meaningful names** become possible only when the scope is narrow enough to name things precisely
- **Consistent notation** is easier to achieve across small, focused diagrams
- **Single-concern focus** is the structural implementation of "Less is More"
- **Legends** become shorter and clearer when fewer custom symbols are needed
- **Audience tailoring** naturally produces smaller diagrams by omitting what the target audience does not need

## Summary

The "Less is More" rule is the foundation of effective UML diagram communication. A diagram that fits on one A4 page, answers one question, and shows only the relevant elements will always outperform a comprehensive but dense diagram. Stakeholder engagement, clarity, and printability are the practical tests for whether a diagram respects this rule.

## Related Notes

- [[Semi-Formal Notations - Unified Modeling Language]]
- [[Semi-Formal Notations - UML Diagrams Overview]]
- [[Semi-Formal Notations - UML Structural Diagrams]]
- [[Semi-Formal Notations - UML Behavioral Diagrams]]
- [[Notations Selection]]
