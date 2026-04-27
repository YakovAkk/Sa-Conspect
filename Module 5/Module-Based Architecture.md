---
title: "Module-Based Architecture"
date: 2026-04-13
tags:
  - module5
  - architecture
  - modular
  - canvas-note
aliases:
  - Modular Architecture
  - Module Based Architecture
cssclasses:
  - canvas-note
---

# Module-Based Architecture

> [!note] Overview
> ==Module-based architecture== is a unique style that goes beyond traditional views by focusing on how **physical modules are organized**. Instead of looking at layers or services, this approach builds software from smaller, ==well-defined modules==.
>
> This architecture focuses on carefully planning how the parts of an application are assembled, making the system easier to **understand, extend, and manage**.

## What is a Module?

> [!info] Module Definition
> A ==module== is characterized as a:
> > *"deployable, manageable, natively reusable, composable, stateless unit of software providing a concise interface to consumers."*
>
> Each module has **clear, explicit properties**:
> - **Name** — uniquely identifies the module.
> - **Version** — allows managing updates and compatibility.
> - **List of dependencies** — declares what the module needs from other modules.
>
> A module works within a **specific business area** and stays within its **physical layer**.
>
> In Java, the quintessential example of a module is a ==JAR file==.

## What is Modularity?

> [!info] Modularity Principle
> ==Modularity== is a guiding design principle that:
> - Fosters **loose coupling** between components.
> - Establishes **clear contracts and dependencies**.
> - Conceals implementation details through **robust encapsulation**.
>
> From a coding perspective, modularity involves **dividing the software application into logical segments**, each addressing distinct concerns. This is the principle of ==separation of concerns== applied at the module level.

## Module vs Traditional Elements

> [!warning] Limitations of Traditional Elements
> Traditional software elements like **objects**, **packages**, and **archives** often **lack strong support for modularity**:
> - They do not enforce versioning.
> - They do not declare explicit dependencies.
> - They do not guarantee encapsulation at the deployment boundary.

| Element | Deployable | Versioned | Explicit Dependencies | Encapsulated |
|---|---|---|---|---|
| Object | No | No | No | Partial |
| Package | No | No | No | Weak |
| Archive (JAR/WAR) | Yes | Manual | No standard | Weak |
| **Module** | **Yes** | **Yes** | **Yes** | **Strong** |

## Platforms and Frameworks

Platforms were created specifically to solve the modularity gap in traditional architectures:

### OSGi (Open Services Gateway Initiative)

> [!info] OSGi
> ==OSGi== provides a **framework for building modular systems** in Java. It defines:
> - A module system (bundles) with explicit versioning and dependency management.
> - A runtime that enforces module boundaries and resolves dependencies dynamically.
>
> **Real implementations**:
> - **Knopflerfish** — lightweight OSGi framework
> - **Equinox** — the OSGi runtime used in Eclipse IDE
> - **Apache Felix** — Apache's OSGi framework
> - **OSGi .Net** — the .NET port of OSGi

### MAF (Mobile Application Framework)

> [!info] MAF
> ==MAF (Mobile Application Framework)== was created to support modular development in mobile contexts, providing structure for assembling modular applications from reusable components.

### Java Jigsaw (Java 9+)

> [!info] Java Jigsaw
> The introduction of ==Jigsaw in Java 9== marked a major step toward native modular support in Java:
> - Introduces the **Java Platform Module System (JPMS)**.
> - Allows defining explicit module boundaries via `module-info.java`.
> - Enforces **strong encapsulation** at the JVM level — packages inside a module are not accessible unless explicitly exported.
> - Reduces the classpath mess and enables smaller, optimized runtime images.

## Key Characteristics

| Characteristic | Description |
|---|---|
| **Module identity** | Each module has a name, version, and declared dependencies |
| **Loose coupling** | Modules interact only through their public interfaces |
| **Strong encapsulation** | Internals are hidden from other modules |
| **Composability** | Modules can be assembled in different combinations |
| **Reusability** | Modules are designed to be reused across applications |
| **Statelessness** | Modules do not hold application state (state lives elsewhere) |
| **Independent deployability** | Modules can be deployed, updated, and replaced individually |

## Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| High maintainability — change one module without ripple effects | Requires upfront discipline in defining module boundaries |
| Reusability — modules can be shared across projects | Dependency management can become complex as modules multiply |
| Clear contracts between parts of the system | Tooling support varies (OSGi vs JPMS vs frameworks) |
| Easier to understand each module in isolation | Versioning and compatibility management overhead |
| Enables independent versioning and deployment | Not all platforms have mature native module support |

## Summary

Module-based architecture shifts the focus from runtime decomposition (services, layers) to **physical composition** — building systems from explicitly versioned, dependency-declared, encapsulated units. Platforms like OSGi and the Java Jigsaw system provide the runtime infrastructure to enforce these boundaries. The key concepts — modularity as a design principle and the module as a first-class unit — together enable systems that are easier to extend, maintain, and reason about over time.

## Related Notes

- [[Architectural Style - Monolith, Layered and Microservices]]
- [[Layered Architecture]]
- [[Coupling and Cohesion]]
- [[Architectural Design Principles]]