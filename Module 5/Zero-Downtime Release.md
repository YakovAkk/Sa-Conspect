---
title: Zero-Downtime Release
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

# Zero-Downtime Release

> [!note] Overview
> A ==zero-downtime release==, also known as ==hot deployment==, allows software updates to be applied to a live system without any interruption for end users. Two key strategies — ==Blue-Green Deployment== and ==Canary Releasing== — both ensure continuous availability while managing the risk of deploying new versions.

## What Is Zero-Downtime Release

A zero-downtime release is a deployment strategy that allows software updates to be applied to a live system without any interruption or downtime for the end users. Unlike traditional deployment strategies where the system is taken offline during updates, a zero-downtime release ensures continuous availability.

Before switching, it's good practice to identify a ==safe rollback point== to prevent any issues during or after the release.

## Two Strategies

| Strategy | How It Works | Rollback |
|---|---|---|
| ==Blue-Green Deployment== | Two identical environments; traffic switches instantly from green to blue | Redirect traffic back to the previous environment |
| ==Canary Releasing== | New version deployed to a subset of users/servers first | Roll back only the affected subset |

### Blue-Green Deployment

In Blue-Green deployment, ==two production environments== are maintained simultaneously. The new version is deployed to the inactive environment, tested, and then traffic is instantly switched from the old to the new environment, enabling rollback by simply redirecting traffic back if needed.

### Canary Releasing

Canary releasing deploys the new version to a ==small subset of users or servers== first, gathering feedback and monitoring performance before a full rollout. It minimizes the risk of large-scale failures by limiting initial exposure.

## When to Choose Which

> [!example] Decision Hints
> - Use ==Blue-Green== when you need an instant, all-or-nothing switch with simple rollback — best for stateless services or when two full parallel environments are feasible.
> - Use ==Canary Releasing== when you want gradual exposure with real-world feedback — best for high-traffic services where a full switch carries too much risk.
> - Both strategies require robust monitoring and a defined rollback plan before deployment begins.

## Related Notes

- [[Blue-Green Deployment]]
- [[Canary Releasing]]
- [[Security Patterns]]
- [[Fault Tolerance Patterns]]
