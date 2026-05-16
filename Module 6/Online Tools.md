---
title: Online Tools
date: 2026-04-29
tags:
  - module6
  - tools
  - uml
  - canvas-note
cssclasses:
  - canvas-note
---

# Online Tools

> [!note] Overview
> ==Diagram and flowchart tools== provide shapes, grids, templates, and export capabilities that help architects create effective diagrams quickly. Modern tools range from feature-rich desktop applications to collaborative web-based platforms. The best tool depends on the notation required, the team's workflow, the need for collaboration, and the integration with existing platforms like Confluence.

## 1. What Diagramming Tools Offer

All modern diagramming tools share a common set of capabilities:

> [!info] Common Features
> - **Shape libraries** — pre-built ovals, arrows, rectangles, diamonds, UML symbols, BPMN shapes, and more
> - **Grids and snap** — enforce alignment automatically (supports the Orthogonality and Tidy Up rules)
> - **Templates** — start from a pre-built structure instead of a blank canvas
> - **Export formats** — PNG, SVG, PDF, XML, and often Visio-compatible formats
> - **Clean interfaces** — drag-and-drop WYSIWYG workflows reduce friction

## 2. Tool Comparison

### 2.1 Enterprise Architect

==Enterprise Architect== (by Sparx Systems) is a full-featured modeling platform aimed at complex enterprise-scale projects.

> [!info] Key Capabilities
> - Supports multiple notations: UML, BPMN, ArchiMate, SysML, and more
> - **Model Wizards** and **Transformation tools** for rapid model creation
> - **Code Generation** — generate code skeletons directly from models
> - Bridges the gap between business and technical teams
> - Collaboration features for executive stakeholders, development, and testing teams

| Strengths | Trade-offs |
|---|---|
| Full-spectrum modeling (design → code) | Steep learning curve |
| Broad notation support | Expensive license |
| Strong enterprise collaboration | Primarily desktop-oriented |

### 2.2 Microsoft Visio

==Microsoft Visio== is a widely adopted diagramming tool integrated into the Microsoft 365 ecosystem.

> [!info] Key Capabilities
> - Supports numerous notations (flowcharts, BPMN, UML, network diagrams, org charts)
> - **Design presets** for aesthetically consistent diagrams out of the box
> - **Data linking** — connect diagram shapes to live data sources (Excel, databases)
> - Collaboration features throughout the diagram creation process

| Strengths | Trade-offs |
|---|---|
| Deep Microsoft 365 integration | Paid license (not standalone free) |
| Familiar interface for Office users | Less capable for complex UML modeling |
| Data-linked diagrams | Windows-first (web version has fewer features) |

### 2.3 OmniGraffle

==OmniGraffle== (by The Omni Group) is a diagramming and digital illustration application for macOS and iOS.

> [!info] Key Capabilities
> - Drag-and-drop WYSIWYG interface
> - Design tools for both technical diagrams and visual illustrations
> - Prototype and mockup documentation annotation functions
> - Supports UML and Relationship notations
> - Organizes system design into **layers** for complex diagrams

| Strengths | Trade-offs |
|---|---|
| macOS/iOS native — excellent platform integration | Apple ecosystem only |
| Strong illustration and annotation features | Not available on Windows/Linux |
| Layer-based organization for complex diagrams | Less suited for heavy UML modeling |

### 2.4 Draw.io (diagrams.net)

==Draw.io== is a free, open-source diagramming tool available both online and as a desktop application.

> [!info] Key Capabilities
> - Completely free — no license required
> - Supports flowcharts, process diagrams, org charts, UML, ER diagrams, network diagrams
> - **Visio import** — open and edit `.vsdx` files directly
> - Integrates with Google Drive, OneDrive, Confluence, Jira, GitHub, and GitLab
> - Available as a VS Code extension and desktop app

| Strengths | Trade-offs |
|---|---|
| Free and open-source | Less polished UI than paid tools |
| Broad notation support | Fewer advanced modeling features than EA or Visio |
| Excellent platform integrations | No built-in real-time collaboration (browser version aside) |
| Visio import/export | |

### 2.5 Gliffy

==Gliffy== is a cloud-based diagramming tool with HTML5 support, notable for its Confluence and Jira integrations.

> [!info] Key Capabilities
> - HTML5-based — no plugins required
> - Drag-and-drop interface for UML diagrams and flowcharts
> - **Real-time sharing and editing** of diagrams
> - Native Confluence and Jira integration
> - Used by Twilio, Pixar, Netflix, Nike, and Harvard

| Strengths | Trade-offs |
|---|---|
| Seamless Confluence/Jira integration | Subscription-based |
| Real-time collaboration | Smaller shape library than draw.io or Visio |
| Simple, clean interface | Limited advanced notation support |

### 2.6 Lucidchart

==Lucidchart== is a web-based collaborative diagramming platform used by major enterprises.

> [!info] Key Capabilities
> - Runs entirely in an HTML5 browser — no third-party plugins (no Adobe Flash)
> - Collaborative drawing, revising, and sharing in real time
> - Broad diagram support: UML, BPMN, flowcharts, wireframes, org charts, network diagrams
> - Integrates with Google Workspace, Microsoft 365, Confluence, Slack, and others
> - Used by Uber, Google, Amazon, Visa, and others

| Strengths | Trade-offs |
|---|---|
| Best-in-class real-time collaboration | Paid subscription for full features |
| Enterprise-grade integrations | Template quality varies by diagram type |
| No software installation needed | Requires internet connection |
| Widely recognized in enterprises | |

### 2.7 PlantUML

==PlantUML== is an open-source tool that generates UML diagrams from plain text descriptions.

> [!info] Key Capabilities
> - Defines diagrams in a simple text language (not drag-and-drop)
> - Supports class, sequence, activity, use case, component, deployment, and state diagrams
> - Uses **Graphviz** for automatic layout generation
> - Free web server for in-browser diagram creation
> - **Accessibility** — assists visually impaired software engineers in designing and interpreting UML diagrams
> - Integrates with documentation tools (Markdown, AsciiDoc, Confluence, GitLab)

| Strengths | Trade-offs |
|---|---|
| Diagrams as code — version-controllable | Text-based learning curve |
| Automatic layout (no manual positioning) | Less control over exact visual layout |
| Free and open-source | Limited to UML (less support for BPMN, ArchiMate) |
| Accessible to visually impaired users | Requires Graphviz installation for local use |

## 3. Tool Comparison at a Glance

| Tool | Free | Web-based | Collaboration | Notation Breadth | Best For |
|---|---|---|---|---|---|
| Enterprise Architect | No | No (desktop) | Yes | Very broad | Complex enterprise modeling |
| Microsoft Visio | No | Partial | Yes | Broad | Microsoft ecosystem teams |
| OmniGraffle | No | No (macOS/iOS) | Limited | Moderate | Apple-ecosystem visual design |
| Draw.io | Yes | Yes | Limited | Broad | Budget-conscious teams, Confluence |
| Gliffy | No | Yes | Yes | Moderate | Confluence/Jira-heavy teams |
| Lucidchart | Freemium | Yes | Excellent | Broad | Enterprise collaboration |
| PlantUML | Yes | Yes | Via VCS | UML-focused | Diagrams-as-code, documentation |

## 4. Choosing the Right Tool

> [!example] Decision Hints
> - **Full UML/BPMN/ArchiMate modeling with code generation** → Enterprise Architect
> - **Microsoft 365 team with data-linked diagrams** → Microsoft Visio
> - **macOS-only team with visual/illustration needs** → OmniGraffle
> - **Free tool with broad notation support and Visio import** → Draw.io
> - **Confluence/Jira-integrated team** → Gliffy or Draw.io (Confluence plugin)
> - **Real-time collaboration across large enterprise teams** → Lucidchart
> - **Diagrams as code, version control, accessible design** → PlantUML
> - **General team, cloud-first, no budget** → Draw.io or Lucidchart (free tier)

## Summary

Online and desktop diagramming tools have become central to architectural practice. Web-based platforms like Draw.io and Lucidchart are gaining popularity for their efficiency, ease of use, and collaboration features. They support a wide range of notation types — from general flowcharts to UML and BPMN — and integrate with platforms like Confluence. The right tool depends on team size, notation requirements, budget, and platform ecosystem. No single tool is best for all contexts — but matching tool to context is itself an application of the Notations Selection principles.

## Related Notes

- [[Notations Selection]]
- [[Semi-Formal Notations - Unified Modeling Language]]
- [[Semi-Formal Notations - BPMN]]
- [[Best Drawing Practices - Orthogonality]]
- [[Best Drawing Practices - Tidy Up]]
