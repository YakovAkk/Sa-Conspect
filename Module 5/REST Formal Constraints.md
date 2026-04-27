---
title: REST Formal Constraints
date: 2026-04-20
tags:
  - module5
  - rest
  - constraints
  - canvas-note
cssclasses:
  - canvas-note
---

# REST Formal Constraints

> [!note] Overview
> To build an actual RESTful API, a web service must follow ==six formal constraints==. These rules ensure the system is well-structured, easy to manage, and scalable. They represent the system's core features.

## 1. Client-Server

A ==clear separation== is maintained between clients and servers, allowing them to evolve independently without dependencies on each other. This decoupling ensures seamless replacement of either side. Clients focus solely on resource URIs, while servers are oblivious to the client's interface.

## 2. Stateless

The ==stateless constraint== means the server does not store data about the client's previous HTTP requests. Each request is treated in isolation without sessions or history. All vital information for servicing requests must be included in each request. After handling the request, the server may alter its state and respond with the appropriate HTTP status code.

## 3. Cacheable

==Caching== enhances client-side performance and server scalability by reducing load. Resources in REST are designated as cacheable when applicable. The goal is to avoid generating the same response repeatedly. Requests traverse a cache in front of the service — if criteria are met the data is returned from cache; otherwise the request proceeds to the server.

## 4. Layered System

REST encourages a ==layered system architecture== where APIs, data storage, and authentication are deployed on separate servers. Clients are unaware whether they are connected to the end server or an intermediary. Scaling services can involve proxies as load balancers to direct requests to the appropriate server instance.

## 5. Code on Demand *(Optional)*

The only ==optional constraint==. Allows servers to enhance REST clients by sending executable code, typically in XML or JSON format. This permits the server to add functionality to the client, improving scalability as the code executes independently on the client side.

## 6. Uniform Interface

The ==Uniform Interface== establishes a contract between clients and servers, requiring each resource to have a logical URI. Resources should include links to corresponding URIs for related information. Once a contract is established, clients and servers can work independently based on the agreed-upon interface.

## Constraints at a Glance

| Constraint | Core Idea | Optional? |
|---|---|---|
| Client-Server | Separation of concerns | No |
| Stateless | No session stored on server | No |
| Cacheable | Responses declare cacheability | No |
| Layered System | Intermediaries transparent to client | No |
| Code on Demand | Server sends executable code | **Yes** |
| Uniform Interface | Logical URIs + standard contract | No |

## Related Notes

- [[REST Architectural Style]]
- [[HTTP Methods]]
- [[Richardson Maturity Model]]
