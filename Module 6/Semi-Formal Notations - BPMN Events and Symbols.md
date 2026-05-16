---
title: "Semi-Formal Notations: BPMN Events and Symbols"
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

# Semi-Formal Notations: BPMN Events and Symbols

> [!note] Overview
> ==Events== are key points in a business process that signal something important has happened. They can originate from inside or outside the system, affect how the process moves forward, and represent the changing, dynamic nature of workflows. BPMN represents events as ==circles with different border styles== to distinguish their role, and places ==symbols inside the circles== to specify the event type. There are three main event positions — ==Start==, ==Intermediate==, and ==End== — each with its own visual convention and behavioral meaning.

---

## 1. Event Positions

BPMN defines three positional event types that reflect where in the process the event occurs.

### Start Event

A ==Start Event== marks the **initiation of a business process** — it is the first thing that happens.

> [!info] Defining Traits
> - Every process requires at least one Start Event
> - Visualized as a **circle with a thin black border** (single thin line)
> - Represents the inception point of the process
> - Can be triggered by various event types (message received, timer fired, signal detected, etc.)
> - Only **catches** events — it cannot throw them

### End Event

An ==End Event== marks the **culmination and completion** of a business process.

> [!info] Defining Traits
> - Visualized as a **circle with a thick black border** (single thick line)
> - Every process path must terminate at an End Event
> - A process can have multiple End Events for different outcomes (success, failure, cancellation)
> - Only **throws** events — it cannot catch them
> - End Event types include: None, Message, Error, Escalation, Signal, Terminate, Compensation

### Intermediate Event

An ==Intermediate Event== occurs **during the execution of a process** — either while an activity is running or after a previous flow element has completed.

> [!info] Defining Traits
> - Visualized as a **circle with a double border** (two concentric lines)
> - Drives business flow based on specified conditions or occurrences
> - Can **catch** events (waiting for something to happen) or **throw** events (sending a signal or message)
> - Can be attached to the boundary of an activity (Boundary Event) to handle interruptions or exceptions

![[Pasted image 20260428201509.png]]
---

## 2. Event Positions — Visual Comparison

| Aspect | Start Event | Intermediate Event | End Event |
|---|---|---|---|
| **Role** | Initiates the process | Occurs during the process | Terminates the process |
| **Border** | Thin single line | Double line (two circles) | Thick single line |
| **Direction** | Catch only | Catch or Throw | Throw only |
| **Multiplicity** | At least one required | Zero or more | At least one required |
| **Placement** | Beginning of flow | Mid-flow or on activity boundary | End of each flow path |

![[Pasted image 20260428201519.png]]
---

## 3. Event Symbols

BPMN uses symbols placed **inside the event circle** to specify the nature of the event. The same symbol can appear in a Start, Intermediate, or End event circle — the border tells you *when* it occurs, the symbol tells you *what* it is.

> [!info] Common Event Symbols
> | Symbol | Icon | Meaning |
> |---|---|---|
> | **None** | Empty circle | Generic event — no specific trigger or result |
> | **Message** | Envelope icon | A message is sent or received (e.g., email, API call) |
> | **Timer** | Clock icon | A specific time or cycle triggers the event |
> | **Error** | Lightning bolt icon | An error or fault is thrown or caught |
> | **Signal** | Triangle/flag icon | A signal is broadcast to multiple recipients |
> | **Escalation** | Arrow-up icon | An issue is escalated to a higher authority |
> | **Conditional** | Document with lines icon | Triggers when a condition becomes true |
> | **Compensation** | Rewind arrows icon | Triggers compensating actions to undo previous steps |
> | **Link** | Arrow icon | Connects flow between different parts of the diagram |
> | **Terminate** | Filled circle icon (end only) | Immediately stops all tokens in the process |

> [!tip] Symbol + Border = Full Event Meaning
> Combine the border style (Start/Intermediate/End) with the interior symbol to read any BPMN event:
> - **Thin border + envelope** = Message Start Event (process starts when a message arrives)
> - **Double border + clock** = Timer Intermediate Event (process pauses until a time condition is met)
> - **Thick border + lightning bolt** = Error End Event (process ends due to an unhandled error)

---

## 4. Catch vs. Throw Events

Events in BPMN are directional — they either **catch** (receive) or **throw** (send) a trigger.

> [!info] Catch and Throw Rules
> - **Start Events** — always catch (they wait for a trigger to begin the process)
> - **End Events** — always throw (they emit a signal, message, or error upon completion)
> - **Intermediate Events** — can be either:
>   - **Catching** (unfilled symbol inside) — the process waits for the event to occur
>   - **Throwing** (filled symbol inside) — the process emits the event and continues

---

## 5. Boundary Events

==Boundary Events== are a special use of Intermediate Events — they are **attached to the boundary of an activity** to handle exceptional situations.

> [!info] Boundary Event Behavior
> - **Interrupting Boundary Event** — solid border: stops the activity and redirects the flow along the exception path
> - **Non-Interrupting Boundary Event** — dashed border: starts a parallel path without stopping the main activity
> - Common uses: handling timeouts on a task, catching errors during a sub-process, reacting to a cancellation request

---

## 6. Order Processing Example

> [!example] BPMN Event in Practice
> Consider a simple order processing flow:
>
> 1. **Start Event** (Message symbol) — the process begins when an order is **received** (message arrives)
> 2. **Intermediate Event** (Conditional symbol) — a credit limit check is performed; the process reacts to the result
> 3. **End Event — Path A** (None symbol) — the order is **successfully processed**
> 4. **End Event — Path B** (Error symbol) — a **problem is found** and the process ends with an error
>
> This example illustrates how the three event positions map to the lifecycle of a real business transaction — initiation, mid-process decision points, and multiple outcome terminations.

---

## 7. Why Event Symbols Matter

> [!tip] Visual Semantics
> The symbol inside the circle makes BPMN diagrams self-documenting:
> - Readers immediately know **what kind of trigger** starts or ends the process
> - Intermediate events with symbols communicate **why** the flow pauses or branches
> - Without symbols, all events would look identical and require textual labels to distinguish them
>
> This symbol system — combined with the three border styles — creates a compact, internationally understood visual language for process behavior.

---

## Summary

==BPMN Events== are represented as circles placed at key points in the process flow. The **border style** identifies position: thin (Start), double (Intermediate), thick (End). The **interior symbol** identifies the event type: message, timer, error, signal, and more. Start Events always catch triggers; End Events always throw; Intermediate Events can do either. Boundary Events extend this model by attaching catching behavior to activity edges for exception and timeout handling. Together, these conventions make process behavior immediately readable — the shape alone communicates both timing and causality.

---

## Related Notes

- [[Semi-Formal Notations - BPMN Flow Objects and Flows]]
- [[Semi-Formal Notations - BPMN Key Concepts]]
- [[Semi-Formal Notations - BPMN]]
- [[Semi-Formal Notations]]
