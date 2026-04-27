---
title: Aggregator - Strategies for Measuring Completeness
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

# Aggregator: Strategies for Measuring Completeness

> [!note] Overview
> The ==Aggregator== is a stateful messaging filter that listens to a stream of messages, groups related ones together, and once a complete set is received, combines their data into a single consolidated message. The key design decision is choosing the right ==completeness strategy== — how the aggregator knows when it has received everything it needs.

## What is the Aggregator?

**The Aggregator** is a special type of filter used in messaging systems. It listens to a stream of messages and groups related ones together. Once it receives a complete set of messages, the Aggregator combines their data into a single, consolidated message, which it then sends to the next step for processing.

Different strategies are used to decide when the Aggregator has received all the necessary messages. These strategies depend on whether the system knows how many messages to expect in advance.

## Eight Completeness Strategies

### Wait for All
Wait until all responses are received, raising an error if not all items are received within a specified timeout. This method provides a comprehensive basis for decision-making but may be slower and more brittle.

### Time Out
Wait for a designated response time and decide based on received responses within that timeframe. It is useful for scenarios where incoming responses are scored, and only the message with the highest score is considered.

### First Best
Wait only until the first (fastest) response is received, disregarding all subsequent responses. This approach is the fastest but sacrifices information and is suitable for critical-response time scenarios.

### Time Out with Override
Wait for a specified time or until a message with a preset minimum score is received. It allows for early abortion if a highly favorable response is obtained; otherwise, ranking among received messages occurs when the time limit is reached.

### External Event
Conclude aggregation upon the arrival of an external business event, such as the financial industry's end of the trading day. The aggregator listens for an Event Message or receives a specially formatted message indicating the end of aggregation.

### Select the "Best" Answer
Assume a single best answer and decide, passing only the "best" message. In real-life scenarios, selection criteria are often more complex, considering factors like delivery time, available items, vendor preferences, etc.

### Condense Data
Reduce message traffic from a high-traffic source by computing averages or adding numeric fields from individual messages into a single message. Effective when each message represents a numeric value, such as the number of orders received.

### Collect Data for Later Evaluation
When the aggregator can't immediately decide on the best answer, it collects individual messages into a single message, which may serve as a compilation of the individual message data. The decision may be deferred to a separate component.

## Strategy Comparison

| Strategy | When to Use | Trade-off |
|---|---|---|
| Wait for All | Need all data for complete picture | Slow, brittle if any response is lost |
| Time Out | Scoring-based selection within a window | May miss late high-value responses |
| First Best | Speed is the highest priority | Sacrifices completeness |
| Time Out with Override | Combine time limit with quality threshold | More complex logic |
| External Event | Business-event driven completion | Depends on reliable external trigger |
| Select Best Answer | Only the best result matters | Selection criteria complexity |
| Condense Data | High-volume numeric aggregation | Loses individual message detail |
| Collect for Later | Deferred or complex decision-making | Decision latency |

> [!info] Maximum Wait Time
> Aggregation strategies often include a ==maximum wait time==, which controls how long the system should wait for all related messages to arrive.

## Example: Loan Broker System

> [!example] Loan Quote Aggregation
> In a loan broker system, an Aggregator can collect loan quotes from different banks. It waits until all the replies are received, then picks the best one. In this case, a ==Recipient List== can help the Aggregator by telling it how many quote messages to expect. This way, the Aggregator knows when it has all the needed information and can send out the best offer.

## Related Notes

- [[Integration Patterns]]
- [[Guaranteed Delivery]]
- [[Content Enricher]]
- [[Messaging History]]
