---
title: "Semi-Formal Notations: BPMN Flow Objects and Flows"
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

# Semi-Formal Notations: BPMN Flow Objects and Flows

> [!note] Overview
> In BPMN, ==Flow Objects== — Events, Activities, and Gateways — define how a business process works and moves forward. Because these elements work together, they need to be linked using ==Connecting Objects==, which creates a clear and logical flow. The two primary flow connectors are ==Sequence Flow== (ordering activities within a pool) and ==Message Flow== (communicating between pools). Together, they show how activities and communication work smoothly to keep business process diagrams clear and easy to understand.

---

## 1. Flow Objects

==Flow Objects== are the active elements that define what happens in a process. There are three types:

### Events

==Events== represent things that **happen** during the course of a process — they trigger, interrupt, or conclude it.

> [!info] Event Categories
> - **Start Event** — initiates a process (thin-bordered circle)
> - **Intermediate Event** — occurs during the process — may catch or throw a signal (double-bordered circle)
> - **End Event** — terminates the process (thick-bordered circle)
> - Event types: Message, Timer, Error, Signal, Escalation, Conditional, Compensation, Link, Terminate

### Activities

==Activities== represent **work that is performed** within the process.

> [!info] Activity Types
> - **Task** — an atomic unit of work that cannot be broken down further (rounded rectangle)
>   - Task markers: User Task, Service Task, Script Task, Manual Task, Business Rule Task, Send Task, Receive Task
> - **Sub-Process** — a compound activity with its own internal process (rectangle with `+` marker)
> - **Call Activity** — reuses a globally defined process or task (bold-bordered rectangle)

### Gateways

==Gateways== control **how the flow splits and merges** — they model decisions, parallelism, and synchronization.

> [!info] Gateway Types
> - **Exclusive Gateway (XOR)** — only one outgoing path is taken (diamond with `X` or empty)
> - **Parallel Gateway (AND)** — all outgoing paths are taken simultaneously (diamond with `+`)
> - **Inclusive Gateway (OR)** — one or more paths are taken based on conditions (diamond with `O`)
> - **Event-Based Gateway** — the next path depends on which event occurs first
> - **Complex Gateway** — advanced conditional logic not covered by the above types

---

## 2. Sequence Flow

==Sequence Flow== represents the **sequential order of activities** to be executed within the process. It defines the direction and order in which flow elements are performed.

### Visual Representation

> [!info] How It Looks
> - Visualized as a **straight line with a solid arrowhead** (→)
> - The arrow points in the direction of execution
> - The source element must complete before the target element begins

### Variants

| Variant | Description | Visual Marker |
|---|---|---|
| **Normal Sequence Flow** | Standard execution connection between two elements | Solid line with arrowhead |
| **Conditional Sequence Flow** | Flow is taken only if a condition is true | Small diamond (condition marker) at the source |
| **Default Sequence Flow** | Taken when all other conditions are false | Slash mark at the source end |

### Scope Rule

> [!warning] Boundary Rule
> Sequence Flow is **exclusive to connecting flow elements within the same pool or lane**. It can cross lane boundaries freely (within the same pool), but it **cannot cross pool boundaries**. Cross-pool communication requires Message Flow instead.

---

## 3. Message Flow

==Message Flow== illustrates the **exchange of messages across organizational boundaries** — between pools, such as between different departments, organizations, or systems.

### Visual Representation

> [!info] How It Looks
> - Visualized as a **dashed line** with:
>   - A **hollow circle** (○) at the **origin** (where the message is sent)
>   - An **open arrowhead** (→) at the **termination** (where the message is received)
> - The direction of the arrow shows who sends and who receives

### Scope Rule

> [!warning] Boundary Rule
> Message Flow is **specifically reserved for connecting events or activities in different pools**. It cannot be used to connect elements within the same pool — that is the role of Sequence Flow.

### What Can Be Connected

> [!info] Valid Message Flow Connections
> - Pool → Pool (between two participants)
> - Event → Activity (across pools)
> - Activity → Event (across pools)
> - Activity → Activity (across pools)
> - The source must be in one pool; the target must be in a different pool

---

## 4. Sequence Flow vs Message Flow — Comparison

| Aspect | Sequence Flow | Message Flow |
|---|---|---|
| **Purpose** | Orders activities within a process | Communicates between separate participants |
| **Scope** | Within a single pool (can cross lanes) | Between two different pools |
| **Visual** | Solid line with arrowhead | Dashed line with circle at source + arrowhead |
| **Represents** | Execution order | Message exchange (data, request, response) |
| **Pool boundary** | Cannot cross pool boundaries | Must cross pool boundaries |
| **Typically connects** | Activity → Activity, Gateway → Activity, Event → Activity | Pool ↔ Pool, Activity ↔ Event (across pools) |

---

## 5. How Flow Objects and Flows Work Together

> [!example] Interaction Pattern
> A complete BPMN process typically uses all three types of flow objects connected by both flow types:
>
> 1. **Start Event** ──Sequence Flow──► **Task** ──Sequence Flow──► **Gateway**
> 2. **Gateway** splits into two paths:
>    - Path A: ──Sequence Flow──► **Service Task** ──Sequence Flow──► **End Event**
>    - Path B: ──Sequence Flow──► **User Task** ──Sequence Flow──► **End Event**
> 3. When the Service Task sends a confirmation to an external system:
>    - **Service Task** ──Message Flow──► **Start Event** (in the external system's pool)
>
> This shows how Sequence Flow drives the internal execution order, while Message Flow handles external communication.

---

## Summary

==Flow Objects== (Events, Activities, Gateways) are the active building blocks that define what a process does. ==Sequence Flow== connects them in execution order within a pool — with normal, conditional, and default variants — and enforces that it cannot cross pool boundaries. ==Message Flow== handles cross-pool communication, visualized as a dashed line with a circle at the source and arrowhead at the destination, and must connect elements in different pools. Together, these elements and connectors make BPMN diagrams self-explanatory: the structure of the diagram reflects the structure of the business process.

---

## Related Notes

- [[Semi-Formal Notations - BPMN Key Concepts]]
- [[Semi-Formal Notations - BPMN Pools and Lanes]]
- [[Semi-Formal Notations - BPMN]]
- [[Semi-Formal Notations]]
