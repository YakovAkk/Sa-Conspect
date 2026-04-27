---
title: Voting
date: 2026-04-20
tags:
  - module5
  - fault-tolerance
  - patterns
  - resilience
  - canvas-note
cssclasses:
  - canvas-note
---

# Voting

> [!note] Overview
> ==Voting== is a fault tolerance pattern that arbitrates between redundant components when they produce different results. A voter evaluates all outputs and selects the correct one — treating any component that loses the vote as erroneous. It is the natural companion to [[Redundancy]].

## The Problem Voting Solves

When [[Redundancy]] is introduced, multiple components run in parallel and may produce conflicting answers. Voting answers: *which result should be trusted?*

> [!info] Context / Risk
> In case of redundancy that provides multiple answers, you need a strategy to decide what answer should be used.

**Intention**: Arbitrate the results from the redundant components.

**Solution**: Devise a voting strategy. In case of disagreement, treat the element that loses the vote as erroneous. Make sure you can trust the entity taking the vote.

## Two Fault Tolerance Techniques Using Voting

### TMR — Triple Modular Redundancy

<picture>

==TMR== is a **hardware** fault tolerance technique that tolerates a single fault at a time. Three redundant copies of critical components are generated and run concurrently. The voter evaluates all three results and selects the majority.

### N-Version Programming

==N-Version Programming== is a **software** fault tolerance technique where N independent versions of the software are developed by N separate individuals or groups. All redundant copies execute concurrently and produce results independently. The voter assesses all results and selects the majority.

## Three Voting Strategies

| Strategy | How It Works | Best For |
|---|---|---|
| ==Majority Vote== | Simple majority wins | Odd number of nodes |
| ==Generalized Median Voting== | Selects the middle result by removing extreme values | Filtering outliers |
| ==Formalized Plurality Voting== | Splits results into groups; randomly picks from the largest group | Larger, more complex sets |

## Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Detects and isolates faulty components | Requires at least 3 redundant components for TMR |
| Works for both hardware and software | Voter itself becomes a potential single point of failure |
| Enables automatic error correction | N-Version adds development cost (N independent teams) |
| Provides strong access control in distributed systems | Voter must be trusted — compromising it breaks the pattern |

## When to Use

> [!example] Decision Hints
> - Use Voting whenever [[Redundancy]] produces multiple conflicting outputs and a single authoritative answer is needed.
> - Use TMR for hardware components where a single silent fault must be masked.
> - Use N-Version Programming when independent software implementations reduce the risk of common-mode failures.
> - Choose Generalized Median Voting when extreme outliers (not simple failures) are the main concern.

## Related Notes

- [[Fault Tolerance Patterns]]
- [[Redundancy]]
- [[Heartbeat]]
- [[Leaky Bucket Counter]]
