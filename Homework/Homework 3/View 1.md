# View 1 — System Context (C4 Level 1)

## View Brief

This view shows the **Learning Management System (LMS)** as a single black box in the centre of its environment. It answers: *who are the people and external systems that interact with the LMS, and through what channel?*

It establishes the **system boundary** and names every actor that crosses it. Internal behaviour (services, databases, workflows) is deliberately hidden — that detail belongs to Views 2 (Component Map) and 3 (Course Booking Workflow).

- **Scope:** the LMS as delivered to the service company.
- **Primary human actors:** Learners, Administrators, Third-Party Suppliers.
- **Key external system dependencies:** Azure AD (SSO) and the Email/SMS Provider.

---

## Legend (C4 Level 1 Notation)

| Shape / Colour              | Element Type           | Meaning                                                    |
| --------------------------- | ---------------------- | ---------------------------------------------------------- |
| 🔵 Blue rounded figure      | **Person**             | Internal human user (inside the organisation)              |
| ⚫ Grey rounded figure       | **Person (External)**  | Human user outside the organisation                        |
| 🟦 Dark-blue rectangle      | **System (In Scope)**  | The LMS itself — the system being designed                 |
| ⬛ Grey rectangle            | **System (External)**  | Existing external system the LMS depends on                |
| → Solid arrow + label       | **Interaction**        | Direction of call / data flow with protocol and purpose    |

**Reading the diagram:** each arrow is labelled with *what happens* + *[protocol / channel]*. Arrows always point from the initiator to the target. External dependencies sit outside the central system box.

---

## Diagram

```mermaid
C4Context
    title System Context — Learning Management System

    Person(learner, "Learner", "Internal employee who searches, books, and attends courses")
    Person(admin, "Administrator", "Internal staff who manages courses, approves bookings, and views reports")
    Person_Ext(supplier, "Third-Party Supplier", "External training vendor that provides course opportunities")

    System(lms, "Learning Management System", "Central platform for internal courses, workshop recordings, vendor courses, bookings, and reporting")

    System_Ext(sso, "SSO Provider (Azure AD)", "Identity and authentication provider")
    System_Ext(notify, "Email / SMS Provider", "Delivers email and SMS notifications")

    Rel(learner, lms, "Searches and books courses, views reports", "HTTPS / Client Web App")
    Rel(admin, lms, "Manages courses, approves bookings, generates reports", "HTTPS / Admin Web App")
    Rel(supplier, lms, "Adds and manages course opportunities", "HTTPS / Integration API")

    Rel(lms, sso, "Authenticates users", "OAuth 2.0 / OIDC")
    Rel(lms, notify, "Sends notifications on events", "REST API / SMTP")

    UpdateLayoutConfig($c4ShapeInRow="3", $c4BoundaryInRow="1")
```

---

## Notation Notes

- `Person(...)` — internal human actor (blue).
- `Person_Ext(...)` — external human actor (grey).
- `System(...)` — the system in scope (dark blue).
- `System_Ext(...)` — external system dependency (grey).
- `Rel(from, to, "label", "technology")` — a directed relationship; the second string is the **technology / protocol** that appears under the label in the rendered diagram.

This follows Simon Brown's C4 model (see *c4model.com*), Level 1 — System Context.
