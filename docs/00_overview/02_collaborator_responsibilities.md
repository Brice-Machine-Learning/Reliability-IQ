# Collaborator Responsibilities & Branch Ownership

This document defines how work is divided across collaborators for the Reliability IQ project.
The goal is to enable parallel progress while avoiding merge conflicts, duplicated effort, and unclear ownership.

Each major notebook or system component has a single primary owner.
Coordination is required before modifying work owned by someone else.

---

## Project Management & Backend Integration

Owner: Project Manager (PM)

Responsibilities:

- Overall project coordination and integration
- Backend architecture and API design
- Data contracts between notebooks and backend
- Final review and promotion of changes to main

Branches:

>- infra/backend-core
>- infra/api-foundation
>- infra/data-contracts
>- infra/integration

Only the PM merges pull requests into main.

---

## Baseline & Problem Framing

Notebook:

- 00_baseline.ipynb

Responsibilities:

- Define prediction targets and labels
- Document assumptions and constraints
- Identify class imbalance and data limitations
- Establish baseline expectations

Branch:

>- feature/baseline-analysis

---

## Exploratory Data Analysis (EDA)

Notebook:

- 01_eda.ipynb

Responsibilities:

- Explore raw and processed data
- Identify data quality issues
- Analyze distributions and anomalies
- Generate feature hypotheses

Branch:

>- feature/eda-initial

---

## Feature Engineering

Notebook:

- 02_feature_engineering.ipynb

Responsibilities:

- Convert EDA insights into engineered features
- Handle missing values and encoding strategies
- Document feature definitions and rationale

Branch:

>- feature/feature-engineering

---

## Baseline Modeling

Notebook:

- 03_modeling.ipynb

Responsibilities:

- Train baseline models
- Compare simple modeling approaches
- Avoid premature optimization
- Document modeling decisions

Branch:

>- feature/model-baseline

---

## Model Evaluation & Metrics

Notebook:

- 04_evaluation.ipynb

Responsibilities:

- Define evaluation metrics
- Perform error analysis
- Assess model stability and failure modes
- Document performance tradeoffs

Branch:

>- feature/model-evaluation

---

## Conclusions & Narrative

Notebook:

- 05_conclusion.ipynb

Responsibilities:

- Summarize findings across notebooks
- Translate results into operational insights
- Document limitations and next steps
- Ensure narrative consistency

Branch:

>- docs/conclusions-and-insights

---

## Collaboration Rules

- Each notebook has one primary owner
- Changes outside your ownership require coordination
- All work is done on feature branches created from develop
- All pull requests target develop
- The PM is responsible for final integration

This structure exists to keep the project coherent and reviewable as it scales.
