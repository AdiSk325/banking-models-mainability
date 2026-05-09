# Stage 6.8 — Monitoring and Periodic Review

> **Status: DRAFT**  
> **Section:** Model Lifecycle Guide, Chapter 6.8

---

## Purpose

Monitoring is a **permanent, ongoing obligation** for every deployed model. Models that perform well at deployment may degrade over time due to data drift, population shifts, behavioural changes, economic cycles, or product changes. This stage ensures that model performance is continuously tracked, deterioration is detected, and appropriate action is taken.

Monitoring is not a post-deployment afterthought — the Monitoring Plan must be established before go-live (see Stage 6.7).

---

## Entry Criteria

- Model is deployed and in production use (Stage 6.7 complete).
- Monitoring Plan is active and approved.
- Reporting infrastructure is in place.

---

## Key Activities

### Ongoing Monitoring

1. **Execute monitoring plan** — run scheduled monitoring reports at defined frequency.
2. **Performance monitoring** — track predictive power, discrimination (Gini, AUC, KS), and calibration.
3. **Stability monitoring** — assess population stability (PSI) and characteristic stability (CSI).
4. **Data quality monitoring** — monitor upstream data for quality degradation, missing values, or distribution shifts.
5. **Override / usage anomaly monitoring** — track model overrides; escalate unusual patterns.
6. **Business outcome tracking** — where outcomes are observable (e.g., actual defaults), track against model predictions.
7. **Escalation on breach of thresholds** — when a monitoring metric breaches a defined threshold, escalate per the escalation protocol.
8. **Monitoring reports** — produce and distribute periodic monitoring reports to Model Owner, MRM, and governance.

### Periodic Review

9. **Conduct periodic model review** — at minimum annually for all tiers (more frequently for Tier 1 and for models on watch).
10. **Holistic fitness-for-purpose assessment** — assess whether the model remains fit for its current use, given any changes in the environment, business, regulation, or population.
11. **Review findings and recommendations** — document review conclusions; escalate if revalidation or recalibration is required.

---

## Monitoring Metric Categories

| Category | Examples |
|----------|---------|
| **Predictive performance** | Gini coefficient, AUC-ROC, KS statistic, accuracy, precision, recall |
| **Calibration** | Predicted vs. actual default rate, Brier score |
| **Stability** | Population Stability Index (PSI), Characteristic Stability Index (CSI) |
| **Data quality** | Missing rate, out-of-range values, upstream data latency |
| **Usage patterns** | Override rate, model non-usage rate, input anomalies |
| **Business outcomes** | Actual loss rates, customer behaviour, portfolio performance |

<!-- TODO: Define specific thresholds per metric category in STD-004. -->

---

## Trigger Events for Escalated Review

The following events automatically trigger an escalated model review:
- Monitoring metric breaches a pre-defined threshold (red threshold).
- Significant change in the model's operating environment (economic, regulatory, data).
- Material change to the product or process the model supports.
- Regulatory or audit finding related to the model.
- Model is identified as contributing to unexpected business outcomes.
- Passage of defined time since last revalidation (see tier requirements).

---

## Roles

| Role | Responsibility |
|------|---------------|
| Data Scientist / MLOps | Executes monitoring; produces reports |
| Model Owner | Receives reports; accountable for response to triggers |
| MRM | Oversees monitoring quality; reviews escalations |
| Business Users | Report anomalies; participate in periodic review |

---

## Required Outputs / Artifacts

| Artifact | Tier 1 | Tier 2 | Tier 3 |
|----------|--------|--------|--------|
| Monitoring Plan (established at deployment) | ✅ Full | ✅ Standard | ✅ Basic |
| Periodic monitoring reports | ✅ Quarterly | ✅ Semi-annual | ✅ Annual |
| Annual periodic review record | ✅ Required | ✅ Required | ✅ Required |
| Escalation / trigger event records | ✅ Required | ✅ Required | ✅ Required |

---

## Linked Documents

| Document | Type | Reference |
|----------|------|-----------|
| Monitoring Standard | Standard | [STD-004](../../01_supporting_standards/STD-004_monitoring_standard.md) |
| Monitoring Plan template | Template | [TMPL-003](../../03_templates/TMPL-003_monitoring_plan.md) |
| Change Management stage | Guide | [Stage 6.9](09_change_management.md) |

---

*Previous: [Stage 6.7 — Deployment and Implementation Controls](07_deployment_implementation.md)*  
*Next: [Stage 6.9 — Change Management](09_change_management.md)*
