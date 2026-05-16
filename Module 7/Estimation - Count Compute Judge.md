---
title: "Estimation: Count, Compute, Judge"
date: 2026-04-29
tags:
  - module7
  - estimation
  - canvas-note
cssclasses:
  - canvas-note
---

# Estimation: Count, Compute, Judge

> [!note] Overview
> "Count, Compute, Judge" is one of the most widely used approaches to software estimation, described by Steve McConnell in *Software Estimation: Demystifying the Black Art*. The order matters: ==counting is most accurate, computation is second, judgment is last resort==. Moving through these methods in sequence — not skipping to judgment first — is what makes this approach effective.

---

## 1. The Core Rule

> [!info] The Estimation Priority Rule
> **"Count if possible. Compute when you can't count. Seek judgment as a last resort."**

Each method builds on the previous one:
- ==Count==: direct measurement of something observable
- ==Compute==: calculation using known data and relationships
- ==Judge==: expert opinion when counting and computing are not possible

The key insight is that judgment feels fast and confident but is the ==least reliable== method. Counting feels slower but produces the most accurate results.

---

## 2. The Conference Room Analogy

To illustrate the three methods, imagine estimating how many people are attending an event in a conference hall — a task four estimators approach differently.

### Estimator A — Judgment

> [!example] Estimator A: Judgment
> Uses personal expertise in crowd monitoring to quickly suggest **340 people**.
> No data, no calculation — pure expert intuition.

---

### Estimator B — Computation

> [!example] Estimator B: Computation
> Multiplies the number of tables × rows × average table occupancy to arrive at **385 people**.
> Uses a logical formula applied to observable data.

---

### Estimator C — Computation with Assumption

> [!example] Estimator C: Computation + Assumption
> Takes the hall's stated capacity (500) and infers an **85% occupancy rate**, yielding **425 people**.
> Combines known data with a reasonable assumption — a form of computation, but with additional uncertainty from the assumption.

---

### Estimator D — Counting

> [!example] Estimator D: Counting
> Counts actual card swipes at the entrance, recording **407 attendees** with no departures confirmed.
> Direct measurement of a real observable event — the most accurate approach.

---

## 3. Why the Order Matters

| Estimator | Method | Estimate | Accuracy |
|---|---|---|---|
| D | ==Count== (card swipes) | 407 | Highest |
| B | Compute (tables × rows × occupancy) | 385 | High |
| C | Compute + assumption (capacity × 85%) | 425 | High |
| A | Judge (expert intuition) | 340 | Lowest |

> [!warning] Judgment Is the Weakest Method
> Estimator A is the least accurate — not because they lack expertise, but because ==personal judgment without supporting data is systematically less reliable== than methods grounded in observable facts. Expertise matters most when used to interpret data, not replace it.

---

## 4. Applying Count, Compute, Judge to Software

In software estimation, the three methods map to concrete practices:

### Count

Look for something you can directly measure:
- Lines of code in similar completed features
- Number of user stories, screens, API endpoints, or database tables
- Historical delivery rates (stories per sprint, features per quarter)
- Function points or feature counts from comparable projects

> [!tip] Count First, Always
> Before estimating from scratch, ask: "Do we have data we can count?" Historical data from past projects is the most reliable foundation for any estimate.

---

### Compute

When direct counting is not available, apply known relationships:
- Multiply story count × average story duration from past sprints
- Use a parametric model (e.g., COCOMO) that converts size metrics to effort
- Scale from a known reference project: "This project is 2× the size of Project X, which took 6 months"
- Apply velocity: team delivers 30 points/sprint × estimated backlog size

> [!example] Computation Example
> "We have 80 story points in the backlog. Our average velocity is 20 points per sprint. That gives us 4 sprints, roughly 8 weeks."

---

### Judge

When neither counting nor computing is feasible, use expert judgment — but apply it carefully:
- Use ==structured techniques== like Planning Poker or Wideband Delphi to aggregate multiple expert opinions
- Combine judgment with at least one anchor from a count or computation
- ==Never rely on a single person's judgment alone== — aggregate opinions reduce individual bias

> [!warning] Judgment Pitfalls
> - Anchoring: the first number said in the room becomes the reference
> - Optimism bias: developers consistently underestimate by 20–30%
> - Social pressure: junior members defer to senior opinions
> - Overconfidence: experts often underestimate their own uncertainty

---

## 5. Combining Methods

The most robust estimates combine all three approaches:

> [!tip] Best Practice
> Use counting to anchor, computation to project, and judgment to sanity-check. If all three converge, confidence is high. If they diverge significantly, investigate the gap before committing.

> [!example] Combined Approach
> 1. **Count**: the backlog has 60 stories
> 2. **Compute**: at 15 stories/sprint, that is 4 sprints = ~8 weeks
> 3. **Judge**: the team SME says "feels about right, maybe 9–10 weeks given the payment integration complexity"
> → Final estimate: **8–10 weeks** (range accounts for the expert's concern)

---

## Summary

The "Count, Compute, Judge" framework enforces a disciplined ==priority order== for estimation methods, counteracting the natural human tendency to jump straight to intuition. Counting real, observable data is always most accurate. Computation applies known relationships when direct counting is unavailable. Judgment is a last resort — valuable as a sanity check or when data is absent, but always weakest when used alone. The most reliable estimates use ==all three in combination==, with judgment interpreting and validating what counting and computation reveal.

## Related Notes
- [[Estimation - Definitions]]
- [[Estimation - Main Sources of Uncertainty]]
- [[Estimation - Why Accurate Estimates Matter]]
- [[Estimation - Precision and Accuracy]]
