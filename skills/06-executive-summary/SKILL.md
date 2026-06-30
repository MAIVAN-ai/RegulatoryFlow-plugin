---
name: regulatoryflow-executive-summary
description: Write an executive summary structure for any regulatory document — suitable for leadership presentation, Notified Body submission cover notes, FDA pre-submission packages, or technical file overview sections. Trigger on "executive summary", "summary for management", "leadership overview of my [document]", "Notified Body cover note", "summary section for my submission", "how to summarise my [document]", "executive overview", "high-level summary of my compliance status". Output is a structured executive summary with compliance status dashboard, key findings, and recommended actions. Human review required before use.
---

# Executive Summary

## Purpose

Produce a **structured executive summary** for a specified regulatory document — the concise, high-level view needed by:
- **Senior leadership**: Non-technical executives who need compliance status without reading the full document
- **Notified Body assessors**: A cover-note or summary section that orients the assessor before they review the technical file
- **FDA reviewers**: A pre-submission or device summary document section
- **Board / Investor audiences**: Regulatory readiness snapshot for due diligence or governance purposes
- **Regulatory Strategy meetings**: The "one-pager" briefing on a document's purpose, status, and key decisions

The executive summary translates dense regulatory content into clear, factual statements of:
- What this document is and why it exists (regulatory basis)
- What it covers (scope)
- What conclusions it reaches (key findings)
- What risks or gaps it flags (compliance status)
- What actions are required (recommendations)

## When to use

Trigger this skill when the user wants to:
- Prepare a cover note for a Notified Body technical file review
- Brief leadership on the regulatory status of a document or submission
- Create the summary section of a complex regulatory document
- Prepare a regulatory readiness report for investors or board
- Produce a PSUR / PMSR executive summary section

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

Require: Sector, Region, Artifact. Additionally ask:
- **Audience**: Leadership / Notified Body / FDA / Investor / Internal governance?
- **Document status**: Does a document exist (summary of an existing doc) or is this a framework for a future document?
- **Key messages**: Are there specific findings or conclusions the user needs to highlight?

Adjust tone, depth, and terminology for the stated audience:
- Leadership / Investor: Plain language, avoid jargon, quantify where possible
- Notified Body / FDA: Technical language, article/clause references retained, formal tone

### Step 2 — Produce the compliance status dashboard

Open the executive summary with a visual status table — the "at a glance" compliance picture:

| Item | Status | Notes |
|------|--------|-------|
| Document exists and is controlled | ✅ / ⚠️ / ❌ | [INSERT: Current version / Not yet drafted] |
| Applicable standard(s) addressed | ✅ / ⚠️ / ❌ | [INSERT: Standards covered] |
| Last reviewed / updated | ✅ / ⚠️ / ❌ | [INSERT: Date] |
| Key conclusions reached | ✅ / ⚠️ / ❌ | [INSERT: Summary of conclusions] |
| Open actions / remediation items | N items | [INSERT: Description] |

Use ✅ (compliant / complete), ⚠️ (partial / pending), ❌ (non-compliant / absent).

### Step 3 — Write the executive summary sections

1. **Regulatory Basis**: Why this document is required (cite the article/clause that mandates it) and what obligation it fulfils
2. **Scope**: What device(s), process(es), or product(s) this document covers
3. **Methodology**: How the document was produced (who authored it, what data sources were used, what standards were applied)
4. **Key Findings / Conclusions**: The main regulatory conclusions the document reaches — stated factually and precisely
5. **Compliance Assessment**: Overall compliance status, with any identified gaps or risks
6. **Recommended Actions**: Specific actions with owner and target date fields

### Step 4 — Add a regulatory timeline (if relevant)

For documents with mandatory review cycles or approaching deadlines (PMSR/PSUR cycle, CEP/CER update, SDP maintenance), add a timeline showing:
- Last review date
- Next mandatory update date
- Trigger events that would require an unscheduled update

## Output Format

```markdown
# Executive Summary: [Artifact Name]
**[Sector] — [Region] | Audience: [Audience type]**
**Framework: [Standards list] | Prepared by: [INSERT: Author] | Date: [INSERT: Date]**

---

## Compliance Status at a Glance

| Item | Status | Detail |
|------|--------|--------|
| Document controlled and approved | ✅ / ⚠️ / ❌ | [INSERT: Version / Author / Approver] |
| Applicable framework addressed | ✅ / ⚠️ / ❌ | [INSERT: Standards covered or gaps] |
| Current to applicable standards | ✅ / ⚠️ / ❌ | [INSERT: Date of last standard review] |
| Key conclusions documented | ✅ / ⚠️ / ❌ | [INSERT: Summary] |
| Open remediation items | [N] items | [INSERT: Description] |
| **Overall status** | ✅ Ready / ⚠️ Needs action / ❌ Not ready | [INSERT: One-line summary] |

---

## 1. Regulatory Basis

[INSERT: This [Document Name] is required under [Standard/Regulation Art.§] for [device category]. It fulfils the manufacturer's obligation to [regulatory obligation in plain language]. Failure to maintain a compliant [Document Name] would result in [regulatory consequence — e.g., CE marking non-renewal, FDA warning letter risk, MDSAP non-conformity].]

---

## 2. Scope

**Device(s) covered:** [INSERT: Device name(s), UDI, or system description]  
**Market(s) covered:** [INSERT: EU / US / Global and specific jurisdictions]  
**Document period:** [INSERT: Applicable date range or product lifecycle stage]  
**Exclusions:** [INSERT: Any explicitly excluded devices, versions, or use cases]

---

## 3. Methodology

[INSERT: This [Document Name] was authored by [Role] using [methodology — e.g., systematic literature review, clinical data analysis, risk assessment per ISO 14971]. Key data sources include [INSERT: sources]. The document was reviewed by [INSERT: roles] and approved by [INSERT: Responsible Person role] on [INSERT: date].]

---

## 4. Key Findings / Conclusions

[INSERT: State the 3–5 most important regulatory conclusions this document reaches. Use factual, precise language. For example: "The residual risk associated with [hazard] has been assessed as acceptable in accordance with ISO 14971 §9" or "Clinical data reviewed supports the safety and performance of the device for its intended use per IVDR Annex XIII."]

1. [Key finding 1]
2. [Key finding 2]
3. [Key finding 3]

---

## 5. Compliance Assessment

**Overall assessment:** [Compliant / Partially compliant — see actions below / Non-compliant — immediate action required]

**Identified gaps or risks:**
- [INSERT: Gap 1 — if none, state "No compliance gaps identified at the time of this review."]
- [INSERT: Gap 2]

---

## 6. Recommended Actions

| # | Action | Owner | Target Date | Priority |
|---|--------|-------|-------------|----------|
| 1 | [Specific action] | [INSERT: Role] | [INSERT: DD/MM/YYYY] | High / Medium / Low |
| 2 | ... | ... | ... | ... |

---

## 7. Regulatory Timeline

| Event | Date | Status |
|-------|------|--------|
| Document effective date | [INSERT] | ✅ |
| Last review / update | [INSERT] | ✅ / ⚠️ |
| Next mandatory review | [INSERT] | 📅 Scheduled |
| Next regulatory trigger (if known) | [INSERT] | 📅 Monitoring |

---
⚠️ *This executive summary requires review by a qualified Regulatory Affairs professional before distribution. For Notified Body or FDA submission, verify that all conclusions are consistent with the full underlying document.*
```

## Safety guardrails

- **No editorial spin**: Executive summaries must be factually accurate. If the document has gaps, the summary must say so. Do not produce a summary that overstates compliance status.
- **Audience calibration**: Plain-language summaries for leadership must not omit material compliance risks. Simplification of language ≠ omission of facts.
- **All conclusions must be sourced**: Every finding stated in the executive summary must be derivable from the underlying document. Do not add conclusions not present in the source.
- **Status indicators are placeholders**: The ✅ / ⚠️ / ❌ fields must be filled in by the user based on their actual document state — pre-fill only if the user provides the underlying document.
- **Human review mandatory**.

## Related skills

- `regulatoryflow-document-drafter` (01) — draft the underlying document first
- `regulatoryflow-gap-analysis` (02) — the gaps found feed the Compliance Assessment section
- `regulatoryflow-audit-prep` (04) — auditors may ask to see this summary during opening meetings
