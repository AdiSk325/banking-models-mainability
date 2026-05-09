# Open Questions

> **Purpose:** Track questions that need to be resolved before the Guide can be finalised.  
> **Format:** Each question should be numbered, tagged with priority, assigned, and have a resolution section.  
> **Status options:** ❓ Open | 🔄 In Progress | ✅ Resolved | ⛔ Blocked

---

## Q001 — Committee and Governance Structure 🔴 CRITICAL

**Question:** What are the actual names and mandates of the governance committees that will approve models?  
**Context:** The Guide refers to "Model Risk Committee" as a placeholder. The actual committee structure (names, remit, approval thresholds, meeting frequency) must be confirmed and inserted.  
**Assigned to:** *[TODO: Governance / MRM lead]*  
**Status:** ❓ Open  
**Resolution:** *[Fill in once confirmed]*

**Sections affected:** Ch. 6.6, Ch. 9, Appendix A (RACI)

---

## Q002 — Tiering Thresholds 🔴 CRITICAL

**Question:** What are the actual financial materiality thresholds for model tiering?  
**Context:** Chapter 4 includes indicative thresholds (e.g., < €500K / €500K–€10M / > €10M) that must be validated against the bank's actual risk appetite and materiality definitions.  
**Assigned to:** *[TODO: Risk / Finance]*  
**Status:** ❓ Open  
**Resolution:** *[Fill in once confirmed]*

**Sections affected:** Ch. 4, all tier-based requirement tables

---

## Q003 — Definition of "Model" — Policy Alignment 🔴 CRITICAL

**Question:** Is the Guide's definition of "model" consistent with the existing Model Risk Management Policy?  
**Context:** If the Policy has a different definition, the Guide must either align or explicitly note the difference.  
**Assigned to:** *[TODO: Legal / Compliance / MRM]*  
**Status:** ❓ Open  
**Resolution:** *[Fill in once confirmed]*

**Sections affected:** Ch. 1.2, Ch. 2

---

## Q004 — KNF-Specific Requirements 🟠 HIGH

**Question:** Are there specific current KNF recommendations or expectations that must be explicitly reflected in the Guide?  
**Context:** KNF has issued various recommendations affecting credit models in particular. These need to be reviewed and incorporated where applicable.  
**Assigned to:** *[TODO: Compliance]*  
**Status:** ❓ Open  
**Resolution:** *[Fill in once confirmed]*

**Sections affected:** Ch. 1.2 (scope), references, tier 1 requirements

---

## Q005 — EU AI Act Applicability Timeline 🟠 HIGH

**Question:** Which of the bank's current models are likely to be classified as "high-risk AI systems" under the EU AI Act, and what is the implementation timeline?  
**Context:** The AI Act is entering into force in stages. Credit scoring and automated decision-making models may be classified as high-risk. This affects STD-008 content and possibly model tiering.  
**Assigned to:** *[TODO: Legal / Compliance]*  
**Status:** ❓ Open  
**Resolution:** *[Fill in once confirmed]*

**Sections affected:** Ch. 4, STD-008

---

## Q006 — Retention Periods 🟡 MEDIUM

**Question:** Are the retention periods in Stage 6.10 (10 years for documentation, 7 years for monitoring reports) consistent with the bank's record retention policy and regulatory requirements?  
**Assigned to:** *[TODO: Legal / Compliance]*  
**Status:** ❓ Open  
**Resolution:** *[Fill in once confirmed]*

**Sections affected:** Ch. 6.10, TMPL-005

---

## Q007 — IT/MLOps Tooling Landscape 🟡 MEDIUM

**Question:** What version control, experiment tracking, model registry, and monitoring tools are currently available or planned?  
**Context:** STD-001 and STD-006 should provide tooling guidance consistent with what is actually available or being procured. Avoid mandating tools the bank doesn't have or plan to have.  
**Assigned to:** *[TODO: IT / Data Engineering]*  
**Status:** ❓ Open  
**Resolution:** *[Fill in once confirmed]*

**Sections affected:** STD-001, STD-006

---

## Q008 — Approval Authority Delegation for Tier 2/3 🟡 MEDIUM

**Question:** Who is the delegated approval authority for Tier 2 models? Is it the MRM function head, a sub-committee, or a senior risk manager?  
**Assigned to:** *[TODO: MRM / Governance]*  
**Status:** ❓ Open  
**Resolution:** *[Fill in once confirmed]*

**Sections affected:** Ch. 6.6, Ch. 4 (tier requirements), RACI

---

## Q009 — Data Scientists' Stakeholder Input 🟡 MEDIUM

**Question:** Have the data scientists who will be the primary users of this Guide been consulted on its practical usability?  
**Context:** The Guide should be practical for DS, not just governance-compliant. Specific feedback on workflow, documentation burden, and governance touchpoints is needed.  
**Assigned to:** *[TODO: Team lead / MRM]*  
**Status:** ❓ Open  
**Resolution:** *[Fill in after stakeholder interviews — see `06_internal_inspiration.md`]*

**Sections affected:** All stage requirements; particularly Ch. 6.3–6.4 (Development and Testing)

---

## Q010 — Vendor Model Documentation Sufficiency 🟢 LOWER

**Question:** What happens when a vendor refuses to provide the documentation required by the Guide? What compensating controls are acceptable?  
**Context:** Some vendors treat methodology documentation as proprietary. The Guide needs to address this practically.  
**Assigned to:** *[TODO: MRM / Procurement]*  
**Status:** ❓ Open  
**Resolution:** *[Fill in once confirmed]*

**Sections affected:** Ch. 4.7.1 (Vendor models), Ch. 6.5 (Validation)

---

*Add new questions above the last entry. Resolved questions should have their status updated to ✅.*
