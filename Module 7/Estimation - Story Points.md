---
title: "Estimation: Story Points"
date: 2026-04-29
tags:
  - module7
  - estimation
  - agile
  - canvas-note
cssclasses:
  - canvas-note
---

# Estimation: Story Points

> [!note] Overview
> A ==story point== is an abstract metric used in Agile project management to estimate the relative effort required to complete a user story. Unlike time-based estimates, story points encode ==complexity, risk, and repetition== into a single number — decoupling effort from hours and enabling more flexible, adaptive sprint planning.

---

## 1. What Is a Story Point?

A story point is an ==abstract, relative unit of measure== assigned to items in the product backlog. It does not represent a fixed amount of time — instead, it communicates *how much effort* a story requires compared to other stories the team has estimated.

> [!info] Key Properties
> - **Abstract**: a "5" has no inherent time value — it only means "roughly twice as hard as a 2.5"
> - **Relative**: story points are calibrated against each other within the same team
> - **Holistic**: a single number captures complexity, risk, and familiarity together
> - **Team-specific**: one team's "5" is not comparable to another team's "5"

---

## 2. The Three Components of Story Points

Story points reflect three distinct dimensions of effort:

### 2.1 Complexity

> [!info] Complexity
> The ==difficulty level== involved in developing a feature. This evaluates the technical intricacy of the task and the engineering challenges it presents.

- How many systems or components are involved?
- Are there algorithmic challenges or architectural decisions?
- Does the solution require research or experimentation?

---

### 2.2 Risk

> [!info] Risk
> Factors such as ==ambiguous requirements, third-party dependencies, or potential mid-process changes== that may impact complexity and timeline.

- Are requirements well-defined, or still unclear?
- Does this story depend on an external team, API, or vendor?
- How likely is scope or design to change during development?

---

### 2.3 Repetition

> [!info] Repetition
> The team's ==familiarity with the feature== and the level of monotony associated with its development tasks.

- Has the team done something similar before?
- Is this a well-understood, routine pattern — or novel territory?
- Familiar, repetitive work earns fewer story points than novel, exploratory work of the same calendar duration.

---

## 3. Story Points vs. Time-Based Estimates

> [!tip] Why Not Just Use Hours?
> Time-based estimates anchor conversations to the clock, which creates pressure, gaming, and inaccuracy. Story points shift the focus to ==relative effort and difficulty==, which is something developers can judge more reliably.

| Aspect | Time-Based (Hours) | Story Points |
|---|---|---|
| Unit | Hours or days | Abstract number (1, 2, 3, 5, 8…) |
| Measures | Duration | Effort, complexity, risk |
| Team dependency | No — hours are universal | Yes — team-specific calibration |
| Sprint planning | Can create false precision | Better — focuses on capacity, not clock |
| Handles uncertainty? | Poorly | Yes — abstraction absorbs unknowns |
| Comparable across teams? | Yes | No |

---

## 4. Benefits of Story Points

> [!info] What Story Points Enable
> - ==More accurate sprint planning== by focusing on effort rather than hours
> - ==Reduced uncertainty== — the abstraction accommodates unknowns without false precision
> - ==Flexibility== in planning: teams can adjust without renegotiating every time estimate
> - ==Adaptability==: helps teams respond to change during the project
> - Fewer anchoring effects from unrealistic manager-imposed time targets

> [!example] Sprint Planning with Story Points
> A team has a velocity of **30 story points per sprint**.
> They select backlog items totalling 28–32 points.
> They don't need to know if a "5-point story" takes 3 hours or 8 hours — they just know their team can handle a certain volume of points per sprint.

---

## 5. Common Sizing Scales

Story points are typically assigned using non-linear scales to reflect the growing uncertainty of larger estimates:

| Scale | Values | Why Non-Linear? |
|---|---|---|
| Fibonacci | 1, 2, 3, 5, 8, 13, 21 | Larger stories carry disproportionately more uncertainty |
| Modified Fibonacci | 1, 2, 3, 5, 8, 13, 20, 40, 100 | Adds large-story markers |
| Powers of 2 | 1, 2, 4, 8, 16, 32 | Simple, fast calibration |
| T-shirt sizes | XS, S, M, L, XL | Good for very early, rough sizing |

---

## Summary

Story points are an ==abstract relative measure== of effort that encode complexity, risk, and repetition into a single value. They deliberately avoid mapping to specific hours, making them more robust under uncertainty and better suited to iterative Agile planning. By calibrating story points around a team's velocity — how many points they consistently complete per sprint — teams can plan work, manage capacity, and adapt to change without being tied to unrealistic time commitments.

## Related Notes
- [[Estimation - Man-Time]]
- [[Estimation - Ideal Man-Time]]
- [[Estimation - Definitions]]
- [[Estimation - Precision and Accuracy]]
