---
name: regulatoryflow-risk-reviewer
description: Formulate a risk-based review strategy for any regulatory document — determining which sections carry the highest regulatory and patient-safety risk, what review depth each section requires, and who should review it. Trigger on "risk-based review", "how should I review my [document]", "prioritise my document review", "review strategy", "which parts of my [document] are highest risk", "risk-based approach to reviewing my [document]", "what should I focus on when reviewing". Applies the correct sector × region framework. Output includes a section-by-section risk classification, review method per section, and reviewer assignment guidance. Human review required.
---

# Risk Reviewer

## Purpose

Produce a **risk-based review strategy** for a specified regulatory document — the structured approach a Senior Quality Manager or Regulatory Affairs Lead applies when reviewing a document to allocate review effort proportionately to regulatory and safety risk.

Not all sections of a regulatory document carry equal weight. A Risk Management Plan's risk acceptability criteria section (ISO 14971 §5) carries patient-safety risk if incorrectly stated; the document header carries administrative risk only. This skill makes that prioritisation explicit and systematic.

The output answers:
1. Which sections of this document are **safety-critical** (errors could directly harm patients or invalidate market access)?
2. Which sections are **regulatory-critical** (errors could cause a submission rejection or a major non-conformity)?
3. Which sections are **administrative** (errors are minor, correctable without regulatory impact)?
4. What **review method** should be applied to each section (technical review, statistical verification, regulatory citation check, cross-reference verification)?
5. Who should **review each section** (Author, RA Lead, Clinical Expert, Biostatistician, QMS owner, etc.)?

## When to use

Trigger this skill when the user wants to:
- Plan a structured internal review before submitting a regulatory document
- Allocate reviewer time efficiently across a long document
- Define the review protocol for a new document type entering the QMS
- Train junior RA staff on how to review a specific document type
- Determine what a regulatory expert reviewer should focus on vs. what a junior reviewer can handle

Complementary to gap analysis (skill 02) — gap analysis identifies whether requirements are met; risk review identifies which gaps matter most.

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

## Risk Classification Scheme

Apply this classification to each document section:

| Risk Level | Definition | Review Approach |
|-----------|-----------|----------------|
| **S — Safety-Critical** | Errors could directly harm patients, cause a device recall, or invalidate clinical claims | Mandatory independent review by RA expert + clinical/technical specialist; 100% verification of cited data |
| **R — Regulatory-Critical** | Errors could cause submission rejection, major non-conformity, or market access delay | Review by senior RA professional; cross-check all regulatory citations against official texts |
| **Q — QMS-Critical** | Errors could cause QMS non-conformities or ISO 13485 audit findings | Review by QMS manager or quality professional |
| **A — Administrative** | Formatting, version control, typographical — no regulatory or safety impact | Junior RA or document controller review |

## Workflow

### Step 1 — Confirm context

Require: Sector, Region, Artifact. Optionally ask if this is a pre-submission review, internal audit preparation, or document creation review.

### Step 2 — Enumerate document sections

List all major sections of the specified artifact (using the same section structure as skill 01's outline for that artifact and framework).

### Step 3 — Classify each section by risk level

For each section, assign S / R / Q / A and explain the risk rationale in one sentence.

### Step 4 — Assign review method

For each section, specify the review method:
- **Technical verification**: Validate data, calculations, test results against source records
- **Regulatory citation check**: Verify each cited article/clause exists and is correctly applied
- **Cross-reference verification**: Check that the section is internally consistent with other QMS documents
- **Statistical review**: Where data or statistics are presented, verify methodology and results
- **Clinical expert review**: Where clinical claims or clinical data are involved
- **Document control check**: Version, date, approval, distribution list

### Step 5 — Assign reviewers

For each section, specify the appropriate reviewer role(s). Use roles, not names.

### Step 6 — Produce the review plan summary

Summarise estimated review effort by risk level and provide a recommended review sequence (highest risk first).

## Output Format

```markdown
# Risk-Based Review Strategy: [Artifact Name]
**[Sector] — [Region] | Framework: [Standards list]**
**Review purpose: [Pre-submission / Internal audit prep / Document creation review]**

---

## Risk Classification Legend

| Code | Level | Review requirement |
|------|-------|-------------------|
| S | Safety-Critical | Independent expert review; 100% data verification |
| R | Regulatory-Critical | Senior RA review; regulatory citation verification |
| Q | QMS-Critical | QMS manager review |
| A | Administrative | Document controller / junior RA review |

---

## Section-by-Section Review Plan

| # | Section | Risk Level | Rationale | Review Method | Reviewer(s) | Estimated Effort |
|---|---------|-----------|-----------|---------------|-------------|-----------------|
| 1 | [Section name] | S / R / Q / A | [One-sentence risk rationale] | [Method(s)] | [Role(s)] | [Hours: Low <1h / Medium 1–3h / High >3h] |
| 2 | ... | ... | ... | ... | ... | ... |

---

## Review Sequence (Highest Risk First)

1. **Safety-Critical sections** — review these first, stop and remediate before proceeding if issues found: [list of S sections]
2. **Regulatory-Critical sections**: [list of R sections]
3. **QMS-Critical sections**: [list of Q sections]
4. **Administrative sections**: [list of A sections]

---

## Review Effort Summary

| Risk Level | Sections | Total estimated effort |
|-----------|---------|----------------------|
| Safety-Critical (S) | [N] | [X hours] |
| Regulatory-Critical (R) | [N] | [X hours] |
| QMS-Critical (Q) | [N] | [X hours] |
| Administrative (A) | [N] | [X hours] |
| **Total** | **[N]** | **[X hours]** |

---

## Review Stop Conditions

Stop the review and escalate if:
- Any Safety-Critical section contains unresolved discrepancies between the document and source data
- Any regulatory citation cannot be verified against the official current text
- The document scope does not match the device described in [INSERT: Technical File or equivalent reference document]

---
⚠️ *Review strategy requires adaptation by a qualified Regulatory Affairs professional. Risk classifications are indicative — your organisation's specific risk profile and submission context may alter priorities.*
```

## Safety guardrails

- **Safety-Critical sections must always get independent review**: Never suggest that Safety-Critical sections can be self-reviewed by the author.
- **Risk level is not negotiable**: Do not downgrade a Safety-Critical section to Regulatory-Critical to save reviewer time. Flag this explicitly.
- **Stop conditions are real**: If a Safety-Critical issue is found, the review must stop — not continue while the issue is tracked as an action item. State this clearly.
- **Framework integrity**: Risk classifications are based on the applicable regulatory framework. Do not apply MDR risk logic to a GMP validation document.
- **Human review mandatory**.

## Related skills

- `regulatoryflow-gap-analysis` (02) — identify the gaps; this skill prioritises their remediation
- `regulatoryflow-audit-prep` (04) — auditors will apply similar risk prioritisation in their review
- `regulatoryflow-document-drafter` (01) — review strategy is most effective when the document structure is sound
