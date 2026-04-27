---
tags:
  - lms-actor
name: Email/SMS Provider
actor_category: External System
role: Notification Delivery Service
key_concerns: Delivery reliability, throughput, latency
system_interface: REST API / SMTP Gateway
communication_channel: Async Event Queue
---
Third-party service that delivers email and SMS notifications triggered by system events (booking changes, course edits, supplier updates).
