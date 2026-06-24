# Document 03: Data Governance

> **⚠️ Disclaimer:** This is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed.

**System:** TalentBridge Screener (ORG-AI-011)
**EU AI Act Reference:** Article 10 (Data and Data Governance)
**Document Type:** Provider documentation (supplied by Vendor G) + Deployer additions
**Version:** 1.0 — October 2026

---

## 1. Overview

Article 10 of the EU AI Act requires that high-risk AI systems use training, validation, and testing data meeting defined quality criteria. This document records the data governance practices for TalentBridge Screener, covering both the vendor's training data and the candidate data the organisation itself processes as deployer.

A governance lesson carried forward directly from Project 4's root cause analysis applies here: that incident found that a retrospective dataset built from years of historical decisions can encode the unfairness of those earlier decisions even without anyone intending it. This document treats that as a standing question to be actively answered for this system, not an assumption to be waved through.

---

## 2. Training Data (Provider — Vendor G)

### 2.1 Training Dataset Description

| Parameter | Detail |
|---|---|
| Dataset composition | A blended corpus of anonymised CV–job description pairs drawn from Vendor G's enterprise customer base, supplemented with a smaller volume of synthetic CV examples generated specifically to fill underrepresented role categories |
| Time range | Rolling 6-year window, refreshed annually to avoid the dataset becoming a frozen historical snapshot |
| Geographic coverage | Primarily the jurisdictions in which the organisation and Vendor G's broader customer base operate |
| Languages | The organisation's primary operating languages, plus several additional European languages present in the broader vendor corpus |

### 2.2 Data Provenance and Lawfulness

Vendor G has confirmed, and the organisation's Legal function has independently reviewed, the following:
- All enterprise customer data was contributed under data processing agreements that explicitly authorise aggregated model training use
- The synthetic CV examples used to fill underrepresented categories were generated from structured templates and do not derive from any single real individual's data, avoiding a separate data protection question that would otherwise arise from using a real person's CV as a synthetic-generation seed
- No data is sourced from any dataset Legal has flagged as carrying an unresolved intellectual property or licensing question

### 2.3 A Specific Question This Documentation Asks Deliberately: Does the Use of Synthetic Data Introduce Its Own Risk?

Because Vendor G's dataset includes synthetic examples specifically to address underrepresented role categories, this document treats that design choice as something to interrogate rather than accept as an automatic improvement. Synthetic data generated to "fill a gap" can introduce a different problem: if the synthetic examples were authored using assumptions about what a "typical" candidate in an underrepresented category looks like, those assumptions can themselves encode bias, just via a different mechanism than historical data bias. The organisation has requested, and Vendor G has agreed to supply, the template logic used to generate synthetic examples, so this can be assessed directly rather than assumed safe simply because it is not "real" historical data.

### 2.4 Data Relevance and Representativeness

| Criterion | Assessment |
|---|---|
| **Relevance** | The dataset consists of genuine CV–job description pairs supplemented by structured synthetic examples; relevant to the CV-to-role matching task |
| **Representativeness** | Coverage is strongest for roles and geographies well represented in Vendor G's broader customer base; the organisation's own role mix (skewed toward financial services functions) is checked specifically against this, given that a generic recruitment dataset may underrepresent the specific blend of compliance, risk, and client-facing roles this organisation actually hires for |
| **Completeness** | Assessed as adequate for the breadth of role types currently in scope; flagged for re-assessment if the organisation begins hiring for a materially new function not well represented in its historical role mix |
| **Freedom from errors** | Automated deduplication, format normalisation, and personal-identifier removal applied by the vendor; the organisation has additionally requested a sample audit of records specifically from financial-services-sector contributors, given that this is the organisation's own sector |
| **Statistical properties** | Documented by Vendor G in the accompanying technical annex; reviewed jointly by the organisation's AI Governance Programme Office and ML Engineering function rather than accepted as supplied without scrutiny |

### 2.5 Bias Assessment of Training Data

Vendor G's pre-contract bias evaluation, reviewed by the organisation before signature, found:

- Shortlisting parity across gender-presentation proxy indicators within the vendor's accepted tolerance
- A measurable, smaller gap for candidates over a defined age threshold, which Vendor G has acknowledged and committed to a specific remediation timeline for ahead of the next model refresh
- Insufficient signal in the dataset to evaluate outcomes for candidates who disclose a disability, an explicit and acknowledged gap rather than an assumed non-issue

**Independent validation:** the organisation will conduct its own validation using a sample of its own historical (de-identified) application data, prior to go-live, rather than relying solely on the vendor's own evaluation — a direct procedural improvement over the predecessor system, where no independent validation of this kind was ever performed.

---

## 3. Validation and Testing Data

### 3.1 Vendor Validation Dataset

Vendor G maintains a held-out validation set, stratified by role category and geography, used for the vendor's own internal model evaluation. Validation metrics are documented in the vendor's technical annex.

### 3.2 The Organisation's Acceptance Testing Dataset

The organisation will conduct its own acceptance testing using a curated set of historical, de-identified applications drawn specifically from roles representative of its own actual hiring mix — deliberately not relying on the vendor's generic validation set alone, since that set may not reflect the specific role types and applicant characteristics this organisation will actually present to the system in production. Acceptance criteria are defined in the deployment plan, and the testing set includes cases with a known, previously-determined "correct" outcome to allow validation against ground truth rather than only against internal model consistency.

---

## 4. Candidate Data Processed by the Organisation (Deployer)

### 4.1 Data Processed

| Data Category | Source | Processing Purpose | Retention |
|---|---|---|---|
| CV content (unstructured text) | Candidate submission | Model input for CV-to-role matching | 12 months post-application |
| Job description text | Internal HR authoring | Model input | Retained as a standard job record |
| Fit score and explanation output | Generated by the system | Reviewer reference | 12 months post-application |
| Reviewer decision and override notes | HR coordinator | Oversight log | 36 months, aligned to relevant employment dispute limitation periods |

### 4.2 Lawful Basis

| Processing Activity | Lawful Basis | Notes |
|---|---|---|
| CV processing for shortlisting | Legitimate interests, balanced against a documented candidate rights assessment | Legal has confirmed this basis as preferred over a contractual basis, given that no contract yet exists with an applicant at the screening stage |
| Logging of AI-assisted decisions | Legal obligation | Required to satisfy the organisation's Article 12 logging obligations |
| Retention for challenge or dispute purposes | Legitimate interests | Retention period set with direct reference to applicable employment dispute limitation periods |

Candidates are informed at the application stage that AI is used for initial CV screening, and are given a clear explanation of how to request human review of a rejection, consistent with the candidate communications approach refined in Project 4's incident response (where customer-facing disclosure quality was itself a remediation focus for a different system).

### 4.3 Data Minimisation

The organisation's deployment configuration processes only CV content as submitted and the relevant job description. It does not supply the model with social media profiles, salary history, references, or any demographic information beyond what a candidate has chosen to include in their own CV. Any proposal to add a new data source requires a fresh Data Protection Impact Assessment and AI Governance Programme Office approval — it cannot be added informally by a business unit.

### 4.4 Special Category Data

CVs may inadvertently contain special category data — for example, health information disclosed in the context of explaining a career gap, or political or religious affiliations mentioned in volunteering history. Vendor G's system applies an automated filter to flag records that may contain this category of data; flagged records are routed directly to manual review and are withheld from automated scoring entirely, rather than being scored and then flagged after the fact.

---

## 5. Data Governance Controls

| Control | Owner | Mechanism |
|---|---|---|
| Data processing agreement with Vendor G | Legal | Executed, including explicit deployer-obligation clauses |
| Candidate-facing AI disclosure | Legal + Product | Reviewed and approved before go-live, not retrofitted post-launch |
| Special category data filter | Vendor G (provider) | Technical control, verified by the organisation during acceptance testing |
| Data retention enforcement | IT / Data Protection Officer | Automated deletion at the defined retention thresholds |
| Annual data governance review | Data Protection Officer + AI Governance Programme Office | Folded into the system's standard annual review cycle established in Project 3 |

---

*Vendor technical documentation supporting this Document is held by the AI Governance Programme Office and available on request, consistent with the documentation provenance practice established in `technical-documentation.md` of this project.*
