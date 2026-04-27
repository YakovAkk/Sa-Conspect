---
title: Stateful vs Stateless
date: 2026-04-07
tags:
  - module5
  - architecture
  - state-management
  - canvas-note
aliases:
  - Stateful and Stateless
cssclasses:
  - canvas-note
---

# Stateful vs Stateless

State is the information that tracks an application's current context, and when stored separately (for example in a shared database), systems can scale reliably because servers can be added or removed without losing context.

Stateful systems keep client context on specific servers (often with sticky sessions), while stateless systems treat each request independently and enable more flexible load balancing and horizontal scaling.
