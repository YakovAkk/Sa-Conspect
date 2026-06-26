---
title: "High-Level Design Example: Three-Tier AWS Architecture"
date: 2026-05-16
tags:
  - module8
  - presales
  - rfp
  - hld
  - example
  - aws
  - canvas-note
aliases:
  - HLD Example
  - Three-Tier AWS Example
cssclasses:
  - canvas-note
---

# High-Level Design Example: Three-Tier AWS Architecture

> [!note] Overview
> The pre-sales team and solution architects have **limited time** to prepare a response. Architects must produce a design with **enough detail for the customer to understand the overall concept**, but **no more**. Most architecture diagrams in RFP responses are **simple and high-level**, illustrating primary components and their relationships.

## 1. Example Architecture

The example shows a ==three-tier architecture deployed within AWS Cloud== across **three availability zones (AZs)** for better reliability.

### Key Elements
> [!info] Composition
> - **Three tiers** (presentation, application, data — typical pattern)
> - **Three Availability Zones** for resilience
> - **VPC** (Virtual Private Cloud) hosts all subnets
> - Each tier sits in a **separate subnet** within the VPC
> - **Security Groups (SGs)** control traffic between layers

### Why Three AZs
- Survives the loss of an entire AZ
- Provides redundancy for production workloads
- Meets common availability NFRs

### Why Separate Subnets per Tier
- Network-level isolation
- Targeted security rules per tier
- Clearer traffic patterns and easier audits

## 2. Variability Across Projects

> [!warning] Designs Will Vary
> While this example illustrates a three-tier AWS architecture, the **specific design will vary** based on the project requirements outlined in the RFP. Use it as a pattern, not a template.

## 3. Common Mistakes to Avoid

> [!warning] Don't Over-Engineer the RFP HLD
> - **Too many details** — overwhelms reviewers.
> - **Excessive microservices** — makes the design difficult to understand.
> - **Implementation-level complexity** — wrong audience at RFP stage.
>
> Either mistake **reduces the likelihood of being selected**.

## 4. What Makes a Strong RFP HLD

> [!tip] Strong RFP HLD Traits
> - **Clear** — visually understandable in seconds.
> - **Comprehensive** — covers all major components.
> - **Aligned with project goals** — connects to the RFP's stated needs.
> - **Right altitude** — high-level, not implementation-level.

## Example Composition Summary

| Element | Purpose |
|---|---|
| Three-tier architecture | Standard separation of presentation/app/data |
| AWS Cloud | Cloud platform |
| Three Availability Zones | Reliability against AZ outages |
| VPC | Isolated network boundary |
| Subnets per tier | Network isolation |
| Security Groups | Inter-tier traffic control |

## Decision Hints

> [!example] When in Doubt
> - **Tempted to add another microservice?** → Ask if it adds clarity or just clutter.
> - **Considering three-tier vs. microservices?** → Default to the simpler pattern unless the RFP forces otherwise.
> - **Many integrations?** → Show them, but as labeled boxes — not internal diagrams.

## Summary

A strong RFP-stage HLD is **simple, high-level, and aligned with the project goals**. The three-tier AWS example — three AZs, a VPC with per-tier subnets, and Security Groups controlling traffic — is a useful pattern, but the actual design must adapt to each RFP. Avoid over-engineering: too many details or excessive microservices reduce clarity and **lower the chance of being selected**.

## Related Notes
- [[High-Level Design in the RFP Phase]]
- [[Request for Proposal]]
- [[RFP Structure]]
