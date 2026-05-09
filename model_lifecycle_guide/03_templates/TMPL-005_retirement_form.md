# TMPL-005 — Model Retirement Form

> **Template version:** DRAFT  
> **Procedure:** [PROC-005 — Retirement Procedure](../02_procedures/PROC-005_retirement_procedure.md)

---

# Model Retirement Form

| Field | Value |
|-------|-------|
| Model ID | |
| Model Name | |
| Current Version | |
| Retirement Request Date | |
| Requested by | |
| Model Owner | |
| Target Retirement Date | |
| Successor Model ID (if applicable) | |

---

## Section 1 — Reason for Retirement [REQUIRED]

- [ ] Replaced by successor model (ID: _______)
- [ ] Business use / product discontinued
- [ ] Performance no longer adequate; no recalibration warranted
- [ ] Regulatory requirement
- [ ] Merger / acquisition / reorganisation
- [ ] Other: *[specify]*

### Detailed Rationale
<!-- Explain the retirement decision with sufficient detail for the record. -->

---

## Section 2 — Impact Assessment [REQUIRED]

### 2.1 Current Active Users / Systems
<!-- List all systems and users currently receiving model outputs. -->

| User / System | Impact of retirement | Transition action |
|--------------|---------------------|------------------|
| | | |

### 2.2 Active Decisions / Portfolios
<!-- Are there any active loan books, products, or regulatory submissions relying on this model? -->

### 2.3 Regulatory Impact
<!-- Will retirement affect regulatory capital, reporting, or any current regulatory submission? -->

### 2.4 Data Retention and Privacy
<!-- Are there GDPR or other legal obligations that affect training data retention or deletion? -->

---

## Section 3 — Transition Plan [REQUIRED if successor model exists]

| Step | Description | Responsible | Target Date | Status |
|------|-------------|-------------|-------------|--------|
| Parallel run start | | | | |
| User communication | | | | |
| IT cutover | | | | |
| Decommission old model | | | | |

---

## Section 4 — Archival Plan [REQUIRED]

| Artefact | Archive location | Retention period | Responsible |
|----------|-----------------|-----------------|-------------|
| Model code (tagged version) | | 10 years | |
| Development documentation | | 10 years | |
| Validation reports | | 10 years | |
| Approval records | | 10 years | |
| Monitoring reports | | 7 years | |
| Training data reference | | Per data policy | |

Archive location root: *[specify repository / storage path]*

---

## Section 5 — Approvals [REQUIRED]

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Model Owner | | | |
| MRM | | | |

---

## Section 6 — Inventory Update Confirmation

| Action | Completed | Date |
|--------|-----------|------|
| Status set to "Retired" in inventory | | |
| Retirement date recorded | | |
| Archive location recorded | | |
| Successor model cross-referenced | | |
| Access revoked in production systems | | |

---

*Template: TMPL-005 | Procedure: PROC-005 | Version: DRAFT*
