---
title: "Estimation: Wideband Delphi Tips"
date: 2026-04-29
tags:
  - module7
  - estimation
  - canvas-note
cssclasses:
  - canvas-note
---

# Estimation: Wideband Delphi Tips

> [!note] Overview
> Wideband Delphi is most effective ==early in a project== when requirements are still forming and when the team needs input from people across different roles. It does not require historical data, making it accessible even for new teams or unfamiliar domains. Five practical tips guide how to run the technique effectively and avoid the common failure modes.

---

## When Wideband Delphi Works Best

> [!info] Ideal Use Cases
> - ==Early project estimates== when scope is still being defined
> - Teams working with ==unfamiliar systems== or new technology stacks
> - Situations requiring input from ==people in different roles or areas of expertise==
> - Projects where ==no historical data== is available to anchor estimates

The method does not require a database of past projects or calibrated velocity metrics. Its accuracy comes from combining diverse human expertise — which is always available — rather than from recorded data that may not exist for a new team or domain.

---

## Tip 1: Select Three to Five Experts

> [!tip] Group Size: 3–5
> Opt for a group review comprising ==three to five experts==, ensuring diverse perspectives and expertise.

**Why this range matters**:
- Fewer than three experts narrows the perspective pool — one person's blind spot becomes the group's blind spot
- More than five creates coordination overhead, makes consensus harder to reach, and can allow dominant voices to crowd out quieter ones
- Three to five is the sweet spot: enough diversity to surface hidden complexity, small enough to reach genuine agreement

> [!info] Who Should Be in the Group
> Aim for cross-functional representation:
> - At least one developer (implementation complexity)
> - At least one QA engineer (testing scope and edge cases)
> - A domain expert or business analyst if requirements are unclear
> - An architect or tech lead for cross-cutting or integration-heavy work

> [!warning] Avoid Homogeneous Groups
> A group of five developers will produce a development estimate, not a project estimate. Missing perspectives produce systematically low estimates — the group can only see what its members collectively know.

---

## Tip 2: Encourage Individual Estimation

> [!tip] Estimate Individually First
> Foster ==individual estimation== to harness the benefits of varied approaches and insights from each participant.

Independent estimation is the foundation of the entire method. If estimators discuss before committing to numbers, anchoring bias takes over: everyone clusters around the first number mentioned, which is often the most confident voice rather than the most accurate one.

> [!info] How to Enforce It
> - Distribute the estimation form ==before any group discussion==
> - Set a time limit for individual preparation (e.g., 15–30 minutes)
> - Collect estimates ==before revealing any results== — even partial ones

> [!example] What Individual Estimation Surfaces
> Developer A focuses on implementation and estimates 4 days. QA engineer B, thinking about regression risk, estimates 7 days. Business analyst C, aware of a stakeholder requirement ambiguity, estimates 9 days. None of these is "wrong" — together they define the true scope. Without independent estimation, only one perspective would have been heard.

---

## Tip 3: Facilitate Iterative Discussion

> [!tip] Promote Convergence Through Iteration
> Promote convergence through ==iterative discussion==, allowing participants to exchange views, address discrepancies, and refine their estimates collaboratively.

Iterative discussion means the group does not try to reach consensus in a single round. Each round follows the same pattern: submit estimates anonymously → reveal summary → discuss divergence → re-estimate. The iteration continues until the spread narrows to an acceptable range.

> [!info] What "Convergence" Looks Like
> - Estimates from different participants are getting closer across rounds
> - The best-case and worst-case range is narrowing
> - Participants can articulate the same assumptions in their own words

> [!warning] Stalled Iteration
> If estimates are not converging after two or three rounds, the discussion is not resolving the underlying disagreement — it is circling around it. The facilitator should identify the specific assumption that is causing divergence and address it directly, even if that means pausing to clarify requirements with stakeholders.

> [!tip] Visualize All Rounds Together
> Show all rounds of estimates on the ==same scale==. Seeing whether the spread is widening or narrowing helps the team decide whether to continue iterating or accept the current state of agreement.

---

## Tip 4: Consensus on Average Estimate

> [!tip] Strive for Consensus
> Strive for ==consensus among participants to accept the average estimate==, ensuring alignment and collective agreement on the final estimation.

Consensus does not mean the average is mathematically correct — it means the group has understood why the average is the best available estimate given what is known. Every participant should be able to say: "I understand how we arrived at this number and I commit to working within it."

> [!info] Average vs. Consensus
> The ==average== is a calculation. ==Consensus== is an agreement. The goal is to reach a consensus *about* an average — not to blindly accept the arithmetic mean. If the average lands between two meaningfully different scenarios, the team should decide which scenario is more likely rather than splitting the difference.

> [!example] When the Average Is Misleading
> Estimates: 2, 3, 3, 4, 14 days. The average is 5.2 days, but four of five estimators cluster at 2–4. The outlier at 14 warrants investigation before accepting 5.2 as the consensus estimate. The right response is to ask the 14-day estimator what they are seeing — which may reveal a risk worth adding to the project buffer rather than inflating the base estimate.

---

## Tip 5: Ensure Anonymity to Eliminate Authority Influence

> [!tip] Maintain Anonymity Throughout
> To mitigate the influence of authority or hierarchy, ==maintain anonymity throughout the process==, facilitating open and unbiased participation from all experts.

The ==HiPPO effect== (Highest Paid Person's Opinion) is one of the most consistent sources of estimation bias in group settings. When a senior engineer or manager shares their estimate first, everyone else adjusts toward it — not because it's more accurate, but because disagreeing feels socially costly.

> [!info] What Anonymity Protects Against
> - Junior team members deferring to senior ones
> - Team members adjusting estimates to match what the manager "wants to hear"
> - The first person to speak setting an anchor everyone else converges toward
> - Groupthink replacing genuine independent analysis

> [!warning] Anonymity Is a Process Design Choice, Not a Courtesy
> Anonymity must be ==built into the procedure==, not relied on voluntarily. The coordinator collects and aggregates all estimates before any are shared. Estimates are presented as a distribution, not attributed to individuals. Without structural enforcement, anonymity evaporates under social pressure.

---

## Summary of the Five Tips

| Tip | Rule | Why It Matters |
|---|---|---|
| ==3–5 experts== | Right group size | Diversity without coordination overhead |
| ==Individual estimation== | Estimate before discussing | Prevents anchoring; captures genuine variation |
| ==Iterative discussion== | Multiple rounds | Surfaces hidden assumptions; drives real convergence |
| ==Consensus on average== | Agree, don't just calculate | Ensures commitment, not just arithmetic |
| ==Anonymity== | Structural, not voluntary | Eliminates authority bias and social pressure |

---

## Why Wideband Delphi Produces Accurate Estimates

> [!info] Mechanism of Accuracy
> Wideband Delphi improves accuracy through three compounding mechanisms:
> 1. **Diverse input**: multiple specialist perspectives cover blind spots that individuals miss
> 2. **Independent first estimates**: prevents anchoring, ensuring the discussion starts from genuine independent analysis
> 3. **Structured iteration**: forces disagreements to be resolved through understanding, not averaging or pressure

The result is an estimate that reflects the team's ==collective intelligence== rather than any one person's guess — which is why it works even in complex or uncertain situations where historical data is unavailable.

---

## Summary

Wideband Delphi is most valuable when applied ==early==, with ==three to five cross-functional experts==, following the discipline of ==individual estimation before group discussion==. Anonymity is not optional — it must be enforced structurally to prevent authority bias from collapsing the diversity the method depends on. Iterative rounds drive genuine convergence; the goal is a ==consensus on an average== that the whole team understands and commits to. When these five tips are followed, Wideband Delphi reliably produces accurate and defensible estimates even in the most uncertain project conditions.

## Related Notes
- [[Estimation - Wideband Delphi]]
- [[Estimation - Expert Judgment in Groups]]
- [[Estimation - Main Sources of Uncertainty]]
- [[Estimation - Story Points Factors]]
- [[Estimation - Decomposition Best Practices]]
