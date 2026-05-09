# STD-004 — Monitoring Standard

> **Status: PLACEHOLDER — content to be completed**  
> **Document type:** Standard (Level 3)  
> **Parent document:** [Model Lifecycle Guide](../00_guide/README.md)  
> **Applies to lifecycle stages:** 6.8 (Monitoring and Periodic Review)  
> **Owner:** Model Risk Management

---

## Purpose

This standard defines the **minimum monitoring requirements** for all deployed models, including metric types, thresholds, reporting frequency, trigger events, and governance of monitoring results. It implements Principle 9 (Monitoring Throughout the Lifecycle).

---

## Contents to Be Developed

<!-- TODO: Draft detailed provisions. -->

### 1. Monitoring Plan Requirements
- What must be in a monitoring plan before go-live.
- Metric selection rationale.
- Threshold-setting methodology.
- Escalation protocol integration.

### 2. Required Metric Categories

| Category | Key Metrics | Frequency |
|----------|------------|-----------|
| Predictive performance | Gini, AUC, KS, accuracy, precision, recall | Tier 1: monthly; Tier 2: quarterly; Tier 3: semi-annual |
| Calibration | Predicted vs. actual rate, Brier score | Per reporting cycle |
| Stability | PSI (overall), CSI (per feature) | Per reporting cycle |
| Data quality | Missing rate, out-of-range, source latency | Per scoring run |
| Usage | Override rate, non-usage rate | Monthly |
| Business outcomes | Actual loss rate, customer outcomes | Quarterly / annual |

### 3. Threshold Framework
- Green / Amber / Red threshold definitions.
- How to set thresholds at model deployment.
- Threshold review and update process.

### 4. Trigger Events
- Automatic review triggers (threshold breach).
- Business / environmental triggers.
- Regulatory triggers.
- Escalation requirements on trigger.

### 5. Periodic Review Requirements
- Minimum review frequency by tier.
- Required content of periodic review.
- Who conducts and approves the review.

### 6. Reporting Requirements
- Report format and content.
- Distribution requirements (Owner, MRM, Committee).
- Aggregated portfolio monitoring reporting.

### 7. Monitoring of Models on Conditions or Exceptions
- Enhanced monitoring requirements.
- Escalation path.

---

## Cross-References

| Document | Relationship |
|----------|-------------|
| [Model Lifecycle Guide — Stage 6.8](../00_guide/06_stage_requirements/08_monitoring_periodic_review.md) | Parent framework |
| [TMPL-003 — Monitoring Plan](../03_templates/TMPL-003_monitoring_plan.md) | Template |
| [STD-005 — Change Management Standard](STD-005_change_management_standard.md) | Monitoring may trigger change |

---

*Key references: SR 11-7 (Section on ongoing monitoring), EBA Guidelines (monitoring chapter), internal model performance standards.*
