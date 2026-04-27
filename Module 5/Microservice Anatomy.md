---
title: "Microservice Anatomy"
date: 2026-04-13
tags:
  - module5
  - architecture
  - microservices
  - canvas-note
aliases:
  - Microservice Structure
  - Anatomy of a Microservice
cssclasses:
  - canvas-note
---

# Microservice Anatomy

> [!note] Overview
> The ==anatomy of a microservice system== brings together independent parts to perform a specific task. Each part works within a framework that helps create a fully functioning network. In microservices architecture, requests usually follow a **standard flow** across different types of services.

## Architecture Diagram
![[Pasted image 20260413134045.png]]

## Request Flow

Every request starts at the ==Microservices Endpoint== — a specific point where users or systems interact with the service. The system is composed of many separate, loosely connected software components (microservices) that can be **deployed independently**.

From the endpoint, each request passes through a layered structure:

```
Microservices Endpoint
        ↓
Presentation Layer
        ↓
Business Logic Layer (BLL)
        ↓
Data Access Layer (DAL)
```
![[Pasted image 20260413134053.png]]

## Layers

### Presentation Layer

> [!info] Presentation Layer
> The ==Presentation Layer== acts as a **translator** between the User Interface (UI) and the Domain layer.
> - Transforms **user input** into business function calls.
> - Presents the **results** in a user-friendly view.
> - Can only access the layer directly below it (Business Logic Layer).

### Business Logic Layer (BLL)

> [!info] Business Logic Layer
> The ==Business Logic Layer (BLL)== is the **middle layer** of the application.
> - Contains the **business rules** and processes requests from the API.
> - Interacts with the Data Access Layer (DAL) to apply rules and work with data.
> - Acts as the decision-making core of the microservice.

### Data Access Layer (DAL)

> [!info] Data Access Layer
> The ==Data Access Layer (DAL)== is the **innermost layer** of the application.
> - Interacts directly with the **database** or other data storage systems.
> - Responsible for **retrieving** and **storing** data.
> - Shields the business layer from database implementation details.

### Integration Logic Layer

> [!info] Integration Logic Layer
> The ==Integration Logic Layer== **orchestrates and transforms** the output of multiple services.
> - Sits between microservices when combining their results.
> - Handles the aggregation, routing, or transformation of data flowing between services.

## Layer Summary

| Layer | Position | Responsibility |
|---|---|---|
| Presentation | Outermost | Translate UI input ↔ domain calls |
| Business Logic (BLL) | Middle | Apply business rules, process API requests |
| Data Access (DAL) | Innermost | Read/write data to storage |
| Integration Logic | Cross-service | Orchestrate and transform multi-service output |

## Benefits of This Structure

> [!tip] Why the Anatomy Matters
> These components work together to create a smooth request flow. Each layer has a **clear, single responsibility**, which:
> - Makes individual microservices **easier to build, test, and update**.
> - Makes it **easier to connect** one service with others.
> - Improves **cost efficiency, flexibility, and performance** by allowing separate modules to be developed and scaled independently.

## Summary

The layered anatomy of a microservice — from the endpoint through the presentation, business logic, data access, and integration layers — mirrors the broader layered architecture principle but scoped to a **single, independently deployable unit**. This clear internal structure is what allows many microservices to function together as a coherent system while remaining loosely coupled and individually maintainable.

## Related Notes

- [[Microservice Architecture]]
- [[Characteristics of Microservices Architecture]]
- [[Layered Architecture]]
- [[Architectural Style - Monolith, Layered and Microservices]]