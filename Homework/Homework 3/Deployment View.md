# Deployment View — Learning Management System

## View Brief

This view describes how the software containers of the Learning Management System
are deployed onto physical and cloud infrastructure. It shows the execution
environments, hosting tiers, network boundaries, and external service integrations.
The purpose is to communicate infrastructure topology, scalability concerns, and
environment boundaries to developers and operations teams.

---

## Legend

| Symbol             | Meaning                                                                  |
| ------------------ | ------------------------------------------------------------------------ |
| Deployment Node    | A physical server, virtual machine, cloud region, or runtime environment |
| Container Instance | A running instance of a software container from the Container diagram    |
| External System    | A third-party cloud service outside the system boundary                  |
| «replicates»       | Multiple instances run in parallel for availability                      |
| <<HTTPS>>          | Encrypted web traffic                                                    |
| <<SQL>>            | Database connection                                                      |
| <<AMQP>>           | Message queue protocol                                                   |

---

## Diagram

```
┌─────────────────────────────────────────────────────────────────┐
│  Cloud (Azure / AWS)                                            │
│                                                                 │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │  CDN (Azure Front Door / CloudFront)                    │   │
│  │   ├── Web Application (React) — static assets          │   │
│  │   ├── Admin Panel (React) — static assets              │   │
│  │   └── Course Supplier Admin — static assets            │   │
│  └───────────────────────┬─────────────────────────────────┘   │
│                           │ HTTPS                               │
│  ┌────────────────────────▼────────────────────────────────┐   │
│  │  Load Balancer                                          │   │
│  └──┬─────────────────────────────────────────────────────┘   │
│     │ HTTPS                                                     │
│  ┌──▼──────────────────────────────────────────────────────┐   │
│  │  Kubernetes Cluster                                     │   │
│  │                                                         │   │
│  │  ┌─────────────────┐   ┌─────────────────┐             │   │
│  │  │ Gateway External│   │  Auth Service   │             │   │
│  │  │   [.Net]  x2    │   │   [.Net]  x2    │             │   │
│  │  └────────┬────────┘   └────────┬────────┘             │   │
│  │           │                     │                       │   │
│  │  ┌────────▼────────┐   ┌────────▼────────┐             │   │
│  │  │  Course Service │   │ Notification    │             │   │
│  │  │   [.Net]  x2    │   │ Service    x1   │             │   │
│  │  └────────┬────────┘   └────────┬────────┘             │   │
│  │           │                     │                       │   │
│  │  ┌────────▼────────┐            │                       │   │
│  │  │ Reporting Svc   │            │                       │   │
│  │  │   [.Net]  x1    │            │                       │   │
│  │  └────────┬────────┘            │                       │   │
│  └───────────┼─────────────────────┼───────────────────────┘   │
│              │ SQL                 │ AMQP                       │
│  ┌───────────▼──────┐   ┌──────────▼──────────┐                │
│  │  Database Cluster│   │  Message Queue      │                │
│  │  Primary + 1     │   │  (RabbitMQ /        │                │
│  │  Read Replica    │   │   Azure Service Bus)│                │
│  └──────────────────┘   └─────────────────────┘                │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘

          │ SAML/OIDC                    │ SMTP / REST
          ▼                              ▼
┌─────────────────────┐      ┌─────────────────────┐
│  Identity Provider  │      │  Email/SMS Provider  │
│  (Azure AD / Okta)  │      │  (SendGrid / Twilio) │
│  [external system]  │      │  [external system]   │
└─────────────────────┘      └─────────────────────┘
```

---

## Key Decisions

**CDN for frontend containers**
Web Application, Admin Panel and Course Supplier Admin are React SPAs —
static files served via CDN reduce latency and offload traffic from the cluster.

**Kubernetes for backend services**
All .Net services run as pods inside a Kubernetes cluster.
Gateway External and Auth Service are replicated (x2) as they sit on the
critical path of every request. Course Service is also replicated for throughput.
Notification and Reporting Services run as single instances — they are not
latency-sensitive.

**Database Primary + Read Replica**
A single write primary with one read replica. Course Service and Reporting Service
read from the replica to reduce load on the primary. Auth Service and Course Service
write to the primary.

**Message Queue**
Decouples Course Service from Notification Service for async flows:
- Course edited → event published → Notification Service consumes → sends email/SMS
- Course edited → event published → Course Service consumes → triggers revalidation

**External services outside cloud boundary**
Identity Provider (SSO) and Email/SMS Provider are managed third-party services —
they are outside the deployment boundary and accessed over public endpoints.
