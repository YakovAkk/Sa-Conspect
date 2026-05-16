---
title: "Estimation: Man-Time"
date: 2026-04-29
tags:
  - module7
  - estimation
  - canvas-note
cssclasses:
  - canvas-note
---

# Estimation: Man-Time

> [!note] Overview
> ==Man-time== (also called staff time or person-time) is the standard unit for measuring effort in software estimation. It counts ==pure labor only== — not breaks, meetings, or interruptions. Understanding what man-time actually measures — and what it misses — is essential for producing realistic effort estimates.

---

## 1. What Is Man-Time?

> [!info] Definition (Wikipedia)
> "A **man-hour** is the amount of work performed by the average worker in one hour. Man-hours do not take account of the breaks that people generally require from work, e.g. for rest, eating, and other bodily functions. They only count pure labor."

==Man-time== is expressed in various granularities depending on the scale of the work:

| Unit | Typical Use |
|---|---|
| Man-hours | Small tasks, bug fixes |
| Man-days | Feature work, sprints |
| Man-months | Project phases |
| Man-years | Large multi-team programs |

---

## 2. How Man-Time Works in Practice

When a task is estimated at, say, **4 staff days**, this is a measure of ==total effort== — not elapsed calendar time. The same effort can be spread across different team configurations:

> [!example] Flexible Staffing
> "4 staff days" could mean:
> - 1 person × 4 days
> - 2 people × 2 days
> - 4 people × 1 day

This flexibility is the key advantage of man-time: it ==separates effort from schedule==, allowing the team to reason about resourcing and duration independently.

---

## 3. Alternative: T-Shirt Sizing

Alongside man-time, ==T-shirt sizing== (S, M, L, XL) is a common lightweight method for quickly communicating task scale without committing to specific numbers.

> [!info] T-Shirt Sizing
> T-shirt sizes give a ==relative, fast indication of task size== and are especially useful in early planning, backlog grooming, or when precise data is not yet available. The mapping to actual hours or days is defined by the team.

---

## 4. The Key Limitation of Man-Time

Man-time measures ==pure, uninterrupted labor== — but real working days are never purely labor. Team members regularly spend time on:

> [!warning] Activities That Reduce Available Labor Time
> - Meetings (standups, planning, retrospectives, stakeholder calls)
> - Interviews and hiring activities
> - Customer support and issue triage
> - Code reviews, documentation, and knowledge sharing
> - Administrative tasks and context-switching

These activities ==reduce the uninterrupted time available== for the estimated task and can significantly affect how long a task actually takes in calendar time.

---

## 5. Man-Time vs. Calendar Time

> [!warning] A Common Estimation Mistake
> Treating man-time as calendar time is one of the most frequent causes of schedule overruns.

| Concept | What It Measures | Example |
|---|---|---|
| ==Man-time (effort)== | Pure labor hours/days | 4 man-days of coding |
| ==Calendar time (duration)== | Elapsed real-world time | 6 actual days to complete |
| Gap | Overhead and interruptions | Meetings, support, context-switching |

To convert man-time to calendar time, teams need to account for ==utilization rate== — the fraction of a working day actually available for focused task work. A typical developer may have only 60–70% of their day available for deep work.

> [!example] Conversion Example
> Task: 4 man-days of effort
> Developer utilization: 65% (rest is meetings, support, etc.)
> Calendar time needed: 4 ÷ 0.65 ≈ **6.2 calendar days**

---

## Summary

Man-time is the standard unit of effort in estimation, measuring ==pure labor== independent of team size or schedule. Its flexibility — one effort estimate can map to many staffing configurations — makes it powerful for planning. However, man-time deliberately ignores overhead: meetings, interruptions, and non-task activities all reduce the real-world throughput. Realistic estimation must account for ==utilization rate== when converting effort to calendar duration. T-shirt sizing offers a complementary, faster approach for relative sizing when precise numbers are premature.

## Related Notes
- [[Estimation - Definitions]]
- [[Estimation - Purpose]]
- [[Estimation - Precision and Accuracy]]
