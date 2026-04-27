---
title: Integration Patterns
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

# Integration Patterns

> [!note] Overview
> ==Integration patterns== are standardized, technology-agnostic solutions for connecting and coordinating software systems, services, and components. First catalogued by Gregor Hohpe and Bobby Woolf in *Enterprise Integration Patterns* (65 patterns total), they emerge from real-world experience and give architects accepted answers to recurring messaging and integration challenges.

## What is Integration?

==Integration== helps make components flexible and easy to deploy across a business. It ensures that different system parts can be easily connected, accessed, and used by different teams or systems. In solution architecture, integration patterns are standard methods used to connect and manage other systems, services, or components. Common integration styles include ==File Transfer==, ==Shared Database==, ==Remote Procedure Invocation==, and ==Messaging==.

![[Integration Patterns diagram]]

## Six Key Messaging Patterns

| Pattern | Question | Solution |
|---|---|---|
| ==Messaging Gateway== | How to encapsulate access to the messaging system? | A class wrapping messaging-specific calls behind domain-specific methods |
| ==Request-Reply== | How to get a response from the receiver? | Send a pair of Request-Reply messages, each on its own channel |
| ==Guaranteed Delivery== | How to ensure delivery even if the system fails? | Persist messages in a data store until the receiver confirms receipt |
| ==Aggregator== | How to combine related messages processed as a whole? | Stateful filter collecting messages until a complete set is received |
| ==Content Enricher== | How to communicate when the message lacks required data? | Specialized transformer augmenting messages from an external data source |
| ==Message History== | How to analyze and debug flow in a loosely coupled system? | Attach a list of all components the message has passed through |

> [!info] Technology-Agnostic
> Integration Patterns provide a shared vocabulary to describe, build, and improve integration solutions regardless of the tools or platforms used. They are not invented — they come from real-world use and give helpful design advice that works across different technologies.

### Messaging Gateway
**Question**: How do you encapsulate access to the messaging system from the rest of the application?
**Solution**: Use a Messaging Gateway, a class that wraps messaging-specific method calls and exposes domain-specific methods to the application.

![[Messaging Gateway diagram]]

### Request-Reply
**Question**: When an application sends a message, how can it get a response from the receiver?
**Solution**: Send a pair of Request-Reply messages, each on its channel.

![[Request-Reply overview diagram]]

### Guaranteed Delivery
**Question**: How can the sender ensure a message will be delivered, even if the messaging system fails?
**Solution**: Use Guaranteed Delivery to make messages persistent so that they are not lost even if the messaging system crashes.

![[Guaranteed Delivery overview diagram]]

### Aggregator
**Question**: How do we combine the results of individual but related messages to be processed as a whole?
**Solution**: Use a stateful filter, an Aggregator, to collect and store individual messages until a complete set of related messages has been received. Then, the Aggregator publishes a single message distilled from the individual messages.

![[Aggregator overview diagram]]

### Content Enricher
**Question**: How do we communicate with another system if the message originator does not have all the required data items?
**Solution**: Use a specialized transformer, a Content Enricher, to access an external data source to augment a message with missing information.

![[Content Enricher overview diagram]]

### Message History
**Question**: How can we effectively analyze and debug the flow of messages in a loosely coupled system?
**Solution**: Attach a Message History to the message. The Message History lists all applications the message has passed through since its origination.

![[Message History overview diagram]]

## Related Notes

- [[Messaging Gateway]]
- [[Request-Reply]]
- [[Guaranteed Delivery]]
- [[Aggregator - Strategies for Measuring Completeness]]
- [[Content Enricher]]
- [[Messaging History]]
