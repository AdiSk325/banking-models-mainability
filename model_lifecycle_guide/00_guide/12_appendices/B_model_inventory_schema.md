# Appendix B — Model Inventory Schema

> **Status: DRAFT**  
> **Section:** Model Lifecycle Guide, Appendix B

---

## Overview

Every model subject to this Guide must have an entry in the central **Model Inventory**. This appendix defines the minimum required fields for each inventory entry.

The model inventory is maintained by MRM. See [PROC-003 — Model Inventory Procedure](../../02_procedures/PROC-003_model_inventory_procedure.md) for operational instructions.

---

## Required Fields

### Identification

| Field | Description | Required |
|-------|-------------|---------|
| Model ID | Unique identifier (system-generated) | ✅ |
| Model Name | Official name of the model | ✅ |
| Model Version | Current production version | ✅ |
| Model Type | Statistical / ML / Rule-based / Vendor | ✅ |
| Model Tier | 1 / 2 / 3 | ✅ |
| Status | Draft / In Development / In Validation / Approved / Deployed / Retired | ✅ |

### Business Context

| Field | Description | Required |
|-------|-------------|---------|
| Business Line | Owning business unit | ✅ |
| Model Owner | Named individual | ✅ |
| Intended Use | Description of what decisions the model supports | ✅ |
| Use Type | Regulatory capital / Business decision / Reporting / Analytics | ✅ |
| Decision Automation Level | Fully automated / Hybrid / Human in loop | ✅ |
| Applicable Regulation | E.g., IRB, IFRS 9, GDPR | ✅ if applicable |

### Technical Details

| Field | Description | Required |
|-------|-------------|---------|
| Methodology | Brief description of approach | ✅ |
| Key Inputs / Features | Main input variables | ✅ |
| Output Type | Score / Probability / Classification / Amount | ✅ |
| Production System | System(s) where model is deployed | ✅ |
| Code Repository | Link to version-controlled code | ✅ |

### Governance Lifecycle

| Field | Description | Required |
|-------|-------------|---------|
| Development Start Date | | ✅ |
| Last Validation Date | | ✅ |
| Last Approval Date | | ✅ |
| Approving Authority | Committee or individual | ✅ |
| Approval Conditions | Any conditions attached to current approval | ✅ if applicable |
| Next Review Due Date | | ✅ |
| Last Monitoring Report Date | | ✅ |
| Current Monitoring Status | Green / Amber / Red | ✅ |
| Open Validation Findings | Count and highest severity | ✅ |
| Active Exceptions | Y / N; reference to exception record | ✅ |

### Retirement (if retired)

| Field | Description | Required |
|-------|-------------|---------|
| Retirement Date | | ✅ if retired |
| Reason for Retirement | Replaced / Discontinued / Performance | ✅ if retired |
| Successor Model ID | | If applicable |
| Archive Location | | ✅ if retired |

---

*Back to: [Appendices](README.md)*
