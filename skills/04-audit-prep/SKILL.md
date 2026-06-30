---
name: regulatoryflow-audit-prep
description: Generate a comprehensive list of likely auditor questions for any regulatory document — from a Notified Body (EU MDR/IVDR), FDA investigator (21 CFR), MDSAP auditor, or internal QMS auditor perspective. Trigger on "auditor questions", "what will an auditor ask", "prepare for audit", "Notified Body questions", "FDA inspection prep", "audit readiness", "what should I expect in my audit", "audit checklist for my [document]", "prepare me for a Notified Body review of my [document]". Produces questions grouped by topic with difficulty level and tips for strong answers. Human review required before audit preparation.
---

# Audit Prep

## Purpose

Generate the **questions a Notified Body assessor, FDA investigator, MDSAP auditor, or internal quality auditor will ask** about a specific regulatory document — so the Regulatory Affairs team can prepare evidence-backed answers before the audit begins.

This skill draws on the knowledge of a **Lead Auditor** to anticipate:
- Opening questions about document purpose and scope
- Deep-dive questions targeting the most commonly non-compliant areas
- Evidence-of-implementation questions (does the documented process actually happen?)
- Cross-reference questions (does this document align with other QMS documents?)
- Historical questions (has the document been updated following required triggers?)

Questions are categorised by topic and labelled by typical auditor seniority level / difficulty: Foundational (expected of any auditor) → Technical (experienced auditor) → Expert (deep-dive, Notified Body technical expert or FDA specialist).

## When to use

Trigger this skill when the user is:
- Preparing for an upcoming Notified Body assessment (ISO 13485, EU MDR, IVDR)
- Preparing for an FDA inspection or 510(k)/PMA review
- Conducting an internal pre-audit mock exercise
- Training RA/QA staff on what to expect during document review

Do not use this skill to generate a gap analysis checklist (→ skill 02) or a risk-based review strategy (→ skill 05) — though these are natural complements.

## Regulatory Framework Reference

| Sector | Region | Mandatory Standards | Audit Body |
|--------|--------|---------------------|-----------|
| MedTech_General | EU | EU MDR 2017/745, ISO 13485:2016, ISO 14971:2019, MEDDEV 2.7/1 Rev 4 | Notified Body |
| MedTech_General | US | FDA 21 CFR Part 820 (QSR), 21 CFR Part 11, ISO 14971:2019 | FDA (QSIT/CAPA) |
| MedTech_General | Global | IMDRF/GRRP WG/N47, ISO 13485:2016 (MDSAP) | MDSAP Auditor |
| MedTech_IVD | EU | EU IVDR 2017/746, ISO 13485:2016, MDCG Guidelines | Notified Body |
| MedTech_IVD | US | FDA 21 CFR Part 809, 21 CFR Part 820, CLIA | FDA |
| MedTech_IVD | Global | IMDRF/IVD WG/N64, GHTF/SG5/N7 | MDSAP Auditor |
| SaMD_and_AI | EU | EU MDR (Rule 11), IEC 62304, IEC 82304-1, EU AI Act | Notified Body + AI Act Notified Body |
| SaMD_and_AI | US | FDA 21 CFR Part 820, FDA PCCP Guidance, NIST AI RMF | FDA (Software) |
| SaMD_and_AI | Global | IMDRF/SaMD WG/N41, ISO/IEC 42001, IEC 62304 | MDSAP Auditor |
| Pharma | EU | EudraLex Vol 4 (EU GMP), Annex 11, EMA Guidelines | EMA / Competent Authority |
| Pharma | US | FDA 21 CFR Part 210/211 (cGMP), 21 CFR Part 11 | FDA (GMP Inspection) |
| Pharma | Global | ICH Q7/Q9/Q10, PIC/S GMP Guide | PIC/S Inspector |

## Workflow

### Step 1 — Confirm context

Require: Sector, Region, Artifact. Optionally ask which audit type (Notified Body / FDA / MDSAP / internal) if not determinable from context.

### Step 2 — Generate questions by topic cluster

Organise questions into 5–8 topic clusters relevant to the artifact. For each cluster:
- 2–3 **Foundational** questions (any auditor will ask these)
- 2–3 **Technical** questions (experienced auditor, targets frequent non-conformities)
- 1–2 **Expert** questions (deep-dive, targets edge cases and cross-system consistency)

Label each question with: `[F] Foundational` / `[T] Technical` / `[E] Expert`

### Step 3 — Add answer guidance

For each question (or at least for Technical and Expert questions), add a brief **Answer tip** explaining:
- What evidence the auditor expects to see
- What a strong vs. weak answer looks like
- Common pitfalls that lead to observations or non-conformities

### Step 4 — Add a pre-audit preparation checklist

Close the output with a brief **Pre-Audit Preparation Checklist** — the documents, records, and personnel the team should have ready before the audit begins.

## Output Format

```markdown
# Audit Preparation: [Artifact Name]
**[Sector] — [Region] | Audit body: [Notified Body / FDA / MDSAP / Internal]**
**Framework: [Standards list]**

---

## How to use this guide

Review each question with the document owner and identify the evidence you would cite in response. For Technical and Expert questions, prepare written notes with specific document sections, record references, and objective evidence. Conduct a mock question-and-answer session before the audit.

---

## Topic 1: [Topic Name]

### [F] [Question text]
*Answer tip: [What the auditor expects; what strong evidence looks like; common pitfalls]*

### [F] [Question text]
*Answer tip: ...*

### [T] [Question text]
*Answer tip: ...*

### [T] [Question text]
*Answer tip: ...*

### [E] [Question text]
*Answer tip: ...*

---

## Topic 2: [Next Topic]

...

---

## Pre-Audit Preparation Checklist

Before the audit, ensure the following are ready and accessible:

- [ ] Current approved version of the [Artifact Name] (version and effective date visible)
- [ ] Complete revision history with rationale for each change
- [ ] [INSERT: other required records specific to the artifact]
- [ ] List of related QMS documents and their current versions
- [ ] Personnel who can be interviewed (Author, QMS owner, Responsible Person)
- [ ] Evidence of last management review / document review cycle

---
⚠️ *Audit preparation output requires review by a qualified Regulatory Affairs or Quality professional. Rehearse answers with objective evidence — never respond to an auditor without evidence to support claims.*
```

## Example

**Input**: Generate auditor questions for my EU MDR Post-Market Surveillance Plan.

**Skill response** (abbreviated):

```markdown
# Audit Preparation: Post-Market Surveillance (PMS) Plan
**MedTech_General — EU | Audit body: Notified Body (EU MDR)**
**Framework: EU MDR 2017/745, ISO 13485:2016, ISO 14971:2019, MEDDEV 2.7/1 Rev 4**

## Topic 1: PMS Plan Completeness and Scope

### [F] Walk me through the scope of your PMS Plan — which devices does it cover, and how is the intended use reflected in the surveillance activities?
*Answer tip: Auditors verify that the PMS Plan covers the exact device and all intended uses stated in the Technical File. A common observation is that the plan covers the device name but not all intended use variants (e.g., different size configurations, accessory combinations).*

### [T] How have you determined which post-market data sources are relevant and proportionate to the risk class of this device?
*Answer tip: For Class IIa and above, the PMS Plan must justify the data sources selected relative to risk. Simply listing "MDR complaint handling and literature review" is often insufficient for Class III devices — a Notified Body will expect a risk-based rationale for each source (MDR Art. 83(3)).*

### [E] Your PMS Plan references a literature review methodology — show me the search strategy and how you've ensured the state of the art has been captured for equivalent devices.
*Answer tip: Expert auditors may ask to see the actual search strings, databases used, and inclusion/exclusion criteria. A plan that references "periodic literature review" without a documented methodology will generate a non-conformity under MDR Annex III §1.1(b).*

## Topic 2: PMSR / PSUR Trigger and Frequency

### [F] When is a PMCF study indicated by your PMS Plan, and what triggers its initiation?
...

## Pre-Audit Preparation Checklist

- [ ] Current approved PMS Plan (version and date of last review visible)
- [ ] PMSR or PSUR (depending on risk class) generated from this plan
- [ ] Evidence of complaint data feeds from vigilance and MDR Art. 87 reporting
- [ ] Literature search logs and results from the last review cycle
- [ ] PMCF plan (if applicable) and evidence of PMCF activities
- [ ] Minutes of the last management review referencing PMS data
```

## Safety guardrails

- **Auditor perspective only**: Write questions as an auditor would ask them — probing, evidence-seeking, sometimes adversarial. Do not soften questions.
- **No guaranteed question list**: State that these are likely questions, not guaranteed ones. Actual audit questions vary by auditor, audit type, and product.
- **Evidence-based preparation**: Emphasise that every answer requires objective evidence. Prepare the team to never answer based on memory alone.
- **Human review mandatory**.

## Related skills

- `regulatoryflow-gap-analysis` (02) — run before audit prep to fix gaps
- `regulatoryflow-risk-reviewer` (05) — risk-prioritise which audit topics carry the most exposure
- `regulatoryflow-document-drafter` (01) — if the document being audited doesn't yet exist
