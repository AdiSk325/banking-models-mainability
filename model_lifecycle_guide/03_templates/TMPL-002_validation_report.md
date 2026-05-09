# TMPL-002 — Validation Report

> **Template version:** DRAFT  
> **Standard:** [STD-003 — Validation Standard](../01_supporting_standards/STD-003_validation_standard.md)  
> **Procedure:** [PROC-002 — Validation Procedure](../02_procedures/PROC-002_validation_procedure.md)

---

# Independent Validation Report

| Field | Value |
|-------|-------|
| Model ID | |
| Model Name | |
| Model Version Validated | |
| Validation Date | |
| Validator(s) | |
| MRM Reviewer | |
| Validation Scope | Full / Standard / Peer Review |
| Overall Validation Conclusion | **[Validated / Validated with Conditions / Not Validated]** |

---

## Section 1 — Executive Summary [REQUIRED]

<!-- 1–2 paragraphs: overall conclusion, most significant findings, recommendation to governance. -->

*[PLACEHOLDER: Summarise the validation conclusion and key points.]*

---

## Section 2 — Model and Validation Context [REQUIRED]

### 2.1 Model Description
<!-- Brief description of what the model does, its intended use, and its tier. -->

### 2.2 Validation Scope
<!-- What was included in and excluded from this validation. Rationale for any scope limitations. -->

### 2.3 Documentation Reviewed
<!-- List all documents reviewed, with version/date. -->

| Document | Version | Date |
|----------|---------|------|
| Model Development Document | | |
| Data Assessment Report | | |
| | | |

### 2.4 Independence Statement
<!-- Confirm validator independence from development team. -->

---

## Section 3 — Documentation Completeness [REQUIRED]

<!-- Assess whether the development documentation meets the requirements of STD-002. -->

| Requirement | Met? | Comments |
|-------------|------|---------|
| Executive summary present | ✅ / ⚠️ / ❌ | |
| Business purpose documented | | |
| Data description complete | | |
| Methodology documented | | |
| Assumptions explicit | | |
| Performance results present | | |
| Limitations identified | | |
| [Other] | | |

Overall documentation assessment: *[Adequate / Partially adequate with findings / Inadequate]*

---

## Section 4 — Conceptual Soundness [REQUIRED]

### 4.1 Methodology Assessment
<!-- Is the chosen methodology appropriate for the intended use? Rationale reviewed and challenged. -->

### 4.2 Assumptions Assessment
<!-- Are key assumptions reasonable, documented, and stress-tested? -->

### 4.3 Conceptual Soundness Conclusion
*[Sound / Sound with observations / Concerns — see findings]*

---

## Section 5 — Data Assessment [REQUIRED]

### 5.1 Data Quality
<!-- Independent assessment of data quality and the developer's assessment. -->

### 5.2 Representativeness
<!-- Is the development sample representative of the intended production population? -->

### 5.3 Data Assessment Conclusion
*[Adequate / Adequate with limitations (noted) / Inadequate — see findings]*

---

## Section 6 — Performance Assessment [REQUIRED]

### 6.1 Independent Performance Results

| Metric | Developer result | Validator result | Consistent? |
|--------|-----------------|-----------------|-------------|
| Gini / AUC | | | |
| KS | | | |
| PSI | | | |
| [Other] | | | |

### 6.2 Performance Adequacy Assessment
<!-- Are performance levels adequate for intended use and tier? Benchmarking conclusion. -->

### 6.3 Performance Conclusion
*[Adequate / Adequate with monitoring conditions / Inadequate — see findings]*

---

## Section 7 — Findings Log [REQUIRED if findings exist]

| # | Finding | Severity | Section | Developer Response | Status |
|---|---------|----------|---------|-------------------|--------|
| F-001 | | Critical / High / Medium / Low | | | Open / Resolved / Risk-accepted |

---

## Section 8 — Validation Conclusion [REQUIRED]

### 8.1 Overall Conclusion

**Overall assessment:** *[Validated / Validated with Conditions / Not Validated]*

Conditions (if any):
1. 
2. 

### 8.2 Recommendation to Governance
<!-- Recommend: approve / approve with conditions / do not approve until critical findings resolved. -->

### 8.3 Post-Deployment Monitoring Requirements
<!-- Any specific monitoring requirements arising from validation. -->

---

## Section 9 — Appendices

<!-- Attach or reference independent test results, data extracts, additional analysis. -->

---

*Template: TMPL-002 | Standard: STD-003 | Version: DRAFT*
