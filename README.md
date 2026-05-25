## Workflow Diagram

```mermaid
flowchart LR

subgraph BU[Business Units]
    B1[1. Use Case Initiation]
    B2[2. Register AI System]
    B3[3. Risk Self-Assessment]
    B4[4. Provide Evidence]
    B9[9. Deploy AI System]
    B10[10. Monitoring]
end

subgraph COE[AI CoE]
    A1[5. Risk Classification]
    A2[6. Review and Challenge]
    A3{7. High Risk?}
    A4[8. Conformity Assessment]
    A5[9. Approval]
    A6[Reassessment Trigger]
end

subgraph LEGAL[AI Ethics and Compliance]
    L1[Legal Review]
    L2[Compliance Sign-Off]
end

B1 --> B2 --> A1
A1 --> B3
B3 --> B4 --> A2
