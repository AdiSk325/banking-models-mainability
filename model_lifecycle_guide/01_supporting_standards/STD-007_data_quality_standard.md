# STD-007 — Data Quality Standard

> **Status: PLACEHOLDER — content to be completed**  
> **Document type:** Standard (Level 3)  
> **Parent document:** [Model Lifecycle Guide](../00_guide/README.md)  
> **Applies to lifecycle stages:** 6.2 (Data Sourcing and Assessment)  
> **Owner:** Model Risk Management / Data Governance

---

## Purpose

This standard defines the **minimum requirements for data quality assessment, data lineage documentation, and data governance** as they apply to model development and operation.

---

## Contents to Be Developed

<!-- TODO: Draft detailed provisions. Align with BCBS 239 and internal data governance framework. -->

### 1. Data Quality Dimensions

| Dimension | Definition | Assessment method |
|-----------|-----------|------------------|
| Completeness | All required values present | Missing rate by variable |
| Accuracy | Values reflect reality | Validation against source, range checks |
| Consistency | No conflicting values across sources | Cross-source comparison |
| Timeliness | Data is current when needed | Latency measurement |
| Validity | Values conform to expected format/range | Rule-based validation |
| Representativeness | Sample reflects target population | Population comparison |

### 2. Data Assessment Requirements
- Required scope of data assessment report.
- Minimum documentation for each data source.
- Treatment of known data quality issues.
- Data quality gate criteria (conditions under which model development may proceed despite issues).

### 3. Data Lineage Documentation Requirements
- Source system identification.
- Transformation steps documentation.
- Data dictionary requirements.
- GDPR / data privacy annotation.

### 4. Data Sampling and Representativeness
- Training / validation / test split requirements.
- Out-of-time period requirements.
- Reject inference requirements (for application scoring models).
- Survivorship bias assessment.

### 5. Ongoing Data Quality Monitoring
- Production data quality monitoring requirements.
- Data drift detection.
- Escalation on data quality deterioration.

### 6. Data Retention and Privacy
- Alignment with GDPR and data privacy requirements.
- Model training data retention and deletion obligations.
- Anonymisation and pseudonymisation requirements.

---

## Cross-References

| Document | Relationship |
|----------|-------------|
| [Model Lifecycle Guide — Stage 6.2](../00_guide/06_stage_requirements/02_data_sourcing_assessment.md) | Parent framework |
| [STD-001 — Development Standard](STD-001_model_development_standard.md) | Uses data quality outputs |
| [TMPL-001 — Model Development Document](../03_templates/TMPL-001_model_development_document.md) | Documentation template |

---

*Key references: BCBS 239 (Risk Data Aggregation and Reporting), GDPR, internal data governance policy.*
