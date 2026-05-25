## Workflow Diagram

```mermaid
flowchart LR

subgraph BU[Business Units]
    B1[Use Case Initiation]
    B2[Register AI System]
    B3[Risk Assessment]
    B4[Provide Evidence]
    B9[Deploy AI System]
    B10[Monitoring]
end

subgraph COE[AI CoE]
    A1[Risk Classification]
    A2[Review and Challenge]
    A3{High Risk}
    A4[Conformity Assessment]
    A5[Approval]
    A6[Reassessment Trigger]
end

subgraph LEGAL[AI Ethics Compliance]
    L1[Legal Review]
    L2[Compliance Sign Off]
end

B1 --> B2 --> A1
A1 --> B3
B3 --> B4 --> A2
A2 --> A3

A3 -- No --> A5
A3 -- Yes --> A4

A4 --> L1
L1 --> L2
