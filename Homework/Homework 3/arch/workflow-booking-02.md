---
tags:
  - lms-workflow
name: Validate Request
workflow_name: Course Booking
step: 2
actor: BookingService (System)
action: Validate request against priority and booking rules
status_before: Proposed
status_after: Under Validation
notification: "-"
---
