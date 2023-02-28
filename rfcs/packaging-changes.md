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
  S3 --> S4[Prem. Master Branch]
  S4 --> C3[Prem. Development Branch]
  C3 --> C4[Prem. Feature branch]
  C4 --> C3
  C3 --> C5[Prem. Release]
  C5 --> C6[Build image]
  C6 --> C8[Push to docker private repo]
  C6 --> C7[Tag release]
  C5 --> S4

  C2 --> O3[OSS Development Branch]
  O3 --> O4[OSS Feature branch]
  O4 --> O3
  O3 --> O5[OSS Release]
  O5 --> O6[Build image]
  O6 --> O9[Push to docker public repo]
  O6 --> O8[Tag release]
  O5 --> O7[Create a PR to Prem.]
  O7 --> C3

```

## Proposal

$$