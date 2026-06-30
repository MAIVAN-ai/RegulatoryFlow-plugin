---
name: regulatoryflow-template-builder
description: Create a compliant, ready-to-fill template for any regulatory document in MedTech (EU MDR / FDA), IVD (IVDR), SaMD/AI (IEC 62304 / PCCP / EU AI Act), or Pharma (GMP / ICH). Trigger on "create a template", "give me a template for", "regulatory document template", "SOP template", "fill-in template for my [document]", "blank form for compliance", or any request for a structured, pre-formatted regulatory document with placeholders. Output is a professional, immediately usable Markdown/Word-ready template with all mandatory sections, [INSERT DATA] fields, tables, and signature blocks. Human review required before use.
---

# Template Builder

## Purpose

Produce a **complete, immediately usable regulatory document template** for the specified artifact — not just an outline, but the full document structure with:
- Pre-formatted sections, tables, and signature blocks
- `[INSERT: field name]` placeholders for all variable content
- Instructional notes (in italics or callout boxes) explaining what each section requires
- Cross-reference placeholders linking to other QMS documents
- Version control and document change history tables
- Approval and review signature blocks compliant with QMS requirements

The template is designed to be handed directly to the authoring team, reducing the time to first draft by providing the structural scaffold that would otherwise take days to research and build.

## When to use

Trigger this skill when the user wants:
- A blank-but-structured document to start writing into
- A standard template for their QMS document set
- A model document structure for a new product line
- A compliant starting point for a specific regulatory submission artifact

Distinct from skill 01 (outline, which gives headings + descriptors) — this skill produces the actual document body ready to be filled in, including formatted tables, checkboxes, and pre-written boilerplate where the regulation permits it.

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

Require: Sector, Region, Artifact. Ask if the user wants:
- Markdown output (for direct editing) or Word-compatible format (for export via docx skill)
- Any organisation-specific elements to incorporate (e.g., company name, logo placeholder, document numbering format)

### Step 2 — Build the document control block

Every regulatory document template must open with:
- **Document header table**: Document title, ID, version, effective date, document type, classification
- **Revision history table**: Version | Date | Author | Description of Change | Approver
- **Distribution / Scope statement**
- **Regulatory references table**: Standard | Relevant Clause | Applicability to this document

### Step 3 — Generate the template body

For each section required by the applicable standards:
- Write the section heading with article/clause anchor
- Provide `[INSERT: ...]` fields for all variable content
- Include pre-written boilerplate where the regulation specifies exact wording (e.g., purpose statements, scope definitions)
- Include formatted tables where the standard requires tabular recording (e.g., risk assessment tables, test result tables, deviation logs)
- Add `*📝 Instruction: [what the author must write here]*` notes in italics to guide authoring
- Add checkboxes `☐` for verification items

### Step 4 — Approval and signature block

Close every template with:
- **Review and Approval table**: Role | Name | Signature | Date | electronic-signature compliant note
- **Next review date field**
- **Related documents cross-reference table**

### Step 5 — Template usage instructions

Add a brief section at the start titled "How to use this template" explaining:
- How to replace `[INSERT: ...]` fields
- How to handle `[OPTIONAL: ...]` sections
- Document control requirements upon first use
- Which sections require regulatory specialist review

## Output Format

```markdown
<!-- TEMPLATE: [Artifact Name] — [Sector] [Region] -->
<!-- Framework: [Standards list] | Version: 1.0 | Generated: [Date] -->

---

# How to use this template

1. Replace all `[INSERT: ...]` fields with your organisation's specific information.
2. Sections marked `[OPTIONAL: ...]` are required only if the noted condition applies to your device.
3. Delete all *📝 Instruction* notes before finalising the document.
4. This template requires review by a qualified Regulatory Affairs professional before use in a regulatory submission or QMS.
5. Assign a document ID per your organisation's document numbering scheme and add it to the header below.

---

## Document Control

| Field | Value |
|-------|-------|
| Document Title | [INSERT: Full Document Title] |
| Document ID | [INSERT: e.g., QMS-RMP-001] |
| Version | 1.0 |
| Effective Date | [INSERT: DD/MM/YYYY] |
| Document Type | [Type — e.g., Plan / Report / SOP / Checklist] |
| Owner | [INSERT: Document Owner Name and Role] |
| Approved by | [INSERT: Approver Name and Role] |

### Revision History

| Version | Date | Author | Description of Change | Approved By |
|---------|------|--------|----------------------|-------------|
| 1.0 | [INSERT: Date] | [INSERT: Name] | Initial release | [INSERT: Name] |

### Regulatory References

| Standard / Regulation | Clause(s) | Applicability |
|----------------------|-----------|---------------|
| [Primary Standard] | [Clause] | [Applicable requirement] |
| [Secondary Standard] | [Clause] | [Applicable requirement] |

---

## 1. Purpose and Scope

*📝 Instruction: State the purpose of this document and define its scope — what device(s), processes, or systems it covers.*

This [Document Type] establishes [INSERT: what it establishes] for [INSERT: Device Name / Process / System] developed and maintained by [INSERT: Company Name].

**Scope:** This document applies to [INSERT: Scope statement — device versions, product lines, organisational units covered].

**Out of scope:** [INSERT: Explicitly list what is excluded, e.g., "Legacy products manufactured before [date]"].

---

## 2. [Next Required Section] ([Standard Art.§])

*📝 Instruction: [Authoring instruction for this section]*

[INSERT: ...]

[PRE-WRITTEN BOILERPLATE WHERE APPLICABLE]

---

## Approval and Signatures

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Author | [INSERT: Name, Title] | _________________ | ____/____/____ |
| Reviewed by | [INSERT: Name, Title] | _________________ | ____/____/____ |
| Approved by | [INSERT: Name, Title] | _________________ | ____/____/____ |

*For electronic signatures: This document has been approved electronically in accordance with [INSERT: eSignature system name] and [21 CFR Part 11 / EU GMP Annex 11] requirements.*

**Next Scheduled Review Date:** [INSERT: DD/MM/YYYY, typically 1–3 years from effective date]

### Related Documents

| Document | Document ID | Version |
|----------|-------------|---------|
| [Related QMS Document] | [INSERT: ID] | [INSERT: Version] |

---
⚠️ *Template requires review by a qualified Regulatory Affairs professional before use. All [INSERT: ...] placeholders must be replaced. Verify against current official regulatory texts before submission.*
```

## Safety guardrails

- **Placeholders mandatory**: Never fill in specific product, company, or clinical data. All variable content must remain as `[INSERT: ...]`.
- **Instructional notes are not content**: Make it visually clear (italics + 📝 prefix) that instruction notes must be deleted before the document is finalised.
- **Framework integrity**: Template sections and their standard citations must match the declared sector/region combination exclusively.
- **No false compliance**: A filled template is not a compliant document. Include this caveat prominently.
- **Human review mandatory**.

## Related skills

- `regulatoryflow-document-drafter` (01) — outline first if structure is unclear
- `regulatoryflow-gap-analysis` (02) — use after filling the template to verify completeness
- `regulatoryflow-audit-prep` (04) — what auditors will expect to see in the filled template
