---
tags:
  - lms-workflow
name: Admin Approves Booking
workflow_name: Course Booking
step: 5
actor: Administrator
action: Change request status to Approved if no objections
status_before: Under Review
status_after: Approved
notification: User notified (Email/SMS) — booking approved
---
