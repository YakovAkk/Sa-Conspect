---
title: Blue-Green Deployment
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

# Blue-Green Deployment

> [!note] Overview
> ==Blue-Green deployment== maintains two identical production environments — blue and green — where one is live and the other is idle. The new version is deployed to the idle environment, smoke-tested, and traffic is switched in ==under a second==. Rollback requires only redirecting traffic back to the previous environment.

## How It Works

Blue-Green deployment achieves zero-downtime releases by maintaining ==two identical production environments==, known as blue and green. One environment is live (serving users), while the other is idle (staging the next release).

These environments can be on different hardware, virtual machines, or separate zones within the same infrastructure to ensure complete isolation.

<picture>

### Four-Step Deployment Process

- **Deploy the Application to the Blue Environment** — Introduce the new version of the application to the blue environment.
- **Allow the Application to Warm Up** — Give the application the necessary time to warm up and stabilize.
- **Conduct Smoke Tests on the Blue Environment** — Execute smoke tests to verify the correct functionality of the blue environment.
- **Update Router Configuration to Direct to Blue** — Modify the router configuration to redirect user traffic to the blue environment instead of the green one.

The Blue-Green deployment strategy is popular because it makes returning to a previous version easy — simply redirect traffic back to the green environment, minimizing the impact of any issues.

## Scenario Example

The Blue-Green deployment model is useful for updating the mechanics microservice of a cloud-native mobile game. It allows for seamless updates that minimize disruption to the gaming experience.

Imagine a cloud-native mobile game where the game mechanics are managed by a dedicated microservice. This microservice handles the core gameplay elements such as physics, collision detection, and game rules.

### User Activity During Initial Release

The game has hundreds of users playing simultaneously. A minor update has been released for the mechanics microservice, altering the size and speed of the red balloon.

### Optimizing Peak Use Time

The Blue-Green deployment strategy is adopted to update the mechanics microservice during peak activity. The goal is to achieve zero downtime.

### Creating an Identical Environment

The current blue (production) container is duplicated to create the green environment. QA and staging processes are conducted via Jenkins.

### Seamless Transition and Load Balancing

The load balancer is updated to redirect traffic from the blue environment to the green environment. Blue gracefully stops accepting new requests and completes ongoing ones. Once fully transitioned, blue can serve as a disaster recovery standby or be repurposed for the next update cycle.

## Five Best Practices

One of the key advantages of Blue-Green deployment is the ability to switch between environments in ==less than a second==, ensuring minimal disruption during traffic redirection.

### Choose Load Balancing Over DNS Switching

Leverage load balancers rather than DNS to switch between environments. Keep DNS pointing to the load balancer, which controls traffic direction between blue and green environments.

### Execute a Rolling Update

Add one new server to the new environment, then retire one old server from the current environment, and repeat. Ensure that old and new code can run ==side-by-side== during the transition period.

### Monitor Your Environments with the Correct Alerts

Use a different API token for production and non-production APM monitoring. Programmatically change the alert policy when switching environments to ensure accurate alerting.

### Automate the Process

Script the switching process between blue and green environments. Ensure proper permissions are in place, and provide self-service capabilities for teams to perform deployments independently.

### Make Your Code Backward and Compatible

Break large changes into mini-updates that support both old and new data formats simultaneously. For example, when renaming a field, release an intermediate version that supports both the old and new field names before completing the rename.

## Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Instant traffic switch — sub-second cutover | Requires double the infrastructure cost |
| Simple rollback — redirect traffic back | Both environments must stay identical and in sync |
| Full environment isolation during testing | Not suitable when running two full environments is too costly |
| Blue can serve as disaster recovery standby | Database schema migrations require careful backward compatibility |

## When to Use

> [!example] Decision Hints
> - Use when you need ==instant, all-or-nothing cutover== with minimal rollback complexity.
> - Best for ==stateless services== where two full parallel environments are feasible.
> - Combine with ==load balancers== (not DNS) for sub-second switching.
> - Ensure code is ==backward compatible== to support side-by-side old/new versions during transition.
> - Avoid when infrastructure cost of running two full environments is prohibitive.

## Related Notes

- [[Zero-Downtime Release]]
- [[Canary Releasing]]
- [[Fault Tolerance Patterns]]
