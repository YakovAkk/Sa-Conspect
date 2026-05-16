---
title: "Best Drawing Practices: Tidy Up"
date: 2026-04-29
tags:
  - module6
  - uml
  - best-practices
  - canvas-note
cssclasses:
  - canvas-note
---

# Best Drawing Practices: Tidy Up

> [!note] Overview
> ==Tidying up== a diagram means aligning elements, making their sizes consistent, and improving overall visual appearance. A neat diagram reduces the need for verbal explanation and lets stakeholders focus on the content — not the layout. When refining a diagram, align elements vertically or horizontally and consider centering them to create a polished, professional result.

## 1. What Tidy Up Means

"Tidy Up" is the final polish step — applied after the content and structure are correct. It addresses three dimensions of visual quality:

| Dimension | What It Means | What It Fixes |
|---|---|---|
| **Alignment** | Elements share a common edge or center axis | Random positioning, uneven spacing |
| **Consistent sizing** | Elements of the same type have the same width and height | Boxes of different sizes for similar concepts |
| **Overall appearance** | Uniform spacing, consistent fonts, clean whitespace | Cluttered, crowded, or unbalanced layout |

> [!info] Why This Matters
> A diagram that is conceptually correct but visually messy sends an implicit message: "this was done hastily." Stakeholders judge the quality of the analysis partly by the quality of the presentation. A ==clean, aligned diagram signals professionalism and thoroughness== — even before a word is spoken.

## 2. Alignment Techniques

### 2.1 Vertical Alignment

Elements placed in a column should share the same left edge, right edge, or center axis.

- **Left-align** when elements form a reading list (top-to-bottom flow)
- **Center-align** when elements form a visual hierarchy (tree, star shape)
- **Right-align** when elements are captions or labels next to a primary element

### 2.2 Horizontal Alignment

Elements placed in a row should share the same top edge, bottom edge, or midline.

- **Top-align** when elements have varying heights and begin at the same level
- **Middle-align** when elements of different heights should appear visually balanced
- **Bottom-align** when elements rest on the same baseline

### 2.3 Centering

When a parent element has children, ==center the parent over its children== (or vice versa). This applies to:
- Class hierarchies (parent class centered above its subclasses)
- Component diagrams (container centered above its components)
- Process flows (decision nodes centered between their branches)

> [!tip] Use Tool Alignment Features
> Every professional diagramming tool (draw.io, Lucidchart, Visio, Enterprise Architect) has built-in **Align** and **Distribute** functions. Use them instead of manual dragging:
> - **Align left/right/center/top/middle/bottom** — snaps selected elements to a shared axis
> - **Distribute horizontally/vertically** — spaces selected elements evenly between the outermost two

## 3. Consistent Sizing

Elements of the same type should have the same dimensions. Inconsistent sizes imply that the larger element is more important — which is rarely the intended message.

> [!warning] The Sizing Trap
> Resizing elements to fit their label text results in boxes of varying sizes. This is the most common source of visual inconsistency. Instead:
> - Choose a **standard size** for each element type (e.g., all classes: 160×80px)
> - Use **word wrap** or **abbreviations** so labels fit the standard size
> - Reserve size differences only for intentional emphasis (e.g., a highlighted or selected element)

### Common Size Conventions

| Element Type | Typical Approach |
|---|---|
| UML class boxes | Same width; height varies only with attribute count |
| Component boxes | Same width and height unless explicitly showing scale |
| Decision diamonds | Same size throughout the diagram |
| Actor figures (use case) | Same height for all actors |
| Swimlane headers | Same width; lane depth may vary by content |

## 4. Overall Appearance Checklist

Before sharing a diagram, check these visual quality factors:

> [!example] Tidy Up Checklist
> - [ ] All elements of the same type are the same size
> - [ ] Elements are aligned (left, right, center, or top/middle/bottom as appropriate)
> - [ ] Spacing between elements is consistent — no crowded clusters and no orphaned elements far from the group
> - [ ] Labels are readable — same font, same size, no text overflowing element boundaries
> - [ ] Connector routing is clean — no connectors running through elements or overlapping labels
> - [ ] Whitespace is balanced — no large empty areas on one side and dense content on the other
> - [ ] The diagram fits cleanly on one page (per the Less is More rule)

## 5. Tidy Up and the Other Practices

Tidy Up is the last rule applied — it refines a diagram that already satisfies the other five practices:

| Rule Applied First | What It Achieves | Tidy Up Then Adds |
|---|---|---|
| **Less is More** | Right amount of content | Clean spacing and padding around remaining elements |
| **No Crossings** | Clean connector routing | Uniform connector widths and colors |
| **Orthogonality** | Right-angle connectors | Consistent connector style across all relationships |
| **Hierarchies** | Correct top-down layout | Centering parents over children, equal sibling spacing |
| **Tidy Up** | Polished visual quality | The final presentation-ready result |

> [!note] Sequence Matters
> Apply the other rules first — content, structure, routing — then tidy up. Tidying a structurally incorrect diagram wastes effort; the layout will change again when the underlying issues are fixed.

## 6. Correct vs. Incorrect at a Glance

| Aspect | Violates Tidy Up | Respects Tidy Up |
|---|---|---|
| Element sizes | Varying sizes for same-type elements | Uniform sizes per element type |
| Element positions | Random, uneven, asymmetric | Aligned to axes, evenly spaced |
| Labels | Overflow boxes, different fonts/sizes | Fit within elements, consistent style |
| Whitespace | Uneven — crowded here, empty there | Balanced margins and element gaps |
| Overall impression | Draft-quality, requires explanation | Presentation-ready, self-explaining |

## Summary

Tidy Up is the finishing step that transforms a correct diagram into a communicative one. Alignment, consistent sizing, and balanced spacing reduce visual noise so stakeholders can focus entirely on the content. A polished diagram signals that the analysis behind it was equally careful. Combined with the other five drawing practices, Tidy Up ensures that the diagram serves its primary purpose: communicating clearly and effectively without requiring additional verbal explanation.

## Related Notes

- [[Best Drawing Practices - Less is More]]
- [[Best Drawing Practices - No Crossings]]
- [[Best Drawing Practices - Orthogonality]]
- [[Best Drawing Practices - Hierarchies]]
- [[Semi-Formal Notations - Unified Modeling Language]]
- [[Notations Selection]]
