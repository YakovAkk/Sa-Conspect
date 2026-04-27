---
title: "Characteristics of Microservices Architecture"
date: 2026-04-13
tags:
  - module5
  - architecture
  - microservices
  - canvas-note
aliases:
  - Microservices Key Features
cssclasses:
  - canvas-note
---

# Characteristics of Microservices Architecture

> [!note] Overview
> Microservices are a modern way to design software by building applications from small, independent, and loosely connected services. Each service focuses on a specific business task and communicates with others through ==clear interfaces==. Together, these nine characteristics define what makes an architecture truly microservice-based.



## 1. Componentization via Services

> [!info] Independent Components
> Applications are ==decomposed into independent components== (services). Each service is modular — it can be developed, deployed, and scaled individually without affecting others.
>
> This component-based approach enhances **flexibility** and **scalability** across the system.

## 2. Organized Around Business Capabilities

> [!info] Business-Oriented Structuring
> Microservices are designed based on **business functionalities**, not organizational structures. Each service corresponds directly to a ==specific business capability== (e.g., payments, user management, notifications).
>
> This keeps services aligned with what the business actually needs, reducing the gap between technical structure and domain logic.

## 3. Products Not Projects

> [!tip] Product Mindset
> Microservices treat software development as an ==ongoing product== rather than a one-time project. The focus shifts to:
> - **Continuous development** over a defined delivery scope.
> - **Sustained business value** delivered in small, frequent increments.
> - Teams own their service long-term — they build it, run it, support it.
>
> This mindset underscores the software's perpetual evolution and ongoing value delivery.

## 4. Smart Endpoints and Dumb Pipes

> [!info] Simple Communication
> Microservices keep ==communication infrastructure simple==. Instead of using a complex intermediary like an Enterprise Service Bus (ESB) to process and route messages, they rely on:
> - **Smart endpoints** — each service contains its own logic and makes its own decisions.
> - **Dumb pipes** — the transport layer (HTTP, message queues) is kept as simple as possible.
>
> Services communicate directly with each other, reducing architectural overhead and single points of failure.

## 5. Decentralized Governance

> [!info] Distributed Responsibility
> Microservices encourage ==decentralized governance==: no central authority dictates which technology, language, or framework each team must use. This gives teams:
> - Flexibility to choose the best tool for their service.
> - Ownership over quality within their domain.
>
> Distributed governance enables adaptability but requires coordination to prevent fragmentation.

## 6. Decentralized Data Management

> [!info] Polyglot Persistence
> Each microservice manages its ==own database==, independently of other services. This approach is known as ==polyglot persistence==:
> - Teams choose the right database technology for their service (relational, document, key-value, graph, etc.).
> - No shared schema — services do not directly access each other's data stores.
> - Independence in data management enables optimization per service.

> [!warning] Trade-off: Distributed Consistency
> Decentralized data makes distributed transactions complex. Coordinating data changes across services typically requires patterns like Saga or eventual consistency instead of ACID transactions.

## 7. Infrastructure Automation

> [!tip] Automated Deployment
> Microservices rely on extensive ==infrastructure automation== for deployment and operations. This includes:
> - **CI/CD pipelines** — automated build, test, and deployment on every change.
> - **Cloud platforms** (e.g., AWS, GCP, Azure) — managed infrastructure reduces operational burden.
> - **Container orchestration** (e.g., Kubernetes) — automates service scheduling, scaling, and health management.
>
> Automation is not optional in microservices — it is what makes managing many services feasible.

## 8. Design for Failure

> [!warning] Assume Failures Will Happen
> Microservices are designed to be ==tolerant of failures==. Since services communicate over a network, partial failures are inevitable. Key practices:
> - **Circuit breakers** — stop calling a failing service and provide a fallback.
> - **Retries with backoff** — handle transient errors without overwhelming a service.
> - **Health checks and monitoring** — detect and respond to failures automatically.
> - **Graceful degradation** — the system continues to function (at reduced capacity) when a service is down.

## 9. Evolutionary Design

> [!tip] Continuous Evolution
> Microservices support an ==evolutionary design approach== — individual components can be changed, replaced, or decomposed further without affecting the entire system.
> - Teams can experiment, refactor, or rewrite a single service independently.
> - The system adapts continuously to changing business requirements.
> - This agility is only possible because services are loosely coupled and independently deployable.

## Summary of Characteristics

| # | Characteristic | Core Idea |
|---|---|---|
| 1 | Componentization via Services | Modular, independently deployable units |
| 2 | Organized Around Business Capabilities | Services mirror business functions |
| 3 | Products Not Projects | Long-term ownership and continuous delivery |
| 4 | Smart Endpoints, Dumb Pipes | Logic in services, not in transport |
| 5 | Decentralized Governance | Teams choose their own tools and are accountable |
| 6 | Decentralized Data Management | Each service owns its own database |
| 7 | Infrastructure Automation | CI/CD and cloud platforms enable scale |
| 8 | Design for Failure | Resilience built in from the start |
| 9 | Evolutionary Design | Change one service without touching the rest |

## Summary

These nine characteristics together define a system that is flexible, scalable, and business-focused. Microservices succeed not because of any single feature, but because these characteristics reinforce each other: decentralized governance enables polyglot persistence; design for failure supports evolutionary change; infrastructure automation makes independent deployment viable at scale. Organizations that embrace all nine tend to build systems that can respond to change, deliver value continuously, and manage complexity more effectively than monolithic alternatives.

## Related Notes

- [[Microservice Architecture]]
- [[Architectural Style - Monolith, Layered and Microservices]]
- [[Coupling and Cohesion]]
- [[Stateful vs Stateless]]
![[Pasted image 20260413133157.png]]