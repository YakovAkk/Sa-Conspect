---
title: "Informal Notations: Tips for Working with Flowcharts"
date: 2026-04-28
tags:
  - module6
  - flowchart
  - swimlane
  - informal
  - notation
  - canvas-note
cssclasses:
  - canvas-note
---

# Informal Notations: Tips for Working with Flowcharts

> [!note] Overview
> Creating an effective flowchart — especially a swim lane diagram — requires more than correct symbols. Four practical techniques significantly improve flowchart clarity and communication: ==color coding== to highlight parties and risk, ==swim lanes== to separate actors, ==clear start and end points== to define scope, and ==breaking complex flows into subflows== to manage complexity. Applied together, these techniques turn a raw process diagram into a clear, navigable communication tool.

---

## 1. Color Coding

==Color coding== uses a deliberate color scheme to make flowcharts visually informative beyond just the shape symbols. Colors add a semantic layer — they communicate meaning at a glance without requiring readers to trace every arrow.

### How to Use Color

> [!info] Color Coding Applications
> - **Highlight different parties** — assign a unique color to each actor, role, or department so readers can instantly see who is involved in each step
> - **Signify risky processes or decisions** — use a warning color (e.g., red or orange) to flag steps that are error-prone, compliance-sensitive, or time-critical
> - **Indicate specific paths** — use color to distinguish the happy path from exception paths, or to highlight a particular scenario being analyzed
> - **Show process stages** — use a gradient or distinct colors for phases (e.g., initiation, processing, completion)

### The Legend Rule

> [!warning] Always Include a Legend
> Color alone is not self-explanatory — different readers may interpret the same color differently. Every color-coded flowchart must include a **legend** that maps each color to its meaning. Without a legend, colors can confuse rather than clarify, especially for new readers or when the diagram is shared outside the team that created it.

> [!example] Example
> In a loan approval flowchart:
> - **Blue** = Applicant actions
> - **Green** = Bank officer actions
> - **Yellow** = Automated system steps
> - **Red** = Decision points with compliance implications
>
> The legend makes the color scheme self-contained — any reader can interpret the diagram without asking for explanation.

---

## 2. Use Swim Lanes to Separate Actors and Parties

When a process involves multiple actors, ==swim lanes== are the most effective structural tool for making responsibility clear. Rather than labeling each step individually with a responsible party, swim lanes group all of a participant's tasks into a dedicated band.

### When to Apply Swim Lanes

> [!info] Swim Lane Guidelines
> - Apply swim lanes when **two or more distinct actors** perform steps in the same process
> - When the actor list is long, **group individuals into departments or roles** rather than giving each person their own lane — too many lanes make the diagram unreadable
> - Use swim lanes as the primary structure when **handoffs between actors** are a key concern — every cross-lane arrow is a handoff made visible
> - Avoid swim lanes for single-actor processes — the added structure adds complexity without benefit

> [!example] Grouping vs. Individual Lanes
> Instead of creating separate lanes for each of five customer service representatives, create a single **"Customer Service"** lane. The lane represents the function, not the individual. This keeps the diagram clean and focused on the process, not the org chart.

### Swim Lanes vs. Color Coding — Combined Use

> [!tip] Combining Both Techniques
> Swim lanes and color coding can be used together:
> - Swim lanes define **which actor** is responsible for each step (structural clarity)
> - Colors within or across lanes highlight **what kind of step** it is (semantic clarity — risk, phase, path)
>
> When combined, color coding should complement lane structure, not substitute for it. If the same information is already conveyed by the lane position, adding a color for it creates redundancy.

---

## 3. Decide on the Start and End Points

A flowchart without clearly defined ==start and end points== is ambiguous — readers cannot tell when the process begins, when it is complete, or what the scope of the diagram covers.

### Why Start and End Points Matter

> [!info] Scope Definition Through Terminals
> - The **Start point** (oval or rounded rectangle with no incoming arrows) marks the trigger — the event or condition that initiates the process
> - The **End point(s)** (oval or rounded rectangle with no outgoing arrows) mark the terminal states — the conditions under which the process is considered complete
> - A well-defined Start and End make the diagram's scope explicit — readers know exactly what is and is not covered
> - Multiple End points are acceptable and often necessary — they represent different terminal outcomes (success, failure, cancellation)

### Common Start/End Mistakes

> [!warning] Anti-Patterns to Avoid
> - **Ambiguous start** — the first task is labeled with a process step rather than a triggering event. Fix: use an oval labeled with the event that initiates the process (e.g., "Customer submits request" not "Review request")
> - **Missing end** — the flow trails off without a terminal symbol. Fix: every path must terminate in an End oval, even paths that end in failure or cancellation
> - **Random endpoints** — the diagram ends at a convenient stopping point rather than a meaningful terminal state. Fix: end at outcomes that represent stable states the process can rest in
> - **Single end forced** — a single end state is used for multiple distinct outcomes. Fix: use multiple End ovals with meaningful labels (e.g., "Order Fulfilled," "Order Cancelled," "Order Escalated")

> [!example] Example
> A returns process should start with "Customer initiates return request" (trigger) and end with separate End ovals for "Refund Issued," "Exchange Completed," and "Return Rejected" — not a single "Process End" that hides the outcome.

---

## 4. Break It Down into Multiple Flows (Subflows)

Complex processes that span many steps, actors, and decision points become unreadable as a single flowchart. ==Subflows== (also called sub-processes or subprocess diagrams) break a large flowchart into manageable, focused segments.

### The Problem with Oversized Flowcharts

> [!warning] Why Long Flowcharts Fail
> - **Overwhelming density**: too many shapes and arrows prevent readers from following any single path
> - **Missed details**: readers scanning a complex diagram skip over steps, especially in dense sections
> - **Scope confusion**: a diagram covering dozens of steps and many actors conflates high-level overview with low-level detail
> - **Maintenance difficulty**: when the process changes, finding and updating the right part of a large diagram is error-prone

### How to Decompose into Subflows

> [!info] Decomposition Strategies
> - **By phase**: split the diagram at natural phase boundaries — each subflow covers one stage of the overall process (e.g., initiation, processing, completion, exception handling)
> - **By actor**: create a high-level diagram showing all actor interactions, then a separate detailed subflow for each actor's internal steps
> - **By frequency**: separate the main (happy) path from exception and edge-case paths — the main flow stays clean; exceptions are detailed in separate subflows
> - **By complexity**: any task that itself requires multiple steps can be represented as a collapsed task in the main diagram and expanded into its own subflow

### Linking Subflows

> [!tip] Cross-Flow References
> - Use a **reference symbol** (a rectangle with a page marker or a labeled connector) in the main flow to indicate "see subflow X"
> - Label the subflow with the name of the step it expands, and show its own Start and End terminals
> - Ensure each subflow can be read independently — it should make sense without requiring the reader to hold the parent diagram in their head simultaneously
> - In digital tools (Lucidchart, Draw.io, Miro), use **hyperlinked shapes** to let readers navigate between the main flow and subflows interactively

> [!example] Example
> A procurement process has 40 steps across 5 departments. Decompose it into:
> 1. **Overview diagram** — high-level flow showing the 5 phases and major handoffs (10 shapes total)
> 2. **Subflow: Request** — the 8 steps in the request and approval phase
> 3. **Subflow: Vendor Selection** — the 7 steps in vendor evaluation and selection
> 4. **Subflow: Order and Delivery** — the 9 steps in PO issuance and delivery tracking
> 5. **Subflow: Exception Handling** — the 6 steps for handling rejections and disputes
>
> Each subflow is readable on its own. The overview provides the map; the subflows provide the detail.

---

## 5. Practical Application — Tips Together

> [!example] Applying All Four Tips
> When creating a complex multi-actor flowchart:
> 1. **Start with scope**: define the Start trigger and all possible End states before drawing any steps
> 2. **Identify the actors**: determine whether there are enough to warrant swim lanes (2+ distinct actors = use lanes)
> 3. **Check complexity**: if the process has more than ~20 steps, plan to decompose into subflows before drawing
> 4. **Add color last**: once the structure (lanes, subflows) is correct, add color coding to highlight parties, risk, or paths — always with a legend
>
> Applying these in order prevents the common trap of drawing first and restructuring later.

---

## Summary

Four practical techniques make flowcharts significantly more effective. ==Color coding== adds a semantic layer to symbol-based diagrams — assigning colors to parties, risks, or paths — but requires a legend to be meaningful. ==Swim lanes== separate actors into dedicated bands, making responsibility clear and handoffs visible, especially when actors are grouped by department rather than individual. ==Clear start and end points== define the scope of the diagram, ensuring every path begins at a trigger and terminates at a meaningful outcome. ==Breaking complex flows into subflows== prevents diagrams from becoming overwhelming, allowing high-level overviews and detailed sub-process diagrams to serve different needs. Applied together, these techniques transform a flowchart from a raw sequence of steps into a clear, navigable communication artifact.

---

## Related Notes

- [[Informal Notations - Flowchart Diagrams]]
- [[Informal Notations - Swim Lane Diagrams]]
- [[Semi-Formal Notations - BPMN Pools and Lanes]]
- [[Semi-Formal Notations - BPMN Artifacts]]
- [[Semi-Formal Notations]]
