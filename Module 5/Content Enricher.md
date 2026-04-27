---
title: Content Enricher
date: 2026-04-20
tags:
  - module5
  - integration
  - patterns
  - messaging
  - canvas-note
cssclasses:
  - canvas-note
---

# Content Enricher

> [!note] Overview
> The ==Content Enricher== is a messaging pattern that augments an incoming message with additional data retrieved from an external system. When the message originator doesn't have all the data the downstream system needs, the Content Enricher fetches the missing information transparently — keeping each system in the integration chain focused on its own responsibility.

## How It Works

**The Content Enricher** is a pattern that adds extra data to a message. It uses key details from the original message, like an ID or name, to request more information from an external system. Once the new data is found, the Content Enricher adds it to the message. Depending on the receiving system's needs, the original data may stay in the message or be replaced.

## Hospital Scheduling Example

A hospital scheduling system sends a message after a doctor's visit containing: patient's first name, ID, and visit date. However, the accounting system needs: full name, insurance provider, and social security number — available only in the customer care system.

![[Content Enricher options diagram]]

### Three Approaches to Handle Missing Data

> [!info] Options
> - **Replicate Data** — Modify the scheduling system to store the additional information, replicating changes from the customer care system. Requires structural modifications, often challenging in packaged applications.
> - **Request Data from Customer Care System** — Have the scheduling system request SSN and carrier data before sending the "Doctor Visit" message. Avoids structural changes but introduces ==tighter coupling== between systems, resulting in brittle integration.
> - **Customer Care System Transforms Message** — Send the message to the customer care system first, allowing it to fetch the required information and forward a complete message to the accounting system. ==Decouples== the scheduling system from the message flow, but may require modifying the customer care system.

## Content Enricher Solution

![[Content Enricher integration diagram]]

Using the Content Enricher approach, the scheduling system stays clean and focused — its only job is to send the "Doctor Visit" message. The Content Enricher gathers any missing information. The accounting system receives the full data it needs without dealing with the details of other systems.

> [!tip] Key Benefit
> This setup keeps each system part ==modular and independent==, making the workflow more efficient and easier to manage. No system is burdened with data it doesn't own.

## Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Keeps source systems focused | Adds a hop in the message flow |
| Avoids tight coupling between systems | Depends on external data source availability |
| Source system doesn't need schema changes | Content Enricher can become a bottleneck |
| Downstream receives complete messages | Data freshness depends on query timing |

## When to Use

> [!example] Decision Hints
> - Use Content Enricher when the ==message originator lacks data== required by downstream systems but structural changes to the source are not feasible.
> - Avoid when the missing data can be looked up by the downstream system itself without coupling concerns.
> - Prefer Content Enricher over source modification when dealing with ==packaged or third-party applications==.

## Related Notes

- [[Integration Patterns]]
- [[Aggregator - Strategies for Measuring Completeness]]
- [[Messaging History]]
