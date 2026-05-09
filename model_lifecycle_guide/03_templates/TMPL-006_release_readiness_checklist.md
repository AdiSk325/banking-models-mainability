# TMPL-006 — Release Readiness Checklist

> **Template version:** DRAFT  
> **Standard:** [STD-006 — Deployment Standard](../01_supporting_standards/STD-006_deployment_standard.md)  
> **Usage:** Complete before every model go-live or material change deployment. All items must be checked before sign-off.

---

# Model Release Readiness Checklist

| Field | Value |
|-------|-------|
| Model ID | |
| Model Name | |
| Version being deployed | |
| Target deployment date | |
| Completed by | |
| Model Owner | |
| IT/MLOps Lead | |

---

## Part A — Governance Prerequisite Checks

| # | Check | Status | Evidence / Reference |
|---|-------|--------|---------------------|
| A1 | Formal approval obtained from required authority | ✅ / ❌ | Approval record: |
| A2 | All critical and high validation findings resolved or risk-accepted | ✅ / ❌ | Findings log ref: |
| A3 | All approval conditions documented | ✅ / N/A | Conditions register: |
| A4 | Model Development Document is finalised and version-controlled | ✅ / ❌ | Doc location: |
| A5 | Model inventory entry is up to date | ✅ / ❌ | |

---

## Part B — Technical Readiness Checks

| # | Check | Status | Evidence / Reference |
|---|-------|--------|---------------------|
| B1 | Production implementation matches the approved and validated model version (hash/commit verified) | ✅ / ❌ | Commit: |
| B2 | Code is in version-controlled repository with release tag | ✅ / ❌ | Repo / tag: |
| B3 | Development, testing, and production environments are strictly segregated | ✅ / ❌ | |
| B4 | All required UAT tests passed; UAT sign-off obtained | ✅ / ❌ | UAT record: |
| B5 | All required SIT tests passed; SIT sign-off obtained | ✅ / N/A | SIT record: |
| B6 | Rollback plan is documented and has been tested | ✅ / ❌ | Rollback plan ref: |
| B7 | Access controls implemented (role-based access; production modification restricted) | ✅ / ❌ | |
| B8 | Parallel run completed (Tier 1 mandatory; Tier 2 if replacing existing model) | ✅ / N/A | Parallel run results: |

---

## Part C — Monitoring Readiness Checks

| # | Check | Status | Evidence / Reference |
|---|-------|--------|---------------------|
| C1 | Monitoring Plan is documented, approved, and active | ✅ / ❌ | Monitoring Plan ref: |
| C2 | Production monitoring data collection is verified | ✅ / ❌ | |
| C3 | Alert thresholds are configured in the monitoring system | ✅ / ❌ | |
| C4 | First monitoring report date is scheduled | ✅ / ❌ | Scheduled date: |

---

## Part D — Operational Readiness Checks

| # | Check | Status | Evidence / Reference |
|---|-------|--------|---------------------|
| D1 | Model Owner has formally accepted operational responsibility | ✅ / ❌ | |
| D2 | Model User team has been trained / briefed on the model | ✅ / ❌ | |
| D3 | Known limitations and approval conditions are communicated to users | ✅ / ❌ | |
| D4 | Downstream system owners have confirmed readiness | ✅ / N/A | |

---

## Sign-Off [ALL REQUIRED]

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Model Owner | | | |
| IT/MLOps Lead | | | |
| MRM | | | |

---

**Deployment approved:** ✅ YES — all checks passed  
**Deployment deferred:** ❌ — outstanding items: *[list]*

---

*Template: TMPL-006 | Standard: STD-006 | Version: DRAFT*
