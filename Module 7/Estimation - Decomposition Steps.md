---
title: "Estimation: Decomposition Steps"
date: 2026-04-29
tags:
  - module7
  - estimation
  - canvas-note
cssclasses:
  - canvas-note
---

# Estimation: Decomposition Steps

> [!note] Overview
> The decomposition process follows ==four structured steps== that move from understanding requirements, through estimating development and non-development effort, to producing a final schedule and resource plan. Each step builds on the previous one, progressively transforming vague project scope into a concrete, validated estimate.

---

## Step 1: Prepare

> [!info] Prepare
> Before any estimation can begin, the team must understand and structure the work.

**Activities:**
- ==Refine the requirements==: review what is known, identify gaps, and fill them with explicit ==assumptions== (document all assumptions — they directly affect estimate validity)
- ==Work out an outline of architecture==: a rough architectural view helps reveal hidden complexity, dependencies, and integration points that are invisible from requirements alone
- ==Perform decomposition via WBS==: break down the project using a Work Breakdown Structure to the level where individual elements can be independently estimated

> [!tip] Why Architecture Matters in Preparation
> Without even a rough architecture, estimators miss integration costs, infrastructure work, and cross-cutting concerns. A 30-minute architecture sketch can prevent days of underestimation.

---

## Step 2: Estimate Development Effort

> [!info] Estimate Development Effort
> Estimate the core technical work: the effort required to build, test, and deliver the software.

**Activities:**
- ==Estimate each lowest-level WBS element== independently — use Count, Compute, or Judge as appropriate for each item
- ==Identify and define risks== associated with each estimate; attach ==assumptions== to any uncertain items
- ==Calculate total development effort== by summing all element-level estimates
- ==Specify what "development" includes==: be explicit about which activities are in scope — coding only? Code review? Unit testing? Performance tuning? Deployment?

> [!warning] Define "Development" Before You Estimate
> If estimators have different mental models of what development includes, the sum will be meaningless. Agree on the definition before the first estimate is made.

> [!example] Development Scope Checklist
> Common items to include (or explicitly exclude):
> - Feature implementation
> - Unit and integration tests
> - Code review cycles
> - Technical documentation
> - Database migrations
> - Deployment scripts and configuration

---

## Step 3: Estimate Other Activities

> [!info] Estimate Other Activities
> Development is never the whole project. All surrounding activities must be estimated and added to the total.

**Activities:**
- ==Add all required project and development activities== that are not strictly coding:
  - Project management
  - Business analysis
  - QA / testing (if not included in development)
  - UX/UI design
  - Technical writing
  - Stakeholder communication and reviews
- ==Estimate them as a percentage of development effort==, or consult BA/QA experts directly if they are available
- ==Estimate all risks== based on their probability and cost:
  - Assign each risk a probability (e.g., 30% likely)
  - Estimate the cost if the risk materializes
  - Add `probability × cost` as a risk buffer to the total

> [!tip] Using Percentages for Non-Development Activities
> If you lack expert input, industry benchmarks offer starting points:
> - QA: 20–40% of development effort
> - Project management: 10–15% of total project effort
> - Business analysis: 10–20% of development effort
>
> Adjust based on your team's actual historical ratios.

> [!example] Risk Estimation Example
> Risk: "Third-party payment API may require significant customization"
> Probability: 40% | Cost if it occurs: 10 extra days
> Risk contribution: 0.4 × 10 = **4 days** added to the estimate

---

## Step 4: Finalize

> [!info] Finalize
> Consolidate all estimates into a final schedule and resource plan, then validate.

**Activities:**
- ==Calculate schedule and resources==: translate total effort into calendar duration using team capacity, load factor, and resource availability
- ==Check yourself using another estimating method== (optional but recommended): if you used decomposition, cross-validate with analogy-based estimation, parametric estimation, or a rough expert judgment — significant divergence is a signal to investigate

> [!tip] Cross-Validation Is a Sanity Check
> If decomposition gives 12 weeks and a quick analogy comparison says "similar projects took 6–8 weeks," investigate the gap before committing. The discrepancy often reveals omitted scope or hidden complexity.

> [!example] Finalization Calculation
> Total development effort: 120 man-days
> Other activities (QA 30% + PM 12% + BA 15%): +68 man-days
> Risk buffer (4 days): +4 man-days
> **Total effort: 192 man-days**
>
> Team: 4 developers + 1 QA, load factor 0.7
> Available daily capacity: 5 × 0.7 = 3.5 ideal-days/day
> Calendar duration: 192 ÷ 3.5 ≈ **55 calendar days (~11 weeks)**

---

## Summary of the Four Steps

| Step | Key Output | Key Risk if Skipped |
|---|---|---|
| ==1. Prepare== | Refined requirements, architecture outline, WBS | Estimating the wrong scope |
| ==2. Estimate Development== | Effort per WBS element, total dev effort, risk list | Missing technical work; undefined "development" |
| ==3. Estimate Other Activities== | Full project effort including QA, PM, BA, risk buffer | Underestimating total project cost by 40–60% |
| ==4. Finalize== | Schedule, resources, validated estimate | No schedule; unvalidated numbers committed to stakeholders |

---

## Summary

The four decomposition steps — Prepare, Estimate Development Effort, Estimate Other Activities, and Finalize — form a ==complete estimation pipeline==. Skipping any step introduces systematic blind spots: missing scope in step 1, undefined boundaries in step 2, ignored overhead in step 3, and unvalidated numbers in step 4. Used together with WBS and Count/Compute/Judge, these steps convert decomposition from a loose idea into a ==reliable, reproducible estimation process==.

## Related Notes
- [[Estimation - Decomposition]]
- [[Estimation - Work Breakdown Structure]]
- [[Estimation - Count Compute Judge]]
- [[Estimation - Ideal Man-Time]]
- [[Estimation - Main Sources of Uncertainty]]
