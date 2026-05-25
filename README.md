# AI Governance Workflow (EU AI Act Aligned)

This repository contains the reference operating model, workflow, and governance structure for managing AI risk and conformity assessments aligned with the EU AI Act.

## 🔷 Overview

This model defines interaction between three core entities:

- 🟦 Business Units (Infrastruttura, Trasporto, Altri Servizi)
- 🟩 AI CoE (Centralised AI Office)
- 🟧 AI Ethics & Compliance Committee (Legal / Compliance)

The workflow ensures:
- Risk-based governance
- Scalable AI oversight
- Audit readiness
- Compliance with EU AI Act

---

## 🔷 Workflow Diagram

```mermaid
flowchart LR

subgraph BU[🟦 Business Units\n(Infrastruttura | Trasporto | Altri Servizi)]
    B1[1. Use Case Initiation\nDefine purpose & scope]
    B2[2. Register AI System\n+ Metadata]
    B3[3. Risk Self-Assessment]
    B4[4. Provide Evidence]
    B9[9. Deploy]
    B10[10. Monitoring]
end

subgraph COE[🟩 AI CoE]
    A1[5. Risk Classification]
    A2[6. Review & Challenge]
    A3{7. High-Risk?}
    A4[8. Conformity Assessment]
    A5[9. Approval]
    A6[Reassessment Trigger]
end

subgraph LEGAL[🟧 AI Ethics & Compliance]
    L1[Legal Review]
    L2[Compliance Sign-Off]
end

B1 --> B2 --> A1
A1 --> B3
B3 --> B4 --> A2
A2 --> A3

A3 -->|No| A5
A3 -->|Yes| A4

A4 --> L1 --> L2 --> A5

A5 --> B9
B9 --> B10

B10 --> A6
A6 --> A2
