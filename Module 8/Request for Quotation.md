---
title: "Request for Quotation (RFQ): Purpose, Process and Architect's Role"
date: 2026-05-16
tags:
  - module8
  - presales
  - rfq
  - canvas-note
aliases:
  - RFQ
  - RFQ Process
cssclasses:
  - canvas-note
---

# Request for Quotation (RFQ): Purpose, Process and Architect's Role

> [!note] Overview
> A ==Request for Quotation (RFQ)== is a common business process used to invite suppliers to bid for specific products or services. Its main goal is to obtain **pricing information** for a solution whose scope is already well-defined. RFQs include detailed information about the required solution — covering both **functional** and **non-functional** requirements.

## 1. Purpose of an RFQ

> [!info] Key Goals
> - Obtain ==pricing== from multiple suppliers
> - Compare bids on **cost** for a known scope
> - Speed up procurement when discussion is unnecessary
> - Capture both **functional** and **non-functional** requirements in detail

> [!tip] Pricing-Focused by Design
> In the RFQ phase, customers mainly focus on **price**. The technical scope is largely fixed; vendors compete on cost.

## 2. What an RFQ Contains

> [!info] Typical Contents
> - Detailed solution description
> - **Functional requirements** (what the system must do)
> - **Non-functional requirements** (performance, availability, security, etc.)
> - Quantities, units, or resource expectations
> - Submission deadline and pricing format

## 3. The Architect's Role

Solution Architects do not handle pricing or discounts directly, but they play an important supporting role.

> [!info] Architect Responsibilities
> - **Verify technical details** in the request
> - Confirm **resource requirements** are realistic
> - **Review and respond** to technical questions from suppliers
> - Ensure proposed solutions are **technically sound and cost-effective**

> [!example] Concrete Example
> The architect might be asked: *"Are two full-time DevOps engineers sufficient for this project?"* — providing guidance based on workload, environments, and operational complexity.

## 4. RFQ vs. RFI vs. RFP

| Aspect | RFI | RFQ | RFP |
|---|---|---|---|
| Goal | Gather capability info | Get pricing for known scope | Get full solution proposal |
| Scope detail | Low | High (functional + non-functional) | High |
| Primary selection criterion | Vendor fit | **Price** | Solution quality + price |
| Discussion with bidders | Optional | Usually **not needed** | Usually needed |
| Architect's focus | Technical questions | Technical verification, resource sizing | Solution design, WBS, estimates |

## 5. Typical Flow

1. Client publishes the RFQ with detailed requirements.
2. Suppliers ask technical clarification questions.
3. Architects on the vendor side **verify scope** and **respond to technical questions**.
4. Vendor submits the **quotation**.
5. Client evaluates bids — **price is the deciding factor**.

## When to Use an RFQ

> [!example] Decision Hints
> - Use **RFQ** when the **scope is locked** and only price varies.
> - Prefer **RFP** when the client needs the vendor to **propose a solution**.
> - Use **RFI** first if you don't yet know which vendors are capable.
> - Sometimes an **RFQ precedes a full RFP** to gauge price ranges before deeper engagement.

## Why Architects Still Matter in RFQs

> [!tip] Quietly Critical
> Even though architects don't set price, they are the people who confirm that the **proposed numbers and resources are realistic**. A technically wrong RFQ response — undersized team, infeasible NFR commitment, missing operational role — is far more damaging than a slightly higher price.

## Summary

A Request for Quotation is a **pricing-focused** business process used when the required solution is well-defined and vendors compete primarily on cost. RFQs contain detailed **functional and non-functional requirements**. Solution Architects don't handle pricing directly but are essential for **verifying technical details, sizing resources, and answering supplier technical questions** — ensuring the quoted solution is both technically sound and cost-effective.

## Related Notes
- [[Request for Information]]
- [[Presales Overall Timeline]]
- [[Presales Process]]
- [[Areas of Responsibilities]]
