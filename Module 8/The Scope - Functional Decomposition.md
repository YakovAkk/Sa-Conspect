---
title: "The Scope: Functional Decomposition"
date: 2026-05-16
tags:
  - module8
  - presales
  - rfp
  - decomposition
  - scope
  - canvas-note
aliases:
  - Functional Decomposition
cssclasses:
  - canvas-note
---

# The Scope: Functional Decomposition

> [!note] Overview
> ==Functional decomposition== is the first step in defining the scope. It breaks the solution into smaller components so the team can collaborate more easily. The result is a clear chart showing the problem and possible solutions — a **functional decomposition diagram** built top-down.

## 1. What Functional Decomposition Is

A **top-down approach** that starts with the main function and progressively reveals smaller steps. It shows the structure of the system and how its parts connect.

> [!info] Key Properties
> - **Top-down** — start broad, drill down
> - **Hierarchical** — each level reveals the next
> - **Visual** — diagram-based, not narrative
> - **Built collaboratively** — analysis + team discussions

## 2. The Three Steps

### 2.1 Identifying the General Function
Determine the **most fundamental task** the solution must accomplish. This single function sits at the top of the diagram and is described succinctly.

### 2.2 Identifying Sub-Functions
Identify the **immediate sub-functions** required to execute the primary function.

> [!info] Diagram Placement
> - Sub-functions are placed on the diagram
> - Each is **connected** to the general function above
> - Choose processes that **directly precede** the primary function — no intermediate steps

### 2.3 Further Sub-Function Identification
For each process identified in the previous step, determine its **next level of sub-functions**.

> [!tip] When to Stop
> Continue iterating until the diagram comprises **basic functions that cannot be further decomposed**.

## Three Steps at a Glance

| Step | What Happens | Output |
|---|---|---|
| 1. General Function | Identify the root task | Top-of-diagram label |
| 2. Sub-Functions | Identify immediate children | One level of sub-functions |
| 3. Further Sub-Functions | Iterate per branch | Fully decomposed tree |

## 3. Why Functional Decomposition Matters

> [!example] Strategic Reasons
> - **Easier collaboration** — small pieces are easier to discuss and assign.
> - **Clear scope** — every box is either in or out of scope.
> - **Better understanding** — surfaces the structure that text often hides.
> - **Foundation for WBS** — feeds directly into the Work Breakdown Structure.

## 4. Best Practices

> [!tip] How to Decompose Well
> - Keep each level **uniform in granularity** — don't mix big and tiny boxes at the same level.
> - **Directly preceding** sub-functions only — no skipping steps.
> - **Stop at indivisible** functions — over-decomposing wastes effort.
> - Validate with the team before moving to WBS.

## Summary

Functional decomposition breaks a solution into a **hierarchical tree of sub-functions** built top-down. The three steps are: identify the **general function**, identify its **immediate sub-functions**, and **iterate further** until you reach indivisible functions. The resulting diagram clarifies scope, eases collaboration, and prepares the team to build the Work Breakdown Structure.

## Related Notes
- [[Work Breakdown Structure - Module 8]]
- [[Challenges of WBS]]
- [[High-Level Design in the RFP Phase]]
- [[Request for Proposal]]
