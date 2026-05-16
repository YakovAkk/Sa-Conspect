---
title: "Estimation: Analogy"
date: 2026-04-29
tags:
  - module7
  - estimation
  - canvas-note
cssclasses:
  - canvas-note
---

# Estimation: Analogy

> [!note] Overview
> ==Estimation by analogy== means creating accurate estimates for a new project by comparing it to a ==similar project done in the past==. The critical rule: use the ==actual results== from the past project as the basis for comparison — not the original estimates. Original estimates carry the same biases and errors being corrected; only actuals reflect what really happened.

---

## The Core Idea

Every project leaves behind data: how long it actually took, how many people worked on it, what it actually cost. Estimation by analogy treats that data as a reference point for future work. The underlying assumption is that ==similar projects have similar effort profiles==, and that the differences between the old and new project can be identified and adjusted for.

> [!tip] Actuals, Not Estimates
> The most common mistake in analogy-based estimation is using the original estimate from the comparison project as the baseline. This embeds all the errors of the original estimate into the new one. ==Always use recorded actuals==: actual hours, actual cost, actual duration, actual defect counts.

---

## The Four Steps

### Step 1 — Get Detailed Actuals from a Similar Past Project

> [!info] Gather Historical Data
> Collect ==detailed results== on the size, effort, and cost of a similar previous project.

What to collect:
- Total development effort (person-days or hours)
- Calendar duration from kickoff to delivery
- Team size and composition
- Feature count, story points, lines of code, or other size metrics
- Defect counts and rework effort
- Cost breakdown by phase (design, dev, QA, deployment)

> [!warning] Quality of the Comparison Project
> The accuracy of the analogy estimate depends entirely on the quality of the historical data. A project with poor tracking data — or one that was significantly over- or under-resourced — is a weak comparator. Choose the most similar, best-documented past project available.

---

### Step 2 — List the Relevant Differences

> [!info] Identify Differences
> Make a ==list of all relevant differences== between the new project and the old project.

Differences to consider:

| Category | Examples |
|---|---|
| ==Scope== | More features, larger data model, additional integrations |
| ==Technology== | New framework, unfamiliar language, different infrastructure |
| ==Team== | Different size, experience level, domain familiarity |
| ==Process== | Different methodology, stricter compliance, new tooling |
| ==Stakeholders== | More complex approval chain, international stakeholders |
| ==Quality requirements== | Higher reliability targets, additional security requirements |
| ==External dependencies== | Third-party APIs, hardware dependencies, regulatory approvals |

> [!tip] Exhaustive Listing Pays Off
> The goal is not to immediately quantify differences — it is first to ensure none are missed. An overlooked difference is an unacknowledged risk. List everything, then assess impact.

---

### Step 3 — Build the Estimate with Adjustments

> [!info] Adjust the Baseline
> Build up the estimate for the new project based on the ==actual results of the old project==, plus ==adjustments for the relevant differences== identified in Step 2.

**Adjustment approach**:
- For each identified difference, estimate the impact relative to the baseline
- Express adjustments as percentages or absolute additions/subtractions
- Sum the adjusted components to reach the total estimate

> [!example] Adjustment Calculation
> Past project: 120 person-days actual effort, delivered a 15-screen web application.
>
> New project differences:
> - 5 additional screens (+33% scope): +40 days
> - New team unfamiliar with the framework (+15% learning curve): +18 days
> - Stricter accessibility requirements (+10%): +12 days
> - Simpler stakeholder structure (−5%): −6 days
>
> Adjusted estimate: 120 + 40 + 18 + 12 − 6 = **184 person-days**

> [!warning] Adjustment Uncertainty
> Each adjustment is itself an estimate. If there are many large adjustments, the analogy becomes less reliable — you are no longer comparing a similar project; you are adjusting a dissimilar one. If adjustments exceed ~30–40% of the baseline, consider whether this project is truly analogous or whether a different estimation method (decomposition, parametric) would be more accurate.

---

### Step 4 — Check for Consistent Assumptions

> [!info] Validate Assumptions
> Check for ==consistent assumptions== across the old project and the new project.

What to validate:
- Does "development effort" mean the same thing in both projects? (Same activities included/excluded?)
- Were the working hours and utilization rates comparable?
- Were quality standards similar, or does the new project have substantially different acceptance criteria?
- Were the project boundaries the same? (Did the old project include deployment and handover, or stop at code complete?)

> [!warning] Hidden Assumption Mismatches
> A common failure: the old project recorded only developer time, but the new project's estimate needs to include QA, BA, and PM effort too. The "120 person-days" baseline may be 80% of the real effort — applying it directly would produce an estimate that is 20% too low before any adjustments are made.

---

## Advantages and Limitations

### Advantages

> [!info] Strengths
> - ==Fast and simple== — does not require a detailed WBS or function point analysis
> - ==Anchored in reality== — based on actual outcomes, not theoretical models
> - ==Accessible== — requires no special tools or training, only historical records
> - ==Intuitive== — easy to explain to stakeholders why a past project is being used as a reference

### Limitations

> [!warning] Limitations
> - ==Requires a good comparator== — needs at least one well-documented similar past project; teams without historical data cannot use this method effectively
> - ==Accuracy degrades with dissimilarity== — if there are many significant differences between the old and new project, the estimate becomes less reliable
> - ==Subjective adjustments== — the adjustment step relies on judgment; different estimators may quantify the same difference very differently
> - ==Hides complexity== — by working at a high level, this method may miss newly introduced complexities that decomposition would surface

---

## Saving Estimation Results

> [!tip] Preserve All Estimation Artefacts
> It is important to ==save estimation results== for:
> - **Further review** — estimates should be revisited as the project evolves and actual data begins to accumulate
> - **Presentation of breakdown** — stakeholders benefit from seeing how the estimate was constructed (which past project, what adjustments, what assumptions)
> - **Adding time buffers** — document any buffers or risk adjustments separately so they can be reviewed and justified

Saving estimation artefacts also feeds the historical data pool. Today's actual results become tomorrow's comparison projects — closing the loop that makes analogy-based estimation more accurate over time.

> [!example] What to Save
> - The name and key metrics of the comparison project
> - The list of identified differences and their estimated impact
> - The final adjusted estimate and its confidence range
> - The assumptions checked in Step 4
> - Any buffers added and their justification

---

## Analogy vs. Decomposition

| Aspect | Analogy | Decomposition |
|---|---|---|
| Speed | Fast | Slow |
| Requires historical data | Yes — at least one good comparator | No |
| Handles unfamiliar scope | Poorly (adjustments become large) | Well (WBS surfaces unknowns) |
| Accuracy | High when projects are similar | High when WBS is complete |
| Best phase | Early — rough feasibility estimates | Any — most accurate at mid-late stage |
| Transparency | Moderate (adjustment rationale) | High (every element is costed) |

> [!example] When to Use Analogy
> - You have a past project that closely resembles the new one
> - You need a quick estimate without time for full decomposition
> - You want to cross-validate a decomposition estimate
> - The project is in early stages and full scope is not yet defined

---

## Summary

Estimation by analogy is a fast, intuition-friendly method that grounds new estimates in ==real historical outcomes==. Its four steps — gather actuals, list differences, adjust the baseline, validate assumptions — produce a defensible estimate quickly. Its accuracy is bounded by two factors: how closely the comparison project resembles the new one, and how thoroughly the differences have been identified and quantified. When those conditions are met, analogy-based estimation is one of the fastest paths from project description to reliable estimate. Saving the estimation breakdown preserves the reasoning for stakeholder review and builds the historical data pool for future analogies.

## Related Notes
- [[Estimation - Decomposition]]
- [[Estimation - Count Compute Judge]]
- [[Estimation - Main Sources of Uncertainty]]
- [[Estimation - Decomposition Steps]]
- [[Estimation - Why Accurate Estimates Matter]]
