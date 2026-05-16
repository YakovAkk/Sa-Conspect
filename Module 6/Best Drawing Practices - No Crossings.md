---
title: "Best Drawing Practices: No Crossings"
date: 2026-04-29
tags:
  - module6
  - uml
  - best-practices
  - canvas-note
cssclasses:
  - canvas-note
---

# Best Drawing Practices: No Crossings

> [!note] Overview
> The ==No Crossings== rule states that lines in a diagram should not cross each other. Avoiding line crossings makes a diagram easier to read and often reflects good design. When crossings cannot be avoided, they signal one of two underlying problems: the diagram is too complex, or there is a flaw in the model itself.

## 1. Why Line Crossings Matter

Lines in UML diagrams represent relationships — associations, dependencies, message flows, transitions. When these lines cross, the reader must visually untangle them to understand what connects to what. This cognitive overhead:

- Slows down comprehension
- Increases the chance of misreading a relationship
- Makes the diagram harder to present and discuss
- Often indicates a deeper structural problem worth fixing

> [!tip] Crossings as a Signal
> Treat a crossing as a ==diagnostic signal==, not just a visual annoyance. A diagram that cannot be drawn without crossings is telling you something about the model or the scope of the diagram.

## 2. The Two Root Causes

When you cannot uncross the lines, one of two problems is typically responsible.

### 2.1 Too Much in the Diagram

The diagram may be attempting to represent ==two distinct aspects of the model simultaneously==. Each aspect has its own set of relationships, and combining them forces their connections to overlap.

> [!info] Signs of This Problem
> - The diagram has two separate "clusters" of elements that happen to connect across each other
> - Removing one group of elements would eliminate all crossings
> - Different stakeholders are interested in different parts of the same diagram

**Solution:** Create separate diagrams, each dedicated to a single aspect. This aligns with the [[Best Drawing Practices - Less is More|Less is More]] rule — reducing scope eliminates both the crossings and the confusion.

### 2.2 Design Flaw in the Model

Well-constructed models typically avoid crossed lines naturally. If the lines cannot be uncrossed by repositioning elements or splitting the diagram, it may indicate a ==design flaw in the underlying model==.

> [!info] Signs of This Problem
> - Repositioning elements does not help — the crossings reappear regardless of layout
> - The crossed relationships represent circular dependencies or bidirectional coupling
> - The crossing persists even when the diagram is reduced to only the relevant elements

**Solution:** Investigate the model. Fixing the design flaw — removing circular dependencies, clarifying responsibilities, introducing an intermediary — should produce a diagram that can be drawn without crossings.

## 3. Comparing the Two Causes

| Aspect | Too Much in the Diagram | Design Flaw in the Model |
|---|---|---|
| Root cause | Scope too broad | Model structure is problematic |
| Fix | Split into separate diagrams | Refactor the model |
| Crossing disappears when... | Scope is reduced | Design is corrected |
| Relationship to other rules | Related to **Less is More** | Stands independently |
| Actionable outcome | New focused diagram per aspect | Improved architecture |

## 4. Practical Techniques to Avoid Crossings

Before concluding that a crossing reveals a design flaw, try these layout adjustments:

1. **Reorder elements** — rearrange nodes so that the most-connected elements are in the center and less-connected ones are on the periphery.
2. **Align by dependency direction** — place elements that depend on others below or to the right of what they depend on, so arrows flow in one direction.
3. **Group related elements** — cluster tightly related elements together, then connect clusters rather than individual nodes.
4. **Use layers** — if the diagram has a natural hierarchy (e.g., presentation → business logic → data), arrange elements in horizontal or vertical bands.

> [!warning] Layout Tricks vs. Structural Fixes
> Repositioning can reduce crossings caused by poor layout, but it cannot fix crossings caused by bidirectional dependencies or circular relationships. If the crossings survive layout changes, the model needs attention.

## 5. Connection to Other Best Practices

The "No Crossings" rule works together with the other five drawing practices:

| Related Rule | How It Connects |
|---|---|
| **Less is More** | The most common fix for crossings is splitting the diagram — exactly what "Less is More" prescribes |
| **Single Concern** | A diagram focused on one concern rarely accumulates enough relationships to generate crossings |
| **Meaningful Names** | Clear naming helps identify which relationships truly belong together, making it easier to split logically |
| **Consistent Notation** | Using standard UML layout conventions (top-to-bottom hierarchy, left-to-right flow) reduces crossings by default |

## 6. Examples at a Glance

| Scenario | Description | Verdict |
|---|---|---|
| FORMAL_COMMUNICATION diagram with crossed lines | Multiple responsibilities shown simultaneously, lines tangle | Violates No Crossings |
| INFORMAL_COMMUNICATION diagram without crossings | Same information, split by concern, clean layout | Respects No Crossings |

> [!example] Decision Hints
> - **Lines cross and removing one cluster fixes it** → split the diagram (scope problem)
> - **Lines cross regardless of layout** → investigate circular dependencies or bidirectional coupling (design flaw)
> - **Lines cross only in one corner** → try repositioning that cluster before escalating to a redesign
> - **Crossings appear after adding a new element** → the new element may be in the wrong place in the architecture

## Summary

The No Crossings rule is both a visual guideline and a diagnostic tool. A crossing-free diagram is easier to read, but more importantly, the effort to eliminate crossings often uncovers real problems — either a diagram that covers too much ground, or a model with structural issues worth addressing. Fixing either problem produces both a cleaner diagram and a better design.

## Related Notes

- [[Best Drawing Practices - Less is More]]
- [[Semi-Formal Notations - Unified Modeling Language]]
- [[Semi-Formal Notations - UML Diagrams Overview]]
- [[Semi-Formal Notations - UML Structural Diagrams]]
- [[Semi-Formal Notations - UML Behavioral Diagrams]]
