# Chapter 7 — Roles and Responsibilities

> **Status: DRAFT**  
> **Section:** Model Lifecycle Guide, Chapter 7

---

## 7.1 Purpose

Effective model governance depends on **clearly defined, unambiguous roles**. This chapter defines each role involved in the model lifecycle, its key responsibilities, and the principles that govern its independence.

For the RACI matrix showing role participation by lifecycle stage, see [Appendix A — RACI Matrix](12_appendices/A_raci_matrix.md).

---

## 7.2 Role Definitions

### 7.2.1 Data Scientist / Model Developer

**What:** The individual or team technically responsible for designing, building, testing, and documenting the model.

**Key responsibilities:**
- Translate the business need into a model design.
- Select and implement appropriate methodology with documented rationale.
- Ensure reproducibility and version control throughout development.
- Prepare and maintain complete development documentation.
- Conduct testing and provide results.
- Respond to validation findings.
- Support deployment and handover.
- Implement approved changes under change management process.

**Independence note:** The Developer may not act as Independent Validator for the same model.

---

### 7.2.2 Model Owner

**What:** The senior business individual who is **accountable** for the model throughout its lifecycle — from initiation to retirement.

**Key responsibilities:**
- Sponsor and justify the model at initiation.
- Confirm that the model continues to be fit for purpose.
- Oversee model use and ensure it is used within approved scope.
- Receive and act on monitoring reports.
- Account for findings and conditions arising from validation.
- Approve retirement decisions.
- Ensure governance obligations are met.

**Note:** The Model Owner is the primary accountable party. Operational duties may be delegated, but accountability is not transferable.

---

### 7.2.3 Model User

**What:** The individual or team that uses model outputs to make decisions, provide recommendations, or generate reports.

**Key responsibilities:**
- Use the model within its approved scope and intended use.
- Report anomalies, unexpected outputs, or operational concerns to the Model Owner.
- Participate in UAT.
- Adhere to any conditions attached to model approval.

---

### 7.2.4 Independent Validator

**What:** A qualified individual or team responsible for providing an **independent, objective assessment** of the model prior to deployment and upon material change or revalidation triggers.

**Key responsibilities:**
- Conduct validation in accordance with [STD-003](../01_supporting_standards/STD-003_validation_standard.md) and [PROC-002](../02_procedures/PROC-002_validation_procedure.md).
- Assess conceptual soundness, data, methodology, and implementation.
- Document findings; classify by severity.
- Issue Validation Report.
- Track and confirm resolution of material findings.

**Independence requirement:** Must be functionally independent of the development team. Reports to MRM or governance, not to the business unit owning the model.

---

### 7.2.5 Model Risk Management (MRM)

**What:** The **second-line oversight function** responsible for the bank's model governance framework.

**Key responsibilities:**
- Maintain and update this Guide and supporting standards.
- Maintain the model inventory.
- Review and confirm model tier assignments.
- Oversee validation quality and independence.
- Facilitate governance committee reviews.
- Monitor aggregate model risk across the portfolio.
- Report to senior management and board on model risk.
- Manage exceptions and escalations.

---

### 7.2.6 Business Sponsor / Senior Stakeholder

**What:** Senior business owner who sponsors the model project and provides organisational resources and support.

**Key responsibilities:**
- Endorse the business case at initiation.
- Support governance participation.
- Receive senior-level risk reporting.

---

### 7.2.7 Data Owner / Data Steward

**What:** The individual responsible for the governance, quality, and availability of specific data assets used by the model.

**Key responsibilities:**
- Confirm data availability and access rights.
- Ensure data quality standards are met.
- Support data lineage documentation.
- Manage data privacy and regulatory compliance for data assets.

---

### 7.2.8 IT / MLOps / Engineering

**What:** The technical team responsible for the production infrastructure supporting model deployment and operations.

**Key responsibilities:**
- Implement models in production environments.
- Ensure environment segregation.
- Conduct SIT.
- Maintain model artefacts in version control.
- Support monitoring infrastructure.
- Implement rollback procedures when required.
- Archive model artefacts at retirement.

---

### 7.2.9 Compliance

**What:** The function responsible for ensuring adherence to applicable laws, regulations, and internal policies.

**Key responsibilities:**
- Confirm regulatory compliance requirements applicable to specific models.
- Review models used in decisions subject to consumer protection or anti-discrimination regulation.
- Advise on GDPR and data privacy implications.
- Review change management for regulatory impact.

---

### 7.2.10 Internal Audit

**What:** The **third-line assurance function** that provides independent assurance to the Board on model governance effectiveness.

**Key responsibilities:**
- Audit model governance framework and its implementation.
- Review compliance with this Guide and supporting standards.
- Report findings to the Audit Committee.
- Note: Internal Audit is not part of the operational model lifecycle — it provides assurance over the process.

---

### 7.2.11 Governance Committees

**What:** The formal bodies that hold approval authority for models and model governance matters.

**Examples:** <!-- TODO: Replace with actual committee names. -->
- Model Risk Committee
- Credit Risk Committee (for credit models)
- Asset and Liability Committee (ALCO) (for financial models)
- Board Risk Committee

**Key responsibilities:**
- Review and approve models at defined stage gates.
- Set risk appetite for model risk.
- Oversee aggregate model risk portfolio.
- Review and approve this Guide and material exceptions.

---

## 7.3 Summary Table

| Role | Primary lifecycle stage(s) | Independence required |
|------|---------------------------|----------------------|
| Data Scientist / Developer | 2, 3, 4, 9 | — |
| Model Owner | All | — |
| Model User | 7, 8 | — |
| Independent Validator | 5, 9 (revalidation) | Yes — from development |
| MRM | All (oversight) | Yes — second line |
| Data Owner / Steward | 2 | — |
| IT / MLOps | 7, 9, 10 | — |
| Compliance | 1, 4, 6, 9 | — |
| Internal Audit | Assurance (not lifecycle) | Yes — third line |
| Governance Committees | 6, 9 (material), 1 (Tier 1) | Yes — governance |

---

*See [Appendix A — RACI Matrix](12_appendices/A_raci_matrix.md) for detailed stage-by-stage responsibility assignment.*

*Previous: [Chapter 6 — Stage Requirements](06_stage_requirements/README.md)*  
*Next: [Chapter 8 — Required Artifacts](08_required_artifacts.md)*
