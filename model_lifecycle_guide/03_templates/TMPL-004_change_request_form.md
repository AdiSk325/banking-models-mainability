# TMPL-004 — Change Request Form

> **Template version:** DRAFT  
> **Standard:** [STD-005 — Change Management Standard](../01_supporting_standards/STD-005_change_management_standard.md)  
> **Procedure:** [PROC-004 — Change Request Procedure](../02_procedures/PROC-004_change_request_procedure.md)

---

# Model Change Request Form

| Field | Value |
|-------|-------|
| Change Request ID | [assigned by MRM] |
| Model ID | |
| Model Name | |
| Current Model Version | |
| Proposed New Version | |
| Request Date | |
| Requested by | |
| Model Owner | |
| Target Implementation Date | |

---

## Section 1 — Change Description [REQUIRED]

### 1.1 Summary of Proposed Change
<!-- Describe the change in plain language: what is changing and why. -->

### 1.2 Detailed Technical Description
<!-- For developers and validators: specify what is changing in the model (methodology, features, parameters, code, data, etc.). -->

### 1.3 Reason / Driver for Change
- [ ] Performance deterioration (monitoring-triggered)
- [ ] Business requirement change
- [ ] Regulatory requirement
- [ ] Data change (new source / feature unavailable)
- [ ] Technology / infrastructure change
- [ ] Other: *[specify]*

---

## Section 2 — Impact Assessment [REQUIRED]

### 2.1 Expected Impact on Model Outputs
<!-- Estimated change in model scores / outputs. Provide quantitative estimates if available. -->

### 2.2 Expected Impact on Model Performance
<!-- Will the change improve / maintain / potentially degrade performance? Rationale. -->

### 2.3 Affected Systems and Users
<!-- Which production systems, downstream processes, and users will be affected? -->

### 2.4 Regulatory / Reporting Impact
<!-- Will this change affect regulatory capital, reporting, or disclosures? -->

---

## Section 3 — Change Classification [REQUIRED]

**Proposed classification by requester:**
- [ ] Material Change
- [ ] Non-Material Change
- [ ] Emergency Change

**Rationale for classification:**
<!-- Explain why you believe this is material / non-material. -->

**MRM confirmation of classification:**
- [ ] Confirmed Material
- [ ] Confirmed Non-Material
- [ ] Re-classified as: *[specify]*

MRM reviewer: _________________ Date: _________________

---

## Section 4 — Governance Requirements [COMPLETED BY MRM]

Based on classification, the following governance steps are required:

| Step | Required? | Notes |
|------|----------|-------|
| Re-testing | ✅ / — | |
| Revalidation | ✅ Full / ✅ Partial / — | |
| Re-approval (governance forum) | ✅ / — | Which forum: |
| Documentation update | ✅ / — | |
| Monitoring plan update | ✅ / — | |

---

## Section 5 — Approvals [REQUIRED]

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Model Owner | | | |
| MRM | | | |
| Governance Forum (if material) | | | |

---

## Section 6 — Post-Implementation

| Field | Value |
|-------|-------|
| Actual implementation date | |
| New version number | |
| Inventory updated | ✅ / — |
| Monitoring plan updated | ✅ / N/A |
| Closed by | |

---

*Template: TMPL-004 | Standard: STD-005 | Version: DRAFT*
