---
title: "Semi-Formal Notations: BPMN Gateways"
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

# Semi-Formal Notations: BPMN Gateways

> [!note] Overview
> ==Gateways== are the third type of BPMN Flow Object — they are **decision points** that control how the process moves forward. Gateways evaluate conditions (from inside the process or from external events) and direct the flow to one or more outgoing paths. All gateways share the same base shape: a ==diamond==. Different icons inside the diamond indicate the gateway type and its routing logic. BPMN defines four primary gateway types: ==Exclusive==, ==Inclusive==, ==Event-Based==, and ==Parallel==.

---

## 1. Exclusive Gateway (XOR)

An ==Exclusive Gateway== is a **diversion point** that allows only **one outgoing path** to be taken in any given process instance. It is the most common gateway type and is used wherever a decision produces mutually exclusive outcomes.

### Key Characteristics

> [!info] Defining Traits
> - Symbol: **diamond with an `X`** (or an empty diamond — both are valid representations)
> - Evaluates conditions on each outgoing sequence flow in order
> - Only one path is taken — the first path whose condition evaluates to true
> - A **default path** (marked with a slash `/` at the source) is taken when no other condition is met
> - Can also be used as a **merging gateway** (multiple incoming flows, one outgoing) — the first arriving token continues

### Splitting vs. Merging

| Mode | Behavior |
|---|---|
| **Split (diverging)** | Evaluates all outgoing conditions — takes exactly one path |
| **Merge (converging)** | Passes through the first token that arrives — no synchronization |

> [!example] Real-World Example
> Processing an invoice:
> - Condition A: Invoice ≤ $1,000 → path "Auto-Approve"
> - Condition B: Invoice $1,001–$10,000 → path "Manager Review"
> - Condition C: Invoice > $10,000 → path "Executive Approval"
> - Default: → path "Manual Review"
>
> In any given instance, exactly one of these paths is taken.

---

## 2. Inclusive Gateway (OR)

An ==Inclusive Gateway== differs from the Exclusive Gateway by **permitting one or more outgoing paths** to be taken simultaneously. All outgoing conditions are evaluated, and every path whose condition is true is activated.

### Key Characteristics

> [!info] Defining Traits
> - Symbol: **diamond with an `O` (circle)**
> - Evaluates **all** outgoing conditions — not just the first true one
> - One, some, or all outgoing paths may be activated depending on how many conditions are true
> - When merging, **waits for all active paths** to complete before continuing (synchronization)
> - A default path handles the case where no conditions are true

### Splitting vs. Merging

| Mode | Behavior |
|---|---|
| **Split (diverging)** | Evaluates all conditions — activates every true path |
| **Merge (converging)** | Waits for all active incoming paths to complete before proceeding |

> [!example] Real-World Example
> Shipping an order:
> - Condition A: Items available → ship by **sea** (activated)
> - Condition B: Express requested → ship by **air** (activated)
> - Both conditions can be true → the order is shipped both by sea AND by air (partial shipments)
>
> The merging Inclusive Gateway waits for both shipments to be confirmed before continuing.

> [!warning] Key Difference from Exclusive
> Exclusive: exactly one path. Inclusive: one or more paths. The merge behavior is also different — Inclusive merges wait for all active paths; Exclusive merges pass through on first arrival.

---

## 3. Event-Based Gateway

An ==Event-Based Gateway== **triggers the outgoing path based on which event occurs first** — rather than evaluating data conditions. The process pauses at the gateway and waits for one of the specified events to happen.

### Key Characteristics

> [!info] Defining Traits
> - Symbol: **diamond with a double circle and pentagon inside** (or with an event symbol)
> - Only **one path is taken** — the path associated with whichever event fires first
> - The process **pauses** at the gateway until one of the events occurs
> - Events are typically initiated by third parties (customer responses, timer expiry, message arrival)
> - Always followed by **catching events** (Message, Timer, Signal, etc.) — not activities or gateways directly

### Behavior

> [!info] How It Works
> 1. Process reaches the Event-Based Gateway and pauses
> 2. The gateway "listens" for any of its outgoing events
> 3. The first event to occur activates its path — all other paths are cancelled
> 4. The process continues along the winning path

> [!example] Real-World Example
> After sending a quotation to a customer:
> - Event A: "Customer Confirms" message received → path "Process Order"
> - Event B: Timer fires after 3 days → path "Send Reminder"
> - Event C: "Customer Rejects" message received → path "Close Lead"
>
> The process waits until one of these events occurs — the first one determines the next step.

---

## 4. Parallel Gateway (AND)

A ==Parallel Gateway== **creates or synchronizes concurrent execution**. It is used in pairs — a splitting gateway initiates multiple simultaneous flows, and a joining gateway waits for all of them to complete before the process continues.

### Key Characteristics

> [!info] Defining Traits
> - Symbol: **diamond with a `+` (plus sign)**
> - **No conditions are evaluated** — all outgoing paths are always activated simultaneously
> - The joining Parallel Gateway **waits for all incoming flows** to complete before proceeding (full synchronization)
> - Always used in pairs in practice: one split + one join

### Splitting vs. Merging

| Mode | Behavior |
|---|---|
| **Split (diverging)** | Activates **all** outgoing paths simultaneously — no conditions |
| **Merge (converging)** | Waits for **all** incoming paths to complete — then continues |

> [!example] Real-World Example
> Processing a loan application:
> - Parallel Gateway splits into:
>   - Path A: "Verify Employment References"
>   - Path B: "Check Credit Score"
> - Both tasks run simultaneously
> - Joining Parallel Gateway waits until **both** are complete → then proceeds to "Make Lending Decision"
>
> This reduces total time since both checks run in parallel instead of sequentially.

> [!tip] Performance Benefit
> Parallel gateways are a key tool for **process optimization** — identifying tasks that have no dependency on each other and running them concurrently rather than sequentially.

---

## 5. Gateway Comparison at a Glance

| Gateway | Symbol | Paths Taken | Condition Evaluation | Merge Behavior |
|---|---|---|---|---|
| **Exclusive (XOR)** | `X` or empty diamond | Exactly one | First true condition wins | First token passes through |
| **Inclusive (OR)** | `O` circle | One or more | All conditions evaluated | Waits for all active paths |
| **Event-Based** | Double circle + pentagon | Exactly one | First event to occur wins | No merge (single path continues) |
| **Parallel (AND)** | `+` plus sign | All of them | No conditions — always all | Waits for all paths |

---

## 6. When to Use Each Gateway

> [!example] Decision Hints
> - Use **Exclusive (XOR)** when only one outcome is possible — conditions are mutually exclusive (e.g., approve or reject, high or low priority)
> - Use **Inclusive (OR)** when multiple outcomes are possible simultaneously — conditions are independent (e.g., different shipping methods based on weight AND delivery time)
> - Use **Event-Based** when the next step depends on which external event arrives first — not on data conditions (e.g., waiting for customer confirmation vs. timeout)
> - Use **Parallel (AND)** when multiple tasks must happen concurrently with no dependency between them (e.g., parallel background checks, simultaneous notifications)

---

## 7. VIP Customer Discount Example

> [!example] Gateway in Context
> A store applies discounts to VIP customers only:
>
> ```
> Start → Check Customer Status → [Exclusive Gateway]
>    ├── Condition: "VIP customer" → Apply 20% Discount → Continue to Checkout
>    └── Default: → Continue to Checkout (no discount)
> ```
>
> The gateway is where the condition is checked, and only one path is followed per customer instance. Non-VIP customers skip the discount step entirely.

---

## Summary

==BPMN Gateways== are diamond-shaped decision points that control branching and synchronization in a process. The **Exclusive (XOR)** gateway takes exactly one path based on conditions. The **Inclusive (OR)** gateway takes one or more paths — all true conditions are evaluated. The **Event-Based** gateway pauses the process and waits for the first external event to fire. The **Parallel (AND)** gateway activates all outgoing paths simultaneously with no condition evaluation and synchronizes them at the joining gateway. Choosing the right gateway type is critical for accurately modeling business logic — the wrong gateway can fundamentally misrepresent how a process behaves.

---

## Related Notes

- [[Semi-Formal Notations - BPMN Flow Objects and Flows]]
- [[Semi-Formal Notations - BPMN Events and Symbols]]
- [[Semi-Formal Notations - BPMN Activities Task Types]]
- [[Semi-Formal Notations - BPMN Activities Sub-Processes and More]]
- [[Semi-Formal Notations - BPMN Key Concepts]]
- [[Semi-Formal Notations - BPMN]]
- [[Semi-Formal Notations]]
