---
title: "Estimation: Wideband Delphi"
date: 2026-04-29
tags:
  - module7
  - estimation
  - canvas-note
cssclasses:
  - canvas-note
---

# Estimation: Wideband Delphi

> [!note] Overview
> ==Wideband Delphi== is a structured group estimation method developed by ==Barry Boehm in 1981==. Unlike the original Delphi method — where experts estimate separately and discuss to reach agreement — Wideband Delphi is more structured and designed to be both ==faster and more accurate==. It combines anonymous individual estimation with facilitated group discussion in iterative rounds until consensus is reached.

---

## Background: Delphi vs. Wideband Delphi

The original RAND Corporation Delphi method used written questionnaires and had no direct group interaction — rounds were slow and experts never met face to face. Boehm's "wideband" extension broadened the communication channel: experts ==interact directly== in group meetings, making the process faster without sacrificing the anonymity that protects against anchoring and social pressure.

| Aspect | Original Delphi | Wideband Delphi |
|---|---|---|
| Expert interaction | None — written only | Direct group meetings |
| Speed | Slow | Faster |
| Anonymity | Full | Partial — estimates anonymous, discussion open |
| Facilitator role | Passive | Active — can assign devil's advocate |
| Output | Range/consensus | Single-point + range |

---

## The 8-Step Procedure

### Step 1 — Identification of Estimators

> [!info] Identify Who Estimates
> The first stage involves ==identifying the estimators== who will participate in the process — typically a mix of developers, QA engineers, architects, and other relevant specialists.

Selecting the right group matters: diversity of expertise reduces blind spots. Too few participants narrows the range of perspectives; too many makes consensus harder to reach.

---

### Step 2 — Initial Estimation

> [!info] Prepare Individual Estimates
> Estimators are presented with the ==project specification== and an ==estimation form==, allowing them to prepare ==initial estimates individually==.

> [!tip] Optional Ordering
> This step can optionally occur after Step 3 (the group meeting). Some teams prefer a brief group discussion first to align on scope before independent estimation — this is a judgment call based on how well-defined the requirements are.

The estimation form typically captures: the task description, the estimator's best-case, most-likely, and worst-case values, and any assumptions or concerns the estimator wants to flag.

---

### Step 3 — Group Meeting

> [!info] Discuss Estimation Issues
> A ==group meeting== is convened to discuss estimation issues openly. If consensus isn't quickly reached, a person may be assigned to play the role of ==devil's advocate== to facilitate discussion.

The devil's advocate role is important: it creates a structured mechanism for challenging over-optimistic or overly conservative estimates without making the disagreement personal. The facilitator may assign this role to whoever holds the most divergent estimate.

---

### Step 4 — Anonymous Submission of Estimates

> [!info] Submit Estimates Anonymously
> Estimators provide their ==individual estimates anonymously== to the coordinator.

Anonymity at this stage is critical. It prevents:
- **Anchoring**: people adjusting their estimates toward whoever spoke last
- **Social pressure**: junior members deferring to senior ones
- **HiPPO effect**: the Highest Paid Person's Opinion dominating

Each estimator commits to a number based on their own analysis, not on what they think others expect.

---

### Step 5 — Summary Presentation

> [!info] Coordinator Presents Summary
> The coordinator ==compiles a summary== of the estimates on an ==iteration form== and presents it to the estimators for comparison.

The summary typically shows all individual estimates side by side — often as a chart or table — so the team can see the distribution at a glance. The key visual is showing all rounds on the ==same scale==, making it easy to see whether estimates are converging or diverging over time.

> [!tip] Visualizing Convergence
> Displaying rounds on the same axis lets the team see immediately whether they are getting closer to agreement. A wide spread after multiple rounds signals that a fundamental disagreement about scope or approach has not yet been resolved.

---

### Step 6 — Discussion of Variations

> [!info] Discuss Divergence
> Estimators ==convene to discuss variations== in their estimates, fostering mutual understanding and alignment.

This is the most valuable step. Divergence between estimates is not a problem to eliminate — it is ==information to extract==. The discussion should focus on:
- What assumptions differ between the high and low estimates?
- What has the high estimator seen that the low estimator hasn't?
- Is there a dependency, integration cost, or edge case driving the high end?

---

### Step 7 — Anonymous Voting

> [!info] Vote on Acceptance
> Estimators ==anonymously vote== on whether to accept the average estimate. If ==any estimator dissents==, the process returns to Step 3 (group meeting).

The dissent threshold is strict by design: a single "no" vote sends the group back to discussion. This prevents premature closure and ensures that minority concerns are genuinely addressed rather than outvoted.

> [!warning] Why Return to Step 3, Not Step 4?
> Returning to the group meeting (not just re-submitting estimates) is intentional. A dissenting vote signals that the discussion has not yet resolved the underlying disagreement. More estimation rounds without more discussion will not fix the problem — the conversation must continue.

---

### Step 8 — Final Estimate

> [!info] Produce the Final Estimate
> The final estimate is determined based on the ==consensus achieved== through the Wideband Delphi exercise. It includes:
> - A ==single-point estimate== derived from the discussion
> - A ==range== reflecting the variability of opinions

The range preserves the information captured during the process — it documents the remaining uncertainty even after consensus is reached. Stakeholders can use the range to understand confidence and risk.

---

## The Full Process at a Glance

```
1. Identify estimators
        ↓
2. Present spec + estimation form (individual preparation)
        ↓
3. Group meeting (discuss scope, assign devil's advocate if needed)
        ↓
4. Anonymous estimate submission to coordinator
        ↓
5. Coordinator presents summary (iteration form, all rounds on same scale)
        ↓
6. Group discusses variations
        ↓
7. Anonymous vote — accept average?
   ├── YES (all agree) → Step 8
   └── NO (any dissent) → back to Step 3
        ↓
8. Final estimate: single point + range
```

> [!tip] Steps 3–7 Can Be Remote
> Steps 3 to 7 can be conducted ==face-to-face or online== (email, chat, video call, collaborative tools). The anonymity of submissions must be preserved regardless of medium — the coordinator collects and aggregates before sharing results.

---

## The Estimation Form

The Wideband Delphi estimation form captures structured data from each estimator across rounds:

| Field | Purpose |
|---|---|
| Task / feature description | Ensures all estimators are estimating the same scope |
| Best-case estimate | Lower bound — ideal conditions |
| Most-likely estimate | Expected outcome under normal conditions |
| Worst-case estimate | Upper bound — significant problems occur |
| Assumptions | Explicit conditions the estimate depends on |
| Concerns / flags | Dependencies, unknowns, or risks the estimator wants to surface |

Collecting estimates in this format makes the ==iteration form== meaningful: the coordinator can show not just the point estimates but also the spread between best/worst cases for each estimator.

---

## Strengths and Limitations

| Strengths | Limitations |
|---|---|
| Anonymous estimates prevent anchoring and social pressure | Requires a skilled facilitator / coordinator |
| Iterative rounds drive genuine convergence | Time-consuming for large backlogs |
| Devil's advocate role structures healthy challenge | Requires all participants to be available simultaneously |
| Single-point + range output documents residual uncertainty | Can stall if one estimator persistently dissents |
| Works remotely with async tools | Less effective if participants don't share domain knowledge |

---

## Summary

Wideband Delphi is a structured, iterative group estimation process that uses ==anonymous individual estimates==, ==facilitated group discussion==, and ==anonymous voting== to reach a consensus estimate. Developed by Barry Boehm in 1981, it improves on the original Delphi method by adding direct group interaction while preserving the anonymity that prevents anchoring and social pressure. The process outputs both a ==single-point estimate== and a ==range==, capturing the team's collective judgment alongside the uncertainty that remains. It is most effective when requirements are moderately defined, when estimators bring diverse expertise, and when the team has a skilled coordinator to manage the rounds.

## Related Notes
- [[Estimation - Expert Judgment in Groups]]
- [[Estimation - Main Sources of Uncertainty]]
- [[Estimation - Probability Statement]]
- [[Estimation - Decomposition Best Practices]]
- [[Estimation - Story Points Factors]]
