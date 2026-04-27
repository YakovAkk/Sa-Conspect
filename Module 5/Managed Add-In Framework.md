---
title: "Managed Add-In Framework (MAF)"
date: 2026-04-13
tags:
  - module5
  - architecture
  - modular
  - dotnet
  - canvas-note
aliases:
  - MAF
  - System.AddIn
cssclasses:
  - canvas-note
---

# Managed Add-In Framework (MAF)

> [!note] Overview
> The ==Managed Add-In Framework (MAF)== comprises two primary modules: a **library analyzer** and a **proxy code generator**. The library analyzer accepts a type of library or a managed software code assembly from an existing host application.
>
> MAF's core features a ==pipeline== that governs **data exchange between the plugin and the host**, offering:
> - **Versioning** — add-ins and hosts can evolve independently.
> - **Lifetime management** — controls when components are loaded and unloaded.
> - **Isolation support** — separates host and add-in processes.
>
> MAF identifies each component and loads them **on demand through reflection**.

## Pipeline Diagram

![[Pasted image 20260413143840.png]]

## The Pipeline

The MAF pipeline has **five segments** organized around a central **contract**:

```
Host Application
      ↓
 Host-Side View
      ↓
 Host-Side Adapter
      ↓
    [Contract]   ← center of the pipeline
      ↓
 Add-In-Side Adapter
      ↓
  Add-In View
      ↓
   Add-In
```

Each pipeline segment is associated with a **distinct assembly**, loaded on demand to oversee the specific add-in.

### Three Key Parts

---

#### 1. Interface Contracts

> [!info] Interface Contracts
> ==Interface contracts== are the foundation of MAF.
> - Allow classes in an application to be **loosely coupled**.
> - Reduce the risk when changes are made between dependent sections of code.
> - The contract is **shared between the host and add-in side adapters**.
> - Should ==never be changed== once established — the contract is the stable, versioned boundary.

The contract sits at the **center** of the pipeline and defines what both sides can expect from each other.

---

#### 2. Views

> [!info] Views
> ==Views== sit on the **edges** of the pipeline — one on the host side, one on the add-in side.
> - Represent a host or add-in-specific **"view" of the contract**.
> - Are the code that the add-in and the host **directly interact with**.
> - Like the contract, views are contained in a **separate assembly**.

Views provide a type-safe, domain-specific interface so neither side needs to work directly with the raw contract.

---

#### 3. Adapters

> [!info] Adapters
> ==Adapters== are the last segment of the pipeline and play a **critical role**:
> - **Bind the contract to the view**.
> - Implement **lifetime management** for the add-in.
> - Handle any necessary **data conversion** between the two ends of the pipeline.

There are two adapters: one on the host side and one on the add-in side. Together they bridge the contract (stable, shared) with the views (host/add-in-specific).

---

## Pipeline Summary

| Segment | Side | Role |
|---|---|---|
| Host Application | Host | The application that loads add-ins |
| Host-Side View | Host | Host's typed "view" of the contract |
| Host-Side Adapter | Host | Binds host view to contract; handles conversions |
| **Contract** | **Shared** | **Stable interface — never changed after release** |
| Add-In-Side Adapter | Add-In | Binds contract to add-in view; handles conversions |
| Add-In View | Add-In | Add-in's typed "view" of the contract |
| Add-In | Add-In | The plugin that implements the functionality |

## Why Five Segments?

> [!tip] Five Segments — by Design
> Although five segments may seem complex, this design is important for ensuring:
> - **Isolation** — host and add-in run in separate boundaries; a failing add-in cannot crash the host.
> - **Version control** — because the contract never changes, old add-ins work with new host versions as long as the contract is honoured.
> - **Independent evolution** — each side can change its implementation without affecting the other.

## History and Status

> [!info] History
> - Introduced with **.NET Framework 3.5**.
> - Has not changed significantly since its introduction.
> - Though it may appear old or complex, it remains a **reliable and effective solution** for scenarios requiring strict add-in isolation and versioning.

## Summary

MAF provides a structured, pipeline-based approach to building extensible applications where plugins (add-ins) and the host must evolve independently without breaking each other. The central contract acts as the immutable boundary; views provide friendly interfaces for each side; and adapters bridge the gap between them while handling lifetime and data conversion. The five-segment design is the price of true isolation and version safety.

## Related Notes

- [[Module-Based Architecture]]
- [[Architectural Style - Monolith, Layered and Microservices]]
- [[Coupling and Cohesion]]