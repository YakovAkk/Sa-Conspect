---
title: "Semi-Formal Notations: BPMN Key Concepts and Features"
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

# Semi-Formal Notations: BPMN Key Concepts and Features

> [!note] Overview
> ==BPMN== shows business processes using diagrams with different ==graphic elements== organized into clear categories. This visual approach makes it easier to understand how a process works — for both business analysts and technical implementers. The main goal is to help design and read both simple and complex business process diagrams in a user-friendly, standardized way. BPMN is especially useful for workflows run by ==orchestration servers==, focusing on activities rather than the internal details of individual components.

![[Pasted image 20260428200214.png]]
---

## 1. Visual Design Philosophy

BPMN's visual approach is built around one core principle: ==readability across audiences==. Diagrams must be understandable by people who design business processes, people who implement them in software, and people who operate them in production.

> [!info] Design Goals
> - **Simple processes** should be simple to draw — a few shapes connected by arrows
> - **Complex processes** (parallel paths, sub-processes, error handling) should be expressible without ambiguity
> - Symbols are organized into **clear categories** so readers can immediately recognize element types
> - The notation is tool-agnostic — any BPMN-compliant tool produces diagrams that follow the same rules

---

## 2. The Five BPMN Symbol Categories

BPMN organizes all its symbols into five official categories. This categorization is what makes large diagrams navigable and consistent.

### Category 1: Flow Objects

==Flow Objects== are the main building blocks of a BPMN diagram — they represent what happens in the process.

> [!info] Flow Object Types
> - **Events** — things that happen (start, intermediate, end) — represented as circles
>   - Types: Message, Timer, Error, Signal, Escalation, Conditional, Compensation, Link, Terminate
> - **Activities** — work that is performed — represented as rounded rectangles
>   - Types: Task (atomic), Sub-Process (compound), Call Activity (reuse)
>   - Task markers: Manual, User, Service, Script, Business Rule, Send, Receive
> - **Gateways** — decision and merging points — represented as diamonds
>   - Types: Exclusive (XOR), Parallel (AND), Inclusive (OR), Event-Based, Complex

### Category 2: Data

==Data== elements represent information used or produced by the process.

> [!info] Data Elements
> - **Data Object** — data item referenced by activities (document icon)
> - **Data Store** — persistent data storage (database icon) — represents data that persists beyond process execution
> - **Data Input / Data Output** — process-level data (used at the process boundary)

### Category 3: Connecting Objects

==Connecting Objects== link elements together and define the flow.

> [!info] Connector Types
> - **Sequence Flow** — ordered connection within a pool (solid arrow) — defines the execution order
> - **Message Flow** — communication between separate pools (dashed arrow) — crosses organizational boundaries
> - **Association** — links artifacts and data to flow elements (dotted line) — no execution semantics

### Category 4: Swimlanes

==Swimlanes== organize the diagram by participant or responsibility.

> [!info] Swimlane Elements
> - **Pool** — represents a participant (organization, person, or system) — the outer container
>   - A pool with visible internal flow is a **White Box Pool** (process visible)
>   - A pool with no internal flow is a **Black Box Pool** (internal process hidden — only interactions visible)
> - **Lane** — horizontal or vertical subdivision within a pool — represents a role, department, or system within the participant

### Category 5: Artifacts

==Artifacts== add supplementary information to a diagram without affecting the flow.

> [!info] Artifact Types
> - **Group** — a dashed rounded rectangle that visually groups related elements (for documentation only — no execution meaning)
> - **Text Annotation** — a note attached to any element to explain or add context

---

## 3. BPMN and Orchestration Servers

> [!tip] Orchestration Focus
> BPMN comes from business process modeling and is especially useful for designing workflows run by ==orchestration servers== (also called BPMN engines or BPM platforms — e.g., Camunda, Activiti, Flowable, IBM BPM).

In an orchestration model:
- A **central coordinator** (the orchestration server) manages the process
- It decides which activity to execute next, sends tasks to participants, and waits for results
- The BPMN diagram is the **executable specification** — the engine reads the diagram and drives execution

> [!info] What Orchestration Servers Use from BPMN
> - **Sequence flows and gateways** — to determine the next step
> - **Service tasks** — to call APIs or backend systems automatically
> - **User tasks** — to assign work items to human users
> - **Timer events** — to schedule delayed execution or deadlines
> - **Error events** — to handle failures and trigger compensation
> - **Sub-processes** — to modularize complex workflows

### Activity Focus, Not Component Focus

> [!warning] Key Design Principle
> BPMN focuses on ==activities== (what needs to be done and in what order) rather than on the internal details of individual components (how a service works internally). This is intentional: the orchestration server cares about **what** to call and **when**, not **how** the called service implements its logic.

---

## 4. Key Features Summary

| Feature | Description |
|---|---|
| **Standardized by OMG** | Governed by the Object Management Group — ensures tool interoperability |
| **Five symbol categories** | Flow Objects, Data, Connecting Objects, Swimlanes, Artifacts |
| **Dual audience** | Readable by business stakeholders AND executable by workflow engines |
| **Orchestration support** | Directly drives BPMN-compliant workflow engines |
| **Scalability** | Handles simple flows (3 steps) and complex enterprise processes (hundreds of elements) |
| **Event-driven** | Rich event taxonomy supports timeouts, errors, messages, signals, and escalation |
| **Concurrency** | Parallel gateways model simultaneous work streams |
| **Modularity** | Sub-processes and call activities enable reuse and encapsulation |

---

## 5. Simple vs Complex Diagrams

> [!example] Diagram Complexity Scale
> - **Simple**: Start → Task A → Task B → End (3 elements, 1 flow)
> - **Moderate**: Add a gateway (XOR) for conditional branching, 2 paths, merge, End
> - **Complex**: Multiple pools (cross-organizational), parallel flows, sub-processes, error handling, timer events, compensation handlers
>
> BPMN's category system ensures that even complex diagrams remain structured and parseable — readers know a diamond is always a gateway, a circle is always an event, a rectangle is always an activity.

---

## Summary

BPMN organizes its visual vocabulary into ==five categories== — Flow Objects, Data, Connecting Objects, Swimlanes, and Artifacts — ensuring diagrams are readable at any complexity level. Its design philosophy prioritizes ==activity-level thinking==: what happens, when, and by whom — not how individual components work internally. This makes it the ideal notation for orchestration-driven workflows, where a central server reads the diagram and drives execution across systems and people. The standardized symbol set ensures consistency across tools and teams.

---

## Related Notes

- [[Semi-Formal Notations - BPMN]]
- [[Semi-Formal Notations]]
- [[Semi-Formal Notations - UML Behavioral Diagrams]]
