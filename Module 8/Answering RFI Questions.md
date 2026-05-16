---
title: "Answering RFI's Questions: Support Sources, Style and Examples"
date: 2026-05-16
tags:
  - module8
  - presales
  - rfi
  - communication
  - canvas-note
aliases:
  - RFI Answers
  - Responding to RFI
cssclasses:
  - canvas-note
---

# Answering RFI's Questions: Support Sources, Style and Examples

> [!note] Overview
> RFI questions often go beyond your personal expertise — for example, questions about ==ISO security specifications==. Successful responses depend on **knowing where to seek help**, providing **specific details** instead of generic claims, and **collaborating** with other teams (especially marketing) to keep answers clear, engaging, and business-focused.

## 1. Where to Seek Help

During presales, **everyone in the company should support one another**. You are not expected to be an expert in every domain the RFI asks about.

### People to Consult
> [!info] Internal Experts
> - **Presales team** — coordinators and consultants
> - **Competency centers** — deep expertise in specific technologies
> - **Solution practices** — domain or industry specialists
> - **Internal community networks** — peers across the company

### Tools to Use
> [!info] Knowledge Tools
> - **Confluence** — internal documentation
> - **Presales portals** — reusable proposal assets
> - Other internal **platforms** with case studies and prior responses

## 2. How to Answer Well

> [!warning] Avoid Generic or Overly Positive Statements
> Vague claims like *"we are leaders in this area"* add no value. Provide **specific details** about your approach, experience, and capabilities. Reference standards (==ITIL==, ISO), real implementations, and concrete tooling.

> [!tip] What Strong Answers Include
> - Specific frameworks and standards followed
> - Real-life examples of past successes
> - Concrete tools and technologies
> - Process specifics (escalation paths, SLAs, KPIs)
> - Adaptability statements (how you adjust to client context)

## 3. Example 1 — Support and Maintenance

> [!example] Question
> Please provide an overview of your support and maintenance process, including incident management, problem management, service request and tracking, system maintenance, release management, and service level reporting.

### Answer Highlights
- Company follows ==ITIL guidelines==, adapted per project.
- Guidelines are part of a **Standard Operations Framework** built from best practices and real experience.
- Framework includes:
  - Process diagrams
  - Checklists
  - **Standard Operating Procedures (SOPs)**
  - Governance models
  - **KPIs**
- Framework can be adjusted during service transition to match the Client's IT operating model.

### ITIL Processes Offered
> [!info] Core ITIL Coverage
> - Incident management
> - Problem management
> - Release management
> - Change management
> - Configuration management
> - Security management

### Operational Details
- Well-defined **incident escalation paths**.
- **24x7 Service Desk** as a single point of contact.
- Tracks each request until the **submitter confirms resolution**.
- Intake channels: email, phone, ITSM tool, monitoring-system-generated.
- Single ITSM tool — either company-proposed or client-preferred.
- High-priority issues outside business hours → **on-call engineer** contacted by Service Desk.

> [!tip] Why This Answer Works
> It cites a specific standard (ITIL), names concrete artifacts (SOPs, KPIs), describes real operational mechanics (24x7 desk, on-call escalation), and shows flexibility (adapts to client's IT operating model).

## 4. Example 2 — Scalable Database Platform

> [!example] Question
> The system will include a scalable, high-performing, structured database platform capable of storing and processing large volumes of data.

### Answer Highlights
- Proposed solution: ==Microsoft SQL Server==.
- Justification:
  - Strong performance and reliability
  - Reduced development and support costs
  - Built-in **backups**, **always-on availability**, **disaster recovery**
  - Trusted by many Microsoft customers
- Flexible setups:
  - **Read-Only / Read-Write** server nodes
  - **Data partitioning**
- Performance enhancement via **in-memory caching**:
  - Stores rarely changed data in memory
  - Uses **read-through** and **write-through** caching patterns

> [!tip] Why This Answer Works
> It names a specific product, lists concrete built-in capabilities, addresses scalability/HA/DR requirements directly, and adds an optional enhancement layer (caching) to demonstrate depth of thinking.

## Generic vs. Specific Answers

| Generic (Weak) | Specific (Strong) |
|---|---|
| "We follow industry best practices." | "We follow ITIL, adapted per project, with SOPs, KPIs, and governance models." |
| "We are highly scalable." | "MS SQL Server with always-on availability, partitioning, and Read-Only nodes, plus read/write-through caching." |
| "We have a great support team." | "24x7 Service Desk as single point of contact, with defined escalation paths and on-call engineers for off-hours P1s." |
| "We can integrate anything." | "We use ITSM tools and accept requests via email, phone, ITSM intake, and monitoring-system triggers." |

## 5. Collaboration With Marketing

> [!tip] Why Marketing Matters
> Working with the **marketing team** helps ensure RFI answers are:
> - **Clear** — easy to read and understand
> - **Engaging** — hold the reader's attention
> - **Business-focused** — show value, not just features
>
> Marketing also helps align tone and language with the client's industry.

## Decision Hints for Strong RFI Answers

> [!example] When in Doubt
> - **Don't know the answer?** → Ask competency centers, solution practices, or community networks.
> - **Need real examples?** → Check Confluence / presales portals for prior case studies.
> - **Tempted to write generic praise?** → Replace it with a standard, a tool name, or a concrete number.
> - **Answer reads dry?** → Loop in marketing before submission.

## Summary

Answering RFI questions well requires **knowing where to seek help** (presales team, competency centers, solution practices, communities, Confluence, presales portals), giving **specific and concrete answers** (not generic praise), backing claims with **real examples and named standards** like ITIL, and **collaborating with marketing** to keep the response clear, engaging, and business-focused. This combination shows real value and meaningfully improves the chance of winning the project.

## Related Notes
- [[Request for Information]]
- [[Presales Overall Timeline]]
- [[Presales Process]]
- [[Areas of Responsibilities]]
