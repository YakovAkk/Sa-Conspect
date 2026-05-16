---
title: "Estimation: Decomposition"
date: 2026-04-29
tags:
  - module7
  - estimation
  - canvas-note
cssclasses:
  - canvas-note
---

# Estimation: Decomposition

> [!note] Overview
> ==Decomposition== is the practice of breaking an estimate into smaller, independently estimated parts and then summing them to produce a total. The ==Law of Large Numbers== explains why this works: small overestimates and underestimates on individual parts tend to cancel each other out, making the overall estimate more accurate than a single top-level guess.

---

## 1. Why Decomposition Works

Estimating a large project as a single unit magnifies any judgment error. Decomposing it into parts distributes and reduces that error.

> [!info] Law of Large Numbers Applied to Estimation
> When you estimate many small items independently, the random errors in each estimate — some too high, some too low — ==tend to balance out==. The aggregate total converges closer to the true value than any single holistic estimate would.

This is the same statistical principle that makes polling a large group more accurate than asking one person.

---

## 2. The Three-Step Decomposition Process

### Step 1: Understand the Features

Identify and list all the features or components that make up the project.

> [!example] Social Network Project
> Assume the project has four features:
> 1. Adding friends
> 2. Sending messages
> 3. Creating stories
> 4. Creating video reels

---

### Step 2: Estimate Each Part Using Count, Compute, Judge

Apply the ==Count, Compute, Judge== technique to each feature independently — do not let one feature's estimate anchor the others.

> [!tip] Estimate in Isolation
> Estimate each feature as if it were a standalone project. This forces honest evaluation of each part's individual complexity and reduces the anchoring effect that distorts holistic estimates.

---

### Step 3: Apply the Law of Large Numbers

After collecting all individual estimates, apply the ==Law of Large Numbers== to produce the final estimate:

> [!info] Trimmed Mean Approach
> Remove the ==lowest and highest estimates== from the set, then average the remaining values. This trims the outliers and gives you the middle estimation — a more reliable central value.

> [!example] Applying the Trimmed Mean
> Feature estimates (in weeks): Adding friends = 2, Messages = 5, Stories = 3, Video reels = 8
> Remove lowest (2) and highest (8):
> Remaining: 5 + 3 = 8 ÷ 2 = **4 weeks average per feature**
> Total estimate: 4 features × 4 weeks = **~16 weeks**

---

## 3. Work Breakdown Structure (WBS)

A ==Work Breakdown Structure (WBS)== is a formal tool for decomposition. It hierarchically breaks down all project work into manageable components.

> [!info] What WBS Provides
> - A ==hierarchical decomposition== of deliverables and tasks
> - Clear ==ownership== of each work package
> - A foundation for ==cost estimation== at each level
> - A structure for ==progress tracking==
> - Input for creating a ==project schedule==

### WBS Structure Example

```
Project: Social Network App
├── Feature 1: Add Friends
│   ├── Backend API
│   ├── Database schema
│   ├── Frontend UI
│   └── Testing
├── Feature 2: Messaging
│   ├── Real-time connection (WebSocket)
│   ├── Message storage
│   ├── UI components
│   └── Testing
├── Feature 3: Stories
│   └── ...
└── Feature 4: Video Reels
    └── ...
```

> [!tip] WBS Best Practice
> Decompose until each work package is small enough to estimate with confidence — typically 8–80 hours of effort. Packages that are too large carry hidden complexity; packages that are too small create overhead.

---

## 4. Decomposition vs. Single Estimate

| Approach | Accuracy | Effort | Risk of Error |
|---|---|---|---|
| Single holistic estimate | Low — magnifies judgment errors | Low | High |
| ==Decomposition== | High — errors cancel out | Medium | Low to Medium |
| Decomposition + WBS | Highest — full structure | Higher | Lowest |

---

## 5. Common Decomposition Pitfalls

> [!warning] Pitfalls to Avoid
> - **Forgetting integration work**: the effort to connect features together is often as large as estimating the features themselves
> - **Omitting non-functional work**: testing, deployment, documentation, and performance tuning are not features but are real effort
> - **Anchoring across features**: if estimators know each other's numbers, earlier estimates distort later ones — estimate blindly where possible (e.g., Planning Poker)
> - **Over-decomposing**: breaking work into units smaller than can be meaningfully estimated wastes time without improving accuracy

---

## Summary

Decomposition is one of the most reliable ways to improve estimation accuracy. By breaking a project into independently estimated parts, the ==Law of Large Numbers== allows random over- and under-estimates to offset each other, producing a more accurate total. The three steps — understand the features, estimate each with Count/Compute/Judge, and apply the trimmed mean — form a practical workflow. A ==Work Breakdown Structure (WBS)== formalizes this process, adding structure for cost estimation, scheduling, and progress tracking.

## Related Notes
- [[Estimation - Count Compute Judge]]
- [[Estimation - Determining What to Count]]
- [[Estimation - Main Sources of Uncertainty]]
- [[Estimation - Why Accurate Estimates Matter]]
