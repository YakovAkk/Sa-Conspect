---
title: "Estimation: Decomposition Percentages (PERT)"
date: 2026-04-29
tags:
  - module7
  - estimation
  - canvas-note
cssclasses:
  - canvas-note
---

# Estimation: Decomposition Percentages (PERT)

> [!note] Overview
> The ==Program Evaluation Review Technique (PERT)== is a project management method that estimates project length by explicitly recognizing that estimates carry risks and require additional surrounding activities. Rather than estimating only development, PERT-style decomposition adds ==percentage-based buffers== for management, testing, bug fixing, BA, and other tasks — typically implemented in a spreadsheet with formulas for easy calculation.

---

## 1. What Is PERT in This Context?

PERT acknowledges a fundamental truth: ==development effort is never the full project effort==. Every software project includes surrounding activities that consume real time and must be estimated.

The approach:
1. Estimate core development effort
2. Add each surrounding activity as a ==percentage of development effort==
3. Sum everything for total project effort

> [!tip] Use a Spreadsheet
> Tracking these percentages in an Excel file or spreadsheet with formulas makes recalculation instant when any base estimate changes. This is especially useful during negotiation when scope or timeline shifts.

---

## 2. Standard Percentage Benchmarks

### Management Activities

> [!info] Management Overhead
> Add **5–10%** of total task effort for ==management activities==:
> - Sprint planning and retrospectives
> - Stakeholder communication
> - Status reporting
> - Risk monitoring

---

### Testing

> [!info] Testing Effort
> Testing effort varies significantly by project type:
> - **20%** — well-understood domain, stable requirements, experienced team
> - **30%** — typical project with moderate complexity
> - **50%** — safety-critical, high-compliance, or complex integration-heavy projects

> [!warning] Testing Is Often Underestimated
> Teams frequently budget 10–15% for testing and then discover it actually consumed 30–40%. Use conservative (higher) percentages unless historical data supports lower.

---

### Bug Fixing and Business Analysis

> [!info] Bug Fixing and BA
> Add **5–15%** for ==bug fixing and business analysis==, depending on:
> - The project (greenfield vs. legacy)
> - The client (how clear and stable their requirements are)
> - The team (experience level, domain familiarity)

---

### Other Development Activities

> [!info] Supporting Development Tasks
> Beyond the main features, estimate these as fixed percentages of core development:

| Activity | Typical % of Dev Effort |
|---|---|
| ==Unit tests== | ~10% |
| ==Integration testing== | ~10% |
| ==Writing documentation== | ~5% |

---

## 3. Full Percentage Reference Table

| Activity | Typical Range | Notes |
|---|---|---|
| Management | 5–10% | Of total effort |
| Testing | 20–50% | Depends on project complexity |
| Bug fixing | 5–15% | Depends on project, client, team |
| Business analysis | 5–15% | Depends on requirements stability |
| Unit tests | ~10% | Of dev effort |
| Integration testing | ~10% | Of dev effort |
| Documentation | ~5% | Of dev effort |

---

## 4. Worked Example

> [!example] PERT-Style Decomposition Example
> **Base development estimate:** 100 days
>
> | Activity | % | Days |
> |---|---|---|
> | Management | 8% | 8 |
> | Testing | 30% | 30 |
> | Bug fixing | 10% | 10 |
> | BA support | 8% | 8 |
> | Unit tests | 10% | 10 |
> | Integration testing | 10% | 10 |
> | Documentation | 5% | 5 |
> | **Total** | **+81%** | **181 days** |
>
> A project estimated at 100 development days actually requires approximately **181 calendar-adjusted days** of total project effort.

> [!warning] Common Mistake
> Presenting 100 days to stakeholders when the real effort is 181 days is one of the most frequent causes of project overruns. The percentage additions are not optional — they represent real, unavoidable work.

---

## 5. Advantages and Limitations of Decomposition

### Advantages

> [!info] Advantages
> - ==High accuracy== — supported by the Law of Large Numbers: small over- and under-estimates balance each other out across many tasks
> - Transparent — every component is visible and traceable
> - Flexible — each percentage can be tuned to team and project specifics
> - Easy to update — changing the base estimate recalculates everything in a spreadsheet

### Limitations

> [!warning] Limitations
> - ==Requires a complete WBS== — if the task breakdown is incomplete, the estimate will be systematically low regardless of how accurate the individual percentages are
> - ==Time-consuming to build== — creating a thorough decomposition takes significant effort, which must itself be factored into planning
> - Percentages are averages — they may not reflect extreme projects (very small, very large, or highly unusual)

---

## Summary

PERT-style decomposition percentages transform a raw development estimate into a ==full project estimate== by explicitly accounting for management, testing, bug fixing, BA, and supporting development activities. The core insight is that development is typically only 55–65% of total project effort. Using consistent percentages — calibrated to your team's historical data — and tracking them in a spreadsheet makes this process both ==rigorous and maintainable==. The approach's accuracy is only as good as the WBS it is built on: incomplete decomposition is the single biggest risk to estimate quality.

## Related Notes
- [[Estimation - Decomposition]]
- [[Estimation - Decomposition Steps]]
- [[Estimation - Work Breakdown Structure]]
- [[Estimation - Why Accurate Estimates Matter]]
