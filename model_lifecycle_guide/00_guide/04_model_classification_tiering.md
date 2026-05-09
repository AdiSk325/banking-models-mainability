# Chapter 4 — Model Classification and Risk Tiering

> **Status: DRAFT**  
> **Section:** Model Lifecycle Guide, Chapter 4

---

## 4.1 Purpose

Not all models carry the same risk. A model used to drive regulatory capital calculations carries substantially greater risk than a simple segmentation tool used for internal analytics. The bank applies a **risk-based tiering system** to ensure that governance rigour is proportionate to model risk.

This chapter defines:
- The classification dimensions used to assess model risk.
- The tier definitions (Tier 1, 2, 3).
- The governance requirements that apply to each tier.
- The process for assigning and changing a model's tier.

---

## 4.2 Classification Dimensions

Model risk tier is determined by assessing the model across **six dimensions**:

| Dimension | Description | Considerations |
|-----------|-------------|----------------|
| **Financial / Business Impact** | Magnitude of potential loss or decision impact if the model fails or is misused | Credit decisions, pricing, regulatory capital, P&L impact |
| **Regulatory Significance** | Whether the model drives or supports regulatory capital, reporting, or mandatory disclosure | IRB models, IFRS 9, stress testing, AML/fraud |
| **Automation Level** | Degree to which model outputs drive automated decisions without human review | Fully automated decisioning vs. human-in-the-loop |
| **Complexity** | Technical and conceptual complexity of the model | ML/DL vs. linear models; exotic derivatives vs. standard credit scoring |
| **Explainability** | Ability to explain model outputs to clients, regulators, or courts | Black-box ML vs. interpretable models |
| **Data Sensitivity** | Whether the model processes personal data, sensitive client data, or proprietary data | GDPR relevance, data privacy risk |

---

## 4.3 Tier Definitions

### Tier 1 — Critical / High Risk

**Characteristics:**
- Directly drives regulatory capital, mandatory reporting, or has material financial impact.
- High automation: outputs drive decisions with limited or no human override.
- Complex methodology with limited explainability.
- Significant regulatory scrutiny expected (e.g., IRB models, IFRS 9 PD/LGD, stress testing).

**Governance requirements:**
- Full development documentation (see [STD-002](../01_supporting_standards/STD-002_model_documentation_standard.md)).
- Mandatory independent validation before deployment (see [Stage 6.5](06_stage_requirements/05_independent_validation.md)).
- Approval by senior governance committee.
- Formal monitoring plan with quarterly review.
- Annual revalidation, or sooner if triggered.
- Strict change management controls.

---

### Tier 2 — Significant / Medium Risk

**Characteristics:**
- Material business impact but not directly driving regulatory capital.
- Significant decision-making role (credit scoring, pricing, collections, churn).
- Some automation but with meaningful human oversight.
- Moderate complexity.

**Governance requirements:**
- Standard development documentation.
- Independent validation required before deployment; depth proportionate to risk.
- Approval by appropriate delegated authority.
- Monitoring plan with semi-annual review.
- Revalidation upon material change or significant performance deterioration.
- Standard change management controls.

---

### Tier 3 — Lower Risk / Internal Use

**Characteristics:**
- Internal analytics, management information, or decision-support tools.
- Outputs inform but do not directly drive significant decisions.
- Low complexity; high explainability.
- No direct regulatory capital or client-facing impact.

**Governance requirements:**
- Simplified documentation.
- Peer review acceptable in place of formal independent validation (MRM oversight still required).
- Approval by model owner and team lead.
- Annual monitoring review.
- Lighter-touch change management.

---

## 4.4 Tier Assignment Matrix

<!-- TODO: Build a scoring matrix that translates dimension ratings into tier assignment. Example approach below. -->

Each dimension is scored Low / Medium / High. The overall tier is determined by the highest risk dimension, adjusted for aggregate risk:

```
Any dimension = HIGH  →  Consider Tier 1
Multiple dimensions = MEDIUM  →  Consider Tier 2
All dimensions = LOW  →  Consider Tier 3
```

| Dimension | Low | Medium | High |
|-----------|-----|--------|------|
| Financial impact | < €500K | €500K – €10M | > €10M |
| Regulatory significance | No regulatory use | Regulatory reporting support | Regulatory capital / mandatory reporting |
| Automation | Human-reviewed output | Hybrid | Fully automated |
| Complexity | Linear / rule-based | Ensemble / tree-based | Deep learning / complex neural |
| Explainability | Fully explainable | Partially explainable | Black-box |
| Data sensitivity | Aggregated / anonymised | Pseudonymised personal data | Full personal / sensitive data |

> **Note:** Thresholds in the above table are indicative and subject to review by MRM. Calibrate with actual bank materiality thresholds. <!-- TODO: Confirm thresholds with Risk and Finance. -->

---

## 4.5 Tier Assignment Process

1. **Initial assessment** by the model developer at initiation, using the classification dimensions above.
2. **Review and confirmation** by MRM as part of model initiation approval.
3. **Re-assessment** required whenever there is a material change to the model's use, scope, or risk profile.
4. **Formal record** of tier assignment held in the model inventory.

---

## 4.6 Impact of Tier on Lifecycle Requirements

| Requirement | Tier 1 | Tier 2 | Tier 3 |
|-------------|--------|--------|--------|
| Full development documentation | ✅ Required | ✅ Required | 🟡 Simplified |
| Independent validation | ✅ Full | ✅ Standard | 🟡 Peer review |
| Senior committee approval | ✅ Required | 🟡 Delegated | 🟡 Owner approval |
| Monitoring plan | ✅ Quarterly | ✅ Semi-annual | ✅ Annual |
| Annual revalidation | ✅ Required | 🟡 On trigger | 🟡 Periodic review |
| Change management | ✅ Strict | ✅ Standard | 🟡 Lighter |
| Model inventory entry | ✅ Full | ✅ Full | ✅ Basic |

<!-- TODO: Align this table with actual bank procedures and committee structures. -->

---

## 4.7 Special Categories

### 4.7.1 Vendor / Third-Party Models

Vendor models are subject to the same tiering and governance requirements as internally developed models. The Model Owner is responsible for ensuring vendor model governance satisfies these requirements, including obtaining sufficient documentation from the vendor to support validation.

### 4.7.2 Experimental / Sandbox Models

Models in experimental or sandbox environments not driving live business decisions may follow a simplified process, but must be formally registered in the model inventory and upgraded to full lifecycle governance before deployment.

### 4.7.3 Legacy Models

Models in production prior to the effective date of this Guide must be assessed and tiered within [<!-- TODO: insert transition timeline -->] of its effective date.

---

*Previous: [Chapter 3 — Guiding Principles](03_guiding_principles.md)*  
*Next: [Chapter 5 — End-to-End Model Lifecycle Overview](05_lifecycle_overview.md)*
