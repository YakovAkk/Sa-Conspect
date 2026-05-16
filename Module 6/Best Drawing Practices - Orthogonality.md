---
title: "Best Drawing Practices: Orthogonality"
date: 2026-04-29
tags:
  - module6
  - uml
  - best-practices
  - canvas-note
cssclasses:
  - canvas-note
---

# Best Drawing Practices: Orthogonality

> [!note] Overview
> The ==Orthogonality== rule recommends using vertical and horizontal lines that meet at right angles instead of diagonal lines. Orthogonal connectors make diagrams cleaner, more organized, and easier to read. Diagrams with lines running at many arbitrary angles look messy and are significantly harder to understand and follow.

## 1. What Orthogonality Means

In geometry, two lines are orthogonal when they are perpendicular — meeting at a 90° angle. In diagram design, the orthogonality rule means:

- **Use only horizontal and vertical connector segments**
- **Connectors turn at right angles** rather than running diagonally across the diagram
- **Elements are aligned** to an invisible grid so connectors can route cleanly between them

> [!info] Defining Traits of Orthogonal Connectors
> - Lines travel horizontally or vertically — never diagonally
> - Turns happen at 90° bends, not at arbitrary angles
> - The path of a connector is predictable — the eye follows it without effort
> - Elements naturally align into rows and columns

## 2. Direct vs. Orthogonal Connectors

The most common violation of orthogonality is the use of ==direct (straight-line) connectors== that link elements point-to-point regardless of angle.

| Aspect | Direct (Straight) Connectors | Orthogonal Connectors |
|---|---|---|
| Line style | Single straight line at any angle | Horizontal/vertical segments with right-angle turns |
| Visual result | Diagonal lines cross the canvas | Clean grid-aligned routing |
| Readability | Lines overlap and crowd the space | Each path is distinct and traceable |
| Overall impression | Messy, spider-web effect | Organized, professional |
| Tool setting | Default in many tools | Must be explicitly selected in most tools |

> [!tip] Tool Setting
> In most diagramming tools (draw.io, Lucidchart, PlantUML, Enterprise Architect), connector style is a global or per-connector setting. Setting **all connectors to orthogonal** is a one-step improvement that immediately transforms a messy diagram into a clear one.

## 3. Why Orthogonality Improves Readability

### 3.1 Predictable Eye Movement

Horizontal and vertical lines align with the natural reading direction (left-to-right, top-to-bottom). The eye follows them automatically without needing to track an angle.

### 3.2 Reduced Visual Noise

Diagonal lines introduce visual angles that compete with the content — shapes, labels, and icons. Orthogonal routing keeps connectors subordinate to the elements they connect.

### 3.3 Grid Alignment Effect

When connectors are orthogonal, elements naturally settle into an implied grid. This grid creates ==visual grouping== without explicit borders or boxes, making the diagram's structure self-evident.

### 3.4 Easier to Modify

Orthogonal connectors adapt cleanly when elements are moved — they re-route along horizontal/vertical paths. Diagonal connectors require manual repositioning and re-angling after every layout change.

## 4. Orthogonality and the Other Practices

| Related Rule | How Orthogonality Supports It |
|---|---|
| **Less is More** | Orthogonal routing makes dense diagrams more manageable by reducing visual noise |
| **No Crossings** | Orthogonal connectors make crossings more visible and easier to eliminate by rerouting |
| **Single Concern** | Focused diagrams have fewer connectors — orthogonality maximizes the clarity gain |
| **Consistent Notation** | Uniform connector style is one dimension of visual consistency |

## 5. Applying the Rule in Practice

> [!example] Step-by-Step
> 1. **Set the default connector style to orthogonal** in your diagramming tool before drawing anything
> 2. **Align elements to a grid** — most tools have a snap-to-grid option that makes orthogonal routing automatic
> 3. **Review after layout changes** — when you move an element, check that its connectors have re-routed cleanly
> 4. **Avoid manual bends** — do not drag connector midpoints to create diagonal segments; reset to orthogonal if needed
> 5. **Check the overall impression** — step back and look at the diagram as a whole; diagonal lines will stand out immediately

> [!warning] When Orthogonality Feels Forced
> In rare cases, a very small diagram with only two or three elements may look equally clear with direct connectors. Orthogonality matters most when there are ==five or more connectors== and the routing would otherwise create visual noise. For very simple diagrams, use judgment — but default to orthogonal.

## 6. Wrong vs. Correct at a Glance

| Scenario | Description | Verdict |
|---|---|---|
| Connectors are straight lines linking elements directly | Diagonal lines at varying angles, spider-web effect | Violates Orthogonality |
| All connector styles set to orthogonal | Lines route horizontally and vertically, clean grid layout | Respects Orthogonality |

## Summary

Orthogonality is one of the simplest best practices to apply and one of the most immediately visible in its effect. Switching all connectors to orthogonal routing — a single setting in most tools — transforms a messy, angle-heavy diagram into a clean, grid-aligned one. The rule works because it aligns with natural reading direction, reduces visual noise, and makes the diagram's structure self-evident. Together with Less is More and No Crossings, orthogonality is a foundation for professional, communication-ready diagrams.

## Related Notes

- [[Best Drawing Practices - Less is More]]
- [[Best Drawing Practices - No Crossings]]
- [[Semi-Formal Notations - Unified Modeling Language]]
- [[Semi-Formal Notations - UML Diagrams Overview]]
- [[Notations Selection]]
