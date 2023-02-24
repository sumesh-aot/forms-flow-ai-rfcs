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
  O1[Open Source Repository] --> C1[Fork a closed repo]
  C1 --> C2[Master]
  C2 --> C3[Development Branch]
  C3 --> C4[Feature branch]
  C4 --> C3
  C3 --> C5[Release]
  C5 --> C6[Build private image]

  O1 --> O2[Master]
  O2 --> O3[Development Branch]
  O3 --> O4[Feature branch]
  O4 --> O3
  O3 --> O5[Release]
  O5 --> O6[Build public image]


```

## Proposal

