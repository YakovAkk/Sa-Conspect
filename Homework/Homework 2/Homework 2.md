---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠== You can decompress Drawing data with the command palette: 'Decompress current Excalidraw file'. For more info check in plugin settings under 'Saving'


# Excalidraw Data

## Text Elements
# Homework 2

## ASR, utility tree, capability map

**Your tasks are:**

1. Write a capability map.
2. Create a utility tree.
3. Identify Architecture Significant Requirements: ASR, Quality Attribute requirements, Constraints. ^k2DN7hgE

Management Capability
ReportingService ^lwHLLHjT

Learning Capability
CourseService ^8UUteauH

Management ^qvwhRFgX

Production ^vSnxgMWz

Compliance Capability
AuditService ^Ny5nJ5Eu

Add third party courses Capability
UploadingService ^GSqcJY6r

Business analytics Capability
ReportService ^VvsdzkXZ

Non-Production ^bkXeIUSh

| Domain                      | Capability                  | Description (what business can do)              | Service / Component   |
| --------------------------- | --------------------------- | ----------------------------------------------- | --------------------- |
| **User & Access**           | Identity & Authentication   | Authenticate users via SSO                      | AuthService           |
|                             | User Management             | Manage learners and administrators              | UserService           |
|                             | Access Control              | Control roles and permissions                   | AccessControlService  |
| **Course Management**       | Course Management           | Manage lifecycle of courses and workshops       | CourseService         |
|                             | Course Content Management   | Store recordings and course materials           | ContentService        |
|                             | Course Creation & Update    | Create and update courses via UI                | CourseService         |
|                             | Course Prioritization       | Assign priority levels to courses               | CourseService         |
|                             | Course Revalidation         | Revalidate courses after rule changes           | ValidationService     |
| **Booking & Enrollment**    | Course Booking              | Allow users to request course participation     | BookingService        |
|                             | Booking Validation          | Validate requests based on rules and priorities | BookingService        |
|                             | Booking Acceptance          | Automatically accept valid requests             | BookingService        |
|                             | Booking Approval Workflow   | Admin approval and status management            | ApprovalService       |
| **Notifications**           | Notification Management     | Send notifications (email/SMS)                  | NotificationService   |
|                             | Event Notification          | Notify users/admins about changes and statuses  | NotificationService   |
| **Third-Party Integration** | External Course Integration | Integrate vendor-provided courses               | IntegrationService    |
|                             | Supplier Management         | Allow suppliers to manage course offerings      | SupplierService       |
|                             | Supplier Notifications      | Notify suppliers and admins on updates          | NotificationService   |
| **Search & Discovery**      | Course Search               | Search courses based on criteria                | SearchService         |
|                             | Filtering & Querying        | Advanced filtering and criteria-based queries   | SearchService         |
| **Reporting & Analytics**   | Reporting                   | Generate reports for bookings, vendors, usage   | ReportingService      |
|                             | Data Export                 | Download reports                                | ReportingService      |
|                             | Analytics                   | Analyze usage and trends                        | AnalyticsService      |
| **Compliance & Governance** | Audit Trail                 | Track system changes and actions                | AuditService          |
|                             | Compliance Management       | Ensure courses meet regulatory requirements     | ComplianceService     |
| **Operations**          | Monitoring & Observability  | Track system health and performance             | Grafana     |
|                             | Logging                     | Centralized logging                             | Graylog        |
 ^84JlNk61

Perfomance ^2mlPeBzW

Utility ^qtccTlC2

**ASRs:**

## 🔷 1. Security — Authentication

All users must be authenticated via **SSO**
System must enforce **role-based access control (RBAC)** for users, admins, and suppliers

**Architectural impact:**

* integration with identity provider
* token-based auth (OAuth/JWT)
* centralized auth flow
* access control model
* authorization layer
* service boundaries & permissions

---

## 🔷 2. Modifiability — Business Rules (Assumption)

Can update booking validation rules **validation & priority rules without redeploy** (Configuration)

**Architectural impact:**

* rule engine / configuration-driven logic
* separation of business rules from code
* dynamic configuration storage

---

## 🔷 3. Integration — Suppliers

The system must allow add new third party provider easily

**Architectural impact:**

* integration abstraction layer
* provider adapters
* versioning & extensibility

---

## 🔷 4. Reporting — Data Processing

Reporting must be generated **without degrading performance of core LMS operations**

**Architectural impact:**

* read/write separation
* async report generation
* data aggregation strategies
* possible separate reporting DB
 ^2ABRsq5R

Constraints

Technical Constraint
The system must use Single SSO for authentication (Azure AD)
Cloud Provider Azure

Business Constraint
Budget
Time

Regulatory Constraint
GDPR
 ^NZJHqBmy

%%
## Drawing
```compressed-json
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

RE4IAA==
```
%%