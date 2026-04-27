---
title: HTTP Methods
date: 2026-04-20
tags:
  - module5
  - rest
  - http
  - canvas-note
cssclasses:
  - canvas-note
---

# HTTP Methods

> [!note] Overview
> ==HTTP methods== tell the server what action the client wants to perform on a resource. Without an HTTP method, a REST API request cannot be made. The most common methods — GET, POST, PUT, DELETE — map to the basic ==CRUD== operations (Create, Read, Update, Delete).

## GET

The ==GET method== retrieves data from a server. Clients may use it to access resources such as web pages, videos, images, JSON documents, XML, CSS, and JAVA files. The request is considered **safe** — no changes will be made to the state of the resources on the server.

## POST

The ==POST method== creates new resources. For example, if a manager intends to add a new product to the database, they would send a POST request to the endpoint. This operation is **not safe** — it has the power to change the server's state, causing side effects.

## PUT

The ==PUT method== replaces an existing resource with an updated version. It restores the entire resource with the data in the request body. It is preferred to send the payload in XML or JSON format. The operation is **not safe** as it changes the state of the server.

## DELETE

The ==DELETE method== removes data from a database. When a client sends a request, it implies the removal of the resource at the specified URL. The operation is **unsafe** and ==idempotent== — meaning the same request transmitted multiple times produces the same result without further state change.

## Comparison

| Method | CRUD | Safe? | Idempotent? |
|---|---|---|---|
| GET | Read | ✅ Yes | ✅ Yes |
| POST | Create | ❌ No | ❌ No |
| PUT | Update | ❌ No | ✅ Yes |
| DELETE | Delete | ❌ No | ✅ Yes |

> [!tip] Design Guideline
> REST guidelines recommend using specific HTTP methods for different server actions. Following these rules keeps the API design clear, consistent, and effective.

## Related Notes

- [[REST Architectural Style]]
- [[REST Formal Constraints]]
- [[Richardson Maturity Model]]
