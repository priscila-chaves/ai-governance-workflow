# Operating Model — AI Risk Assessment

**EU AI Act compliance · v2.0**

How an AI use case moves from idea to production — safely, and at speed. This document is the detailed reference for the model summarised in the [repository README](../README.md).

| | |
|---|---|
| **Owner** | AI CoE — Governance |
| **Scope** | All AI/ML use cases, EU operations |
| **SLA** | Fast lane ≤ 5 days · Full review ≤ 20 days |
| **Review cadence** | Quarterly — Risk &amp; Audit Committee |
| **Regulatory anchor** | Regulation (EU) 2024/1689 (EU AI Act) |

## Purpose and scope

The model exists to make AI governance proportionate. Most use cases an organisation runs are minimal- or limited-risk and should reach production quickly; a smaller set is high-risk and warrants a full conformity assessment, a fundamental-rights review and an executive approval. A single uniform process either over-controls the former or under-controls the latter. This model resolves that by triaging early and cheaply, then concentrating scrutiny where the regulation — and the risk — actually require it.

It applies to every AI/ML use case in EU operations, regardless of whether the system is built in-house or procured. Procured systems pick up one additional step (vendor due diligence) but follow the same path.

## Design principles

Four choices make the process fast without weakening control.

**Two-stage triage.** The Business Unit self-clears the use case through a five-question binary screen at intake. The target is for more than 70% of cases to clear without any CoE involvement; the CoE only reviews the remainder. This keeps central capacity focused on cases that genuinely need expert categorization.

**Parallel, not sequential.** For high-risk systems the technical assessment, vendor due diligence and the Legal-led FRIA run side-by-side. There is no idle handoff time between them — the three reviews converge on the board gate rather than queuing behind one another.

**One board gate only.** Board approval is triggered exclusively for high-risk systems. Minimal- and limited-risk cases are delegated and never reach the board. The gate is a single meeting producing a single record — not a standing committee that re-reviews low-stakes work.

**Continuous and evidence-linked.** Live monitoring feeds the same record created at intake. Because the intake record, assessment dossier, board decision and monitoring KPIs are one continuous artifact, any system is audit-ready by default rather than reconstructed on demand.

## Risk classification (EU AI Act, Art. 5–6)

Formal categorization (Step 03) places every use case into one of four tiers.

| Tier | Typical examples | Obligation under this model |
|---|---|---|
| **Minimal** | Spam filters, internal productivity tools | Voluntary code of conduct only. No CoE review required. |
| **Limited** | Chatbots, generative content | Transparency and disclosure obligations. User-facing notices and watermarking at go-live. |
| **High** | HR, credit, critical infrastructure | Full conformity assessment and FRIA. Routed to parallel review and the board gate. |
| **Prohibited** | Social scoring, manipulation | Blocked at intake — no exceptions. Stopped at Step 03. |

## Workflow — seven phases, twelve steps

The process is organised into seven phases (Intake → Classify → Assess → Review → Approve → Deploy → Monitor), decomposed into twelve steps.

| Step | Phase | Owner | Action | Output |
|---|---|---|---|---|
| **01 · FORM** | Intake | Business Unit | Sponsor files a one-page intake in the AI portal: purpose, data, users, expected impact. | Intake record |
| **02 · SELF-SERVE** | Intake | Business Unit | Answer five binary questions — HR, credit, biometrics, safety, public-facing. Targets &gt;70% cleared without CoE review. | Triage decision |
| **03 · FORMAL** *(auto, 24h)* | Classify | AI CoE | Apply EU AI Act tests to cases not cleared at triage. Prohibited use cases are stopped here. | Risk tier + route |
| **04 · TECHNICAL** | Assess | AI CoE | Assess model, data, bias, security and DPIA. Produces the technical evidence pack for the board dossier. | Assessment dossier |
| **05 · VENDOR DD** | Assess | AI CoE | Third-party AI only: technical docs, training-data provenance, security and IP indemnities. Escalate gaps to procurement. | Vendor pack |
| **06 · FRIA** | Assess | Legal &amp; Compliance | Fundamental Rights Impact Assessment, GDPR alignment and contractual review. Runs in parallel with Step 04. | FRIA report |
| **07 · GATE** | Review &amp; Approve | AI Risk Governance Board | Review the combined dossier (Steps 04, 05, 06). Decision: Approve, Conditional or Reject. One meeting, one record. | Board decision |
| **08 · REGISTER** | Deploy | AI CoE | Log into the central AI inventory; wire up event logging (6-month rolling retention), human-oversight hooks and a rollback plan. | Inventory entry |
| **09 · GO-LIVE** | Deploy | Business Unit | Activate the use case, brief end-users, publish transparency notices and watermarking where required. | User disclosure |
| **10 · MONITOR** | Monitor | AI CoE | Drift, fairness and performance dashboards. Re-assess on retrain, architecture change, new data or change of purpose. | Monitoring KPIs |
| **11 · OVERSIGHT** | Monitor | Risk &amp; Audit Committee | Quarterly review of monitoring KPIs, incidents and regulator updates. Retires or re-tiers use cases. | Audit-ready record |
| **12 · OPERATE** | Monitor | Business Unit | Operate within agreed controls; report any incident or material change within 72 hours. | Incident log |

## Ownership and accountability

Four functions own the model end-to-end. Each phase has a single accountable owner.

**Business Unit (Use-case Sponsor)** — Defines the business need, owns the product, and is accountable for safe operation in its domain. *Accountable: BU Product Owner.*

**AI Center of Excellence (CoE)** — Runs the process, classifies risk, executes technical assessments, and maintains the AI inventory. *Accountable: Head of AI Governance.*

**Legal &amp; Compliance** — Owns regulatory interpretation, fundamental-rights review, and the conformity assessment record. *Accountable: DPO / AI Compliance Lead.*

**AI Risk Governance Board** — The single approval gate for high-risk systems. Accountable to the Executive Committee and to the external regulator. *Chaired by the Chief AI Officer.*

## Decision gates and routing logic

The model has three branch points.

The **triage gate** (after Step 02) splits the flow. Cases that self-clear take the fast lane straight to registration (Step 08), bypassing CoE review entirely. Cases that do not clear are routed to formal categorization.

The **classification gate** (after Step 03) routes by risk tier. Prohibited use cases are stopped permanently. Minimal- and limited-risk cases proceed directly to registration. Only high-risk cases enter parallel assessment.

The **board gate** (Step 07) is the single approval point for high-risk systems. The board reviews the combined dossier and returns one of three decisions: Approve, Conditional (deploy subject to named remediations) or Reject (not deployed).

## Monitoring and re-assessment

Deployment is not the end of the process. Live monitoring (Step 10) tracks drift, fairness and performance against KPIs, and the quarterly portfolio review (Step 11) reconciles those KPIs with incidents and regulator updates, retiring or re-tiering systems as needed.

A system re-enters the workflow at formal categorization (Step 03) on any **material change**, defined as: a retrain, an architecture change, the introduction of new data, or a change of purpose. A change of purpose is significant because it can move a system into a different risk tier. Incidents and material changes must be reported within 72 hours (Step 12).

## Regulatory mapping and scope notes

This model is an internal operating standard built on the EU AI Act. Two points are worth stating precisely so the documentation does not over- or under-claim against the regulation.

**FRIA scope.** The model applies a Fundamental Rights Impact Assessment to every high-risk system as a uniform internal control. The AI Act's FRIA obligation (Art. 27) is in fact narrower — it binds only certain *deployers* of high-risk systems (public bodies, private providers of public services, and deployers of the creditworthiness and insurance-pricing use cases). Applying FRIA to all high-risk systems is therefore a deliberate decision to exceed the legal minimum for consistency; it should be documented as policy, not presented as a strict statutory requirement for every case.

**Conformity assessment.** "Full conformity assessment" for high-risk systems should be read against the Act's own routing — the assessment procedure (internal control vs. third-party notified-body assessment) depends on the high-risk category in question. The board dossier is the internal record supporting that assessment; it does not replace any external notified-body step where one is required.

**Logging and transparency.** The 6-month rolling event-logging retention (Step 08) and the user-facing transparency notices and watermarking (Step 09) correspond to the Act's logging and transparency duties; retention periods and disclosure wording should be confirmed against the current text and any implementing guidance.

These notes do not change the workflow. They flag where the model is a policy choice layered on top of the regulation, which is the distinction an auditor or regulator will expect to see made explicit.

## Diagram source

The canonical Mermaid source for the workflow diagram is [`workflow.mmd`](workflow.mmd). It renders directly on GitHub and in any Mermaid-compatible tool. The same diagram is embedded in the [repository README](../README.md) for at-a-glance viewing.

---

*Source: EU AI Act — Governance Operating Model v2.0. Regulatory basis: Regulation (EU) 2024/1689 — eur-lex.europa.eu.*
