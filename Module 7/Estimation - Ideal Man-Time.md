---
title: "Estimation: Ideal Man-Time"
date: 2026-04-29
tags:
  - module7
  - estimation
  - canvas-note
cssclasses:
  - canvas-note
---

# Estimation: Ideal Man-Time

> [!note] Overview
> ==Ideal time== is the estimated duration a task would take under perfect, uninterrupted conditions — no meetings, no context-switching, everything needed is at hand. It is a useful abstraction for estimating task effort, but it must be converted to ==actual elapsed time== using a ==load factor== that accounts for real-world overhead.

---

## 1. What Is Ideal Time?

> [!info] Mike Cohn's Definition
> "When estimating in ideal days, you assume that the story being estimated is the only thing you'll work on, everything you need will be on hand when you start, and there will be no interruptions."

The practical question to ask is:

> *"If I'm doing nothing else, how long would this take me?"*

The answer reflects the ==concentrated effort required== under optimal conditions. It is a clean measure of task complexity, free from organizational noise.

---

## 2. Ideal Time vs. Man-Time

Ideal time and man-time are ==related but distinct== concepts:

| Concept | What It Assumes | What It Ignores |
|---|---|---|
| ==Man-time== | Pure labor, no breaks | Interruptions, overhead |
| ==Ideal time== | Single focus, no distractions, everything on hand | Meetings, waiting, context-switching, coordination |

Ideal time is a ==subset of man-time thinking== — it goes further by also excluding waiting for dependencies and context-switching costs. Because of this difference, a direct 1:1 conversion to actual schedule time is ==not valid== without applying a load factor.

---

## 3. The Load Factor

The ==load factor== is a conversion coefficient that maps ideal time to actual elapsed time. It captures the efficiency of real work relative to the ideal scenario.

> [!info] Load Factor Formula
> **Load Factor = Ideal Hours Achieved ÷ Total Hours in Period**
>
> Example: If a developer achieves **6 ideal hours** of focused work in an **8-hour workday**:
> Load Factor = 6 ÷ 8 = **0.75**

### What Influences the Load Factor

The load factor is not universal — it depends on the team and organization:

> [!warning] Factors That Lower the Load Factor
> - Organizational culture (meeting-heavy vs. deep-work-friendly)
> - Team structure and communication overhead
> - Process maturity (unclear requirements increase churn)
> - Level of experience (junior developers need more support time)
> - External interruptions (support duties, stakeholder requests)

---

## 4. Determining the Load Factor Empirically

The most reliable approach is to derive the load factor from ==real historical data== using **XpVelocity** analysis.

### Method: Velocity-Based Load Factor

1. Select a recent completed iteration (sprint or week)
2. Sum the ==ideal time== of all completed stories/tasks
3. Record the ==elapsed calendar time== for that period
4. Calculate: **Load Factor = Total Ideal Time ÷ Elapsed Time**

> [!example] Velocity-Based Example
> - Ideal time for all completed stories in a week: **23 hours**
> - Elapsed time (workweek): **40 hours**
> - Load Factor = 23 ÷ 40 = **0.575 ≈ 0.6**
>
> This means the team works at roughly **60% of ideal efficiency** during a typical week.

---

## 5. Applying the Load Factor

Once the load factor is known, converting ideal time to elapsed (actual) time is straightforward:

> [!info] Conversion Formula
> **Elapsed Time = Ideal Time ÷ Load Factor**

> [!example] Applying the Load Factor
> Task estimated at **5 ideal days**
> Team load factor: **0.6**
> Elapsed time = 5 ÷ 0.6 = **~8.3 calendar days**

This conversion gives a realistic schedule estimate that accounts for real-world working conditions.

---

## 6. Step-by-Step Process Summary

| Step | Action | Output |
|---|---|---|
| 1. Ideal Time Assessment | Estimate how long the task takes with zero interruptions | Ideal hours/days |
| 2. Determine Load Factor | Use empirical velocity data or known utilization rate | A number between 0 and 1 |
| 3. Convert to Elapsed Time | Ideal Time ÷ Load Factor | Actual calendar time needed |
| 4. Apply to Planning | Use elapsed time for scheduling and commitment | Realistic project timeline |

---

## Summary

The ==ideal time== concept separates task complexity from organizational overhead — it answers "how hard is this?" without conflating it with "how long will this take in our environment?" The ==load factor== bridges the two, translating ideal effort into realistic schedule using empirical data. Together they improve estimation accuracy and help teams make better decisions about project timelines. The key discipline is deriving the load factor from actual velocity data, not guessing it.

## Related Notes
- [[Estimation - Man-Time]]
- [[Estimation - Definitions]]
- [[Estimation - Main Sources of Uncertainty]]
- [[Estimation - Precision and Accuracy]]
