```mermaid
flowchart LR
  %% -------------------------------------------------
  %% Starter Template: Human-in-the-Loop Workflow
  %% Students: Replace TODO labels with your scenario,
  %% roles, risks, and decision logic.
  %% -------------------------------------------------

  A[TODO: Content brief submitted by ROLE] --> B[TODO: AI generates OUTPUT TYPE]

  B --> D[TODO: Human review checkpoint ROLE]

  D --> F{TODO: Reviewer decision criteria}

  F -- Approve --> G[TODO: Publish or deliver content]
  G --> H[TODO: Log approval metadata]
  H --> I[TODO: Capture feedback for improvement]
  I --> J[TODO: Update prompts, guidelines, or guardrails]

  F -- Edit --> K[TODO: Reviewer edits content]
  K --> L{TODO: Are changes material}
  L -- No --> G
  L -- Yes --> M[TODO: Regenerate or revise with AI using reviewer notes]
  M --> D

  F -- Reject --> N[TODO: Reject and block use]
  N --> O[TODO: Log rejection rationale]
  O --> E[TODO: Escalate to specialist ROLE]

  F -- Escalate --> E[TODO: Escalate to specialist ROLE]
  E --> P{TODO: Escalation outcome}
  P -- Approve --> G
  P -- Request changes --> M
  P -- Final reject --> N

  subgraph Notes
    R1[TODO: Risk controlled at review checkpoint]
    R2[TODO: Accountability mechanism]
    R3[TODO: Human-AI collaboration rule]
    R4[TODO: Feedback loop purpose]
  end

  R1 -.-> D
  R2 -.-> H
  R3 -.-> K
  R4 -.-> I