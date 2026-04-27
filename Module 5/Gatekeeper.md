---
title: Gatekeeper
date: 2026-04-20
tags:
  - module5
  - security
  - patterns
  - access-control
  - canvas-note
cssclasses:
  - canvas-note
---

# Gatekeeper

> [!note] Overview
> The ==Gatekeeper pattern== interposes a dedicated host between clients and the application, validating and sanitizing all incoming requests before they reach trusted internal components. It ==decouples== public-facing endpoint exposure from internal request processing and data access, reducing the attack surface and limiting the blast radius of a compromised entry point.

## How It Works

**The Gatekeeper pattern** uses a special host to manage requests between clients and the application or service. This middle layer checks and cleans the requests to add extra security and reduce the system's attack surface. It works by using a facade or a special task that talks to the client, then passes the request, often through a ==decoupled interface==, to the parts of the system that will handle it.

In cloud-hosted systems, the gatekeeper role or virtual machine is separated from the trusted parts of the application. Messages can be passed between them using an ==internal endpoint==, a ==queue==, or ==storage==.

<picture>

<picture>

Cloud services allow client applications to access APIs to use storage and other services on behalf of the customer. If a malicious user gets into the hosting environment, they could bypass security and put the whole system at risk. A Gatekeeper helps by first handling the client's request and then passing it on to the trusted hosts through a decoupled interface, adding an extra layer of protection.

## Three Advantages

> [!info] Validation
> The gatekeeper validates all requests, and rejects those that don't meet verification requirements.

> [!info] Limited Risk and Exposure
> The credentials or keys used by the trusted host are not accessible by the gatekeeper. In case of the pattern's compromise, the attacker won't access valuable information.

> [!info] Security
> The gatekeeper is executed in a mode with ==limited privileges==, compared to the rest of the application. It secures the data and services in case of compromise.

## Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Reduces system attack surface | Adds a hop in the request path |
| Isolates credentials from the public-facing layer | Gatekeeper itself can become a bottleneck |
| Enables centralized request validation | Requires maintaining a separate deployment unit |
| Supports decoupled communication via queue/storage | Increased operational complexity |

## When to Use

> [!example] Decision Hints
> - Use when applications handle ==sensitive data== and require strong protection against malicious access.
> - Apply in distributed systems to separate request validation from core business logic.
> - Especially valuable in cloud-hosted systems where the hosting environment can be targeted.
> - Combine with [[Federated Identity]] to separate authentication from request handling.
> - Consider with [[Circuit Breaker]] to stop forwarding when the trusted host is failing.

## Related Notes

- [[Security Patterns]]
- [[Federated Identity]]
- [[Valet Key]]
- [[Isolation]]
