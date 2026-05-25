# AI Governance Workflow (EU AI Act Aligned)

## Overview

This repository defines an end-to-end AI governance workflow aligned with the **EU AI Act**, covering:

- Risk-based classification of AI systems  
- Structured risk assessment (triage + detailed evaluation)  
- Conformity assessment for high-risk AI systems  
- Regulatory compliance obligations and reporting  

The model establishes a **clear separation of responsibilities** across three core entities:

- 🔵 **Business Units** – Execution and risk ownership  
- 🟢 **AI Centre of Excellence (AI CoE)** – Governance, validation, and approval  
- 🟠 **AI Ethics & Compliance Committee** – Legal oversight and regulatory assurance  
- 🔴 **EU AI Act Obligations** – External compliance and reporting  

---

# EU AI Act — Governance Operating Model

A two-stage triage model for moving an AI use case from idea to production — safely, and at speed.

> **v2.0** &nbsp;·&nbsp; Owner: AI CoE — Governance &nbsp;·&nbsp; Scope: all AI/ML use cases, EU operations
> **SLA:** Fast lane ≤ 5 days &nbsp;·&nbsp; Full review ≤ 20 days &nbsp;·&nbsp; Reviewed quarterly by the Risk &amp; Audit Committee
> **Anchor:** Regulation (EU) 2024/1689 (EU AI Act)

## What this is

This repository documents an operating model for governing AI under the EU AI Act. Its design goal is to keep governance proportionate: the majority of use cases carry little regulatory risk and should not be slowed by a process built for the minority that do. The model therefore runs a lightweight self-service triage at intake, reserves formal categorization and assessment for cases that need it, and routes only high-risk systems to a single board-level approval gate. Technical, vendor and fundamental-rights reviews run in parallel rather than as sequential handoffs, and the monitoring stage feeds the same record created at intake so that any system is audit-ready by default.

The detailed process — phases, steps, owners, decision logic and regulatory mapping — lives in [`operating-model/`](operating-model/README.md).

## The model at a glance

```mermaid
flowchart TD
    Idea([AI use-case idea]) --> S1

    S1["01 · FORM<br/>Submit use case<br/>→ Intake record"]
    S2["02 · SELF-SERVE<br/>5-question binary triage<br/>→ Triage decision"]
    S1 --> S2 --> Triage{"&gt;70%<br/>self-clear?"}

    Triage -->|"fast lane · low-risk bypass"| S8
    Triage -->|"needs formal review"| S3

    S3["03 · FORMAL · 24h<br/>EU AI Act categorization<br/>→ Risk tier + route"]
    S3 --> Tier{Risk tier?}

    Tier -->|prohibited| Stop([Blocked at intake — no exceptions])
    Tier -->|minimal / limited| S8
    Tier -->|high risk| S4 & S5 & S6

    S4["04 · TECHNICAL<br/>Model · data · bias · security · DPIA<br/>→ Assessment dossier"]
    S5["05 · VENDOR DD<br/>Third-party AI only<br/>→ Vendor pack"]
    S6["06 · FRIA<br/>Fundamental Rights Impact Assessment<br/>→ FRIA report"]

    S4 & S5 & S6 --> S7{"07 · GATE<br/>Board reviews combined dossier"}

    S7 -->|reject| Rej([Not deployed])
    S7 -->|approve / conditional| S8

    S8["08 · REGISTER<br/>AI inventory · logging · oversight · rollback<br/>→ Inventory entry"]
    S9["09 · GO-LIVE<br/>Launch · brief users · disclose<br/>→ User disclosure"]
    S8 --> S9 --> S10

    S10["10 · MONITOR<br/>Drift · fairness · performance<br/>→ Monitoring KPIs"]
    S11["11 · OVERSIGHT<br/>Quarterly portfolio review<br/>→ Audit-ready record"]
    S12["12 · OPERATE<br/>Run within controls · report incidents &lt;72h<br/>→ Incident log"]

    S10 --> S11
    S10 --> S12 --> S10
    S10 -.->|"material change → re-assess"| S3

    classDef bu fill:#E8F0FE,stroke:#3B6FD4,color:#0B1F44
    classDef coe fill:#E9F7EF,stroke:#1E8E5A,color:#0B2A1C
    classDef legal fill:#FEF3E0,stroke:#D98A0B,color:#3A2700
    classDef board fill:#F3E8FE,stroke:#7B3FD4,color:#240B44
    classDef decision fill:#FFFFFF,stroke:#5B6470,color:#1A1F26
    classDef stop fill:#FDECEC,stroke:#D14343,color:#4A0D0D

    class S1,S2,S9,S12 bu
    class S3,S4,S5,S8,S10 coe
    class S6 legal
    class S7,S11 board
    class Triage,Tier,Idea decision
    class Stop,Rej stop
```

**Lane colours** — blue: Business Unit · green: AI CoE · amber: Legal &amp; Compliance · purple: AI Risk Governance Board.

## Risk classification (EU AI Act, Art. 5–6)

| Tier | Examples | Obligation |
|---|---|---|
| **Minimal** | Spam filters, internal productivity tools | Voluntary code of conduct only |
| **Limited** | Chatbots, generative content | Transparency &amp; disclosure obligations |
| **High** | HR, credit, critical infrastructure | Full conformity assessment &amp; FRIA |
| **Prohibited** | Social scoring, manipulation | Blocked at intake — no exceptions |

## Repository structure

```
.
├── README.md                  ← you are here: model overview + diagram
└── operating-model/
    ├── README.md              ← detailed process: phases, steps, owners, routing, regulatory mapping
    └── workflow.mmd           ← canonical Mermaid source for the workflow diagram
```

## Source

Operating model: *EU AI Act — Governance Operating Model v2.0* (AI Risk Assessment Model).
Regulatory basis: Regulation (EU) 2024/1689 — <https://eur-lex.europa.eu>.

## Workflow Diagram

![AI Governance Workflow](assets/ai-governance-workflow-3.pdf)

