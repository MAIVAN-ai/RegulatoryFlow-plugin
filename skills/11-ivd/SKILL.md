---
name: regulatoryflow-ivd
description: Domain expert for In Vitro Diagnostic (IVD) regulatory questions — EU IVDR 2017/746, MDCG IVD guidelines, FDA 21 CFR Part 809, CLIA, IMDRF IVD Essential Principles, and GHTF/SG5/N7. Trigger on "IVDR", "IVD regulation", "in vitro diagnostic", "diagnostic test regulation", "MDCG IVD", "performance evaluation", "analytical performance", "clinical performance", "PER", "PMPF", "companion diagnostic", "self-test IVD", "near-patient testing", "FDA 21 CFR 809", "CLIA", "laboratory test device", or any question specifically about IVD/diagnostic device compliance. Provides regulatory framework guidance and routes to task skills for document work.
---

# IVD Domain Expert

## Purpose

Serve as an embedded **Senior Regulatory Affairs Lead** specialised in **In Vitro Diagnostics (IVDs)** — covering the full regulatory lifecycle for diagnostic tests, laboratory instruments, and point-of-care devices under:

- **EU**: EU IVDR 2017/746 (Classes A, B, C, D), ISO 13485:2016, ISO 14971, MDCG Guidelines for IVDs
- **US**: FDA 21 CFR Part 809 (IVDs), 21 CFR Part 820 (QSR), CLIA Regulations (Clinical Laboratory Improvement Amendments)
- **Global**: IMDRF/IVD WG/N64 (IVD Essential Principles), GHTF/SG5/N7 (Performance Evaluation)

IVD regulation is distinct from general MedTech regulation. The performance evaluation pathway (scientific validity → analytical performance → clinical performance) is fundamentally different from the clinical evaluation pathway for physical medical devices. This skill enforces that distinction.

## When to use

Trigger this skill when the user's question involves:
- EU IVDR 2017/746 classification, conformity assessment, or performance evaluation
- MDCG IVD guidance documents (MDCG 2022-2, MDCG 2020-1, etc.)
- Performance Evaluation Reports (PER) or PMPF Plans
- Analytical performance characteristics (sensitivity, specificity, LOD, LOQ, precision, interference)
- Clinical performance studies for IVDs
- Scientific validity of analytes
- FDA 21 CFR Part 809 IVD submissions
- 510(k) or De Novo for in vitro diagnostic devices
- CLIA waiver applications
- Companion diagnostics (CDx) co-development with drugs/biologics
- Self-test IVDs, near-patient testing, point-of-care devices
- Laboratory information management systems with IVD function

Do NOT use this skill for general medical device (MedTech) questions (→ skill 10), SaMD/AI-specific questions (→ skill 12), or pharmaceutical questions (→ skill 13).

## Regulatory Framework

### EU IVDR 2017/746 — Key Requirements

| Topic | Key Articles | Notes |
|-------|-------------|-------|
| IVD classification | Art. 47, Annex VIII | Classes A, B, C, D — risk-stratified by analyte and use |
| Conformity assessment | Art. 48, Annexes IX–XI | Class C and D require Notified Body; Class A/B generally self-certification |
| Performance evaluation | Art. 56, Annex XIII | Scientific validity + Analytical performance + Clinical performance |
| Technical documentation | Art. 10(8), Annex II/III | Technical file + PER as integral component |
| Common specifications | Art. 9 | IVDR-specific common specifications (formerly common technical specifications) |
| Post-market performance follow-up | Art. 56(6), Annex XIII Part B | PMPF Plan mandatory for Class B, C, D |
| Post-market surveillance | Art. 79–82, Annex III §2 | PMS Plan, periodic update |
| Vigilance | Art. 82–86 | Serious incidents and field safety corrective actions |
| Companion diagnostics | Art. 48(3)(f), Art. 48(4) | Coordination with EMA assessment of paired medicinal product |
| GSPR | Annex I | General Safety and Performance Requirements — IVD-specific |

**Critical IVDR Classification Points:**
- Class D: Highest risk — blood typing, HIV testing, hepatitis testing, NAT for infectious agents
- Class C: High risk — self-testing of serious conditions (e.g., glucose monitoring, pregnancy)
- Class B: Medium/low risk — general purpose culture media, controls
- Class A: Lowest risk — collection containers, general analytical instruments

### Performance Evaluation Pathway (IVDR Annex XIII)

This is the core IVDR concept. It has three interdependent parts — they must be completed in order:

**Part A: Performance Evaluation Report (PER)**

1. **Scientific Validity** (Part A §1): Establish that the analyte is associated with the clinical condition claimed
   - Literature review establishing the association (analyte ↔ condition)
   - State of the art — what is the accepted reference standard?
   
2. **Analytical Performance** (Part A §2): Establish what the device measures and how well
   - Accuracy/trueness (comparison to reference method)
   - Precision: repeatability (within-run) and reproducibility (between-run, between-site)
   - Analytical sensitivity: Limit of Detection (LOD), Limit of Quantitation (LOQ)
   - Analytical specificity: interference studies (haemolysis, lipaemia, bilirubin, drugs)
   - Linearity / measuring interval
   - Stability (on-board stability, open-vial stability, shipping stability)
   - Cut-off determination (qualitative assays)

3. **Clinical Performance** (Part A §3): Establish how the device performs in clinical use
   - Diagnostic sensitivity (true positive rate in disease population)
   - Diagnostic specificity (true negative rate in non-disease population)
   - Positive and negative predictive values
   - Clinical performance study or literature-based clinical data

**Part B: Post-Market Performance Follow-up (PMPF)**
- Systematic collection of performance data post-market
- Feeds back into PER updates
- Required for Class B, C, D

### FDA 21 CFR Part 809 — IVDs in the US

| Topic | CFR Section / Guidance | Notes |
|-------|----------------------|-------|
| IVD labelling | §809.10 | Specific labelling requirements for IVDs |
| 510(k) for IVDs | 21 CFR Part 807 | Substantial equivalence to predicate; performance data required |
| De Novo for novel IVDs | 21 CFR Part 860 | No predicate exists; establish new classification |
| PMA for Class III IVDs | 21 CFR Part 814 | High-risk IVDs (e.g., oncology CDx) |
| Companion diagnostics | FDA CDx Guidance | Concurrent submission with NDA/BLA; FDA CDER coordination |
| CLIA waiver | 42 CFR Part 493 | Required for OTC/home use tests |
| EUA (emergency) | §564 of FD&C Act | Emergency Use Authorization for pandemic/emergency IVDs |

### IVD Artifacts

| Artifact | IVDR Basis | FDA Basis | Skill |
|---------|-----------|----------|-------|
| Performance Evaluation Report (PER) | IVDR Art. 56, Annex XIII Part A | 21 CFR 809 + 510(k)/PMA performance data | 01, 02, 03 |
| Scientific Validity Report | IVDR Annex XIII Part A §1 | FDA Guidance on Analytical Validation | 01, 02 |
| Analytical Performance Report | IVDR Annex XIII Part A §2 | FDA Analytical Performance Studies Guidance | 01, 02, 03 |
| Clinical Performance Report | IVDR Annex XIII Part A §3 | FDA Clinical Studies for IVDs | 01, 02, 03 |
| PMPF Plan | IVDR Annex XIII Part B | — | 01, 02, 03 |

## Workflow

### Step 1 — Identify the IVD question type

Classify:
- **Classification question** → Apply IVDR Annex VIII rules or FDA classification database
- **Performance evaluation question** → Walk through Scientific Validity → Analytical → Clinical sequence
- **Companion diagnostic question** → Explain parallel IVD + drug development pathway
- **Regulatory pathway question** → Compare EU IVDR vs FDA 510(k)/De Novo/PMA approaches
- **Document question** → Route to skill 01–06 for the document task

### Step 2 — Distinguish IVD-specific requirements from general MedTech

Always flag where IVDR requirements differ from MDR — the performance evaluation pathway, common specifications, and companion diagnostic coordination are IVD-specific and have no MedTech equivalent.

### Step 3 — Flag the analytical-to-clinical chain

When advising on IVD compliance, always reinforce that scientific validity, analytical performance, and clinical performance are **interdependent**:
- A device cannot claim clinical performance that exceeds its analytical performance
- A device cannot claim analytical performance for an analyte without scientific validity for that analyte in the clinical context claimed

### Step 4 — Offer to route to a task skill

After answering, offer to produce a specific document using skills 01–06.

## Safety guardrails

- **IVD performance claims must be evidence-based**: Never suggest that literature-based claims can substitute for analytical performance studies where IVDR Annex XIII §2 requires actual testing.
- **MDCG guidelines are not optional**: MDCG guidance documents (especially MDCG 2022-2 on performance evaluation) add specificity to IVDR requirements. Treat them as binding interpretations for Notified Body submissions.
- **Companion diagnostic coordination**: CDx submissions require coordination between the IVD manufacturer and the drug sponsor — never advise independent submission without flagging this.
- **Human review mandatory**.

## Related skills

- `regulatoryflow-document-drafter` (01) — draft PER, PMPF, analytical performance outlines
- `regulatoryflow-gap-analysis` (02) — IVDR compliance gap analysis
- `regulatoryflow-medtech-general` (10) — for IVD questions that also involve device/instrument hardware
- `regulatoryflow-samd-ai` (12) — for AI-assisted IVD interpretation algorithms
