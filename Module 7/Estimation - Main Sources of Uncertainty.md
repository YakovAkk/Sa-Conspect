---
title: "Estimation: Main Sources of Uncertainty"
date: 2026-04-29
tags:
  - module7
  - estimation
  - canvas-note
cssclasses:
  - canvas-note
---

# Estimation: Main Sources of Uncertainty

> [!note] Overview
> Estimation uncertainty comes from two root sources: ==poor input data== and ==problems in the estimation process itself==. Both make it harder to understand the project and its key factors. Five specific forms of inaccuracy emerge from these roots — and each can be reduced through better methods, historical learning, and expert collaboration.

---

## 1. The Two Root Sources

### Source 1: Poor Input Data

==Missing, incorrect, or changing information== makes it difficult for estimators to understand the project and its key factors. This can arise from:

> [!info] Causes of Poor Input Data
> - Changing project requirements (scope creep, shifting priorities)
> - Market shifts that alter assumptions mid-project
> - Weak or incomplete data collection processes
> - Stakeholders who do not yet know what they want

When input data is unreliable, even a good estimation process will produce uncertain results — garbage in, garbage out.

---

### Source 2: Problems in the Estimation Process

Even with good data, the estimation process itself can introduce uncertainty through flawed methods, cognitive biases, or conversion errors.

> [!info] Causes of Process Problems
> - Using inappropriate estimation techniques for the project type
> - Lack of historical reference data from past projects
> - Insufficient expert involvement
> - Poor communication and information-sharing culture

---

## 2. Five Forms of Estimation Inaccuracy

### 2.1 Omitted Activities

> [!warning] Omitted Activities
> Failure to account for ==all relevant tasks and activities== within the project scope results in underestimation of the effort and resources required.

Common omissions include:
- Testing, code review, and QA activities
- Documentation, deployment, and handover tasks
- Integration work with external systems
- Rework cycles and bug-fixing time

---

### 2.2 Unfamiliar Business or Technology Area

> [!warning] Unfamiliar Domain
> When estimators work in ==unfamiliar business domains or with emerging technologies==, they struggle to gauge the true complexity of the work.

This leads to estimation errors because:
- Hidden complexities are not visible until implementation begins
- Learning curves are not factored in
- Edge cases in new domains are harder to anticipate

> [!example] Example
> Estimating a blockchain-based payment system when the team has no prior blockchain experience — the unknowns compound quickly.

---

### 2.3 Subjectivity and Bias

> [!warning] Subjectivity and Bias
> Estimation involves ==subjective judgments==, which can be distorted by personal biases or organizational pressures.

| Type of Bias | Effect |
|---|---|
| Optimism bias | Underestimating effort (developers skew low by 20–30%) |
| Anchoring | First estimate becomes a fixed reference point regardless of evidence |
| Organizational pressure | Stakeholders push for lower estimates to win deals or meet targets |
| Recency bias | Over-relying on the most recent project as a reference |

---

### 2.4 Incorrect Conversion

> [!warning] Incorrect Conversion
> Errors in converting ==estimated effort to project duration== or ==time to schedule== distort the final estimates.

Common conversion mistakes:
- Assuming 1 person-day = 1 calendar day (ignoring meetings, overhead, context-switching)
- Not accounting for team size effects on productivity
- Ignoring parallel vs. sequential task dependencies
- Forgetting holidays, onboarding time, or part-time contributions

> [!example] Example
> An estimate of 100 person-hours divided by 5 people = 20 hours (2.5 days). But if the work is sequential and interdependent, it may take 5–8 days in practice.

---

### 2.5 Project Size and Complexity Factor

> [!warning] Size and Complexity
> ==Larger and more complex projects== have greater uncertainty because of the sheer number of variables, interdependencies, and unknowns involved.

The relationship is non-linear:
- A 2× larger project does not have 2× the uncertainty — it typically has much more
- More stakeholders → more coordination → more miscommunication risk
- More components → more integration points → more unexpected interactions

---

## 3. Summary of the Five Inaccuracy Forms

| Form | Root Source | Primary Risk |
|---|---|---|
| Omitted Activities | Both (data + process) | Scope underestimation |
| Unfamiliar Domain | Poor input data | Hidden complexity |
| Subjectivity and Bias | Process problem | Over- or underestimation |
| Incorrect Conversion | Process problem | Schedule distortion |
| Size / Complexity | Both | Compounding uncertainty |

---

## 4. How to Reduce Estimation Uncertainty

> [!tip] Mitigation Strategies
> - Use ==robust estimation methods== suited to the project type (e.g., analogy, parametric, expert judgment)
> - ==Learn from past projects== — build and maintain a historical data repository
> - ==Involve experts== who know the domain and technology
> - Foster a ==culture of open information sharing== — teams that communicate well estimate better
> - Decompose large projects into smaller chunks to reduce complexity impact
> - Always review estimates for omissions using structured checklists

---

## Summary

Estimation uncertainty has two root causes — poor input data and flawed estimation processes — and it manifests in five specific forms: omitted activities, unfamiliar domains, subjectivity and bias, incorrect conversions, and the compounding effect of project size. Understanding each form makes it possible to take targeted action: better methods, historical learning, expert input, and a collaborative team culture all help organizations produce ==more accurate and more useful estimates==.

## Related Notes
- [[Estimation - Definitions]]
- [[Estimation - Why Accurate Estimates Matter]]
- [[Estimation - Precision and Accuracy]]
- [[Estimation - Purpose]]
