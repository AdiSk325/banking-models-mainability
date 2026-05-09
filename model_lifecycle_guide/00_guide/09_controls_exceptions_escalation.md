# Chapter 9 — Controls, Exceptions and Escalation

> **Status: DRAFT**  
> **Section:** Model Lifecycle Guide, Chapter 9

---

## 9.1 Purpose

This chapter defines the **governance controls** built into the model lifecycle, the **exception management process** for situations where requirements cannot be met, and the **escalation framework** for issues that exceed normal operational boundaries.

---

## 9.2 Control Framework

The model lifecycle incorporates controls at multiple levels:

### 9.2.1 Preventive Controls (built into process)

| Control | Purpose | Where Applied |
|---------|---------|--------------|
| Tier assignment | Ensures proportionate governance from the start | Stage 6.1 |
| Stage gates | Prevent progression without mandatory sign-offs | All stages |
| Segregation of duties | Prevent self-approval of models | Stages 3, 5, 6 |
| Independent validation | Objective challenge before deployment | Stage 6.5 |
| Release readiness checklist | Confirm deployment controls before go-live | Stage 6.7 |
| Change classification | Ensure changes receive appropriate governance | Stage 6.9 |
| Monitoring plan before go-live | Ensure monitoring is active from day one | Stages 6.7–6.8 |

### 9.2.2 Detective Controls (ongoing)

| Control | Purpose | Where Applied |
|---------|---------|--------------|
| Ongoing monitoring | Detect performance degradation | Stage 6.8 |
| Threshold alerts | Automated detection of metric breaches | Stage 6.8 |
| Annual periodic review | Periodic holistic assessment | Stage 6.8 |
| Model inventory review | Identify inactive / unmonitored models | Continuous |
| Audit | Independent assurance on governance compliance | Third line |

### 9.2.3 Corrective Controls (response)

| Control | Purpose | Where Applied |
|---------|---------|--------------|
| Escalation protocol | Ensure timely response to issues | Any stage |
| Findings closure tracking | Ensure validation findings are resolved | Stage 6.5 |
| Material change process | Govern corrections to deployed models | Stage 6.9 |
| Conditions monitoring | Track and close approval conditions | Stage 6.6+ |
| Exception management | Manage controlled departures from requirements | Any stage |

---

## 9.3 Governance Forums

<!-- TODO: Replace placeholders with actual committee names and meeting frequencies. -->

| Forum | Role | Scope | Frequency |
|-------|------|-------|-----------|
| **Model Risk Committee** (or equivalent) | Senior approval and oversight | Tier 1 approvals; aggregate model risk | Quarterly (or monthly) |
| **MRM Function** | Operational governance | Tier 2 approvals; inventory; exceptions | Ongoing |
| **Business Risk Committee** | Business-line oversight | Tier 2 models; business-line monitoring | As per governance calendar |
| **Audit Committee** | Third-line oversight | MRM audit findings | Per audit cycle |

---

## 9.4 Exception Management

### What Is an Exception?

An exception is a **formally approved, time-limited departure** from a requirement of this Guide or its supporting standards, granted when full compliance is not possible or practical.

Exceptions are **not** a mechanism to bypass governance — they require formal approval, documented rationale, compensating controls, and an active remediation plan.

### When Can an Exception Be Granted?

Examples of valid exception scenarios:
- A model urgently required by regulatory deadline, where timeline does not permit full validation.
- Unavailability of an independent validator for a specific model type (e.g., highly specialised methodology).
- Data unavailability that temporarily prevents a required test.
- Vendor model where certain documentation cannot be obtained (limitation to be compensated by enhanced monitoring).

### Exception Process

1. **Exception Request:** Raise a formal exception request documenting: the requirement being departed from, the reason, the duration, and proposed compensating controls.
2. **Risk Assessment:** MRM assesses the residual risk of granting the exception.
3. **Approval:** Exceptions are approved by:
   - MRM function head for minor exceptions.
   - Model Risk Committee for material exceptions (e.g., deployment without full validation).
4. **Conditions:** All approved exceptions must include: duration, compensating controls, and remediation plan.
5. **Tracking:** MRM maintains an active exception register.
6. **Closure:** Exceptions are closed when the underlying issue is resolved; extension requires re-approval.

See [PROC-006 — Exception Management Procedure](../02_procedures/PROC-006_exception_management_procedure.md).

---

## 9.5 Escalation Framework

### Escalation Triggers

The following events require immediate escalation to MRM and the Model Owner:

- A monitoring metric breaches a **critical threshold** defined in the Monitoring Plan.
- A model is identified as having been used **outside its approved scope**.
- A model produces **material errors** affecting business decisions or regulatory reporting.
- A **validation finding** is not resolved within the agreed timeframe.
- A model change is implemented **without appropriate governance approval**.
- A **regulatory or audit finding** is raised in relation to a specific model.

### Escalation Path

```
Discovery by Developer / User / Monitor
        │
        ▼
Model Owner notified immediately
        │
        ▼
MRM notified within [X] business days  ← TODO: define timing
        │
        ├── Minor issue → MRM tracks and monitors
        │
        └── Material issue → Model Risk Committee escalation
                  │
                  └── Board Risk Committee (if systemic or high impact)
```

<!-- TODO: Define specific timelines for escalation at each level. Align with operational risk escalation policy. -->

---

## 9.6 Model Use Restrictions

Models operating under approval conditions or exceptions must:
- Have conditions clearly communicated to Model Users.
- Be marked in the model inventory as operating under conditions / exception.
- Be subject to enhanced monitoring during the exception / condition period.
- Have a defined remediation timeline.

---

*Previous: [Chapter 8 — Required Artifacts](08_required_artifacts.md)*  
*Next: [Chapter 10 — Links to Supporting Documents](10_linked_documents.md)*
