---
title: "Actor-Based Architecture"
date: 2026-04-13
tags:
  - module5
  - architecture
  - actor-model
  - canvas-note
aliases:
  - Actor Model
  - Actor Architecture
cssclasses:
  - canvas-note
---

# Actor-Based Architecture

> [!note] Overview
> The ==Actor model== is based on the idea that **everything is an actor**. An actor is a small, independent unit that can:
> - **Send messages** to other actors.
> - **Create new actors**.
> - **Decide how to handle** the next message it receives.
>
> These actions can happen **simultaneously** and do not need to follow a specific order.

## Architecture Diagram

![[Pasted image 20260413143202.png]]

## How Actors Work

### Asynchronous Messaging

> [!info] Sender-Communication Separation
> A key benefit of the Actor model is that it **separates the sender from the communication process**, allowing messages to be sent ==asynchronously==.
> - Actors **continue working** without waiting for a response.
> - This eliminates blocking and allows the system to remain responsive under load.

### Mailbox and Scheduling

> [!info] Mailbox Queue
> When an actor receives a message, it adds it to a **mailbox (queue)**:
> 1. If the actor is not already running → it becomes **ready**.
> 2. A **scheduler** picks it up and runs it.
> 3. The actor processes its messages **one by one** (sequential within a single actor).
>
> Many actors can run **at the same time**, but each one handles its own messages individually — this avoids shared-state concurrency issues without locking.

### Location Transparency

> [!tip] Local or Remote — Same Behavior
> Whether an actor is **local** (same machine) or **remote** (different node in the network), its behavior stays the same. This ==location transparency== makes the Actor model a natural fit for **distributed systems**.

## Real-World Example: Halo 4

The Actor model is used in **Halo 4**. The development team built two main services using this architecture:
![[Pasted image 20260413143215.png]]

### Presence Service

> [!info] Presence Service
> **Presence** defines the attendance (status) of a player in the game.
>
> Flow:
> 1. A **Router actor** sends a heartbeat message with game updates to the service.
> 2. The Router **decompresses** the message and retrieves the **Session ID** and **Player ID**.
> 3. It sends the information to the correct **game session actor**.
> 4. The game session actor **saves the update** of the game's current state.

### Statistics Service

> [!info] Statistics Service
> **Statistics** collects stats for every player who has ever played the game.
>
> Flow:
> 1. The **game session actor** saves post-game statistics to the **Azure Blob Store**.
> 2. Relevant pieces are sent to the **player actor**.
> 3. The **player actor** processes the data and stores the final state in the **Azure Table Store**.
> 4. Statistics can also be read by querying the Table Store directly.

## Key Characteristics

| Characteristic | Description |
|---|---|
| **Everything is an actor** | All computation units are modeled as actors |
| **Asynchronous messaging** | Actors communicate without blocking |
| **Mailbox (queue)** | Incoming messages are queued and processed one at a time |
| **No shared state** | Actors do not share memory; they only communicate via messages |
| **Concurrency by default** | Many actors run simultaneously without locks |
| **Location transparency** | Local and remote actors behave identically |
| **Dynamic topology** | Actors can create other actors at runtime |

## Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Natural concurrency — no locks needed | Actor systems can be harder to reason about |
| Fault isolation — a failing actor does not crash others | Debugging asynchronous message flows is complex |
| Scales across machines (location transparency) | Message ordering not guaranteed across actors |
| Loose coupling via messages | Increased overhead for simple sequential tasks |
| Composable — actors can create sub-actors | Requires actor-aware frameworks (Akka, Orleans, etc.) |

## When to Use Actor-Based Architecture

> [!example] Good Fit
> - **Highly concurrent systems** — simulations, games, IoT event processing.
> - **Distributed systems** — where location transparency simplifies cross-node communication.
> - **Systems with many independent entities** — players in a game, users in a chat, devices in a network.
> - **Fault-tolerant designs** — actor supervision trees allow automatic recovery from failures.

## Summary

The Actor model provides a powerful abstraction for building concurrent, distributed, and fault-tolerant systems by treating every unit of computation as an independent actor that communicates only through messages. Its mailbox queue, asynchronous processing, and location transparency eliminate the need for explicit locking and make it well-suited to real-world systems like Halo 4's presence and statistics services. The main trade-offs are increased complexity in reasoning about message flows and the need for actor-aware infrastructure.

## Related Notes

- [[Event-Driven Architecture]]
- [[Microservice Architecture]]
- [[Architectural Style - Monolith, Layered and Microservices]]
- [[Stateful vs Stateless]]