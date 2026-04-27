---
title: Guaranteed Delivery
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

# Guaranteed Delivery

> [!note] Overview
> ==Guaranteed Delivery== is a messaging pattern that prevents message loss by persisting each message in a local data store before transmission. A message is only considered sent once safely saved in the sender's storage, and it remains there until the receiver successfully acknowledges it — surviving network failures and system crashes.

## How It Works

Guaranteed Delivery works by using a ==built-in data store== in the messaging system. Each computer running the messaging system keeps its own local storage. A message is only considered sent once it has been safely saved in the sender's data store.

The message stays saved — usually on disk — on at least one machine until the receiver successfully receives and confirms it. This pattern helps prevent data loss, even in ==network failures or system crashes==.

## Two Key Scenarios

### High-Traffic Scenarios

> [!warning] Disk Space Trade-off
> In high-traffic scenarios, Guaranteed Delivery can lead to substantial ==disk space consumption==. Extended network outages may result in a significant buildup of messages on the local disk drive of the producing computer. Some messaging systems allow configuring a **retry timeout parameter** to manage the buffering duration of messages inside the system.

### Testing and Debugging

> [!tip] Disable During Testing
> During testing and debugging, turning off Guaranteed Delivery can be beneficial. Disabling Guaranteed Delivery simplifies debugging by preventing queued messages from complicating the process, especially in asynchronous, guaranteed messaging scenarios. Commercial messaging implementations often provide options to **purge queues** individually for a clean restart during testing.

## Performance vs. Reliability Trade-off

This strong level of message persistence comes with a ==performance cost==. Saving each message to disk can slow down the system.

> [!example] Decision Point
> If your application can tolerate losing some messages during a system crash or shutdown, it might be better to choose a faster messaging option without Guaranteed Delivery. This allows for higher **message throughput**, which may be more important in certain use cases.

## Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Prevents message loss on system crash | Disk I/O adds latency per message |
| Survives network failures | Can accumulate large message backlogs |
| Configurable retry timeout | Increased disk space consumption |
| Pairs well with async messaging | Must be disabled/managed during testing |

## Related Notes

- [[Integration Patterns]]
- [[Messaging Gateway]]
- [[Request-Reply]]
- [[Aggregator - Strategies for Measuring Completeness]]
