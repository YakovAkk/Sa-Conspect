---
title: "Best Drawing Practices: Hierarchies"
date: 2026-04-29
tags:
  - module6
  - uml
  - best-practices
  - canvas-note
cssclasses:
  - canvas-note
---

# Best Drawing Practices: Hierarchies

> [!note] Overview
> The ==Hierarchies== rule states that parent elements should always be placed **above** their child elements, so that arrows point upward from child to parent. When one parent has several children, a ==vertical tree layout== should be used to show the hierarchy clearly. Consistent top-to-bottom placement makes inheritance and composition relationships immediately readable without tracing arrow directions.

## 1. The Core Rule

In any hierarchical diagram — class inheritance, component trees, organizational structures — the position of elements carries meaning:

- **Parent** (the more general, owning, or higher-level element) → placed **above**
- **Child** (the more specific, owned, or lower-level element) → placed **below**
- **Arrows** travel **upward** from child to parent (following UML inheritance convention)

> [!info] Why Arrows Point Upward
> In UML, inheritance arrows point from the subclass (child) **toward** the superclass (parent). Placing the parent above the child ensures the arrow travels upward — which is the natural direction for "is a kind of" and "is owned by" relationships. This matches the mental model most readers bring to hierarchical diagrams.

## 2. Vertical Tree Layout for Multiple Children

When one parent has several children, a ==vertical tree layout== makes the hierarchy explicit:

```
        Parent
       /   |   \
   Child  Child  Child
```

This arrangement:
- Groups siblings at the same horizontal level, making peer relationships visible
- Makes the parent's position unambiguous — it is always at the top
- Allows the eye to scan children left-to-right and then move up to their shared parent

> [!tip] Vertical vs. Horizontal Trees
> A **vertical tree** (parent at top, children spread horizontally below) is preferred for inheritance and generalization hierarchies. A **horizontal tree** (parent at left, children to the right) is sometimes used for decomposition or package structures. Whichever you choose, apply it consistently throughout the entire diagram.

## 3. Correct vs. Incorrect Layout

| Aspect | Incorrect (Arrows Down) | Correct (Arrows Up) |
|---|---|---|
| Parent position | Below children or at same level | Always above children |
| Arrow direction | Point downward from parent | Point upward from child |
| Child position | Above or beside parent | Always below parent |
| Visual impression | Ambiguous, requires arrow-tracing | Hierarchy is self-evident from layout |
| Multiple children | Scattered around parent | Spread horizontally below parent |

> [!warning] Mixed Directions
> The most common mistake is having some arrows pointing up and others pointing down in the same diagram. Even if each individual relationship is correctly labeled, inconsistent direction forces the reader to trace every arrow individually. ==Consistent upward direction== removes this cognitive overhead entirely.

## 4. Applying the Rule in Practice

### 4.1 Start with the Root

Identify the root element (the most general parent) and place it at the top center of the diagram. All other elements flow downward from it.

### 4.2 Assign Levels

Group elements by their depth in the hierarchy:
- **Level 0** — root (top)
- **Level 1** — direct children of the root
- **Level 2** — grandchildren
- And so on…

All elements at the same level should be ==aligned horizontally==, reinforcing the visual sense of peer equivalence.

### 4.3 Distribute Children Evenly

Spread sibling elements evenly below their parent. Center the parent over its children group so that the connecting lines form a balanced tree shape.

> [!example] Decision Hints
> - **Inheritance hierarchy (UML class diagram)** → place the most abstract superclass at the top; concrete subclasses at the bottom
> - **Component decomposition** → place the container component at the top; sub-components below
> - **Organizational chart** → management at the top; reports below
> - **Package structure** → top-level packages above; nested packages below
> - **When a child has multiple parents** (multiple inheritance) → align both parents above and connect arrows upward from the shared child

## 5. Connection to the Other Practices

| Related Rule | How Hierarchies Supports It |
|---|---|
| **Less is More** | A well-structured tree with clear levels naturally limits the diagram to one concern — the hierarchy itself |
| **No Crossings** | Top-down tree layout eliminates most crossings because siblings are ordered at the same level |
| **Orthogonality** | Vertical/horizontal tree structure pairs naturally with orthogonal connectors |
| **Consistent Notation** | Arrow direction is part of notational consistency — one direction for the whole diagram |

## 6. The Corrected Version

In the corrected diagram (per the source material), the arrow directions are fixed so they all point upward from child to parent. The result:

- **Clearer structure** — the top-down reading path matches the hierarchical meaning
- **Easier comprehension** — no arrow-tracing required; layout alone communicates the relationships
- **More consistent** — all relationships follow the same visual convention

## Summary

The Hierarchies rule is about spatial semantics — where an element sits tells the reader what role it plays. Placing parents above children, pointing arrows upward, and grouping siblings at the same horizontal level creates a self-explanatory layout. The reader understands the hierarchy from the diagram's shape alone, before reading a single label. Combined with orthogonality and no-crossing rules, a well-laid-out hierarchy is one of the clearest diagrams an architect can produce.

## Related Notes

- [[Best Drawing Practices - Less is More]]
- [[Best Drawing Practices - No Crossings]]
- [[Best Drawing Practices - Orthogonality]]
- [[Semi-Formal Notations - UML Diagrams Overview]]
- [[Semi-Formal Notations - UML Structural Diagrams]]
