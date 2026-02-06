# Data Sources

This document describes the data sources used by **Reliability IQ**, including scope, provenance, and access instructions.  
Raw datasets are **not redistributed** in this repository. Contributors are expected to download source data directly from the original provider.

---

## Primary Dataset: Digital Payment System Transaction Records

### Description

The primary dataset used in this project consists of **transaction-level records from a digital payment system**, published as an open research dataset on Zenodo.

The dataset contains anonymized transaction events with attributes such as:

- Transaction identifiers
- Timestamps
- Monetary amounts
- Transaction channels or types
- Status and outcome fields
- Additional metadata relevant to transaction processing

The structure is representative of real payment or transaction processing systems and is suitable for analyzing **transaction outcomes, failure behavior, retries, and escalation patterns**.

This dataset is used as the foundation for:

- Transaction outcome classification
- Failure and recovery analysis
- Operational prioritization and ranking logic

---

### Source & Provenance

- **Repository:** Zenodo  
- **Record ID:** 17092322  
- **Dataset URL:**  
  <https://zenodo.org/records/17092322>

Zenodo is operated by CERN and OpenAIRE and is widely used for publishing research datasets with stable identifiers and long-term availability.

All dataset metadata, documentation, and licensing terms are maintained by the original author(s) on the Zenodo record page.

---

### Access Instructions

Contributors should obtain the raw dataset directly from the source:

1. Navigate to the dataset page:  
   <https://zenodo.org/records/17092322>
2. Review the dataset description, files, and license information.
3. Download the raw data files as provided by the author.
4. Place downloaded files in the local data directory specified in the project architecture documentation.
5. Do **not** commit raw data files to this repository.

Any preprocessing, validation, or transformation steps are handled by project ingestion pipelines and documented separately.

---

### Licensing & Usage

Dataset usage is governed by the license specified on the Zenodo record page.  
All contributors are responsible for ensuring their use of the data complies with the stated license terms.

This project:

- Uses the dataset for educational and portfolio demonstration purposes
- Does not redistribute the raw data
- References the original source for transparency and attribution

---

### Notes on Realism and Scope

Due to privacy, regulatory, and security constraints, **real customer transaction data is not publicly released by financial institutions**. This dataset provides a structurally realistic alternative, capturing the behaviors and signals relevant to transaction reliability and operational analysis without exposing sensitive information.

The project focuses on **system behavior and operational decision support**, not on financial forecasting, fraud detection, or individual customer modeling.

---

## Future Data Sources

Additional datasets may be incorporated to:

- Extend coverage across transaction types or systems
- Support stress testing and scenario analysis
- Validate robustness of classification and prioritization logic

Any new data source will be documented in this file prior to use.
