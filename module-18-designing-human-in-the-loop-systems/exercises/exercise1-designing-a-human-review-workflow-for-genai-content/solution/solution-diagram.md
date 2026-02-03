```mermaid
flowchart LR
  A[Content brief from content strategist] --> B[AI generates draft content]

  B --> D[Editor review checkpoint]

  D --> F{Editor decision}

  F -- Approve --> G[Publish content]
  G --> H[Log approval metadata]
  H --> I[Capture editorial feedback]
  I --> J[Update prompts and style guidance]

  F -- Edit --> K[Editor revises content]
  K --> L{Substantive changes}
  L -- No --> G
  L -- Yes --> M[Request AI revision with editor notes]
  M --> D

  F -- Reject --> N[Reject and block publication]
  N --> O[Log rejection rationale]
  O --> E[Escalate to managing editor]

  F -- Escalate --> E[Escalate to managing editor]
  E --> P{Escalation outcome}
  P -- Approve --> G
  P -- Request changes --> M
  P -- Final reject --> N

  subgraph Notes
    R1[Risk control: factual accuracy and hallucinations]
    R2[Risk control: tone, bias, and brand alignment]
    R3[Accountability: named editor and decision logs]
    R4[Learning loop: editorial feedback improves system]
  end

  R1 -.-> D
  R2 -.-> D
  R3 -.-> H
  R4 -.-> I