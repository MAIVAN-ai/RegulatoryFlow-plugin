---
name: regulatoryflow-gap-analysis
description: Create a compliance gap analysis checklist for any regulatory document against its applicable framework (EU MDR, IVDR, FDA, IEC 62304, GMP, ICH, etc.). Trigger on "gap analysis", "compliance check", "what am I missing", "review my document against the standard", "checklist for compliance", "what does my [document] need", "GSPR gap", "MDR compliance gaps", or any request to assess whether a document or system meets a regulatory requirement. Produces an itemised checklist with requirement, compliance status, evidence field, and remediation action. Human review required before submission.
---

# Gap Analysis

## Purpose

Produce a **compliance gap analysis checklist** for a specified regulatory document against the applicable mandatory standards. This is the tool a Regulatory Affairs Lead or Lead Auditor uses to systematically determine whether a document — or the system it describes — meets every applicable requirement before submission or audit.

Each checklist item maps:
- The **requirement** (specific article/clause)
- A **compliance status field** (Compliant / Partial / Non-compliant / N/A)
- An **evidence field** (where in the document the requirement is met)
- A **remediation action** if non-compliant or partial

This output is the same structure a Notified Body or FDA auditor uses when conducting a document review — so it simultaneously prepares the team for audit and identifies genuine compliance gaps.

## When to use

Trigger this skill when the user wants to:
- Check whether an existing document covers all required elements
- Prepare a document for Notified Body or FDA submission review
- Run an internal audit against a regulatory standard
- Identify gaps before a third-party audit
- Create a remediation roadmap for a non-compliant document

Do **not** use this skill for creating document structure from scratch (→ skill 01) or producing a fillable template (→ skill 03).

## Regulatory Framework Reference

| Sector | Region | Mandatory Standards |
|--------|--------|---------------------|
| MedTech_General | EU | EU MDR 2017/745, ISO 13485:2016, ISO 14971:2019, MEDDEV 2.7/1 Rev 4 |
| MedTech_General | US | FDA 21 CFR Part 820 (QSR), 21 CFR Part 11, ISO 14971:2019, FDA Human Factors Guidance |
| MedTech_General | Global | IMDRF/GRRP WG/N47 (Essential Principles), ISO 13485:2016 (MDSAP) |
| MedTech_IVD | EU | EU IVDR 2017/746, ISO 13485:2016, ISO 14971, MDCG Guidelines for IVDs |
| MedTech_IVD | US | FDA 21 CFR Part 809 (IVDs), 21 CFR Part 820, CLIA Regulations |
| MedTech_IVD | Global | IMDRF/IVD WG/N64 (IVD Essential Principles), GHTF/SG5/N7 |
| SaMD_and_AI | EU | EU MDR 2017/745 (Rule 11), IEC 62304:2006+A1:2015, IEC 82304-1, EU AI Act |
| SaMD_and_AI | US | FDA 21 CFR Part 820, FDA AI/ML Action Plan, FDA PCCP Guidance, NIST AI RMF |
| SaMD_and_AI | Global | IMDRF/SaMD WG/N41 (SaMD Clinical Evaluation), ISO/IEC 42001, IEC 62304 |
| Pharma | EU | EudraLex Vol 4 (EU GMP), EU GMP Annex 11, EMA Scientific Guidelines |
| Pharma | US | FDA 21 CFR Part 210/211 (cGMP), 21 CFR Part 11, FDA Data Integrity Guidance |
| Pharma | Global | ICH Q7 (API), ICH Q9 (Risk Management), ICH Q10 (Pharma QS), PIC/S GMP Guide |

## Workflow

### Step 1 — Confirm context

Require: Sector, Region, Artifact. Optionally ask if the user has an existing document to assess (vs. a theoretical checklist for a document not yet written).

### Step 2 — Build the checklist

For the declared artifact and framework, enumerate every **mandatory requirement element** from the applicable standards. Structure as:

1. **Document-level requirements**: Does the document exist? Is it controlled, versioned, approved?
2. **Content requirements**: Every element the standard mandates must be present
3. **Process requirements**: Is the documented process actually implemented and evidenced?
4. **Linkage requirements**: Are required cross-references to other QMS documents present and correct?
5. **Review/update requirements**: Is there a defined review cycle? Has the document been updated following relevant triggers (design changes, FSCA, post-market data)?

For each requirement, produce one checklist row with:
- `#` — sequential number
- `Requirement` — precise statement of what is required, with article/clause citation
- `Status` — `[ ] Compliant` / `[ ] Partial` / `[ ] Non-compliant` / `[ ] N/A`
- `Evidence / Location` — blank field for reviewer to enter document section or record reference
- `Remediation Action` — specific corrective action if non-compliant or partial (pre-filled with the typical remediation)
- `Priority` — Critical / Major / Minor (aligned with ISO 13485 audit classification)

### Step 3 — Summary scorecard

After the checklist, produce a summary:
- Total items: N
- Critical items: N
- Items requiring remediation: N
- Estimated remediation effort: [Low/Medium/High] per item
- Overall compliance assessment: [Ready for submission / Needs minor remediation / Significant gaps — do not submit]

### Step 4 — Common finding flags

Flag the **top 5 most common audit findings** for this document type as a separate highlighted block. These represent observations frequently cited by Notified Bodies, FDA inspectors, or MDSAP auditors for this artifact.

## Output Format

```markdown
# Compliance Gap Analysis: [Artifact Name]
**[Sector] — [Region] | Framework: [Standards list]**
**Date: [INSERT: Review Date] | Reviewer: [INSERT: Reviewer Name]**
**Document under review: [INSERT: Document ID and Version, or "Not yet drafted"]**

---

## Gap Analysis Checklist

| # | Requirement | Article/Clause | Status | Evidence / Location | Remediation Action | Priority |
|---|-------------|---------------|--------|--------------------|--------------------|----------|
| 1 | [Requirement text — precise regulatory language] | [Standard Art.§] | [ ] Compliant / [ ] Partial / [ ] Non-compliant / [ ] N/A | [Document section / record] | [Specific action if non-compliant] | Critical / Major / Minor |
| 2 | ... | ... | ... | ... | ... | ... |

---

## Summary Scorecard

| Metric | Value |
|--------|-------|
| Total requirements assessed | [N] |
| Critical requirements | [N] |
| Major requirements | [N] |
| Minor requirements | [N] |
| Items needing remediation | [N] |
| Overall assessment | [Ready / Needs remediation / Do not submit] |

---

## ⚠️ Top 5 Common Audit Findings for [Artifact Name]

1. [Finding 1 — from Notified Body / FDA experience]
2. [Finding 2]
3. [Finding 3]
4. [Finding 4]
5. [Finding 5]

---
⚠️ *Gap analysis output requires review by a qualified Regulatory Affairs professional. Compliance determinations are preliminary — all findings must be verified against the current version of cited standards and your organisation's specific QMS context.*
```

## Example

**Input**: Create a gap analysis checklist for my EU IVDR Performance Evaluation Report.

**Skill response** (abbreviated):

```markdown
# Compliance Gap Analysis: Performance Evaluation Report (PER)
**MedTech_IVD — EU | Framework: EU IVDR 2017/746, ISO 13485:2016, ISO 14971, MDCG Guidelines for IVDs**

| # | Requirement | Article/Clause | Status | Evidence / Location | Remediation Action | Priority |
|---|-------------|---------------|--------|--------------------|--------------------|----------|
| 1 | PER covers all claims made for the device's intended purpose | IVDR Art. 56(1), Annex XIII Part A | [ ] Compliant [ ] Partial [ ] Non-compliant | | Map each claim to a corresponding performance study or literature reference | Critical |
| 2 | Scientific validity of the analyte is established | IVDR Art. 56(1), Annex XIII Part A §1.1 | [ ] Compliant [ ] Partial [ ] Non-compliant | | Provide literature evidence establishing the analyte as a valid biomarker for the claimed condition | Critical |
| 3 | Analytical performance established (sensitivity, specificity, precision, LOD, LOQ, linearity, interference) | IVDR Annex XIII Part A §2.2 | [ ] Compliant [ ] Partial [ ] Non-compliant | | Conduct or cite studies demonstrating all analytical performance characteristics | Critical |
| 4 | Clinical performance data generated from clinical performance studies or literature | IVDR Annex XIII Part A §3 | [ ] Compliant [ ] Partial [ ] Non-compliant | | Provide clinical performance study data or systematic literature review | Critical |
| 5 | State of the art considered — comparison to predicate and competitor devices | IVDR Art. 56(1), MDCG 2022-2 | [ ] Compliant [ ] Partial [ ] Non-compliant | | Include state of the art section with documented comparator analysis | Major |
...

## ⚠️ Top 5 Common Audit Findings for Performance Evaluation Report (PER)

1. **Scientific validity section missing**: Manufacturers present analytical performance data without first establishing that the analyte is clinically valid for the claimed intended use.
2. **Inadequate interference studies**: LOD and LOQ documented but cross-reactivity and interference panel (haemolysis, lipaemia, bilirubin) absent.
3. **PER not updated after design changes**: PER version does not reflect the current device state; post-design-change performance data not incorporated.
4. **Clinical claims unsupported**: Intended use claims (e.g., "aids in diagnosis of X") not supported by clinical performance data for that specific intended purpose.
5. **MDCG guidance not referenced**: PER does not address MDCG 2022-2 guidance requirements specific to self-tests or near-patient testing (if applicable).
```

## Safety guardrails

- **Standard-specific requirements only**: List only requirements that are genuinely mandatory under the cited standards. Do not include advisory guidance as if it were mandatory unless the applicable standard or regulation makes it so.
- **No false assurances**: Never mark items as compliant in the output — leave all status fields blank for the reviewer to complete. Pre-filling compliance status would give false assurance.
- **Priority classification**: Use Critical for requirements whose absence would result in a Major non-conformity or rejection; Major for significant gaps; Minor for documentation improvements.
- **Framework integrity**: Do not mix Pharma and MedTech requirements in the same checklist.
- **Human review mandatory**.

## Related skills

- `regulatoryflow-intake` (00) — context collection
- `regulatoryflow-document-drafter` (01) — draft the document structure first, then gap-analyse
- `regulatoryflow-audit-prep` (04) — auditor questions complement the gap analysis
- `regulatoryflow-risk-reviewer` (05) — risk-based prioritisation of the gaps found
