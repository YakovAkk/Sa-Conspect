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

## 🔷 1. Performance — Search (Assumption)

The system must support **search, filtering, and sorting across 100k+ courses with response time < 1 second**

**Architectural impact:**

* requires indexing strategy
* may require search engine (e.g. Elastic)
* pagination & query optimization
* caching layer

---

## 🔷 2. Performance — Booking Flow

Course booking requests must be processed with **low latency (< 1–2 seconds)**

**Architectural impact:**

* async vs sync validation
* transaction boundaries
* potential queue/event usage

---

## 🔷 3. Availability — External Integrations

LMS must remain operational if **third-party supplier integrations fail**

**Architectural impact:**

* async integration (queues/jobs)
* fallback strategies
* timeout & retry policies
* isolation of external dependencies

---

## 🔷 4. Security — Authentication

All users must be authenticated via **SSO**

**Architectural impact:**

* integration with identity provider
* token-based auth (OAuth/JWT)
* centralized auth flow

---

## 🔷 5. Security — Authorization

System must enforce **role-based access control (RBAC)** for users, admins, and suppliers

**Architectural impact:**

* access control model
* authorization layer
* service boundaries & permissions

---

## 🔷 6. Modifiability — Business Rules (Assumption)

Booking validation and course priority rules must be **modifiable without full system redeployment**

**Architectural impact:**

* rule engine / configuration-driven logic
* separation of business rules from code
* dynamic configuration storage

---

## 🔷 7. Integration — Suppliers

The system must support **integration with multiple third-party course providers**

**Architectural impact:**

* integration abstraction layer
* provider adapters
* versioning & extensibility
* error handling strategy

---

## 🔷 8. Scalability — Users & Load

The system must support **scaling to increased number of users without performance degradation**

**Architectural impact:**

* horizontal scaling
* stateless services
* load balancing

---

## 🔷 9. Reporting — Data Processing

Reporting must be generated **without degrading performance of core LMS operations**

**Architectural impact:**

* read/write separation
* async report generation
* data aggregation strategies
* possible separate reporting DB

---

## 🔷 10. Reliability — Background Processing

Background processes (revalidation, notifications, integrations) must be **reliable and retryable**

**Architectural impact:**

* job scheduler (Hangfire)
* retry strategies
* idempotency
* failure handling

## 🔷 11. Security — Audit

System must provide traceable and queryable history of course changes and approvals

**Architectural impact:**

* audit storage design (separate store?)
* event sourcing vs audit tables
* querying/reporting strategy
* data retention
 ^2ABRsq5R

%%
## Drawing
```compressed-json
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
```
%%