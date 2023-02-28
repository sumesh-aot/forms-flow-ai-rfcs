# Title of RFC

| Status        | (Proposed / Accepted / Implemented / Obsolete)       |
:-------------- |:---------------------------------------------------- |
| **RFC PR #**     |  |
| **Author(s)** | Sumesh Kaariyil (sumesh.pk@aot-technologies.com) |


## Objective


## Motivation

```mermaid
graph TD
  A[Open Source Repository] --> B[Master Branch]
  B --> C[Feature Branch]
  C --> D[Development Branch]
  D --> E[Release Branch]
  D --> F[Hotfix Branch]
  E --> G[Tag Release]
  F --> G
  C --> H[Forked Repository]
  H --> I[Feature Branch]
  I --> J[Development Branch]
  J --> K[Release Branch]
  J --> L[Hotfix Branch]
  K --> M[Tag Release]
  L --> M
  K --> N[Private Repository]
  N --> O[Feature Branch]
  O --> P[Development Branch]
  P --> Q[Release Branch]
  P --> R[Hotfix Branch]
  Q --> S[Tag Release]
  R --> S

```

```mermaid
graph TD
  S1[forms-flow-ai OSS] --> C2[Master]
  C2 --> S2[Fork]
  S2 --> S3[forms-flow-ai-ee]
  S3 --> S4[Master Branch]
  S4 --> C3[Development Branch]
  C3 --> C4[Premium Feature branch]
  C4 --> C3
  C3 --> C5[Release]
  C5 --> C6[Build private image]
  C5 --> S4

  C2 --> O3[Development Branch]
  O3 --> O4[Public Feature branch]
  O4 --> O3
  O3 --> O5[Release]
  O5 --> O6[Build public image]
  O5 --> O7[Create a PR to closed repo]
  O7 --> C3
  O5 --> O2

```

## Proposal

$$