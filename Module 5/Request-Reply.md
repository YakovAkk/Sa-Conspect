---
title: Request-Reply
date: 2026-04-20
tags:
  - module5
  - integration
  - patterns
  - messaging
  - canvas-note
cssclasses:
  - canvas-note
---

# Request-Reply

> [!note] Overview
> The ==Request-Reply== pattern enables two-way communication in messaging systems by managing a pair of messages — one for the request and one for the reply — each traveling on its own dedicated channel. In messaging systems, communication is normally one-way; this pattern adds the interactive exchange required when the sender needs a response.

## How It Works

When an application needs a response after sending a message, the Request-Reply integration pattern is used. This pattern supports two-way communication by managing two messages: one for the request and one for the reply. Each message travels on its channel.

![[Request-Reply diagram]]

## Four Participants

> [!info] Participants
> - **==Requestor==** — Initiates the interaction by sending a request message and awaits a corresponding reply.
> - **==Replier==** — Responds to the received request message with an appropriate reply.
> - **==Request Channel==** — Carries the initial request message. Can be Point-to-Point or Publish-Subscribe depending on whether the request needs broad dissemination or is intended for a single consumer.
> - **==Reply Channel==** — Typically Point-to-Point; ensures that responses are directed specifically to the originating requestor.

## Channel Types

| Channel | Type | When to Use |
|---|---|---|
| Request Channel | Point-to-Point | Single consumer |
| Request Channel | Publish-Subscribe | Broad dissemination needed |
| Reply Channel | Point-to-Point | Always — reply must reach original sender |

## SOAP Integration

> [!example] SOAP Use Case
> The Request-Reply pattern is commonly used in ==SOAP (Simple Object Access Protocol)== messaging. A SOAP request message tells the receiver which service the sender wants to use, and the SOAP response message returns the result of that service. The response can include either a result or a **fault**, similar to an exception in programming. This makes Request-Reply a natural fit for SOAP, where the request and the reply are clearly defined.

## Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Enables interactive, two-way exchanges | Adds latency compared to fire-and-forget |
| Natural fit for SOAP and RPC-style APIs | Requestor blocks (if synchronous) while awaiting reply |
| Clear contract between requestor and replier | Requires managing two channels and correlation |
| Supports both sync and async modes | Reply channel management adds complexity |

## Related Notes

- [[Integration Patterns]]
- [[Messaging Gateway]]
- [[Guaranteed Delivery]]
