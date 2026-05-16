---
title: "Estimation: Expert Judgment in Groups"
date: 2026-04-29
tags:
  - module7
  - estimation
  - canvas-note
cssclasses:
  - canvas-note
---

# Estimation: Expert Judgment in Groups

> [!note] Overview
> ==Group expert judgment techniques== — also called "group reviews" — improve estimation accuracy when there are many unknowns or when the project is still early and individual estimates carry high uncertainty. A straightforward way to improve individual estimates is to combine them through structured group review. The process follows ==three core rules== that distinguish it from simply averaging numbers.

---

## Why Group Reviews Work

Individual estimates are shaped by each person's experience, assumptions, and blind spots. A developer may underestimate QA effort; a QA engineer may miss technical complexity. Group reviews surface these gaps before they become schedule problems.

> [!tip] When to Use Group Reviews
> - ==Early in a project== when requirements are vague and individual estimates diverge widely
> - When the domain is ==unfamiliar== to most team members
> - When ==many unknowns== exist that different specialists can help surface
> - When individual estimates have already been made and need validation

Group reviews do not replace individual estimation — they build on it. The individual estimate is the starting point; the group review is the calibration step.

---

## Rule 1: Estimate Individually and Then Compare

> [!info] Estimate Individually First
> Team members estimate each project component ==independently==, without seeing each other's numbers. These individual estimates are then revealed and compared.

**Why independence matters**: if estimates are shared before individuals commit to their own number, anchoring bias kicks in — everyone clusters around the first number they see, regardless of its accuracy. Independent estimates capture genuine variation in perspective.

**What happens after comparison**:
- Disparities are ==thoroughly discussed== to identify their underlying causes
- The team explores the high and low ends of the estimation ranges
- A consensus is ==gradually reached through collaborative discussion==, not by fiat

> [!example] Divergent Estimates as Signal
> Developer A estimates 3 days for a feature. Developer B estimates 8 days. Rather than averaging to 5.5, the team asks: "What is Developer B seeing that Developer A is not?" The answer reveals a hidden dependency — and the real estimate ends up at 7 days. Without the comparison, the project would have been planned around 3.

---

## Rule 2: Avoid Only Averaging Estimates

> [!warning] Do Not Simply Average
> Rather than averaging all estimates and accepting the result, it is ==imperative to delve deeper into the differences== among individual estimations.

Averaging obscures information. If one person estimates 2 days and another estimates 10 days, the average of 6 days may be the one value that is least likely to be correct. The outliers carry information — they represent someone's understanding of the problem that the rest of the group hasn't yet considered.

**What to do instead**:
- ==Engage in constructive dialogue== to understand variations in estimates
- Ask: "What does the high estimate know that the low estimate doesn't?"
- Ask: "What assumptions would have to be true for the low estimate to be right?"
- Treat extreme estimates as hypotheses worth examining, not noise to be filtered

> [!tip] The Gap Is the Signal
> Large gaps between estimates almost always indicate a ==missing shared understanding==: an undiscussed dependency, an assumption that varies across team members, or a requirement that some people have interpreted differently. Closing the gap through dialogue is more valuable than the estimate itself.

---

## Rule 3: Arrive at a Consensus Estimate

> [!info] Achieve Consensus
> The goal is a ==consensus estimate that all team members endorse==. This is not a majority vote — it requires open discussion until genuine alignment is reached.

Consensus means that every participant can say: "I may not think this is the perfect estimate, but I understand why we arrived here and I can commit to working within it."

**How to build consensus**:
- Ensure all concerns have been voiced and heard
- Reconcile differences through ==open discussion==, not pressure
- Make all assumptions explicit so disagreements can be traced to their source
- Obtain ==buy-in from all stakeholders== in the room

> [!warning] Consensus ≠ Unanimity
> Consensus does not require everyone to agree the estimate is perfect. It requires that everyone understands the reasoning behind it and is willing to commit. A team member who says "I think it's wrong but I'll go along with the group" is not consensus — their concern must be addressed or documented.

> [!example] Documented Disagreement
> If one team member consistently believes a task will take longer, and the group proceeds with a lower estimate, that person's concern should be ==logged as a risk== with a probability and cost. This preserves the dissenting perspective without blocking the team.

---

## Benefits of Group Expert Judgment

| Benefit | Mechanism |
|---|---|
| ==Higher accuracy== | Multiple perspectives catch blind spots that individuals miss |
| ==Better reliability== | Consensus estimates are more defensible than individual guesses |
| ==Improved decision-making== | Discussed estimates surface assumptions that affect planning |
| ==Better project planning== | Hidden complexity, dependencies, and risks are identified earlier |
| ==Team alignment== | Everyone understands the scope the same way after the review |

---

## Group Review vs. Individual Estimation

| Aspect | Individual Estimation | Group Review |
|---|---|---|
| Speed | Fast | Slower (requires coordination) |
| Accuracy | Varies with experience | Higher — offsets individual blind spots |
| Bias | Anchoring, optimism, familiarity | Reduced through independent first estimates |
| Risk identification | Limited to one person's knowledge | Broader — specialist knowledge surfaces earlier |
| Buy-in | Low — only the estimator owns it | High — the group endorsed the number |

> [!tip] Combine Both
> The best process uses ==individual estimation first== (to avoid anchoring) and ==group review second== (to improve accuracy). Neither alone is as effective as both together.

---

## Common Group Review Techniques

> [!info] Planning Poker
> Each team member selects a card representing their estimate (often Fibonacci-scaled). Cards are revealed simultaneously. Large gaps trigger discussion. Rounds continue until consensus is reached.
>
> Advantages: anonymous first reveal, structured discussion, fast iteration.

> [!info] Wideband Delphi
> A more formal version: estimates are collected anonymously, distributed as a summary, discussed, and re-estimated in multiple rounds until convergence. Best for large unknowns and high-stakes estimates.

> [!info] Affinity Estimation
> Team members silently sort stories into size buckets (XS, S, M, L, XL). Disagreements on placement trigger discussion. Faster than card-based methods for large backlogs.

---

## Summary

Group expert judgment improves estimation by combining independent individual estimates with structured collaborative review. The three rules — estimate independently, then compare; avoid averaging; arrive at true consensus — ensure that the group's collective knowledge actually improves accuracy rather than just creating false confidence in a number. Properly run group reviews surface ==hidden complexity==, ==reduce individual bias==, and produce estimates the entire team can commit to. They are most valuable ==early in a project== and whenever individual estimates diverge significantly.

## Related Notes
- [[Estimation - Main Sources of Uncertainty]]
- [[Estimation - Count Compute Judge]]
- [[Estimation - Story Points Factors]]
- [[Estimation - Decomposition Best Practices]]
- [[Estimation - Probability Statement]]
