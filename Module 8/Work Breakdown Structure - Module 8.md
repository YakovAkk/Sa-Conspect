---
title: "Work Breakdown Structure (WBS) in RFP"
date: 2026-05-16
tags:
  - module8
  - presales
  - rfp
  - wbs
  - canvas-note
aliases:
  - WBS in RFP
cssclasses:
  - canvas-note
---

# Work Breakdown Structure (WBS) in RFP

> [!note] Overview
> After functional decomposition, the **Solution Architect creates a Work Breakdown Structure (WBS)** for each component. Unlike functional decomposition, there are ==no strict rules== for building a WBS — it depends on the architect's **experience and preferences**. The result is a tree structure that supports project management and helps deliver results that meet or exceed client expectations.

## 1. What WBS Is

> [!info] Key Properties
> - **Tree structure** — hierarchical, like functional decomposition but oriented around work, not functions
> - **Per component** — typically one WBS per major component
> - **Flexible** — no universal template; shaped by architect judgment

## 2. Purposes of a WBS

A WBS serves several important roles in project planning and execution:

> [!info] Common Purposes
> - **Scope clarity** — defines exactly what work is in
> - **Estimation foundation** — granular work items can be sized
> - **Resource planning** — assign people to specific work
> - **Schedule building** — sequence and time the work
> - **Tracking progress** — measure completion against the structure
> - **Risk identification** — surfaces high-uncertainty branches

## 3. Architect's Role

> [!tip] Why Experience Matters
> Because there are no strict rules for WBS creation, the result reflects the architect's judgment. **Senior architects** typically produce WBSes that:
> - Match the actual delivery model
> - Anticipate cross-cutting concerns (security, observability, testing)
> - Include realistic management overhead
> - Avoid invisible scope creep

## 4. WBS vs. Functional Decomposition

| Aspect | Functional Decomposition | Work Breakdown Structure |
|---|---|---|
| Focus | What the system *does* | What the team *will do* |
| Granularity rule | Stop at indivisible function | Stop at estimable work item |
| Strictness | Standard top-down method | Flexible, architect-driven |
| Used for | Scope clarification | Planning, estimation, tracking |
| Built by | Architect + team | Solution Architect |

## 5. Where WBS Fits in the RFP

> [!example] WBS Usage
> - **Estimations** — bottom-up costing relies on WBS leaves.
> - **Team sizing** — counts roles against work items.
> - **Timeline** — sequences work and identifies critical paths.
> - **Risk register** — each branch can carry risks.
> - **Contract scope** — WBS often anchors the SOW.

## Summary

The Work Breakdown Structure decomposes each component of a solution into a **tree of work items** that can be planned, estimated, resourced, and tracked. Unlike functional decomposition, WBS construction is **flexible** — it depends on the architect's experience and preferences. It is one of the most load-bearing artifacts in an RFP response: estimations, timelines, resource plans, and the SOW all build on top of it.

## Related Notes
- [[The Scope - Functional Decomposition]]
- [[Challenges of WBS]]
- [[Estimation Techniques]]
- [[Timeline - Module 8]]
- [[Resource Plan]]
