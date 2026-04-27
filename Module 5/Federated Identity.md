---
title: Federated Identity
date: 2026-04-20
tags:
  - module5
  - security
  - patterns
  - authentication
  - canvas-note
cssclasses:
  - canvas-note
---

# Federated Identity

> [!note] Overview
> The ==Federated Identity== security pattern delegates user authentication to a trusted external identity provider rather than the application itself. It eliminates disjointed user experiences across systems, reduces security vulnerabilities from co-located auth code, and simplifies user management — particularly in ==Single Sign-On (SSO)== and multi-partner scenarios.

## How It Works

**The Federated Identity** security pattern helps solve system security issues and reduce risks by handing over user authentication to an external identity provider. It is useful when an application needs SSO or must authenticate users from multiple partners — common in SaaS applications.

<picture>

## Three Usage Scenarios

### Single Sign-On

**Scenario**: Authenticate employees for cloud-based applications outside the corporate security boundary.
**Use**: Users experience SSO, eliminating the need for repeated sign-ins across applications after initial authentication.

### Multiple Partners

**Scenario**: Authenticate both corporate employees and business partners without corporate directory accounts.
**Use**: Common in ==business-to-business applications==, third-party service integrations, and situations involving merged or shared resources.

### SaaS Applications

**Scenario**: Authenticate tenants in SaaS applications provided by independent software vendors.
**Use**: Tenants use a suitable identity provider for authentication, such as corporate or social identity credentials.

## Microsoft Azure Example

**[Microsoft Azure](https://azure.microsoft.com/en-us/)** hosts a multi-tenant SaaS application where tenants log in using a federated identity created by Active Directory Federation Services (ADFS).

The authentication flow:

<picture>

- **Token Request to ADFS** — Tenants authenticate with their identity provider (ADFS). After successful authentication, ADFS issues a token.
- **Token Request to Federation Provider** — The client browser forwards the token to the SaaS application's federation provider, which trusts tokens from the tenant's ADFS and returns a valid token for the SaaS federation provider.
- **Transformation Claims** — If necessary, the SaaS federation provider transforms the token's claims into claims that the application recognizes before returning the new token to the client browser.
- **Authorisation through SaaS Application** — The application trusts tokens issued by the SaaS federation provider and uses the token claims to apply authorization rules.

Tenants do not need to remember separate login details. An administrator at the tenant's company can manage and set the list of users who can access the application through their own ADFS.

## Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Enables SSO across multiple applications | Requires trust configuration with each identity provider |
| Removes authentication code from the application | Depends on availability of external identity providers |
| Simplifies user management at scale | More complex initial setup in multi-partner scenarios |
| Supports corporate, social, and third-party credentials | Not worth the overhead when only one provider is needed |

## When to Use

> [!example] Decision Hints
> - Use when users must authenticate across ==multiple applications from different organizations==.
> - Use for enterprise SSO, business-to-business integrations, or SaaS multi-tenant systems.
> - Avoid when only one identity provider is needed and no external connections are required.
> - Preferred for systems accessed via VPN or cloud-hosted apps connecting to on-premises directories.

## Related Notes

- [[Security Patterns]]
- [[Gatekeeper]]
- [[Valet Key]]
