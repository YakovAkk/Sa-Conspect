---
title: REST Architectural Style
date: 2026-04-20
tags:
  - module5
  - rest
  - architecture
  - canvas-note
cssclasses:
  - canvas-note
---

# REST Architectural Style

> [!note] Overview
> ==Representational State Transfer (REST)== is a software architecture style that helps systems communicate with each other. It sets rules for building web services and is widely used in web development. REST-based systems are **stateless**, meaning each request is handled independently, separating the roles of the client and the server.

## How It Works

When a client requests a resource, it sends an ==HTTP request==, and the server replies with an ==HTTP response== that contains data about the resource. These REST messages are **self-descriptive** and include all the information needed to understand and handle them.

Instead of setting strict rules, REST offers high-level design guidelines, giving developers flexibility in building systems. To be considered truly RESTful, an API should follow **six architectural constraints**.

## Core Components

> [!info] Three Building Blocks
> - **The Application** — presented as an Application Data Model; contains a dynamic state accessed by API code; lists entities and their relationships
> - **The API** — accesses application state via the application interface; the RESTful resource model adapts the application data model to suit RESTful API entities
> - **The Client** — acquires the RESTful API through standard HTTP protocol and its libraries; supports many target platforms and languages

## Key Characteristics

| Property | Description |
|---|---|
| ==Stateless== | Each request is self-contained; no session or history on the server |
| ==Self-descriptive== | Messages carry all info needed to process them |
| ==Client-Server== | Clear separation of concerns; each side evolves independently |
| ==Flexible== | High-level guidelines, not strict rules |

## Related Notes

- [[REST Formal Constraints]]
- [[HTTP Methods]]
- [[Richardson Maturity Model]]
- [[Hypermedia as the Engine of Application State]]
