---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠== You can decompress Drawing data with the command palette: 'Decompress current Excalidraw file'. For more info check in plugin settings under 'Saving'


# Excalidraw Data

## Text Elements
Homework 1
1) Provide business drivers, goals, objectives, and values for the case.
2) Fill in the information regarding stakeholders.
3) Create a power-interest matrix.
4) Fill in the RACI matrix. ^XBqOnJgY

1. Business drivers, goals, objectives and values
Text or visual form.

2. Identify Stakeholders
Note: Groups are organisational parties, e.g. HR, marketing, and sales. Views are visuals and documents they may be interested in, e.g. use case diagrams, high-level design, data protection regulations, and activity diagrams.

Name        Role        Group        Concerns        Views
 
3. Power-interest matrix
 ^X1E04SD8

4. RACI matrix ^h6P8pUNu

Responsible (R), Accountable (A), Consulted (C), Informed (I) ^J2NPa5v1

Activity/Role        Person 1        Person 2        …        … ^6qZ5ntmZ

Activity 1        R        A        C        I ^4Yqc8zbt

Activity 2        R        I        I        C ^akquc2Jh

…        I        C        R        I ^5VELMFL1

LEARNING MANAGEMENT SYSTEM
A service company would like to create a learning management system. These should include internal courses, workshop recordings, and different security courses and courses from training vendors. The system should have the following capabilities.

System capabilities breakdown
Course Management and Recording: The system allows the recording and management of internal courses and workshops. These include various security courses and workshops.
Security and Authentication: Users, including both learners and administrators, are authenticated using Single Sign-On (SSO) to access the system.
Course Creation and Update: Administrators can create new courses and update existing ones through a user-friendly web form interface.
Priority Assignment: Administrators can assign priority levels to newly created or updated courses through the web form.
Revalidation of Courses: After changes are made to a course, the system automatically revalidates all existing courses that are not in a paid status against the new rules.
Notification: If a course is edited, administrators are notified via email or SMS.
Course Approval: End-users can create new course booking requests, and the system assigns a "Proposed" status to these requests. Users are notified via email or SMS.
Validation and Acceptance: If the course request is valid according to priority and booking rules, it is automatically accepted. Otherwise, it may be rejected based on validation rules.
Approval Workflow: Administrators review course details and, if no objections exist, change the request status to "Approved." Users are notified of the status change.
Third-Party Supplier Integration: Third-party suppliers can add and manage their course opportunities through the system. This includes the ability to view, edit, and add new opportunities. Notifications are sent to both the supplier and administrators when changes are made.
Search functionality: Users can search courses following the requested criteria.
Reporting Capabilities: Administrators and end-users have access to detailed reports based on defined search criteria. This includes viewing and downloading booking, vendor, and usage details reports. ^3C6wl60f

# 1. Business drivers, goals, objectives and values

### 1) Business drivers:

internal:

* Relevance and quality of courses (internal + vendor content)
* Admin responsiveness in approval workflows (slow approvals → user drop)
* Team engagement and continuous learning culture
* Efficiency of course management (reduce manual work)
* Consistency of validation rules (revalidation logic after updates)
* System usability (simple booking, search, navigation)

external:

* Competitors offering better learning platforms
* Course suppliers interest and quality of their offerings
* Market trend toward digital learning / LMS platforms
* Compliance and security regulations (mandatory trainings)
* User expectations (fast, simple, SSO-based systems)

---

### 2) Business goals

* Financial goal
  Company wants to reduce operational costs and potentially monetize training (vendors, paid courses)

* Social goal
  Company wants to educate employees and users, improving knowledge and skills

* Process goals
  Company wants smooth and automated processes for:
  - course approval
  - booking validation
  - notifications

* Employee goals
  Company wants employees to:
  - easily access learning
  - grow professionally
  - stay engaged

* Growth goals
  Company wants to:
  - scale platform usage
  - attract more suppliers
  - stay competitive in the LMS market

* Compliance goals
  Company wants to ensure:
  - all required trainings are completed
  - courses are always valid and up-to-date

---

### 3) Business objectives:

* Achieve ≥90% employee adoption of LMS within 12 months
* Reduce manual approval effort by at least 50% within 6 months
* Ensure 100% tracking of mandatory security courses
* Maintain course search response time < 1 seconds
* Ensure booking/approval workflow completes asynchronously within < 10 minutes
* Achieve ≥99% notification delivery success rate
* Onboard N new course suppliers per quarter
* Ensure 0 outdated courses remain active (via revalidation)
* Generate reports (booking, vendor, usage) in < 5 seconds
* Ensure ≥80% of course bookings are done through the platform

---

### 4) Business value:

tangible:

* Reduced operational costs (automation, fewer manual processes)
* Increased productivity (faster booking and approvals)
* Better utilization of training budget and resources
* Reduced compliance risks and penalties
* Centralized data for reporting and decision-making

intangible:

* Improved company reputation as a learning-focused organization
* Higher employee satisfaction and engagement
* Stronger relationships with course suppliers
* Increased trust due to compliance and transparency
* Knowledge growth and internal expertise development ^np5j7tsH

# 2. Identify Stakeholders (Internal / External)

## 🔹 Internal Stakeholders (inside the organization)

| Name             | Role                                  | Group                | Concerns                                    | Views                     |
| ---------------- | ------------------------------------- | -------------------- | ------------------------------------------- | ------------------------- |
| HR Department    | Manages employee training programs    | HR                   | Training completion, employee development   | Reports, dashboards       |
| Training Manager | Oversees course quality and planning  | Training / L&D       | Course relevance, scheduling, effectiveness | Course analytics, reports |
| Support Team     | Handles user issues and incidents     | Support / Operations | System reliability, issue resolution        | Logs, dashboards          |
| Data Analyst     | Analyzes usage and performance data   | Analytics            | Insights, reporting accuracy, trends        | Reports, BI dashboards    |
| Legal Department | Ensures legal compliance              | Legal                | Contracts, liability, data protection       | Legal docs, policies      |
| Internal Auditor | Reviews internal compliance processes | Audit                | Audit trails, process transparency          | Audit reports             |
| Compliance Officer |       Ensures regulatory compliance    |    Compliance / Security   |     Auditability, mandatory training tracking  |      Audit logs, compliance reports|
| System Owner      |  Defines product direction     |   Product / Business       | Business value, adoption, scalability      |  Roadmaps, KPIs, high-level design|
| Executive Management  |      Strategic decision-making   |     Management    |    ROI, risk, growth      |  Executive dashboards, summary reports|


---

## 🔹 External Stakeholders (outside the organization)

| Name                                    | Role                   | Group             | Concerns                                | Views                       |
| --------------------------------------- | ---------------------- | ----------------- | --------------------------------------- | --------------------------- |
| Identity Provider (SSO)                 | Authenticates users    | External Service  | Security, uptime, integration stability | Integration docs            |
| Email/SMS Provider                      | Sends notifications    | External Service  | Delivery reliability, performance       | API docs                    |
| Payment Provider (if paid courses)      | Handles transactions   | External Service  | Transaction reliability, security       | Financial reports, API docs |
| External Customers (if platform public) | Consume courses        | Customers         | Accessibility, quality, usability       | UI, catalog                 |
| Certification Authorities               | Provide certifications | External Partners | Validity of certifications              | Certification reports       |
| Data Protection Authority               | Oversees data privacy  | Regulatory        | GDPR / data compliance                  | Compliance reports          |
| Third-party Supplier   |     Provides and manages courses    |    External Partners      |  Ease of integration, visibility, course management    |    API documentation, integration guides |
| Regulators      |  Ensure compliance with standards  |      Regulatory Bodies  |      Compliance, auditability, reporting    |    Audit reports, compliance documentation |


## 🔹Delivery Stakeholders (inside the organization, but do not make decisions)

| Name            | Role                     | Group       | Concerns                           | Views                 |
| --------------- | ------------------------ | ----------- | ---------------------------------- | --------------------- |
| Developer       | Implements features      | Engineering | Code quality, requirements clarity | API specs             |
| Architect       | Defines system design    | Engineering | Scalability, maintainability       | Architecture diagrams |
| DevOps          | Maintains infrastructure | Engineering | Deployment, monitoring             | Infra diagrams        |
| QA              | Ensures quality          | QA          | Test coverage, bugs                | Test reports          |
| Project Manager | Coordinates delivery     | Project     | Timeline, scope, risks             | Plans, roadmaps       |
| Team Lead | Leads development team, ensures delivery quality and alignment | Engineering | Code quality, team productivity, delivery timelines, technical decisions | Architecture diagrams, code structure, technical plans |

 ^mpPcAvXI

# 3. Power–Interest Matrix

## 🔴 High Power – High Interest (Manage Closely)

**Internal:**

* System Owner
* Compliance Officer
* Training Manager
* HR Department
* Internal Auditor

**External:**

* Regulators
* Data Protection Authority

👉 These stakeholders:

* Define **requirements, compliance, and core processes**
* Must be involved in **regular decision-making and validation**

---

## 🟡 High Power – Low Interest (Keep Satisfied)

**Internal:**

* Executive Management
* Legal Department

**External:**

* Certification Authorities *(standards, but not daily involved)*

👉 These stakeholders:

* Influence **strategy, legal constraints, and risk**
* Need **periodic updates and high-level visibility**

---

## 🔵 Low Power – High Interest (Keep Informed)

**Internal:**

* Support Team
* Data Analyst

**External:**

* Third-party Suppliers
* External Customers

👉 These stakeholders:

* Actively use or depend on the system
* Provide **feedback and operational insights**

---

## ⚪ Low Power – Low Interest (Monitor)

**External:**

* Identity Provider (SSO)
* Email/SMS Provider
* Payment Provider

**Delivery (internal but non-decision):**

* Developer
* QA
* DevOps
* Architect
* Project Manager
* Team Lead

👉 These stakeholders:

* Important for **execution and operations**
* Minimal involvement in **business decisions**
 ^w6oKDdZk

# 4.1 Product / Strategy RACI

| Activity / Decision             | System Owner | Executive Management | HR Department | Training Manager | Compliance Officer | Data Analyst |
| ------------------------------- | ------------ | -------------------- | ------------- | ---------------- | ------------------ | ------------ |
| Define product vision & roadmap | A            | C                    | C             | C                | C                  | I            |
| Define business goals & KPIs    | A            | R                    | C             | C                | C                  | R            |
| Prioritize features             | A            | C                    | I             | C                | C                  | I            |
| Approve major product changes   | R            | A                    | I             | I                | C                  | I            |
| Monitor product performance     | A            | C                    | C             | C                | I                  | R            |

---

# 4.2 Compliance & Governance RACI

| Activity / Decision            | Compliance Officer | Legal Department | Internal Auditor | Regulators | Data Protection Authority | System Owner |
| ------------------------------ | ------------------ | ---------------- | ---------------- | ---------- | ------------------------- | ------------ |
| Define compliance requirements | A                  | C                | C                | C          | C                         | I            |
| Define data protection rules   | R                  | C                | I                | I          | A                         | I            |
| Approve compliance policies    | R                  | A                | C                | C          | C                         | I            |
| Perform audits                 | C                  | I                | R                | A          | C                         | I            |
| Ensure ongoing compliance      | A                  | C                | R                | C          | C                         | I            |

---

# 4.3 Development & Delivery RACI

| Activity / Decision            | Team Lead | Developer | QA | Architect | DevOps | Project Manager |
| ------------------------------ | --------- | --------- | -- | --------- | ------ | --------------- |
| Define technical approach      | R         | C         | I  | A         | C      | I               |
| Implement features             | A         | R         | I  | C         | I      | I               |
| Code review & quality control  | A         | R         | C  | C         | I      | I               |
| Testing & validation           | C         | I         | R  | I         | I      | A               |
| Deployment & release           | C         | I         | C  | I         | R      | A               |
| Sprint planning & coordination | R         | C         | C  | C         | C      | A               |

---

# 4.4 Vendor / Supplier Integration RACI

| Activity / Decision                    | System Owner | Third-party Supplier | DevOps | Architect | Legal Department | Compliance Officer |
| -------------------------------------- | ------------ | -------------------- | ------ | --------- | ---------------- | ------------------ |
| Define integration requirements        | A            | C                    | I      | R         | C                | C                  |
| Provide API / integration capabilities | I            | R                    | C      | C         | I                | I                  |
| Validate integration compliance        | C            | I                    | I      | C         | C                | A                  |
| Supplier onboarding                    | A            | R                    | C      | C         | C                | I                  |
| Monitor integration performance        | A            | C                    | R      | C         | I                | I                  |
 ^qoeANBTD

## Embedded Files
dd06c5d8ea0e766edf99d4f98c2e1059911f45c0: [[Pasted Image 20260328205737_612.png]]

%%
## Drawing
```compressed-json
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=
```
%%