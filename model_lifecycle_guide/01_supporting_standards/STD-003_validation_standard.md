# STD-003 — Validation Standard

> **Status: PLACEHOLDER — content to be completed**  
> **Document type:** Standard (Level 3)  
> **Parent document:** [Model Lifecycle Guide](../00_guide/README.md)  
> **Applies to lifecycle stages:** 6.5 (Independent Validation), 6.9 (Change — revalidation)  
> **Owner:** Model Risk Management

---

## Purpose

This standard defines the **minimum scope, methodology, and independence requirements** for independent model validation. It implements Principle 6 (Independent Challenge) and Principle 7 (Segregation of Duties).

---

## Contents to Be Developed

<!-- TODO: Draft detailed provisions. Use SR 11-7 Section V and EBA Guidelines Chapter 5 as primary references. -->

### 1. Validation Independence Requirements
- Functional independence: who may validate.
- Reporting line requirements.
- Conflict of interest management.
- Consequences of independence breach.

### 2. Validation Triggers
- Pre-deployment (all models).
- Material change (Section 6.9).
- Periodic revalidation (frequency by tier).
- Monitoring-triggered revalidation.
- Regulatory requirement.

### 3. Validation Scope by Tier

#### Tier 1 — Full Validation
- Conceptual soundness review.
- Data and assumptions review.
- Independent replication of key analyses.
- Independent performance testing.
- Implementation testing.
- Ongoing monitoring assessment.

#### Tier 2 — Standard Validation
- Conceptual soundness review.
- Data and documentation review.
- Performance validation (may use developer results with independent challenge).
- Implementation assessment.

#### Tier 3 — Peer Review
- Qualified peer reviews methodology, data, and outputs.
- Documents findings in memo.

### 4. Validation Methodology
- Documentation review approach.
- Independent testing approach.
- Benchmarking.
- Sensitivity analysis.
- Back-testing (for models with observable outcomes).

### 5. Findings Classification
- Critical / High / Medium / Low — definitions and treatment.
- Conditional approval criteria.

### 6. Validation Report Requirements
- Required sections.
- Quality criteria.
- Distribution and confidentiality.

### 7. Findings Management
- Closure timeline requirements by severity.
- Re-opening conditions.
- Exception / risk acceptance process for unresolved findings.

---

## Cross-References

| Document | Relationship |
|----------|-------------|
| [Model Lifecycle Guide — Stage 6.5](../00_guide/06_stage_requirements/05_independent_validation.md) | Parent framework |
| [PROC-002 — Validation Procedure](../02_procedures/PROC-002_validation_procedure.md) | Procedural implementation |
| [TMPL-002 — Validation Report](../03_templates/TMPL-002_validation_report.md) | Output template |
| [STD-005 — Change Management Standard](STD-005_change_management_standard.md) | Revalidation trigger |

---

*Key references: SR 11-7 (Section V), EBA/GL Model Risk Management (Chapter on validation), ECB Guide to Internal Models (validation chapter).*
