---
title: Security Patterns
date: 2026-04-20
tags:
  - module5
  - security
  - patterns
  - canvas-note
cssclasses:
  - canvas-note
---

# Security Patterns

> [!note] Overview
> ==Security patterns== are tried-and-tested solutions to common security problems. They offer reusable methods to help design safe and reliable systems, guiding developers in protecting sensitive data, controlling secure access, and reducing security risks. Three key patterns — Federated Identity, Gatekeeper, and Valet Key — together address authentication delegation, request validation, and time-limited resource access.

## Patterns at a Glance

| Pattern | Context / Risk | Intention | Solution |
|---|---|---|---|
| ==Federated Identity== | Users work across multiple applications from different organizations | Eliminate disjointed UX; minimize vulnerabilities; simplify user management | Delegate authentication to a trusted external identity provider |
| ==Gatekeeper== | Authentication and business logic co-located — exposes attack surface | Minimize risk of clients accessing sensitive data through a compromised environment | Decouple public-facing hosts from internal processing; introduce controlled validation |
| ==Valet Key== | Direct data transfer routes through the application, adding overhead and risk | Minimize transfer costs and scaling needs; maximize performance | Provide time-limited, scope-limited tokens clients use to access resources directly |

## Federated Identity

==Federated Identity== solves system security issues by handing user authentication to an external identity provider. Particularly useful when an application needs ==Single Sign-On (SSO)== or must authenticate users from multiple partners, as commonly seen in SaaS applications.

**Main uses**: SSO in businesses, federated identity with multiple partners, federated identity in SaaS applications.

> [!tip] When Not to Use
> Not recommended when only one identity provider is needed and there is no requirement to connect with others. Better suited for business applications using a corporate directory, VPN-accessed systems, or cloud-hosted setups connecting to on-premises directories.

## Gatekeeper

==The Gatekeeper pattern== uses a dedicated host to manage requests between clients and the application. The middle layer checks and sanitizes requests, reducing the system's attack surface. In cloud-hosted systems, the gatekeeper role or VM is separated from trusted application components; messages pass between them via an internal endpoint, a queue, or storage.

**Key advantages**:
- **Validation** — Validates all requests; rejects those that fail verification
- **Limited Risk and Exposure** — Credentials/keys of the trusted host are inaccessible to the gatekeeper; compromise doesn't expose valuable information
- **Security** — Runs with limited privileges; secures data and services in case of compromise

## Valet Key

==A Valet Key== is a token granting ==temporary, scope-limited access== to specific resources. The client receives the token at runtime and uses it for a set period with predefined operation limits (read, write, upload, download). The token expires automatically and cannot be reused.

**Key benefit**: Eliminates user provisioning overhead — no need to create, grant permissions to, and later remove a user. The token handles everything inline, at runtime.

> [!warning] Limitations
> Not suitable for simple data transformation before storage. Does not support audit tracking notifications, access frequency controls, or data volume limits — which can cause problems during large upload operations.

## Related Notes

- [[Federated Identity]]
- [[Gatekeeper]]
- [[Valet Key]]
- [[Fault Tolerance Patterns]]
