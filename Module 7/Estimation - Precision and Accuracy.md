---
title: "Estimation: Precision and Accuracy"
date: 2026-04-29
tags:
  - module7
  - estimation
  - canvas-note
cssclasses:
  - canvas-note
---

# Estimation: Precision and Accuracy

> [!note] Overview
> ==Accuracy== and ==precision== are two distinct properties of an estimate, and confusing them leads to misleading — even harmful — results. As Warren Buffett said: *"It's better to be approximately right than precisely wrong."* Estimates are never exact; the goal is to be close to the real value, not to produce an impressively detailed number that is far from reality.

## 1. The Two Concepts Defined

### Accuracy

==Accuracy== refers to how close an estimate is to the actual result.

> [!info] Accuracy
> An estimate is **accurate** when it reflects what actually happens — even if it is expressed as a range or a rough number.

**Example:** Task X will take **between two and four days.**
- If Task X actually takes 3 days, this estimate is ==accurate==.
- It does not need to be exact — it just needs to capture the real value.

---

### Precision

==Precision== refers to how detailed or specific an estimate is — for example, how many decimal places it uses or how narrow the range is.

> [!info] Precision
> An estimate is **precise** when it is expressed with high specificity — but precision says nothing about whether the number is correct.

**Example:** Task X will take **2.04 days.**
- This looks highly confident and detailed.
- But if Task X actually takes 3 days, this estimate is ==precise but inaccurate==.

---

## 2. Why Precision Without Accuracy Is Dangerous

> [!warning] False Precision
> A highly precise estimate creates an illusion of certainty. Stakeholders may trust it more than a wider, more honest range — even though the precise number is further from reality.

Consider a project estimated to last **several years**. Expressing this estimate in exact work-hours implies a level of control and knowledge that simply does not exist at that stage. The precision is ==misleading== because:
- Future work is not yet fully understood
- Dependencies, risks, and scope will change
- The precision conveys a false sense of accuracy

---

## 3. The Key Principle: Match Precision to Accuracy

> [!tip] The Matching Rule
> The level of ==precision== in an estimate should match the level of ==accuracy== that is realistically achievable.

| Situation | Appropriate Precision |
|---|---|
| Early-stage project, high uncertainty | Wide range (e.g., "3–6 months") |
| Mid-project, moderate certainty | Narrower range (e.g., "3–4 weeks") |
| Well-understood task, low uncertainty | Specific estimate (e.g., "2–3 days") |
| Very specific task, all details known | Precise estimate (e.g., "~6 hours") |

> [!warning] Do NOT Do This
> Estimating a multi-year project in exact work-hours is a classic mistake. It implies precision far beyond what is knowable — and that precision actively misleads decision-makers.

---

## 4. Comparison: Accurate vs. Precise

| Property | Accurate | Precise |
|---|---|---|
| Definition | Close to the actual result | High level of detail / specificity |
| Example | "2–4 days" (actual: 3 days) ✓ | "2.04 days" (actual: 3 days) ✗ |
| Can be wrong? | Yes, but by design it's close | Yes — precision does not guarantee correctness |
| Preferred? | ==Yes — always aim for this== | Only when accuracy is also achievable |
| Risk of misuse | Low | High — creates false confidence |

---

## 5. Practical Examples

> [!example] Accurate but Not Precise
> "This feature will take **about 3 days**."
> - Actual result: 3.2 days
> - This estimate is useful, honest, and trustworthy.

> [!example] Precise but Not Accurate
> "This feature will take **2.13 days**."
> - Actual result: 3.2 days
> - This estimate is misleading. The precision implies knowledge that wasn't there.

> [!example] Both Accurate and Precise (ideal, but rare)
> "This task will take **3–3.5 days**."
> - Actual result: 3.3 days
> - Achievable only when the work is very well understood.

---

## Summary

Accuracy and precision are not the same. ==Accuracy== is about being close to the truth; ==precision== is about the level of detail in your expression. The best estimates are accurate first, and precise only to the degree that accuracy allows. Forcing false precision onto an inherently uncertain estimate does not make it better — it makes it more dangerous, because it misleads decision-makers into trusting a number more than they should.

## Related Notes
- [[Estimation - Definitions]]
- [[Estimation - Why Accurate Estimates Matter]]
- [[Estimation - Purpose]]
