---
title: Hypermedia as the Engine of Application State
date: 2026-04-20
tags:
  - module5
  - rest
  - hateoas
  - canvas-note
cssclasses:
  - canvas-note
---

# Hypermedia as the Engine of Application State

> [!note] Overview
> ==HATEOAS== (Hypermedia as the Engine of Application State) is a special REST constraint that differentiates REST from other network architecture types. In a REST system, the client starts accessing a fixed, simple URL. What makes HATEOAS unique is that **the server provides all the next possible actions as links inside the response**.

## How It Works

The server guides the client by including ==hypermedia links== in each response. The client does not need to know the whole structure of the API in advance. Instead, it follows the links given by the server to move through the application.

## HATEOAS Example

![[Pasted image 20260420184017.png]]

## Key Benefits

> [!info] Why HATEOAS Matters
> - **Self-explanatory** — APIs explain themselves through response links
> - **No fixed endpoint rules** — clients adjust to system changes without extra documentation
> - **Loosely connected design** — improves scalability and long-term growth
> - **Flexible and explorable** — simpler to maintain and navigate

HATEOAS helps make RESTful APIs self-explanatory. It allows clients to adjust to system changes without needing extra documentation or fixed rules for endpoints. This makes RESTful systems more flexible, easier to explore, and simpler to maintain. It also supports a ==loosely connected design==, which improves scalability and long-term growth.

## Relation to Richardson Maturity Model

> [!example] Level 3
> HATEOAS is the defining feature of **Level 3** in the Richardson Maturity Model — the most mature level of REST compliance.

## Related Notes

- [[REST Architectural Style]]
- [[REST Formal Constraints]]
- [[Richardson Maturity Model]]
