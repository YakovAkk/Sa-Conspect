---
title: "Semi-Formal Notations: BPMN Activities — Task Types"
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

# Semi-Formal Notations: BPMN Activities — Task Types

> [!note] Overview
> ==Activities== are one of the three core Flow Objects in BPMN. They represent **work that is performed** within a business process — from automated system calls to manual human actions. Activities are visualized as ==rectangles with rounded corners==, each labeled with a descriptive name. BPMN defines seven distinct ==task types==, each carrying a small marker icon in the top-left corner to indicate how the work is performed. This allows readers to immediately distinguish automated system tasks from human interactions, message-based handoffs, and scripted operations — without reading any textual description.

---

## 1. What Is a Task?

A ==Task== is an atomic unit of work — it cannot be broken down into smaller sub-processes within the same diagram. Tasks are the basic building blocks of any BPMN process.

> [!info] Visual Conventions
> - Represented as a **rounded rectangle**
> - Labeled with the task name (verb phrase describing the work)
> - A **small icon marker** in the top-left corner identifies the task type
> - No marker = a generic (untyped) task

---

## 2. The Seven Task Types

### Service Task

A ==Service Task== uses an **automated application, web service, or other automated service** to execute the task. It represents system-to-system automation with no direct human involvement.

> [!info] Defining Traits
> - Marker: **gear icon**
> - The process engine calls an external service or application
> - Execution is automatic — completes when the service responds
> - Typical uses: API calls, system integrations, automated data processing

> [!example] Real-World Example
> Publishing an answer on Twitter through a web service in response to a forum question — the service task sends the API request and receives confirmation automatically.

---

### Send Task

A ==Send Task== **sends a message to another lane or pool**. The task completes as soon as the message has been successfully delivered.

> [!info] Defining Traits
> - Marker: **filled envelope icon** (dark/solid)
> - Produces and dispatches a message to an external recipient
> - Completes immediately upon successful delivery — does not wait for a reply
> - Pairs naturally with a Receive Task in the target pool

> [!example] Real-World Example
> In an article approval process, a Send Task creates and delivers a "rejection status" message to the author — the task ends when the message is sent.

---

### Receive Task

A ==Receive Task== **waits for an incoming message** before the process can continue. The task completes when the expected message is received.

> [!info] Defining Traits
> - Marker: **unfilled envelope icon** (hollow/outline)
> - Pauses the process until a specific message arrives
> - Completes upon message reception — the process then continues downstream
> - Pairs naturally with a Send Task in the originating pool

> [!example] Real-World Example
> In courier pickup management, the task "Receive Pickup Request" waits until the pickup request message arrives before the courier workflow can proceed.

---

### User Task

A ==User Task== involves **a human user performing the task using a software application**. The process engine assigns the task to a user, who completes it through a UI (e.g., a task list or form).

> [!info] Defining Traits
> - Marker: **person/user icon**
> - The process engine manages task assignment and tracks completion
> - Requires human interaction — the engine waits for the user to submit the form or confirm
> - Most common task type in workflow automation platforms

> [!example] Real-World Example
> An order approval task in an order handling process — the buyer reviews the order details in the shopping system and clicks "Approve" to complete the task.

---

### Manual Task

A ==Manual Task== represents work **performed without any business process engine or application support**. It is a task that happens entirely outside of the automated system.

> [!info] Defining Traits
> - Marker: **hand icon**
> - The process engine does not control or track execution
> - Used to document offline, paper-based, or physical activities in the process
> - The engine simply moves forward when the manual step is acknowledged

> [!example] Real-World Example
> A sign-off task in a Cart Inspection process — an inspector physically reviews the cart and signs a paper form, with no software interaction involved.

---

### Business Rule Task

A ==Business Rule Task== **provides input to a business rules engine** and receives the calculated output. It delegates decision logic to an external rule engine rather than embedding it in the process.

> [!info] Defining Traits
> - Marker: **table/grid icon**
> - The process engine sends data to a rules engine (e.g., Drools, IBM ODM)
> - The rules engine evaluates conditions and returns a result
> - Used for complex decision logic that changes independently of the process flow

> [!example] Real-World Example
> Analyzing survey results using a business rules engine — the task sends raw data, the engine applies scoring rules, summarizes the results, and returns the output for further processing (e.g., mailing to the main office).

---

### Script Task

A ==Script Task== is **executed directly by the business process engine** using a predefined script. It completes when the script finishes running.

> [!info] Defining Traits
> - Marker: **scroll/document icon**
> - The script is embedded in or referenced by the process model
> - No external system call required — the engine itself runs the logic
> - Typical uses: data transformation, validation, calculation within the process engine

> [!example] Real-World Example
> In a loan request approval process, a Script Task "Check Credit" runs a pre-written script that queries the applicant's credit status from an internal data source and returns a pass/fail result.

---

## 3. Task Types — Comparison at a Glance

| Task Type | Marker | Executor | Human Involved? | Waits For? |
|---|---|---|---|---|
| **Service Task** | Gear | External system/API | No | Service response |
| **Send Task** | Filled envelope | Process engine | No | Nothing (fire and forget) |
| **Receive Task** | Hollow envelope | Process engine | No | Incoming message |
| **User Task** | Person icon | Human via UI | Yes | User action/submission |
| **Manual Task** | Hand icon | Human (offline) | Yes | Manual acknowledgment |
| **Business Rule Task** | Table/grid | Rules engine | No | Rules engine result |
| **Script Task** | Scroll | Process engine (script) | No | Script completion |

---

## 4. Choosing the Right Task Type

> [!example] Decision Hints
> - Use **Service Task** when calling an API, web service, or backend system automatically
> - Use **Send Task** when dispatching a message or notification — and you don't wait for a reply
> - Use **Receive Task** when the process must pause and wait for an incoming message
> - Use **User Task** when a human completes work via a software interface (form, dashboard)
> - Use **Manual Task** when documenting an offline, physical, or paper-based activity
> - Use **Business Rule Task** when delegating complex decision logic to a dedicated rules engine
> - Use **Script Task** when the process engine itself should run embedded logic or transformation

> [!warning] Practical Note
> Not all BPMN tools implement every task type. Service Task and User Task are the most universally supported. Manual Task and Business Rule Task are often simplified or merged in lighter-weight tools.

---

## Summary

BPMN defines ==seven task types== — Service, Send, Receive, User, Manual, Business Rule, and Script — each distinguished by a small marker icon in the top-left corner of the rounded rectangle. The markers encode the execution mode at a glance: who or what performs the task, whether it waits for input, and whether human interaction is required. This taxonomy gives process designers precise vocabulary for modeling both automated workflows and human-in-the-loop processes, making the diagram self-explanatory to both business stakeholders and technical implementers.

---

## Related Notes

- [[Semi-Formal Notations - BPMN Flow Objects and Flows]]
- [[Semi-Formal Notations - BPMN Events and Symbols]]
- [[Semi-Formal Notations - BPMN Key Concepts]]
- [[Semi-Formal Notations - BPMN]]
- [[Semi-Formal Notations]]
