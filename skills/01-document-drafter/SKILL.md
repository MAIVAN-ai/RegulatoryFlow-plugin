---
name: regulatoryflow-document-drafter
description: Draft a detailed, hierarchical outline for any regulatory document in MedTech, IVD, SaMD/AI, or Pharma — with specific article and clause citations from the applicable regulatory framework. Trigger on "draft an outline for", "create an outline", "structure my [document]", "what sections should my [document] have", "help me write my Risk Management Plan / CEP / SDP / VMP / CAPA / PMS Plan" or any request to produce the skeleton or architecture of a regulatory artifact. Applies the correct framework (EU MDR/FDA/IMDRF × sector) automatically. Output is professional Markdown, audit-ready, with [INSERT DATA] placeholders for product-specific content. Human review required before submission.
---

# Document Drafter

## Purpose

Produce a **detailed, hierarchical outline** for a specified regulatory document — the complete section-by-section skeleton a Regulatory Affairs professional needs to begin writing, with:
- Correct heading hierarchy (Section → Sub-section → Sub-sub-section)
- Specific regulatory article/clause references anchoring each section
- Explanatory notes on what each section must contain to satisfy the standard
- [INSERT DATA] placeholders where product-specific information is required
- Compliance notes flagging cross-references between sections

This is the equivalent of a Senior Regulatory Affairs Lead or Quality Manager generating the gold-standard structural framework before the authoring team fills in the content.

## When to use

Trigger this skill when the user wants to:
- Draft or start writing a regulatory document from scratch
- Understand what sections a specific regulatory document must contain
- Create the table of contents / skeleton for a technical file component
- Verify their current document structure against regulatory requirements

Do **not** use this skill if the user wants a filled-in template (→ skill 03), a gap analysis against an existing document (→ skill 02), or auditor questions (→ skill 04).

## Regulatory Framework Reference

The outline structure and cited articles are driven entirely by Sector × Region. Apply only the framework for the declared combination.

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

Require before proceeding:
- **Sector** (MedTech_General / MedTech_IVD / SaMD_and_AI / Pharma)
- **Region** (EU / US / Global)
- **Artifact** (specific document name)
- **Role perspective** (default: Regulatory Affairs Lead; alternatives: Senior Quality Manager, Lead Auditor, Compliance Officer, AI Regulatory Specialist)

If not provided, run intake (skill 00) or ask directly.

### Step 2 — Select the governing standard

From the framework table, identify the primary standard to cite (always the first entry in the standards list for that sector/region combination). Use that standard for article-level citations throughout the outline.

### Step 3 — Generate the outline

Produce the outline in **Professional Markdown** with these rules:

1. **Heading hierarchy**: `## 1. Section Title` → `### 1.1 Sub-section` → `#### 1.1.1 Detail` 
2. **Regulatory anchor**: After each heading, cite the governing article/clause in parentheses — e.g., `(EU MDR Art. 10(2), ISO 14971 §4.1)`
3. **Content descriptor**: Under each heading, write 2–4 sentences describing what the section must contain to satisfy the cited requirement. Use precise regulatory terminology; no generic language.
4. **Placeholders**: Use `[INSERT: <field name>]` for all product-specific data (device name, device description, UDI, intended use, risk class, etc.)
5. **Cross-references**: Note where one section feeds another (e.g., "Risk acceptability criteria defined here are referenced in Section 5 — Risk Controls")
6. **Revision block**: Include a standard document header with `[INSERT: Document ID]`, `[INSERT: Version]`, `[INSERT: Effective Date]`, `[INSERT: Author]`, `[INSERT: Approver]`

### Step 4 — Add compliance notes

After the outline, add a **Compliance Notes** block listing:
- Sections with mandatory annexes or sub-documents (e.g., "Section 3 requires a standalone Risk Management Report per ISO 14971 §9")
- Common audit findings relevant to this document type
- Interoperability requirements (other QMS documents this artifact must align with)

## Output Format

```markdown
# [Artifact Name]
**[Sector] — [Region] | Framework: [Standards list]**
**Role Perspective: [Role]**

| Field | Value |
|-------|-------|
| Document ID | [INSERT: Document ID] |
| Version | [INSERT: Version] |
| Effective Date | [INSERT: Effective Date] |
| Author | [INSERT: Author Name, Role] |
| Approver | [INSERT: Approver Name, Role] |
| Classification | [INSERT: Risk Class / Product Category] |

---

## 1. [Section Title] ([Primary Standard Art./§])

[2–4 sentences: what this section must contain and why the cited article requires it. Use precise regulatory terminology.]

### 1.1 [Sub-section] ([Standard Art./§])

[Content descriptor + any INSERT placeholders]

#### 1.1.1 [Detail level if needed]

[Content descriptor]

---

## 2. [Next Section] ...

---

## Compliance Notes

- **Mandatory sub-documents**: [list]
- **Common audit findings**: [list]
- **QMS cross-references**: [list of related documents this artifact must align with]

---
⚠️ *This outline requires review by a qualified Regulatory Affairs professional before use. Verify all cited articles against the current official text (EUR-Lex / FDA.gov / ISO). [INSERT DATA] placeholders must be replaced with product-specific information before submission.*
```

## Example

**Input**: Draft an outline for an EU MDR Risk Management Plan for a Class IIb active implantable cardiac device.

**Skill response** (abbreviated):

```markdown
# Risk Management Plan
**MedTech_General — EU | Framework: EU MDR 2017/745, ISO 13485:2016, ISO 14971:2019, MEDDEV 2.7/1 Rev 4**
**Role Perspective: Regulatory Affairs Lead**

| Field | Value |
|-------|-------|
| Document ID | [INSERT: Document ID, e.g., RMP-001] |
| Version | [INSERT: Version, e.g., 1.0] |
| ...  | ... |

---

## 1. Scope and Intended Use (EU MDR Art. 2(1), ISO 14971 §4.1)

Define the device and its intended use as the boundary of this Risk Management Plan. The scope must encompass all reasonably foreseeable uses and misuses identified during intended use analysis. For active implantable cardiac devices, the scope must explicitly address both implantation-phase and chronic-implant-phase hazards per MDR Annex I §1.

- Device trade name: [INSERT: Device Trade Name]
- UDI-DI: [INSERT: UDI-DI]
- Intended patient population: [INSERT: Patient Population, e.g., adults with symptomatic bradycardia]
- Intended use: [INSERT: Intended Use Statement per MDR Art. 2(12)]
- Contraindications: [INSERT: Contraindications List]

### 1.1 Risk Management Scope Boundaries (ISO 14971 §4.1(a))

State explicitly what is within and outside the scope of this plan — including software components, accessories, and patient-contacting materials. Software of unknown provenance (SOUP) must be listed if IEC 62304 applies as a subordinate standard.

...

## 2. Risk Management Policy (ISO 14971 §4.2, EU MDR Annex I §8)

Define the organisation's risk management policy, including the criteria for risk acceptability. The policy must reference the manufacturer's Quality Policy (ISO 13485 §5.3) and define the acceptable residual risk threshold using both individual risk and overall residual risk criteria consistent with MEDDEV 2.7/1 Rev 4 §A6.

...

## Compliance Notes

- **Mandatory sub-documents**: Risk Management Report (ISO 14971 §9), Risk Management File Index, Post-Market Safety Update (PMSU) (MDR Art. 86)
- **Common audit findings**: Missing risk acceptability criteria rationale; SOUP not captured; overall residual risk not explicitly accepted by responsible person
- **QMS cross-references**: Clinical Evaluation Plan (CEP), Post-Market Surveillance Plan (PMS), Design History File (DHF)
```

## Safety guardrails

- **Framework integrity**: Cite only standards from the declared sector/region framework. ISO 14971 is the risk management standard for MedTech; ICH Q9 is the risk management standard for Pharma. Never substitute.
- **No hallucinated article numbers**: Only cite article numbers you are confident exist in the stated standard. If unsure of the exact clause, cite at section level (e.g., "ISO 14971 §4" rather than inventing a sub-clause).
- **Placeholders, not content**: Never fill in actual product data. All product-specific fields use [INSERT: field name] so the user cannot accidentally submit AI-generated product claims.
- **Human review mandatory**: State clearly at the end that the output requires professional review before use.
- **Regulatory text currency**: Note that the user should verify cited articles against the current official text, as standards and guidance documents are updated.

## Related skills

- `regulatoryflow-intake` (00) — context collection and routing
- `regulatoryflow-gap-analysis` (02) — check an existing document against the same framework
- `regulatoryflow-template-builder` (03) — produce a fillable template rather than an outline
- `regulatoryflow-audit-prep` (04) — what auditors will look for in this document
- `regulatoryflow-medtech-general` (10), `regulatoryflow-ivd` (11), `regulatoryflow-samd-ai` (12), `regulatoryflow-pharma-gmp` (13) — domain context for the relevant sector
