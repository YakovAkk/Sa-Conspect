---
title: "Estimation: Determining What to Count"
date: 2026-04-29
tags:
  - module7
  - estimation
  - canvas-note
cssclasses:
  - canvas-note
---

# Estimation: Determining What to Count

> [!note] Overview
> Choosing ==what to count== is a critical decision in project estimation. The right countable items differ by project stage — early on you count high-level artifacts, later you count detailed technical items. Identifying and measuring the right elements helps teams make better decisions, reduce risk, and keep the project on track.

---

## 1. What to Count by Project Stage

The available countable items evolve as the project progresses and more detail becomes known.

### Early in the Project

> [!info] Early-Stage Countables
> When the project is just beginning and requirements are still high-level, you can count:
> - ==Marketing requirements==
> - ==Features==
> - ==Use cases==
> - ==User stories==
> - Other high-level scope artifacts

These items are coarse-grained but give a useful first approximation of project size when no detailed design exists yet.

---

### In the Middle of the Project

> [!info] Mid-Stage Countables
> As design and architecture mature, counting becomes more refined:
> - ==Engineering requirements==
> - ==Function points==
> - ==Change requests==
> - ==Web pages==
> - ==Reports==
> - ==Dialog boxes / screens==
> - ==Database tables==

These items are more granular and correlate more tightly with implementation effort.

---

### Late in the Project

> [!info] Late-Stage Countables
> Near the end of the project, the most detailed items become countable:
> - ==Existing lines of code==
> - ==Reported defects==
> - ==Classes==
> - ==Tasks==
> - Refined counts of items from earlier stages

At this stage, counting can validate earlier estimates and support effort forecasting for remaining work.

---

## 2. How Countable Items Evolve

| Project Stage | Granularity | Example Countables |
|---|---|---|
| Early | Coarse | Features, use cases, stories, marketing requirements |
| Middle | Medium | Engineering requirements, screens, tables, function points |
| Late | Fine | Classes, defects, lines of code, tasks |

> [!tip] Count What Is Available
> Don't wait for perfect data. Count the most granular items available at each stage. Rough counts early in the project are more valuable than no count at all — they reduce reliance on pure judgment.

---

## 3. Five Criteria for Choosing What to Count

Not everything countable is worth counting. Apply these five criteria to select the most useful items:

> [!info] Criterion 1: Related to Software Size
> Choose something that ==correlates with the size of the software== you are estimating. Feature counts, use cases, and function points all reflect scope in a way that, say, number of meetings does not.

---

> [!info] Criterion 2: Available Early
> Choose something you can count ==early in development==, before all the details are known. Early countables (features, use cases) allow estimation to begin before full design is complete.

---

> [!info] Criterion 3: Yields a Useful Average
> Choose an element that provides a ==useful average based on historical data==. If your team has completed 10 similar projects, you can calculate average effort per feature, per use case, or per screen — and use that as your multiplier.

---

> [!info] Criterion 4: Clearly Defined
> Make sure ==everyone understands exactly what is being counted==. "A feature" means different things to different people. Define your unit precisely: "a feature is a discrete piece of user-visible functionality described in a single use case."

---

> [!info] Criterion 5: Easy to Count
> Choose something that can be ==counted with little effort==. If the counting process itself takes significant time, the benefit may not justify the cost. Prefer items that are already tracked in your backlog, design docs, or project management tools.

---

## 4. Applying the Criteria: Selection Matrix

| Candidate | Size-Related? | Available Early? | Useful Average? | Clearly Defined? | Easy to Count? |
|---|---|---|---|---|---|
| User stories | ✓ | ✓ | ✓ | ✓ (if consistent) | ✓ |
| Function points | ✓ | Partial | ✓ | ✓ | Moderate |
| Database tables | ✓ | Partial | ✓ | ✓ | ✓ |
| Lines of code | ✓ | ✗ | ✓ | ✓ | ✓ (late only) |
| Number of meetings | ✗ | ✓ | ✗ | ✓ | ✓ |

> [!example] Best Early-Stage Pick
> ==User stories== score high on all five criteria — they are scope-related, available from day one, trackable for averages, definable, and already in the backlog.

> [!example] Best Late-Stage Pick
> ==Defects and lines of code== only become countable late, but they provide the highest-fidelity data for remaining-work estimates.

---

## Summary

Determining what to count is not a one-time decision — it evolves across the project lifecycle. Early on, high-level items like features and use cases provide the best available anchors. Mid-project, engineering artifacts and UI elements give finer resolution. Late in the project, code-level items offer the most precise counts. In every case, the five criteria — ==size-related, early availability, useful average, clearly defined, easy to count== — provide a structured way to choose the right items and avoid counting things that don't actually improve estimate quality.

## Related Notes
- [[Estimation - Count Compute Judge]]
- [[Estimation - Main Sources of Uncertainty]]
- [[Estimation - Definitions]]
