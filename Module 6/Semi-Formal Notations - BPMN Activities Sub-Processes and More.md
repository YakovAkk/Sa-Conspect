---
title: "Semi-Formal Notations: BPMN Activities — Sub-Processes, Call Activities, Event Sub-Processes, Transactions"
date: 2026-04-28
tags:
  - module6
  - bpmn
  - semi-formal
  - notation
  - canvas-note
cssclasses:
  - canvas-note
---

# Semi-Formal Notations: BPMN Activities — Sub-Processes, Call Activities, Event Sub-Processes, Transactions

> [!note] Overview
> Beyond atomic ==Tasks==, BPMN defines four **compound activity types** that add structure, encapsulation, and reusability to business process models: ==Sub-Processes==, ==Event Sub-Processes==, ==Transactions==, and ==Call Activities==. Each type addresses a different modeling need — from hiding internal complexity behind a collapsible container, to handling exceptional events inside a process boundary, to wrapping reusable global workflows. Together they are the primary tools for managing complexity in large-scale BPMN diagrams.

---

## 1. Sub-Process

A ==Sub-Process== is a compound activity that **contains its own internal process flow** — a complete sequence of tasks, gateways, and events nested inside a parent process.

### Key Characteristics

> [!info] Defining Traits
> - Represented as a **rounded rectangle with a `+` marker** in the bottom center
> - Can be **collapsed** (showing only the outer box with `+`) or **expanded** (showing the full internal flow)
> - The `+` icon is the BPMN convention for "click to expand" — critical for managing diagram readability
> - Has its own Start and End Events internally
> - Inherits the context of the parent process (data, variables)
> - Sequence flows inside the sub-process are separate from the parent process flow

### Collapsed vs. Expanded

| Mode | Who Sees It | What's Shown |
|---|---|---|
| **Collapsed** | Stakeholders, executives | A single box labeled with the sub-process name — hides complexity |
| **Expanded** | Developers, analysts | The full internal flow — all tasks, gateways, and events inside |

> [!tip] Core Value
> Sub-processes offer **dual-audience communication**: collapse for high-level stakeholder discussions, expand for developer-level implementation review. This makes them the primary tool for managing complexity in large BPMN diagrams without sacrificing detail.

---

## 2. Event Sub-Process

An ==Event Sub-Process== is a **self-contained process triggered by a start event within the boundaries of a parent sub-process or process**. It operates outside the normal sequence flow — it is not connected to the main flow by sequence flows but is activated when its triggering event occurs.

### Key Characteristics

> [!info] Defining Traits
> - Placed **inside** a sub-process boundary but **outside** its normal flow
> - Always starts with a **Start Event** (the trigger)
> - Represented as a **rounded rectangle with a dashed border** (to distinguish from regular sub-processes)
> - Not connected to the main flow by sequence flows — it is event-driven
> - Useful for handling exceptions, cancellations, or notifications within a scope

### Two Types

> [!info] Interrupting vs. Non-Interrupting
> | Type | Effect on Parent Process | Visual Marker |
> |---|---|---|
> | **Interrupting** | Stops the ongoing parent process and redirects control to the event sub-process | Start event with solid border inside the event sub-process |
> | **Non-Interrupting** | Runs in parallel — parent process continues undisturbed | Start event with dashed border inside the event sub-process |

> [!example] When to Use Event Sub-Process
> - **Interrupting**: Handling an "Order Cancelled" event that must stop the current order fulfillment flow
> - **Non-Interrupting**: Sending an automatic status notification email while order processing continues normally

---

## 3. Transaction

A ==Transaction== is a **sub-process that represents a logical unit of work** where all steps must either succeed together or fail together — similar to a database transaction in software systems.

### Key Characteristics

> [!info] Defining Traits
> - Represented as a **rounded rectangle with a double-line border** (two concentric rectangles)
> - Guarantees atomicity: either all participants complete their roles successfully, or the entire transaction is rolled back
> - Completion is verified by confirming **all participants have fulfilled their obligations**
> - Must always have a compensation mechanism defined — if the transaction fails, prior completed steps must be undone

### Transaction Outcomes

| Outcome | Meaning | Triggered By |
|---|---|---|
| **Successful** | All steps completed and confirmed — transaction commits | Normal End Event inside the transaction |
| **Ended** | Process reached an end state without full confirmation | End Event before all roles fulfilled |
| **Canceled** | Transaction explicitly aborted — compensation is triggered | Cancel End Event inside the transaction |

> [!warning] Compensation Requirement
> Transactions require ==Compensation Events== to handle rollback. Each step that may need to be undone should have a corresponding compensation handler (a task that reverses the step's effect — e.g., "Refund Payment" as compensation for "Charge Payment").

> [!example] Real-World Example
> A travel booking transaction: "Book Flight" + "Book Hotel" + "Charge Card." If the hotel booking fails after the flight is booked and the card is charged, the transaction cancels — triggering compensation: "Cancel Flight" and "Refund Card."

---

## 4. Call Activity

A ==Call Activity== is a **wrapper that invokes a globally defined process or task** — a reusable component that can be called from multiple places across the enterprise.

### Key Characteristics

> [!info] Defining Traits
> - Represented as a **rounded rectangle with a thick/bold border** (heavier than a regular task)
> - References a **Global Process** or **Global Task** defined elsewhere in the model
> - When executed, **control transfers** from the current process to the called global element
> - After the global element completes, control returns to the calling process
> - The called element is reusable — any process can reference the same global definition
> - Often labeled as "Global" in enterprise process catalogs

### Call Activity vs. Sub-Process

| Aspect | Call Activity | Sub-Process |
|---|---|---|
| **Definition location** | Defined globally, outside the current process | Defined inline within the parent process |
| **Reusability** | Can be called from multiple processes | Belongs to one parent process |
| **Border style** | Thick/bold border | Normal border with `+` marker |
| **Use case** | Standardized enterprise processes | Local process encapsulation |

> [!example] Real-World Example
> An enterprise-wide "Employee Onboarding" process is defined globally. Any department's onboarding flow uses a Call Activity to invoke it — the HR process, IT setup process, and finance setup process all call the same global "Employee Onboarding" definition, ensuring consistency and single-point maintenance.

---

## 5. Comparison at a Glance

| Type | Border Style | Trigger | Reusable? | Key Purpose |
|---|---|---|---|---|
| **Sub-Process** | Normal + `+` marker | Sequence flow (parent reaches it) | No — local | Hide / encapsulate internal flow |
| **Event Sub-Process** | Dashed border | Start Event (event-driven) | No — local | Handle exceptions within a scope |
| **Transaction** | Double border | Sequence flow (parent reaches it) | No — local | Guarantee all-or-nothing execution |
| **Call Activity** | Thick/bold border | Sequence flow (parent reaches it) | Yes — global | Reuse a globally defined process/task |

---

## 6. When to Use Each

> [!example] Decision Hints
> - Use **Sub-Process** when a group of tasks is complex enough to deserve its own scope, or when you want to show/hide detail based on audience
> - Use **Event Sub-Process** when you need to react to an event (error, cancellation, timer) that occurs within a scope — especially for interruption and exception handling
> - Use **Transaction** when all steps must commit together — i.e., partial completion is not acceptable and rollback must be possible
> - Use **Call Activity** when invoking a standardized, reusable process or task that is shared across multiple workflows in the organization

---

## Summary

BPMN's four compound activity types address the key challenges of large-scale process modeling. ==Sub-Processes== encapsulate complexity behind a collapsible `+` container. ==Event Sub-Processes== handle in-scope exceptions and notifications without disrupting the main flow structure. ==Transactions== enforce all-or-nothing execution semantics with compensation support. ==Call Activities== promote reuse by invoking globally defined processes from any workflow in the enterprise. Together they give BPMN diagrams both the detail needed by developers and the clarity needed by business stakeholders.

---

## Related Notes

- [[Semi-Formal Notations - BPMN Activities Task Types]]
- [[Semi-Formal Notations - BPMN Flow Objects and Flows]]
- [[Semi-Formal Notations - BPMN Events and Symbols]]
- [[Semi-Formal Notations - BPMN Key Concepts]]
- [[Semi-Formal Notations - BPMN]]
- [[Semi-Formal Notations]]
