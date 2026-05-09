# Stage 6.4 — Testing and Documentation

> **Status: DRAFT**  
> **Section:** Model Lifecycle Guide, Chapter 6.4

---

## Purpose

The Testing and Documentation stage ensures that the model has been rigorously evaluated against defined performance criteria and that the complete documentation package is in place before independent validation. This stage is the quality gate that protects the validation team and governance process from incomplete or under-tested models.

---

## Entry Criteria

- Development Complete sign-off obtained (Stage 6.3 complete).
- Test plan approved.
- Documentation structure is in place (at minimum: methodology, data, assumptions sections drafted).

---

## Key Activities

### Testing

1. **In-sample and out-of-sample performance testing** — assess predictive power (e.g., Gini, AUC, KS) on held-out data.
2. **Out-of-time testing** — validate performance on a time period not used in development.
3. **Stability testing** — assess Population Stability Index (PSI) and Characteristic Stability Index (CSI).
4. **Calibration testing** — verify that predicted probabilities (or scores) are well-calibrated against observed outcomes.
5. **Sensitivity / stress testing** — test model behaviour under adverse or extreme input scenarios.
6. **Benchmark comparison** — compare performance against challenger models or simpler benchmarks.
7. **Explainability analysis** — document feature importance, SHAP values, or partial dependence plots as appropriate to model tier and methodology.
8. **Bias and fairness assessment** — where the model is used in decisions affecting individuals, assess for potential discriminatory impacts.
9. **Implementation testing** — confirm that the scored outputs on the development platform match expected results.

### Documentation

10. **Complete Model Development Document** — ensure all required sections are completed (see [STD-002](../../01_supporting_standards/STD-002_model_documentation_standard.md)).
11. **Compile test results** — document all test results with interpretation.
12. **Prepare Limitations Summary** — consolidate all known model limitations and proposed mitigants / monitoring.
13. **Prepare Validation Handover Package** — assemble the full documentation package for independent validation.

---

## Roles

| Role | Responsibility |
|------|---------------|
| Data Scientist / Developer | Conducts tests; completes documentation |
| Model Owner | Reviews business logic and documentation; confirms fitness for validation |
| MRM | Reviews test plan for Tier 1; confirms documentation completeness |

---

## Required Outputs / Artifacts

| Artifact | Tier 1 | Tier 2 | Tier 3 |
|----------|--------|--------|--------|
| Complete Model Development Document | ✅ Full | ✅ Full | 🟡 Simplified |
| Performance test results | ✅ Required | ✅ Required | ✅ Required |
| Out-of-time test results | ✅ Required | ✅ Required | 🟡 Recommended |
| Stability test results (PSI/CSI) | ✅ Required | 🟡 Recommended | 🟡 Optional |
| Calibration test results | ✅ Required | ✅ Required | 🟡 If applicable |
| Stress / sensitivity test results | ✅ Required | 🟡 Recommended | — |
| Explainability analysis | ✅ Required | ✅ Required | 🟡 Summary |
| Bias / fairness assessment | ✅ Required | ✅ If applicable | 🟡 If applicable |
| Limitations summary | ✅ Required | ✅ Required | ✅ Required |
| Validation handover package | ✅ Required | ✅ Required | 🟡 Simplified |

---

## Exit Criteria / Stage Gate

✅ **Documentation and Testing Complete** sign-off before proceeding to Stage 6.5.

Confirms:
- All required tests have been completed and results are documented.
- Full Model Development Document is complete.
- Known limitations are explicitly stated.
- Validation handover package is assembled.

<!-- TODO: Define documentation completeness checklist — align with STD-002. -->

---

## Linked Documents

| Document | Type | Reference |
|----------|------|-----------|
| Model Documentation Standard | Standard | [STD-002](../../01_supporting_standards/STD-002_model_documentation_standard.md) |
| AI/ML Explainability Standard | Standard | [STD-008](../../01_supporting_standards/STD-008_ai_ml_explainability_standard.md) |
| Model Development Standard | Standard | [STD-001](../../01_supporting_standards/STD-001_model_development_standard.md) |
| Model Development Document template | Template | [TMPL-001](../../03_templates/TMPL-001_model_development_document.md) |
| Release Readiness Checklist | Template | [TMPL-006](../../03_templates/TMPL-006_release_readiness_checklist.md) |

---

*Previous: [Stage 6.3 — Design and Development](03_design_development.md)*  
*Next: [Stage 6.5 — Independent Validation](05_independent_validation.md)*
