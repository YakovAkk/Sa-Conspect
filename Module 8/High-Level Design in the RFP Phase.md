---
title: "High-Level Design in the RFP Phase: Steps and Principles"
date: 2026-05-16
tags:
  - module8
  - presales
  - rfp
  - architecture
  - hld
  - canvas-note
aliases:
  - HLD in RFP
  - High-Level Design Steps
cssclasses:
  - canvas-note
---

# High-Level Design in the RFP Phase: Steps and Principles

> [!note] Overview
> During the RFP phase, it is important to create a ==High-Level Design (HLD)== that matches the project scope and objectives. Unrealistic ambitions (e.g., *"build Facebook or Bitcoin in a short time"*) should be replaced with a clearly defined **project scope, user scenarios, and system context**. The design follows a standard four-step method.

## 1. Defining Functional Scope

Outline the **range of services** your system will provide — later encapsulated as use cases.

> [!info] What to Do
> - Identify **user scenarios**
> - Outline **major use cases** and workflows
> - Define what the system *will* and *will not* do at a high level

## 2. Considering System Context

Identify the **immediate sub-functions** required to execute the primary function.

> [!info] Diagram Convention
> - Sub-functions are placed on the diagram and connected to the **general function**
> - Choose processes that **directly precede** the primary function (no extra steps in between)

## 3. Identifying Architecturally Significant Requirements (ASRs)

> [!tip] What ASRs Are
> ASRs are prerequisites that exert a **measurable impact** on the system's architecture. They are the foundational elements shaping the architectural design.

Typical ASR categories include performance, scalability, availability, security, compliance, and integration constraints.

## 4. Creating High-Level Design (HLD)

Prepare a high-level design encompassing a **solution approach and architecture** tailored to address the ASRs.

> [!info] What the HLD Contains
> - System architecture description
> - Database structure
> - Overview of **platforms, systems, services, and processes** integral to the product
> - **Interrelationships** between components

## Four Steps at a Glance

| # | Step | Output |
|---|---|---|
| 1 | Defining Functional Scope | Use cases, user scenarios |
| 2 | Considering System Context | Sub-functions and their connections |
| 3 | Identifying ASRs | Prioritized list of architecture-shaping requirements |
| 4 | Creating HLD | Architecture diagram + database + platform overview |

## Why HLD Matters at RFP Stage

> [!example] Strategic Reasons
> - **Understand feasibility** — does the proposed solution make sense?
> - **Show alignment** — demonstrate how the design supports organizational goals.
> - **Set expectations** — define scope visually, not just in text.
> - **Enable decisions** — clients can judge whether to proceed with this vendor.

## Common Pitfalls

> [!warning] Things to Avoid
> - Promising unrealistic outcomes (Facebook-in-6-weeks).
> - Skipping ASR identification — leads to a design that can't meet NFRs.
> - Going too deep — at RFP stage, the design should be **high-level**, not implementation-ready.

## Summary

Creating a High-Level Design in the RFP phase follows four standardized steps: **Defining Functional Scope, Considering System Context, Identifying Architecturally Significant Requirements (ASRs), and Creating the HLD itself**. The result shows how components relate, supports a feasibility judgment, and demonstrates that the proposed solution genuinely supports the organization's goals — all without descending into implementation-level detail.

## Related Notes
- [[High-Level Design Example]]
- [[Request for Proposal]]
- [[RFP Structure]]
- [[The Scope - Functional Decomposition]]
