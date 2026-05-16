---
title: "Semi-Formal Notations: BPMN Diagram Types"
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

# Semi-Formal Notations: BPMN Diagram Types

> [!note] Overview
> BPMN uses two main diagram types in solution architecture, each serving a different modeling purpose. ==Process Diagrams== describe the internal step-by-step flow of tasks, events, and decisions within a single participant's process. ==Collaboration Diagrams== show how two or more participants (organizations, departments, or systems) interact with each other through message flows. Choosing the right diagram type depends on whether you need to document how a process works internally or how multiple parties communicate externally.

---

## 1. Process Diagram

A ==Process Diagram== (also called an **orchestration diagram**) models the **internal workflow of a single participant** — showing how tasks, events, gateways, and flows sequence to complete a business objective.
![[Pasted image 20260428203126.png]]
### Key Characteristics

> [!info] Defining Traits
> - Depicts the flow of work **within one organizational participant** (a pool or a set of lanes)
> - Focuses on: **what tasks are performed**, in **what order**, and **under what conditions**
> - Contains Sequence Flows connecting events, activities, and gateways
> - May include Data Objects and Data Stores to show information dependencies
> - Can be a single pool (one department) or multiple lanes within one pool (roles within a department)
> - Does **not** show communication with external parties — that requires a Collaboration Diagram

### Structure

> [!info] Typical Elements
> - **Start Event** — initiates the process
> - **Tasks** — atomic units of work (with task type markers)
> - **Gateways** — decision points (XOR, AND, OR, Event-Based)
> - **Sub-Processes** — compound activities encapsulating internal flows
> - **End Event** — terminates each flow path
> - **Data Objects / Stores** — information used or produced
> - **Annotations / Groups** — documentation layer

> [!example] Real-World Example
> An order review process:
>
> ```
> Start → Review Customer Order → [XOR Gateway: Policy Applies?]
>    ├── Yes → Apply Policy → Update Order → End
>    └── No → Process Standard Order → End
> ```
>
> This diagram focuses entirely on the internal decision logic of the order review team — what they check, what decisions they make, and what results they produce. No external communication is shown.

### When to Use a Process Diagram

> [!tip] Best Scenarios
> - Documenting the internal workflow of a department, team, or system
> - Designing a workflow for automation by a BPMN engine (Camunda, Activiti)
> - Analyzing process efficiency, identifying bottlenecks, or redesigning flows
> - Communicating a process internally to developers or analysts

---

## 2. Collaboration Diagram

A ==Collaboration Diagram== models **how two or more participants interact** — showing the message flows that cross organizational or system boundaries. It combines multiple processes (pools) and the communication between them.
![[Pasted image 20260428203137.png]]
### Key Characteristics

> [!info] Defining Traits
> - Shows **two or more pools** — each representing a different participant (organization, department, system, customer, partner)
> - Uses **Message Flows** (dashed arrows) to show communication between pools
> - Each pool may show its internal process (White Box) or hide it (Black Box)
> - Sequence Flows stay inside each pool — Message Flows cross pool boundaries
> - Focuses on **what messages are exchanged** and **when** — not on internal implementation details
> - Models the coordination protocol between multiple autonomous participants

### Structure

> [!info] Typical Elements
> - **Multiple Pools** — one per participant
> - **White Box Pools** — participants whose internal process is visible
> - **Black Box Pools** — participants whose internals are hidden (only message exchanges are shown)
> - **Message Flows** — dashed arrows crossing pool boundaries
> - **Message Events** — Start, Intermediate, or End events that send or receive messages
> - Internal Sequence Flows within each pool

> [!example] Real-World Example — Doctor and Patient
> A Doctor–Patient collaboration:
>
> ```
> [Patient Pool]                          [Doctor Pool]
> Patient becomes ill ──msg──► Doctor receives patient
>                               Doctor examines patient
>                               Doctor prescribes medication ──msg──►
>                                                           Patient receives prescription
>                                                           Patient picks up medication
> ```
>
> The collaboration starts when the Patient pool sends a message (illness notification / appointment request) to the Doctor pool, and ends when the Patient receives the prescription. The internal steps of each participant are visible inside their own pool.

### When to Use a Collaboration Diagram

> [!tip] Best Scenarios
> - Modeling how an organization interacts with customers, partners, or external systems
> - Designing APIs, integration contracts, or inter-system communication protocols
> - Showing the "handshake protocol" between two parties without exposing internal logic
> - Documenting end-to-end business transactions that span organizational boundaries

---

## 3. Process vs. Collaboration — Comparison at a Glance

| Aspect | Process Diagram | Collaboration Diagram |
|---|---|---|
| **Focus** | Internal workflow of one participant | Communication between multiple participants |
| **Participants** | One pool (or multiple lanes in one pool) | Two or more pools |
| **Primary flow type** | Sequence Flow | Message Flow (plus internal Sequence Flows) |
| **Primary question** | How does this process work internally? | How do these parties talk to each other? |
| **Black Box pools** | Not applicable | External participants can be Black Box |
| **Typical audience** | Process designers, developers, workflow engines | Architects, integrators, business stakeholders |
| **Use case** | Process design, automation, internal analysis | Integration design, cross-org coordination |

---

## 4. Combining Both Types

> [!tip] Layered Modeling Approach
> In practice, organizations use both diagram types together:
> 1. **Collaboration Diagram** — defines the high-level interaction between all parties (what messages are exchanged)
> 2. **Process Diagrams** — one per participant — detail the internal steps within each pool
>
> This layered approach separates concerns: the collaboration diagram is the contract between parties; the process diagrams implement that contract internally. Architects work at the collaboration level; analysts and developers work at the process level.

---

## 5. When to Choose Which

> [!example] Decision Hints
> - Use a **Process Diagram** when documenting or designing the **internal workflow** of a single team, department, or system — especially when driving a BPMN engine
> - Use a **Collaboration Diagram** when modeling **interactions between multiple parties** — customers, partners, external systems, or different departments
> - Use **both** when building an end-to-end integration: collaboration for the interface contract, process diagrams for each participant's internal implementation

---

## Summary

BPMN defines two primary diagram types for solution architecture: ==Process Diagrams== model the sequential flow of tasks, decisions, and events within a single participant, making them ideal for internal workflow design and process automation. ==Collaboration Diagrams== model the message exchange between multiple participants — combining pools, their internal processes, and the Message Flows that connect them — making them ideal for cross-organizational integration design. The two types are complementary: collaboration diagrams define the communication contract; process diagrams implement each participant's role in that contract.

---

## Related Notes

- [[Semi-Formal Notations - BPMN]]
- [[Semi-Formal Notations - BPMN Key Concepts]]
- [[Semi-Formal Notations - BPMN Pools and Lanes]]
- [[Semi-Formal Notations - BPMN Flow Objects and Flows]]
- [[Semi-Formal Notations]]
