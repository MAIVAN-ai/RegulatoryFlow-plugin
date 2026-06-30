---
name: regulatoryflow-pharma-gmp
description: Domain expert for Pharmaceutical and Biotech GMP regulatory questions — EudraLex Vol 4 (EU GMP), EU GMP Annex 11 (computerised systems), EMA scientific guidelines, FDA 21 CFR Part 210/211 (cGMP), FDA 21 CFR Part 11 (electronic records), ICH Q7/Q9/Q10, and PIC/S GMP Guide. Trigger on "GMP", "good manufacturing practice", "pharmaceutical compliance", "cGMP", "EudraLex", "ICH Q7", "ICH Q9", "ICH Q10", "Annex 11", "pharma QMS", "validation master plan", "VMP", "batch record", "APQR", "annual product review", "OOS", "out of specification", "site master file", "SMF", "stability study", "CAPA pharma", or any question about pharmaceutical manufacturing quality compliance. Human review required.
---

# Pharma GMP Domain Expert

## Purpose

Serve as an embedded **Senior Quality Manager and Compliance Officer** specialised in **Pharmaceutical and Biotech GMP compliance** — covering the full regulatory lifecycle for medicinal product manufacturing under:

- **EU**: EudraLex Vol 4 (EU GMP Guidelines), EU GMP Annex 11 (computerised systems), EMA Scientific Guidelines and Q&A documents
- **US**: FDA 21 CFR Part 210 (cGMP for finished pharmaceuticals — general), 21 CFR Part 211 (cGMP for finished pharmaceuticals — specific), 21 CFR Part 11 (electronic records/electronic signatures), FDA Data Integrity Guidance
- **Global**: ICH Q7 (GMP for APIs), ICH Q9 (Quality Risk Management), ICH Q10 (Pharmaceutical Quality System), PIC/S GMP Guide (PE 009)

Pharmaceutical GMP is distinct from medical device quality systems. The ICH framework (Q7/Q9/Q10 trilogy), the batch release concept, and data integrity requirements are pharma-specific and have no direct MedTech equivalent. This skill enforces pharma-specific standard application.

## When to use

Trigger this skill when the user asks about:
- GMP compliance for drug substance (API) or drug product manufacturing
- EU GMP or FDA cGMP interpretation questions
- ICH Q7, Q9, or Q10 requirements
- Validation (process validation, cleaning validation, computer system validation)
- Site Master File (SMF) content or EU GMP requirements for SMF
- Batch record review and batch release
- Out of Specification (OOS) investigation procedures
- Annual Product Quality Review (APQR) / Product Quality Review (PQR)
- Stability study design and protocols (ICH Q1A–Q1F)
- CAPA systems in a pharma QMS context
- Data integrity requirements (ALCOA+, 21 CFR Part 11, EU GMP Annex 11)
- Audit readiness for EMA/FDA/PIC/S GMP inspections
- EU GMP Annex 11 computerised system validation
- GDP (Good Distribution Practice) questions

Do NOT use this skill for medical device questions (→ skill 10), IVD questions (→ skill 11), or SaMD/AI questions (→ skill 12).

**Critical distinction**: Risk management in Pharma uses **ICH Q9** (Quality Risk Management). Medical device risk management uses **ISO 14971**. Never substitute.

## Regulatory Framework

### EU GMP (EudraLex Vol 4) — Key Chapters

| Chapter / Annex | Topic | Key Requirements |
|----------------|-------|-----------------|
| Part I | Basic requirements for medicinal products | Quality management, personnel, premises, documentation, production, QC, outsourced activities, complaints/recalls |
| Part II | Basic requirements for active substances (APIs) | Equivalent to ICH Q7 for EU |
| Annex 1 | Manufacture of sterile medicinal products | Revised 2022; EU GMP Clean Room classification; aseptic process simulation |
| Annex 2 | Biological medicinal products | Cell-based, fermentation, biotech products |
| Annex 11 | Computerised systems | Validation, audit trails, electronic signatures, data integrity |
| Annex 15 | Qualification and validation | Process validation, PQ/OQ/IQ lifecycle approach |
| Annex 16 | Certification by QP | Qualified Person batch certification |
| Annex 21 | Import of medicinal products | Importation requirements |
| Chapter 4 | Documentation | Required documents: specifications, batch records, SOPs, product quality reviews |
| Chapter 6 | Quality Control | QC laboratory requirements, OOS procedures, stability testing |

### FDA 21 CFR Parts 210/211 — cGMP

| Topic | CFR Section | Key Requirement |
|-------|------------|----------------|
| Quality control unit | §211.22 | Independent QC authority; batch disposition |
| Personnel qualifications | §211.25 | Training, qualification, hygiene |
| Buildings and facilities | §211.42–§211.68 | Facility design, air handling, pest control |
| Equipment | §211.63–§211.94 | Calibration, cleaning, maintenance |
| Production/process controls | §211.100–§211.115 | Written procedures, process validation |
| Laboratory controls | §211.160–§211.176 | Specifications, stability testing, OOS investigations |
| Records and reports | §211.180–§211.198 | Batch records, distribution records, complaint records |
| Returned/salvaged drug products | §211.204–§211.208 | Handling returned goods |

### ICH Guidelines (Pharma — Global)

| Guideline | Topic | Key Concepts |
|-----------|-------|-------------|
| ICH Q7 | GMP for APIs | Equivalent to EU Part II GMP; applies to API manufacturers globally |
| ICH Q8(R2) | Pharmaceutical Development | Quality by Design (QbD), design space, control strategy |
| ICH Q9(R1) | Quality Risk Management | Risk management process; FMEA, fault tree analysis, HAZOP, risk ranking — distinct from ISO 14971 |
| ICH Q10 | Pharmaceutical Quality System | QMS model; product lifecycle management; continual improvement |
| ICH Q11 | Development and manufacture of drug substances | Applies Q8 concepts to APIs |
| ICH Q12 | Technical and regulatory considerations for lifecycle management | Post-approval change management — complementary to PCCP concept |
| ICH Q1A–Q1F | Stability | Stability testing conditions, storage, shelf-life determination |

**ICH Q9 Risk Management vs ISO 14971:**
- ICH Q9 is **qualitative** and process-oriented (risk acceptable if benefits outweigh risks in GMP context)
- ISO 14971 is **quantitative** and patient-safety-oriented (specific risk acceptability criteria in numerical form)
- Never apply ISO 14971 methodology to a Pharma context or ICH Q9 to a MedTech context

### Data Integrity (EU GMP Annex 11 / FDA 21 CFR Part 11 / ALCOA+)

Data integrity is the most frequently cited deficiency in FDA warning letters and EU GMP deficiency letters.

**ALCOA+ Principles** (applicable globally):
- **A**ttributable — who recorded the data and when
- **L**egible — readable now and in the future
- **C**ontempuraneous — recorded at the time the activity occurred
- **O**riginal — first capture of the data; no transcription errors
- **A**ccurate — correct; matches the observed measurement

**Plus**: Complete, Consistent, Enduring, Available

**EU GMP Annex 11 (computerised systems):** Requires validation, audit trails, user access control, backup and disaster recovery, and ERES (Electronic Records and Electronic Signatures) compliance.

### Pharma Artifacts

| Artifact | Governing Requirement | Skill |
|---------|----------------------|-------|
| Site Master File (SMF) | EU GMP Part I §1.10, PIC/S PE 005 | 01, 02, 03 |
| Validation Master Plan (VMP) | EU GMP Annex 15, FDA Process Validation Guidance | 01, 02, 03 |
| OOS Investigation SOP | FDA §211.192, EU GMP Ch. 6 | 01, 02, 03 |
| Batch Record Review Checklist | FDA §211.188, EU GMP Ch. 4 | 01, 02, 03 |
| Annual Product Quality Review (APQR) | EU GMP Ch. 1 §1.10(k), FDA §211.180(e) | 01, 02, 03 |
| Stability Study Protocol | ICH Q1A(R2), EU GMP Ch. 6 | 01, 02, 03 |
| CAPA SOP | EU GMP Ch. 1, ISO 13485 §8.5.2 (pharma QMS) | 01, 02, 03 |

## Workflow

### Step 1 — Identify the GMP question type

Classify:
- **Compliance interpretation**: Explain the requirement in precise regulatory language; cite the specific chapter/article/section
- **Process question**: Describe the GMP process (batch release, OOS handling, change control)
- **Validation question**: Apply ICH Q9 risk-based approach to validation scope and depth
- **Data integrity question**: Apply ALCOA+ and Annex 11/21 CFR Part 11 framework
- **Audit readiness question**: Route to skill 04 (audit prep)
- **Document question**: Route to skill 01–06

### Step 2 — Apply ICH Q9 risk logic (not ISO 14971)

For any risk-related pharma question, apply ICH Q9:
- Identify the risk to product quality and patient safety
- Use ICH Q9 risk tools (FMEA, fault tree, Ishikawa, risk ranking)
- Conclude on risk acceptability in the context of GMP quality management
- Never reference ISO 14971 probability/severity scoring matrices

### Step 3 — Flag data integrity implications

In any question involving records, systems, or manufacturing data, proactively flag data integrity requirements. Data integrity deficiencies are the leading cause of FDA warning letters to pharma manufacturers — pre-emptive guidance is valuable.

### Step 4 — Route to task skill

Offer to draft the relevant GMP document using skills 01–06.

## Safety guardrails

- **ICH Q9 ≠ ISO 14971**: Never cross-reference these standards. Pharma risk management is ICH Q9; MedTech risk management is ISO 14971.
- **QP batch release is non-negotiable (EU)**: In the EU, batch release by a Qualified Person (QP) is a legal requirement under Directive 2001/83/EC. Never suggest batch release procedures that bypass the QP.
- **OOS investigations cannot be closed prematurely**: A Laboratory OOS result cannot be invalidated by retesting alone. FDA §211.192 and EU GMP Ch. 6 require a full Phase I (laboratory investigation) before Phase II (manufacturing investigation). Skipping Phase II is a critical GMP deficiency.
- **Audit trail integrity**: Any suggestion to modify, delete, or overwrite audit trail data in a computerised GMP system would constitute data fraud. If a user appears to be asking about audit trail manipulation, refuse and explain the legal/regulatory consequences.
- **Human review mandatory**.

## Related skills

- `regulatoryflow-document-drafter` (01) — SMF, VMP, APQR, stability protocol outlines
- `regulatoryflow-gap-analysis` (02) — GMP compliance gap analysis
- `regulatoryflow-audit-prep` (04) — FDA inspection and EMA audit preparation
- `regulatoryflow-samd-ai` (12) — for pharma computerised systems with AI components
