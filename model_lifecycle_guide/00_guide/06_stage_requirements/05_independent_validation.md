# Stage 6.5 — Independent Validation

> **Status: DRAFT**  
> **Section:** Model Lifecycle Guide, Chapter 6.5

---

## Purpose

Independent Validation is the bank's primary mechanism for ensuring that models are **conceptually sound, technically correct, and fit for their intended use** before deployment. This stage provides an independent, objective challenge to the work of the development team and is a core requirement of model governance under both internal policy and regulatory expectation.

Validation is not a sign-off exercise — it is a substantive, risk-based assessment.

---

## Entry Criteria

- Documentation and Testing Complete sign-off obtained (Stage 6.4 complete).
- Full validation handover package submitted to the Validator.
- Validation scope agreed between MRM, Validator, and Model Owner.

---

## Independence Requirements

The validator must be **functionally independent** of the model development team. Specifically:
- The validator must not have participated in the model's design or development.
- The validator reports to a governance structure independent of the business unit developing the model.
- For Tier 1 models: validation must be conducted by or under the oversight of the Model Risk Management function.
- For Tier 2 models: validation by independent specialist within MRM or a designated validation team.
- For Tier 3 models: peer review by a qualified colleague not involved in development; MRM oversight still required.

<!-- TODO: Confirm organisational independence arrangements with HR and governance. -->

---

## Key Activities

1. **Scope definition** — agree the scope and depth of validation proportionate to model tier.
2. **Documentation review** — assess completeness and quality of the development documentation.
3. **Conceptual soundness review** — evaluate the appropriateness and rationale for the chosen methodology.
4. **Data review** — independently assess data quality, representativeness, and lineage.
5. **Replication / independent testing** — replicate key analyses and/or conduct independent testing.
6. **Performance assessment** — independently assess model performance using validation datasets.
7. **Assumption challenge** — critically evaluate key modelling assumptions.
8. **Limitation assessment** — assess whether limitations are fully identified and appropriately mitigated.
9. **Implementation check** — confirm that the production implementation matches the validated model.
10. **Findings documentation** — document all findings, classify by severity, and discuss with developer.
11. **Produce Validation Report** — issue formal Validation Report with conclusions and findings.
12. **Findings resolution** — track and confirm resolution of material findings before approval.

---

## Validation Findings Classification

| Severity | Definition | Treatment |
|----------|-----------|-----------|
| **Critical** | Material flaw that prevents approval; must be resolved before deployment | Model cannot be deployed until resolved |
| **High** | Significant finding that materially limits the model's reliability | Must be resolved or risk-accepted by governance before approval |
| **Medium** | Notable limitation or weakness; mitigating action recommended | Remediation plan required; may proceed with conditions |
| **Low / Informational** | Minor observation or improvement suggestion | Noted; to be addressed in next development cycle |

---

## Roles

| Role | Responsibility |
|------|---------------|
| Independent Validator | Conducts validation; issues findings and validation report |
| Data Scientist / Developer | Provides documentation; responds to findings |
| Model Owner | Accountable for resolving material findings |
| MRM | Oversees validation quality; approves validation report |

---

## Required Outputs / Artifacts

| Artifact | Tier 1 | Tier 2 | Tier 3 |
|----------|--------|--------|--------|
| Validation Report | ✅ Full | ✅ Full | 🟡 Peer review memo |
| Findings Log | ✅ Required | ✅ Required | 🟡 If findings |
| Findings Resolution Record | ✅ Required | ✅ Required | 🟡 If findings |

---

## Exit Criteria / Stage Gate

✅ **Validation Passed** (or **Conditional Approval**) before proceeding to Stage 6.6.

Options:
- **Validated — No material findings:** Proceed to Approval.
- **Validated with conditions:** Proceed to Approval with documented conditions (mitigating actions, monitoring requirements, or time-limited approval).
- **Not validated:** Model must be revised and resubmitted for validation.

---

## Linked Documents

| Document | Type | Reference |
|----------|------|-----------|
| Validation Standard | Standard | [STD-003](../../01_supporting_standards/STD-003_validation_standard.md) |
| Validation Procedure | Procedure | [PROC-002](../../02_procedures/PROC-002_validation_procedure.md) |
| Validation Report template | Template | [TMPL-002](../../03_templates/TMPL-002_validation_report.md) |

---

*Previous: [Stage 6.4 — Testing and Documentation](04_testing_documentation.md)*  
*Next: [Stage 6.6 — Approval and Governance Review](06_approval_governance.md)*
