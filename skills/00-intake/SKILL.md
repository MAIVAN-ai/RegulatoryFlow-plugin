---
name: regulatoryflow-intake
description: Entry point for any regulatory document task in MedTech, IVD, SaMD/AI, or Pharma. Use when the user mentions a regulatory document, compliance need, audit preparation, or framework question without specifying what they need. Trigger on phrases like "I need help with regulatory", "I need to create a [document name]", "compliance question", "MDR/IVDR/FDA/GMP question", "regulatory review", or any mention of regulatory document names (CEP, PMS Plan, SDP, VMP, CAPA, etc.). Captures sector, region, artifact, and task type, then routes to the correct RegulatoryFlow skill.
---

# Regulatory Intake

## Purpose

This is the **entry point** for all RegulatoryFlow tasks. Before generating any regulatory content, you need four pieces of context — sector, region, artifact, and task type — to guarantee the right regulatory framework is applied. This skill collects that context and routes to the correct downstream skill.

Without this context, regulatory output risks using the wrong standards (e.g., ISO 14971 risk management applied to a Pharma context, which should be ICH Q9). The AdHoCon validation matrix makes this explicit: no cross-contamination of standards is allowed.

## When to use

Trigger this skill whenever:
- The user asks for help with a regulatory document without specifying sector/region
- The user mentions a regulatory artifact (Risk Management Plan, VMP, SDP, CAPA, etc.)
- The user asks a general regulatory compliance question
- No prior context exists about sector or region in the conversation

Skip this skill and go directly to a task skill if the user has already clearly stated their sector + region + artifact + task (e.g., "Create a gap analysis for my EU MDR Risk Management Plan").

## Regulatory Framework Reference

The framework applied is determined entirely by Sector × Region. Never mix frameworks across sectors.

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

## Artifact Catalogue

**MedTech_General:** Risk Management Plan · Clinical Evaluation Plan (CEP) · Post-Market Surveillance (PMS) Plan · Technical File Index (Annex II) · Biocompatibility Assessment (ISO 10993) · General Safety and Performance Requirements (GSPR) Checklist

**MedTech_IVD:** Performance Evaluation Report (PER) · Scientific Validity Report · Analytical Performance Report · Clinical Performance Report · IVD Post-Market Performance Follow-up (PMPF) Plan

**SaMD_and_AI:** Software Development Plan (SDP) · Software Requirements Specification (SRS) · Cybersecurity Vulnerability Management Plan · Predetermined Change Control Plan (PCCP) · AI Model Card / Datasheet · Algorithm Bias Assessment Report · Usability Engineering File (IEC 62366 for SaMD)

**Pharma:** Site Master File (SMF) · Validation Master Plan (VMP) · Out of Specification (OOS) Investigation SOP · Batch Record Review Checklist · Annual Product Quality Review (APQR) · Stability Study Protocol · Corrective and Preventive Action (CAPA) SOP

## Workflow

### Step 1 — Extract what you already know

Scan the user's message for:
- **Sector signals**: MDR/IVDR → MedTech; IVD/diagnostics → MedTech_IVD; SaMD/AI/software/algorithm → SaMD_and_AI; GMP/pharma/API/drug → Pharma
- **Region signals**: EU/Europe/Notified Body/CE marking → EU; FDA/510k/PMA/US → US; IMDRF/global/MDSAP → Global
- **Artifact signals**: Any document name from the artifact catalogue above
- **Task signals**: "draft/outline" → skill 01; "gap analysis/checklist" → skill 02; "template" → skill 03; "audit questions/audit prep" → skill 04; "risk review/risk-based" → skill 05; "executive summary" → skill 06

### Step 2 — Ask only for what is missing

If sector, region, and artifact are clear from context, skip to Step 3.

If any are missing, ask the user in one focused question — do not run through them one by one. Example:

> "To generate audit-ready output with the right regulatory framework, I need a few details:
> - **Sector**: MedTech (hardware), IVD (diagnostics), SaMD/AI, or Pharma?
> - **Region**: EU, US (FDA), or Global/IMDRF?
> - **Document**: Which artifact are you working on? (e.g., Risk Management Plan, VMP, SDP)
> - **Task**: What do you need? Outline · Gap analysis · Template · Audit prep · Risk review · Executive summary"

### Step 3 — Confirm the framework

State the resolved context and the regulatory framework that will be applied before generating any content:

```
Sector: [sector]
Region: [region]
Artifact: [artifact]
Task: [task]
Framework: [comma-separated standards list from the reference table]
Role perspective: [role if specified, else default to Regulatory Affairs Lead]
```

Ask the user to confirm or correct before proceeding.

### Step 4 — Route to the correct skill

| Task | Route to |
|------|----------|
| Draft a detailed outline | `regulatoryflow-document-drafter` (skill 01) |
| Compliance gap analysis | `regulatoryflow-gap-analysis` (skill 02) |
| Compliant template | `regulatoryflow-template-builder` (skill 03) |
| Auditor questions | `regulatoryflow-audit-prep` (skill 04) |
| Risk-based review strategy | `regulatoryflow-risk-reviewer` (skill 05) |
| Executive summary structure | `regulatoryflow-executive-summary` (skill 06) |
| Domain question (MedTech) | `regulatoryflow-medtech-general` (skill 10) |
| Domain question (IVD) | `regulatoryflow-ivd` (skill 11) |
| Domain question (SaMD/AI) | `regulatoryflow-samd-ai` (skill 12) |
| Domain question (Pharma) | `regulatoryflow-pharma-gmp` (skill 13) |
| "What next?" | `regulatoryflow-orchestrator` (skill 99) |

Pass the confirmed context (sector, region, artifact, framework string, role) to the routed skill so it does not need to re-ask.

## Safety guardrails

- **Never mix frameworks**: A Pharma prompt must never cite ISO 14971 as its risk management standard; that is ICH Q9. A MedTech prompt must not cite ICH Q9. The intake step is the firewall.
- **Always confirm before generating**: State the resolved framework and get explicit confirmation. One wrong sector/region choice invalidates the entire output.
- **Flag ambiguity**: If the artifact could belong to more than one sector (e.g., "CAPA SOP" exists in both MedTech and Pharma contexts), ask explicitly which sector governs this CAPA.
- **Human review mandatory**: Outputs require review by a qualified RA professional before any submission or regulatory filing.

## Related skills

- `regulatoryflow-document-drafter` (01) — draft outlines
- `regulatoryflow-gap-analysis` (02) — compliance checklists
- `regulatoryflow-template-builder` (03) — compliant templates
- `regulatoryflow-audit-prep` (04) — auditor questions
- `regulatoryflow-risk-reviewer` (05) — risk-based review strategies
- `regulatoryflow-executive-summary` (06) — executive summary structures
- `regulatoryflow-orchestrator` (99) — what to work on next
