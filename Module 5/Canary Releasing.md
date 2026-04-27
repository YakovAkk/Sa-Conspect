---
title: Canary Releasing
date: 2026-04-20
tags:
  - module5
  - deployment
  - patterns
  - release
  - canvas-note
cssclasses:
  - canvas-note
---

# Canary Releasing

> [!note] Overview
> ==Canary releasing== reduces risk during software deployment by gradually rolling out changes to a ==small subset of users== before a full-scale rollout. The new version is first deployed to infrastructure with no user traffic, then incrementally exposed through three phases until all users migrate and the old infrastructure is decommissioned.

## How It Works

A canary release reduces risk during software deployment by gradually rolling out changes to a small subset of users before a full-scale rollout.

To solve this, the new version is first deployed to part of the system where ==no users are sent==.

<picture>

### Three Phases

**Phase 1** — Deploy the new version to a subset of infrastructure. No users are routed to it yet.

**Phase 2** — Route a small number of selected users to the new version to gather real-world feedback and monitor performance.

**Phase 3** — Continue the migration incrementally until all users are on the new version. Decommission the old infrastructure.

### User Selection Methods

Users for the initial canary subset can be selected:
- ==Randomly== from the full user base
- As ==internal users first== to minimize external risk
- Based on ==demographic or behavioral profiles== to control the risk exposure

Running multiple versions simultaneously continues until the migration is complete and all users have been moved to the new version.

## Benefits and Hints

The main benefit of a canary release is that it lowers the risk of significant errors by limiting the initial exposure to a small subset of users, allowing teams to monitor and respond before a broader rollout.

> [!info] Benefits
> Canary releases offer benefits such as ==risk mitigation== through limited user exposure, ==early feedback== for issue identification, ==gradual deployment== to minimize downtime, and ==controlled monitoring== for a smooth transition. Rolling back to the previous version is simplified, as only a small percentage of users are affected if issues arise.

> [!tip] Hints
> To optimize canary releases, careful ==user subset selection==, strong ==monitoring tools==, incremental exposure, automation for swift deployment, infrastructure support for multiple versions, transparent communication with users, and a well-defined ==rollback plan== are essential components.

## Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Limits blast radius — only subset of users affected | Must maintain multiple versions simultaneously |
| Early real-world feedback before full rollout | Requires sophisticated routing and monitoring infrastructure |
| Simplified rollback — only small subset impacted | Slower full deployment compared to Blue-Green |
| Supports profile-based user targeting | Session stickiness may be needed to keep users on one version |

## When to Use

> [!example] Decision Hints
> - Use when ==gradual exposure== and real-world validation are more important than instant cutover.
> - Best for ==high-traffic services== where a full switch risk is too high.
> - Use when you want ==early feedback== from a controlled user group before full rollout.
> - Avoid when your infrastructure cannot support ==running multiple versions simultaneously==.
> - Combine with strong monitoring and a clear rollback plan before starting the canary.

## Related Notes

- [[Zero-Downtime Release]]
- [[Blue-Green Deployment]]
- [[Fault Tolerance Patterns]]
