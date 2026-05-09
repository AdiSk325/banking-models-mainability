# TMPL-003 — Monitoring Plan

> **Template version:** DRAFT  
> **Standard:** [STD-004 — Monitoring Standard](../01_supporting_standards/STD-004_monitoring_standard.md)  
> **Note:** This plan must be completed and approved BEFORE model go-live (Stage 6.7).

---

# Model Monitoring Plan

| Field | Value |
|-------|-------|
| Model ID | |
| Model Name | |
| Model Tier | 1 / 2 / 3 |
| Plan Version | |
| Plan Date | |
| Monitoring Owner | |
| MRM Reviewer | |
| Review Frequency | Monthly / Quarterly / Semi-annual / Annual |

---

## Section 1 — Model Overview [REQUIRED]

<!-- Brief description of the model, its use, and the monitoring objectives. -->

---

## Section 2 — Performance Monitoring Metrics [REQUIRED]

<!-- For each metric: name, description, data source, calculation, threshold, and escalation action. -->

| Metric | Description | Data source | Frequency | Green threshold | Amber threshold | Red threshold | Breach action |
|--------|-------------|-------------|-----------|----------------|----------------|--------------|--------------|
| Gini / AUC | Discrimination | [source] | Monthly | > X | X–Y | < Y | Review + escalate to MRM |
| KS Statistic | Separation | | | | | | |
| PSI | Score stability | | | < 0.10 | 0.10–0.25 | > 0.25 | Full review |
| CSI — [feature] | Feature stability | | | < 0.10 | 0.10–0.25 | > 0.25 | Investigate |
| Predicted vs. Actual rate | Calibration | | | ±X% | ±Y% | > ±Z% | Recalibration review |
| Override rate | Usage anomaly | | Monthly | < X% | X–Y% | > Y% | Escalate to Owner |

---

## Section 3 — Data Quality Monitoring [REQUIRED]

| Data quality metric | Source | Frequency | Threshold | Action on breach |
|--------------------|--------|-----------|-----------|-----------------|
| Missing rate — [key feature] | | | < X% | Investigate source |
| Out-of-range values | | | < X% | Flag for review |
| Data latency | | | < X hours | IT escalation |

---

## Section 4 — Business Outcome Monitoring [REQUIRED for Tier 1–2]

<!-- Track actual outcomes against model predictions where observable (e.g., actual default rates). -->

| Metric | Description | Frequency | Action on adverse trend |
|--------|-------------|-----------|------------------------|
| | | | |

---

## Section 5 — Trigger Events [REQUIRED]

The following events will automatically trigger an escalated model review, regardless of metric thresholds:

- [ ] Any metric reaches **Red** threshold.
- [ ] A material change to the model's input data feed.
- [ ] Significant economic, regulatory, or market event affecting the model's domain.
- [ ] Model override rate exceeds [X]% for [N] consecutive periods.
- [ ] [Other model-specific trigger].

---

## Section 6 — Escalation Protocol [REQUIRED]

| Event | Notified party | Timeline | Action required |
|-------|--------------|----------|----------------|
| Amber threshold breach | Model Owner | Next reporting cycle | Document and monitor |
| Red threshold breach | Model Owner + MRM | Within 5 business days | Formal review |
| Trigger event | Model Owner + MRM | Immediately | Convene review |
| Two consecutive amber breaches | Model Owner + MRM | | Elevate to formal review |

---

## Section 7 — Reporting Schedule [REQUIRED]

| Report type | Frequency | Produced by | Distributed to | Format |
|-------------|-----------|-------------|---------------|--------|
| Routine monitoring report | [frequency] | | Model Owner, MRM | Markdown / dashboard |
| Annual periodic review | Annual | | MRM, Committee | Formal report |
| Ad-hoc trigger report | On trigger | | MRM, Model Owner | Memo |

---

## Section 8 — Monitoring Plan Review [REQUIRED]

This plan will be reviewed:
- Annually as part of the periodic model review.
- Upon any material change to the model.
- If monitoring data or methodology changes.

Next scheduled review: *[date]*

---

*Template: TMPL-003 | Standard: STD-004 | Version: DRAFT*
