---
title: Event Sourcing
date: 2026-04-20
tags:
  - module5
  - event-sourcing
  - patterns
  - canvas-note
cssclasses:
  - canvas-note
---

# Event Sourcing

> [!note] Overview
> ==Event Sourcing== stores all changes to application data as a sequence of ==immutable events== in an append-only log. Rather than persisting current state directly, the system records what happened; the current state is always derived by replaying the event history. This model provides auditability, extensibility, and natural alignment with event-driven architectures.

## How Event Sourcing Works

The Event Sourcing pattern stores changes to data as a sequence of events in an ==append-only log==. Each event shows what changed in the system. The application sends events in the order they happened, describing each action taken on the data. These event logs can be used to rebuild past states and adjust them later if needed.

![[Pasted image 20260420190351.png]]
## Key Characteristics

### Immutability of Events

Events within the Event Sourcing pattern are ==immutable==. Once an event is generated, its state cannot be altered. This immutability ensures a reliable and unchangeable record of actions.

### Simple Object Representation

Events are simple objects that ==encapsulate information about a specific action== within the system. They serve as concise representations of events, making them easy to understand and work with.

### Meaningful to Domain Experts

Events are designed to carry meaning for ==domain experts==. They encapsulate business-specific actions, providing a clear and understandable representation of the events that have transpired in the system.

### Audit Trail

> [!info] Built-in Auditability
> Event Sourcing inherently provides an ==audit trail== of all actions performed within the system. This audit trail, composed of immutable events, offers a chronological record of changes, which can be invaluable for tracking system behavior and debugging.

### Easy Extensibility and Integration

The event-driven nature of Event Sourcing lends itself to easy ==extensibility and integration== with other services or listeners. New functionalities or services can be seamlessly added by reacting to the system-generated events.

## Event Sourcing Example

The illustration below gives an overview of the Event Sourcing pattern. It shows how the event stream can be used in different ways—for example, to create a ==materialized view==, connect with external systems, or replay events to rebuild the current state of a specific part of the system.

![[Event Sourcing example]]

## Characteristics Summary

| Characteristic | Description |
|---|---|
| Immutability | Events cannot be changed after creation |
| Simple Objects | Events are small, focused data objects |
| Domain Meaningful | Events represent business actions |
| Audit Trail | Full chronological history of all changes |
| Easy Extensibility | New consumers attach to the event stream |

Because it uses unchangeable (immutable) events, and focuses on simplicity, clear domain logic, auditability, and easy extension, Event Sourcing is a strong and effective pattern for improving performance and scalability in modern systems.

## Related Notes

- [[Performance and Scalability Patterns]]
- [[CQRS Requirements]]
- [[Event Sourcing Use Cases]]
