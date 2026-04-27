---
title: Richardson Maturity Model
date: 2026-04-20
tags:
  - module5
  - rest
  - maturity
  - canvas-note
cssclasses:
  - canvas-note
---

# Richardson Maturity Model

> [!note] Overview
> The ==Richardson Maturity Model== is a framework used to measure how closely a web service follows REST principles. Created by **Leonard Richardson**, it divides web service designs into four levels based on how well they apply REST ideas. The model focuses on three main areas: ==URLs==, ==HTTP methods==, and ==hypermedia==.

## 
Level 0 — POX Swamp

> [!warning] Least RESTful
> ==POX== stands for Plain Old XML. This level indicates the service is the least conforming to REST. It exposes **only one URL** for the entire application and uses **HTTP POST for all actions**, including data fetch.

![[Pasted image 20260420184114.png]]
## Level 1 — Resources

The services employ **multiple URLs**. However, they only use POST for all operations. Each resource has its own unique URL. This ==resource-based addressing== can be considered the starting point for RESTful APIs.

## Level 2 — HTTP Verbs

APIs at this level use **all HTTP commands** — GET, POST, PUT, and DELETE. The request body doesn't carry the operation information. ==Return codes are properly used== so that clients can check for errors.

## Level 3 — Hypermedia Controls

> [!example] Most Mature
> The most mature level utilizes ==HATEOAS== (Hypertext As The Engine Of the Application State), also known as HyperMedia, which consists of resource links and forms. Connections between resources are established automatically, aiding client-driven automation.

## Levels at a Glance

| Level | Name | URLs | HTTP Verbs | Hypermedia |
|---|---|---|---|---|
| 0 | POX Swamp | Single | POST only | ❌ |
| 1 | Resources | Multiple | POST only | ❌ |
| 2 | HTTP Verbs | Multiple | All verbs | ❌ |
| 3 | Hypermedia Controls | Multiple | All verbs | ✅ HATEOAS |

## Related Notes

- [[REST Architectural Style]]
- [[REST Formal Constraints]]
- [[HTTP Methods]]
- [[Hypermedia as the Engine of Application State]]
