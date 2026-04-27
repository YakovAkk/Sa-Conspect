---
tags:
  - lms-workflow
name: Auto-Accept or Reject
workflow_name: Course Booking
step: 3
actor: BookingService (System)
action: Auto-accept valid requests; reject invalid ones with reason
status_before: Under Validation
status_after: Accepted / Rejected
notification: User notified (Email/SMS) of outcome
---
