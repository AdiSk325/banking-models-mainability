# Appendix C — Glossary

> **Status: DRAFT**  
> **Section:** Model Lifecycle Guide, Appendix C

---

This glossary provides definitions for all key terms used in the Model Lifecycle Guide and its supporting documents. Core definitions are also presented in [Chapter 2 — Key Definitions](../02_definitions.md).

---

## A

**Approval to Develop** — The formal stage gate authorisation to proceed with model development, granted after Initiation review confirms the business case and tier assignment.

**Artifact** — A documented output produced at a lifecycle stage that serves as governance, audit, and operational evidence.

**Audit Trail** — The complete record of all decisions, approvals, changes, and actions taken throughout a model's lifecycle.

---

## B

**Backtesting** — A validation technique that assesses model performance on historical data to evaluate its predictive accuracy.

**Benchmark Model** — A simpler or alternative model used as a reference point to evaluate the performance of the model under review.

**Bias (Statistical)** — Systematic error in model outputs arising from flawed assumptions or non-representative training data.

---

## C

**Calibration** — The degree to which a model's predicted probabilities or values correspond to observed outcomes. A well-calibrated model has predicted rates close to actual rates.

**Change Log** — A record of all changes made to a model, including version, description, date, and approval reference.

**Characteristic Stability Index (CSI)** — A metric measuring the stability of an individual input variable's distribution over time.

**Compensating Control** — A control implemented to mitigate a risk or weakness that cannot be directly remediated (e.g., enhanced monitoring in lieu of a full validation).

**Conditions (approval)** — Requirements attached to a model's approval that must be satisfied within a defined period as a prerequisite for continued use.

---

## D

**Data Dictionary** — A structured document describing each input variable: name, definition, source, format, and transformation logic.

**Data Drift** — A change in the statistical properties of input data over time that may degrade model performance.

**Data Leakage** — The inadvertent inclusion of information in training data that would not be available at the time of prediction in production, leading to inflated performance estimates.

**Data Lineage** — The documented history of a data element from its original source through all transformations to its use as a model input.

---

## E

**Exception** — A formally approved, time-limited departure from a requirement of this Guide or its supporting documents.

**Explainability** — The degree to which a model's outputs can be explained in terms of its inputs and logic to non-technical audiences or for regulatory purposes.

---

## F

**Feature Engineering** — The process of transforming raw data into input variables (features) suitable for use in a model.

**Feature Importance** — A measure of each input variable's contribution to model output.

**Findings Log** — A structured record of observations, weaknesses, or deficiencies identified during validation, with severity classification and resolution status.

---

## G

**Gini Coefficient** — A discrimination metric commonly used in credit models, ranging from 0 (no discrimination) to 1 (perfect discrimination). Equivalent to 2×AUC − 1.

**Governance Forum** — A formal committee or approval body with authority to approve models, exceptions, or material changes.

---

## H

**Hyperparameter** — A parameter set before training begins that controls the learning process (e.g., learning rate, tree depth, regularisation).

---

## I

**Independent Validation** — The objective assessment of a model by a party functionally independent of the development team.

**Inherent Risk** — The risk associated with a model before any controls are applied.

**IRB (Internal Ratings-Based)** — An approach to calculating regulatory credit capital based on the bank's own internal models, subject to regulatory approval.

---

## K

**KS Statistic (Kolmogorov-Smirnov)** — A discrimination metric measuring the maximum separation between cumulative distributions of events and non-events.

---

## M

**Material Change** — A model change that significantly affects methodology, inputs, outputs, or risk profile, triggering mandatory re-testing, re-validation, and re-approval.

**Model** — See [Chapter 2](../02_definitions.md) for the full definition.

**Model Documentation** — The formal written record of a model's purpose, design, data, methodology, assumptions, limitations, testing results, and governance history.

**Model Inventory** — The central register of all models in use or under development.

**Model Owner** — The senior business individual accountable for a model throughout its lifecycle.

**Model Risk** — The risk of adverse consequences from model errors or misuse.

**Model Risk Management (MRM)** — The second-line function responsible for model governance framework.

**Model Tier** — A risk-based classification (1, 2, or 3) that determines governance requirements.

**Monitoring** — The ongoing assessment of a deployed model's performance, stability, and fitness for purpose.

---

## O

**Out-of-Sample Testing** — Performance assessment on data not used during model development.

**Out-of-Time Testing** — Performance assessment on data from a different time period than the development sample.

---

## P

**Parallel Run** — A period during which both the old and new versions of a model are run simultaneously to compare outputs before full cutover.

**Population Stability Index (PSI)** — A metric measuring changes in the distribution of the scored population over time.

**Proportionality** — The principle that governance requirements are scaled to the risk and materiality of the model.

---

## R

**RACI** — Responsible, Accountable, Consulted, Informed — a framework for assigning roles in a process.

**Reproducibility** — The ability to recreate model outputs given the same inputs, data, code, and environment.

**Residual Risk** — The risk remaining after controls are applied.

**Rollback** — The process of reverting a system to a previous known-good state following a failed deployment.

---

## S

**Segregation of Duties** — The control principle that the roles of development, validation, and approval are held by separate, independent parties.

**SHAP (SHapley Additive exPlanations)** — A method for explaining individual predictions by attributing output contributions to each input feature.

**Stage Gate** — A mandatory decision point between lifecycle stages, requiring documented sign-off before progression.

---

## T

**Traceability** — The ability to trace any model output back to the inputs, data, and logic that produced it.

---

## U

**UAT (User Acceptance Testing)** — Testing conducted by business users to confirm that model behaviour in the production-equivalent environment meets expectations.

---

## V

**Validation** — See [Independent Validation].

**Vendor Model** — A model developed externally and procured by the bank, subject to the same governance requirements as internally developed models.

**Version Control** — The practice of tracking and managing changes to code, documents, and artefacts using a system such as Git.

---

<!-- TODO: Expand glossary as Guide content is finalised. Ensure consistency with Model Risk Management Policy glossary. -->

*Back to: [Appendices](README.md) | [Chapter 2 — Key Definitions](../02_definitions.md)*
