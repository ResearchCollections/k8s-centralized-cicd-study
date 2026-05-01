# Enterprise CI/CD Migration Dataset

## Overview
This repository contains the anonymized quantitative dataset used to evaluate the operational efficiency of migrating from a decentralized CI/CD approach to a Centralized CI/CD architecture.

The data was collected as part of a retrospective observational case study of an enterprise-scale Kubernetes migration involving over 300 microservices between April 2025 and early 2026. The primary metrics derived from this dataset are infrastructure-specific adaptations of DORA metrics: **Lead Time for Change**, **Mean Time to Restore (MTTR)**, and **Change Failure Rate (CFR)**.

## Dataset Schema
The data is provided in a single CSV file (`dataset.csv`). Each row represents a single operational configuration or remediation session (derived from recorded synchronous engineering meetings).

| Data Field | Format | Description |
| :--- | :--- | :--- |
| **Date Recorded** | `MM/DD/YYYY` | The chronological date the operational meeting took place. |
| **Meeting Duration** | `HH:MM:SS` | The total length of the active configuration or remediation session. |
| **Event Type** | `Categorical` | The primary operational purpose of the meeting (e.g., *Routine Deployment*, *Critical Bug Fix*, *Vulnerability*). |
| **Architecture / Phase** | `Categorical` | The architectural model in use at the time of the recorded event (*Legacy Decentralized*, *Transition*, *Centralized*). |
| **Apps Deployed** | `Integer` | The total volume of individual applications configured or patched during the session. |

## Context & Methodology
This dataset serves as the fundamental unit of analysis for evaluating the complex trade-offs of adopting a Platform Engineering approach. Meeting duration serves as a consistent observational proxy for the coordinating effort and cognitive load required in deployment-related operations across different architectural phases. 

*   **Lead Time for Change:** Calculated as `Total Session Duration / Number of Applications Deployed`.
*   **MTTR:** Calculated as the arithmetic mean of all emergency incident resolution sessions.
*   **Change Failure Rate:** Calculated as the ratio of strictly incident-dedicated meetings to the total volume of routine deployment configuration meetings.

## Data Availability and Confidentiality

Due to the proprietary nature of the enterprise environment observed, the published dataset has been rigorously anonymized to protect organizational confidentiality. All personally identifiable information (PII), internal application names, proprietary infrastructure details, and exact operational timestamps have been entirely redacted. The publicly available data is strictly limited to the generalized categorical variables and the raw quantitative metrics required to independently verify the calculations detailed in the research methodology.

**Disclaimer on Data Resemblance:** Care has been taken to ensure that the dataset cannot be reverse-engineered to expose sensitive company operations or specific incident responses. While the structural characteristics of the operational events have been preserved to maintain the statistical integrity of the study, the data has been aggregated and generalized. Consequently, any specific resemblance recognized by internal personnel regarding exact incidents, specific teams, or proprietary infrastructure is a byproduct of this standardization process and does not represent the exposure of confidential operational logs.
