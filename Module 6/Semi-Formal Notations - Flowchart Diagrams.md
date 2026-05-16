---
title: "Semi-Formal Notations: Flowchart Diagrams"
date: 2026-04-28
tags:
  - module6
  - flowchart
  - semi-formal
  - notation
  - canvas-note
cssclasses:
  - canvas-note
---

# Semi-Formal Notations: Flowchart Diagrams

> [!note] Overview
> ==Flowcharts== are visual tools that show each step in a process using standardized shapes connected by arrows. Arrows guide the viewer from the beginning to the end of the process, while shapes communicate what kind of step is happening. The primary benefit of flowcharts is their ==simplicity== — they are easy to understand for both technical and non-technical audiences, making them one of the most widely used notations for documenting and communicating simple processes.

---

## 1. Core Symbols

Flowcharts rely on a small set of standard shapes. Each shape carries a specific semantic meaning, allowing readers to interpret the diagram without a legend.

### Arrow

An ==Arrow== represents the **flow of control** between steps in the process.

> [!info] Defining Traits
> - Connects one symbol to another with a directional arrowhead
> - Indicates the order of execution — from source symbol to destination symbol
> - Guides the viewer from the start of the process to its end
> - Multiple arrows can leave a diamond (decision point) to represent different outcomes
> - Never carries process logic itself — logic is expressed by the shapes it connects

> [!example] Real-World Example
> After a "Submit Application" rectangle, an arrow points to an "Application Complete?" diamond. The arrow communicates: "once submission is done, the next step is to evaluate completeness." The direction is explicit — no ambiguity about what follows what.

---

### Diamond

A ==Diamond== represents a **decision point** in the process — a question that must be answered before the process can continue.

> [!info] Defining Traits
> - Shaped as a rotated square (diamond / rhombus)
> - Contains a Yes/No or True/False question
> - Has **two or more arrows** emanating from it — one per possible outcome
> - Each outgoing arrow is typically labeled with the answer it represents (e.g., "Yes," "No," "Approved," "Rejected")
> - The process branches based on which condition is met — only one branch is followed per execution

> [!example] Real-World Example
> A diamond labeled "Is the form valid?" has two outgoing arrows:
> - "Yes" → "Process Submission" rectangle
> - "No" → "Return Error to User" rectangle
>
> The diamond makes the conditional logic visible — no ambiguity about when each path is taken.

> [!tip] Comparison with BPMN
> The flowchart diamond serves the same conceptual role as a BPMN **Exclusive Gateway (XOR)** — it branches the flow based on a condition. However, flowchart diamonds are informal and carry no execution semantics, whereas BPMN gateways are precisely defined in the BPMN specification.

---

### Rectangle

A ==Rectangle== represents a **task or activity** — a specific action or step that needs to be undertaken.

> [!info] Defining Traits
> - Standard rectangular shape (sometimes with slightly rounded corners in modern tools)
> - Contains a short description of the action being performed (e.g., "Send Confirmation Email," "Calculate Total," "Validate Input")
> - Represents a single unit of work — atomic in the context of the flowchart's granularity
> - Has one incoming arrow and one outgoing arrow in most cases (no branching — that is the diamond's role)
> - Can represent manual actions, automated steps, or system operations depending on context

> [!example] Real-World Example
> A rectangle labeled "Check Book Status" performs a lookup in the library system. It receives control from an arrow (from the Start Event) and passes control via an arrow to the next step (a decision diamond). The rectangle communicates what work is done — not how or why.

---

## 2. Basic Symbol Reference

| Symbol | Shape | Represents | Arrows In | Arrows Out |
|---|---|---|---|---|
| **Arrow** | Directed line with arrowhead | Flow of control between steps | — | — |
| **Diamond** | Rotated square | Decision point (Yes/No, True/False) | 1 | 2 or more |
| **Rectangle** | Standard rectangle | Task or activity | 1 | 1 |
| **Oval / Rounded rectangle** | Oval or pill shape | Start or End event | 0 (Start) / 1 (End) | 1 (Start) / 0 (End) |

> [!info] Start and End
> Most flowcharts also include **oval or rounded rectangle** shapes to mark the Start and End of the process. They are sometimes called **terminals**. The Start oval has one outgoing arrow; the End oval has one incoming arrow and no outgoing arrows.

---

## 3. Benefits and Use Cases

### Simplicity

> [!tip] Accessible to All Audiences
> Flowcharts are designed for simplicity:
> - A small symbol set (rectangles, diamonds, arrows, ovals) is all that is needed
> - Both technical and non-technical audiences can read a flowchart without training
> - The directional arrows make the flow self-evident — the reader's eye follows the arrows naturally
> - No background in formal notations (BPMN, UML) is required

### Process Design and Documentation

> [!info] When to Use Flowcharts
> Flowcharts are most effective for:
> - **Designing simple processes or programs** — capturing the intended logic before implementation
> - **Documenting existing processes** — creating a visual record of how a process currently works
> - **Spotting problems** — a visual representation makes mistakes, redundancies, and delays easier to identify than a written description
> - **Onboarding and training** — new team members can understand a process quickly from a flowchart

### Flexibility

> [!example] Types of Flowcharts
> Different flowchart types exist, each using its own set of shapes and conventions:
> - **Process Flowchart** — the most common; maps the steps of any business or technical process
> - **Swimlane Flowchart** — adds horizontal or vertical lanes to show which person or team is responsible for each step (similar to BPMN lanes)
> - **Data Flow Diagram (DFD)** — extends flowchart concepts to show how data moves through a system
> - **System Flowchart** — focuses on hardware and software components in an IT context
>
> This flexibility makes flowcharts applicable across domains — from software development to business operations to scientific research.

---

## 4. Flowcharts vs. BPMN — When to Choose Which

| Aspect | Flowchart | BPMN |
|---|---|---|
| **Formality** | Informal — no governing specification | Semi-formal — governed by OMG BPMN 2.0 spec |
| **Symbol set** | Small (rectangles, diamonds, arrows, ovals) | Large (events, gateways, tasks, pools, lanes, data) |
| **Audience** | Technical and non-technical | Primarily business analysts, architects, developers |
| **Execution** | Not executable — documentation only | Can drive BPMN-compliant workflow engines |
| **Decision modeling** | Diamond (informal Yes/No) | Exclusive, Inclusive, Parallel, Event-Based gateways |
| **Multi-participant** | Swimlane variant (informal) | Collaboration diagrams with pools and message flows |
| **Best for** | Simple processes, quick documentation, training | Complex enterprise processes, automation, integration |

> [!example] Decision Hint
> - Use a **Flowchart** when the audience includes non-technical stakeholders, the process is simple, or a quick visual overview is the goal
> - Use **BPMN** when the process will be automated, involves multiple organizations, requires precise decision modeling, or needs to serve as an executable specification

---

## Summary

==Flowcharts== use three primary symbols — ==Arrows== (flow of control), ==Diamonds== (decision points with Yes/No or True/False branches), and ==Rectangles== (tasks or activities) — to visualize the steps of a process. Their defining strength is ==simplicity==: a small, standardized symbol set makes flowcharts readable by both technical and non-technical audiences. They are well-suited for designing and documenting simple processes, spotting bottlenecks and errors, and onboarding new team members. Different flowchart types (process, swimlane, data flow, system) extend the basic notation for specific contexts, while BPMN provides a more formal and executable alternative for complex enterprise processes.

---

## Related Notes

- [[Semi-Formal Notations - BPMN]]
- [[Semi-Formal Notations - BPMN Gateways]]
- [[Semi-Formal Notations - BPMN Pools and Lanes]]
- [[Semi-Formal Notations]]
