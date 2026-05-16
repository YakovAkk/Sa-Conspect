# Homework 4: Learning Management System - Project Planning

## Assignment Overview
Create a comprehensive project plan for the Learning Management System including:
1. Work Breakdown Structure (WBS) document
2. Project Estimation (man-days, story points)
3. High-level Project Timeline
4. Resource Plan

---

## Executive Summary

| Metric | Value |
|--------|-------|
| **Total Effort** | 295 man-days |
| **Total Story Points** | 481 |
| **Project Duration** | 17 weeks (4.25 months) |
| **Team Size** | 10 FTE |
| **Estimated Budget** | $824K |
| **Methodology** | Agile (2-week sprints) |
| **Number of Tasks** | 40 tasks across 10 components |
| **Critical Path** | 18 weeks |

---

# 1. Work Breakdown Structure (WBS)

## WBS Levels
- **Level 1**: Learning Management System (Main Project)
- **Level 2**: 10 Major Components
- **Level 3**: 40 Detailed Tasks

## Complete WBS Table

| WBS Code | Task Name | Level | Description | Deliverable |
|----------|-----------|-------|-------------|------------|
| 1.0 | Learning Management System | 1 | Main project | Complete LMS |
| 1.1 | Project Planning & Setup | 2 | Foundation phase | Project charter, risk register |
| 1.1.1 | Requirements analysis | 3 | Detailed requirement gathering | Requirements document |
| 1.1.2 | Technical architecture design | 3 | System design & tech stack | Architecture diagram |
| 1.1.3 | Project team setup | 3 | Resource allocation & kickoff | Team structure, tools |
| 1.2 | Core Platform Infrastructure | 2 | Backend & deployment infrastructure | Infrastructure setup |
| 1.2.1 | Database design & setup | 3 | Schema, indexing, backups | Database schema |
| 1.2.2 | API framework & base services | 3 | RESTful API, common utilities | API documentation |
| 1.2.3 | Authentication infrastructure (SSO) | 3 | SSO integration setup | SSO configuration |
| 1.2.4 | Cloud infrastructure & DevOps | 3 | CI/CD, containers, deployment | Infrastructure code |
| 1.3 | User Management & Authentication | 2 | User roles, permissions, SSO | User management module |
| 1.3.1 | User registration & profile management | 3 | Create users, manage profiles | User API endpoints |
| 1.3.2 | Role-based access control (RBAC) | 3 | Admin, learner, instructor roles | RBAC implementation |
| 1.3.3 | SSO integration | 3 | External identity provider setup | SSO integration |
| 1.3.4 | Security & data protection | 3 | Encryption, compliance | Security audit |
| 1.4 | Course Management Module | 2 | Course CRUD operations | Course management system |
| 1.4.1 | Course creation & editing interface | 3 | Web form for course management | Course form UI |
| 1.4.2 | Course recording integration | 3 | Record, store, stream videos | Video management system |
| 1.4.3 | Priority assignment system | 3 | Set & manage course priorities | Priority engine |
| 1.4.4 | Course validation rules engine | 3 | Validate courses against rules | Validation service |
| 1.4.5 | Automatic course revalidation | 3 | Trigger revalidation on changes | Revalidation scheduler |
| 1.4.6 | Course search functionality | 3 | Full-text search, filters | Search API |
| 1.5 | Course Booking & Approval System | 2 | Booking requests, approval workflow | Booking module |
| 1.5.1 | Booking request creation | 3 | Users create booking requests | Booking API |
| 1.5.2 | Automatic validation & status assignment | 3 | Validate against rules | Validation engine |
| 1.5.3 | Admin approval workflow | 3 | Admin review & approval UI | Workflow interface |
| 1.5.4 | Request status management | 3 | Track: Proposed → Accepted/Rejected → Approved | Status management |
| 1.6 | Notification System | 2 | Email & SMS notifications | Notification service |
| 1.6.1 | Email notification service | 3 | Email templates, delivery | Email service |
| 1.6.2 | SMS notification service | 3 | SMS templates, delivery | SMS service |
| 1.6.3 | Notification triggers & rules | 3 | When to notify (course edit, booking status, etc) | Trigger configuration |
| 1.7 | Third-Party Supplier Integration | 2 | Vendor course management | Supplier portal |
| 1.7.1 | Supplier portal interface | 3 | View, add, edit courses | Portal UI |
| 1.7.2 | Supplier course management API | 3 | CRUD operations for suppliers | Supplier API |
| 1.7.3 | Supplier notifications | 3 | Notify suppliers of changes | Notification workflows |
| 1.8 | Reporting & Analytics | 2 | Reports & dashboards | Reporting system |
| 1.8.1 | Booking reports | 3 | Create, download booking reports | Report engine |
| 1.8.2 | Vendor performance reports | 3 | Vendor usage & metrics | Vendor reports |
| 1.8.3 | Usage analytics dashboard | 3 | System usage visualization | Analytics dashboard |
| 1.8.4 | Report export functionality | 3 | PDF/Excel export | Export module |
| 1.9 | Testing & Quality Assurance | 2 | QA & testing phase | Test reports, defect logs |
| 1.9.1 | Unit testing & code review | 3 | Developer testing | Unit test coverage |
| 1.9.2 | Integration testing | 3 | Component integration tests | Integration test report |
| 1.9.3 | User acceptance testing (UAT) | 3 | End-user testing | UAT sign-off |
| 1.9.4 | Performance & security testing | 3 | Load testing, security audit | Performance report |
| 1.10 | Deployment & Go-Live | 2 | Production deployment & training | Production system |
| 1.10.1 | Production environment setup | 3 | Deploy to production | Deployment docs |
| 1.10.2 | User training & documentation | 3 | User manuals, training sessions | Training materials |
| 1.10.3 | Go-live & support | 3 | Launch & first-week support | Go-live report |

**Total WBS Items: 40 tasks**

---

# 2. Project Estimation

## Estimation Summary

| Category | Man-Days | Story Points | Percentage |
|----------|----------|--------------|-----------|
| Planning & Preparation | 15 | 24 | 5% |
| Infrastructure & Setup | 36 | 59 | 12% |
| User Management | 26 | 43 | 9% |
| Course Management | 48 | 78 | 16% |
| Booking & Approval | 30 | 49 | 10% |
| Notifications | 22 | 36 | 7% |
| Supplier Integration | 28 | 46 | 9% |
| Reporting & Analytics | 30 | 48 | 10% |
| Testing & QA | 42 | 69 | 14% |
| Deployment & Go-Live | 18 | 29 | 6% |
| **TOTAL** | **295 man-days** | **481 story points** | **100%** |

## Detailed Task Estimation

| WBS Code | Task Name | Man-Days | Story Points | Complexity |
|----------|-----------|----------|--------------|-----------|
| 1.1.1 | Requirements analysis | 5 | 8 | Medium |
| 1.1.2 | Technical architecture design | 8 | 13 | High |
| 1.1.3 | Project team setup | 2 | 3 | Low |
| 1.2.1 | Database design & setup | 6 | 10 | High |
| 1.2.2 | API framework & base services | 10 | 16 | High |
| 1.2.3 | Authentication infrastructure (SSO) | 8 | 13 | High |
| 1.2.4 | Cloud infrastructure & DevOps | 12 | 20 | Very High |
| 1.3.1 | User registration & profile management | 6 | 10 | Medium |
| 1.3.2 | Role-based access control (RBAC) | 8 | 13 | High |
| 1.3.3 | SSO integration | 5 | 8 | Medium |
| 1.3.4 | Security & data protection | 7 | 12 | High |
| 1.4.1 | Course creation & editing interface | 10 | 16 | High |
| 1.4.2 | Course recording integration | 12 | 20 | Very High |
| 1.4.3 | Priority assignment system | 4 | 6 | Low |
| 1.4.4 | Course validation rules engine | 10 | 16 | High |
| 1.4.5 | Automatic course revalidation | 8 | 13 | High |
| 1.4.6 | Course search functionality | 8 | 13 | Medium |
| 1.5.1 | Booking request creation | 6 | 10 | Medium |
| 1.5.2 | Automatic validation & status assignment | 8 | 13 | High |
| 1.5.3 | Admin approval workflow | 10 | 16 | High |
| 1.5.4 | Request status management | 6 | 10 | Medium |
| 1.6.1 | Email notification service | 6 | 10 | Low |
| 1.6.2 | SMS notification service | 8 | 13 | Medium |
| 1.6.3 | Notification triggers & rules | 8 | 13 | High |
| 1.7.1 | Supplier portal interface | 12 | 20 | High |
| 1.7.2 | Supplier course management API | 10 | 16 | High |
| 1.7.3 | Supplier notifications | 6 | 10 | Medium |
| 1.8.1 | Booking reports | 8 | 13 | Medium |
| 1.8.2 | Vendor performance reports | 8 | 13 | Medium |
| 1.8.3 | Usage analytics dashboard | 10 | 16 | High |
| 1.8.4 | Report export functionality | 4 | 6 | Low |
| 1.9.1 | Unit testing & code review | 10 | 16 | High |
| 1.9.2 | Integration testing | 12 | 20 | High |
| 1.9.3 | User acceptance testing (UAT) | 8 | 13 | Medium |
| 1.9.4 | Performance & security testing | 12 | 20 | Very High |
| 1.10.1 | Production environment setup | 6 | 10 | Medium |
| 1.10.2 | User training & documentation | 8 | 13 | Medium |
| 1.10.3 | Go-live & support | 4 | 6 | Low |

### Units of Measure Explained
- **Man-Days**: 1 man-day = 8 hours of focused work
- **Story Points**: Relative sizing (Fibonacci: 1, 2, 3, 5, 8, 13, 20, 40)
  - 1-3 = Small, simple tasks
  - 5-8 = Medium complexity
  - 13-20 = High complexity
  - 40+ = Epic-level

### Estimation Confidence
- **High** (±10%): Infrastructure, User Management, Notifications
- **Medium** (±20%): Course Management, Booking, Analytics
- **Low** (±30%): Video integration, Performance testing

### With Contingency Buffer
- Technical contingency: +10% → 325 man-days
- Risk buffer: +15% → 340 man-days
- **Recommended total: 340 man-days**

---

# 3. Project Timeline

## Project Schedule Overview

| Phase | Duration | Week Start | Week End | Man-Days | Focus |
|-------|----------|-----------|---------|----------|-------|
| Phase 1: Planning & Design | 2 weeks | Week 1 | Week 2 | 15 | Planning |
| Phase 2: Infrastructure Setup | 3 weeks | Week 2 | Week 4 | 36 | Infrastructure |
| Phase 3: Core Development | 10 weeks | Week 3 | Week 12 | 200 | Feature development |
| Phase 4: Testing & QA | 4 weeks | Week 9 | Week 12 | 42 | Testing (parallel) |
| Phase 5: Deployment & Go-Live | 2 weeks | Week 13 | Week 14 | 18 | Deployment |
| Phase 6: Post-Launch Support | 3 weeks | Week 15 | Week 17 | - | Maintenance |

**Total Duration: 17 weeks**

## Sprint Breakdown (Agile - 2-week sprints)

| Sprint | Weeks | Story Points | Key Deliverables |
|--------|-------|--------------|-----------------|
| Sprint 1-2 | W1-W2 | 24 | Requirements, Architecture, Team setup |
| Sprint 3 | W3-W4 | 69 | Database, API framework, User registration |
| Sprint 4 | W5-W6 | 73 | RBAC, SSO, Course management MVP |
| Sprint 5 | W7-W8 | 75 | Video integration, Booking API |
| Sprint 6 | W9-W10 | 98 | Workflow, Notifications, Supplier portal |
| Sprint 7 | W11-W12 | 82 | Analytics, Reports, Search refinement |
| Sprint 8 | W13-W14 | 60 | Testing, Fixes, Production deployment |

## Critical Path Sequence
```
1. Planning & Requirements (2w)
2. Infrastructure & Database (3w)
3. API & User Management (2w)
4. Core Features - Course, Booking, Notifications (6w)
5. Testing & QA (4w)
6. Deployment & Go-Live (1w)
```

## Key Milestones

| # | Milestone | Target Week | Completion Criteria |
|---|-----------|------------|-------------------|
| M1 | Requirements Complete | Week 2 | Approved requirements document |
| M2 | Infrastructure Ready | Week 4 | Dev environment operational |
| M3 | User Management Live | Week 6 | Login, roles, permissions working |
| M4 | Course Management MVP | Week 8 | Create, edit, search courses |
| M5 | Booking System Ready | Week 10 | End-to-end booking + approval workflow |
| M6 | Notifications Active | Week 11 | Email/SMS triggered correctly |
| M7 | Supplier Portal Live | Week 12 | Supplier management functional |
| M8 | Testing Complete | Week 13 | 95% bugs resolved, UAT approved |
| M9 | Go-Live Ready | Week 14 | Production verified |
| M10 | Production Live | Week 15 | System in production |
| M11 | Stabilization Complete | Week 17 | Post-launch issues resolved |

---

# 4. Resource Plan

## Team Structure

**Total: 10 FTE (Full-Time Equivalents)**

### Leadership & Management (3 FTE)
- 1 Project Manager (100% throughout)
- 1 Business Analyst (100% Weeks 1-6, then 30%)
- 1 Solutions Architect (100% Weeks 1-4, then 20%)

### Development Team (8 FTE)
- 1 Dev Team Lead (100% throughout)
- 1 Senior Backend Developer (100% throughout)
- 3 Backend Developers (100% Weeks 3-13, 50% Week 14)
- 1 Senior Frontend Developer (100% Weeks 3-13, 50% Week 14)
- 1 Frontend Developer (100% Weeks 5-13, 50% Week 14)
- 1 Database Administrator (100% Weeks 2-4, 30% ongoing)

### Quality Assurance (4 FTE)
- 1 QA Lead (50% Weeks 1-8, 100% Weeks 9-14)
- 2 QA Engineers/Manual Testers (20% Weeks 1-8, 100% Weeks 9-14)
- 1 Test Automation Engineer (50% Weeks 5-8, 100% Weeks 9-14)

### Infrastructure & DevOps (1.5 FTE)
- 1 DevOps/Infrastructure Engineer (100% Weeks 2-4, 80% Weeks 5-14)
- 0.5 Infrastructure Support (50% Weeks 15-17)

## Resource Allocation by Phase

### Phase 1: Planning & Requirements (Weeks 1-2)
**Total: 5.8 FTE**
- Project Manager: 100%
- Business Analyst: 100%
- Solutions Architect: 100%
- Dev Team Lead: 50%
- QA Lead: 30%

### Phase 2: Infrastructure Setup (Weeks 3-4)
**Total: 8.7 FTE**
- Project Manager: 100%
- Solutions Architect: 50%
- Dev Team Lead: 100%
- Senior Backend Dev: 100%
- Backend Devs (2): 100%
- Database Admin: 100%
- DevOps: 100%
- QA Lead: 20%

### Phase 3: Core Development (Weeks 5-12)
**Total: 10.0 FTE**
- Project Manager: 100%
- Business Analyst: 40%
- Dev Team Lead: 100%
- Senior Backend Dev: 100%
- Backend Devs (3): 100%
- Senior Frontend Dev: 100%
- Frontend Dev: 100%
- Database Admin: 30%
- QA Lead: 50%
- QA Engineers (2): 80%
- Test Automation: 80%
- DevOps: 30%

### Phase 4: Testing & QA (Weeks 9-13)
**Total: 8.5 FTE**
- Project Manager: 100%
- QA Lead: 100%
- QA Engineers (2): 100%
- Test Automation: 100%
- Dev Team Lead: 80%
- Backend Devs (2): 80%
- Frontend Devs (1.5): 80%
- DevOps: 50%

### Phase 5: Deployment & Go-Live (Weeks 14-15)
**Total: 5.5 FTE**
- Project Manager: 100%
- Dev Team Lead: 50%
- Backend Dev: 50%
- Frontend Dev: 50%
- QA Lead: 100%
- QA Engineer: 50%
- DevOps: 100%

## Specialist Skill Requirements

| Specialty | Skills | Experience | Count |
|-----------|--------|------------|-------|
| **Backend Development** | APIs, microservices, databases, auth | 5+ years | 4 FTE |
| **Frontend Development** | Responsive UI, React/Angular, CSS | 3+ years | 2 FTE |
| **QA & Testing** | Test design, automation, UAT | 3+ years | 3-4 FTE |
| **DevOps/Infrastructure** | K8s, CI/CD, AWS/Azure, containers | 4+ years | 1 FTE |
| **Database Admin** | SQL, schema design, optimization | 5+ years | 1 FTE |
| **Project Management** | Agile, Scrum, risk management | 5+ years | 2 FTE |

## Project Budget Estimate

| Category | FTE | Annual Rate | Cost |
|----------|-----|------------|------|
| Management (PM, BA, Arch) | 3.0 | $115K | $120K |
| Development | 8.0 | $120K | $320K |
| QA & Testing | 4.0 | $85K | $136K |
| DevOps/Infrastructure | 1.5 | $115K | $48K |
| **Labor Subtotal** | **16.5** | - | **$624K** |
| Infrastructure & Tools (20%) | - | - | $125K |
| Contingency (10%) | - | - | $75K |
| **TOTAL PROJECT BUDGET** | - | - | **$824K** |

---

# Project Assumptions & Constraints

## Key Assumptions
1. Team has experience with similar enterprise systems
2. No major unknowns or unproven technologies
3. Parallel development reduces total duration
4. External dependencies available (SSO, video hosting)
5. 2-week sprints with ~10 man-days per person per sprint
6. Standard 8-hour work day

## Constraints
- Fixed start date and completion deadline
- Budget cap of $824K
- Team size limited to 10 people
- External SSO and video providers required
- Regulatory/compliance requirements apply

## Risks & Mitigations

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|-----------|
| Video integration delays | Medium | High | Early POC, 12 man-days buffer |
| Scope creep | High | High | Weekly scope reviews, change control |
| Performance bottlenecks | Medium | High | Load testing Week 11-12 |
| Third-party SSO issues | Low | High | Proof of concept Week 1-2 |
| Resource unavailability | Low | Medium | Cross-training, backup resources |

---

## Deliverables Summary

✅ **Work Breakdown Structure** - 40 tasks across 10 components  
✅ **Project Estimation** - 295 man-days / 481 story points  
✅ **Timeline** - 17 weeks with Gantt schedule  
✅ **Resource Plan** - 10 FTE with $824K budget  

