---
name: regulatoryflow-orchestrator
description: Journey orchestrator for regulatory affairs workflows — tracks where you are in your regulatory document lifecycle and recommends the next-best-action. Trigger on "what should I work on next", "what's my next step", "where am I in my submission", "help me plan my regulatory workflow", "what regulatory documents do I need", "regulatory roadmap", "submission readiness", "what order should I do these in", "regulatory project plan", or any request for a structured view of what a regulatory professional should do next. Routes to the correct RegulatoryFlow skill based on journey state. Human review required before submission decisions.
---

# Journey Orchestrator

## Purpose

Track the **regulatory document lifecycle state** for a project and recommend the **next-best-action** — the highest-value task a Regulatory Affairs professional should do next given their current position in the journey.

This skill answers: *"Given what I've told you about my project and what's done/pending, what should I work on next and in what order?"*

It maps the user's declared journey state to a sequence of prioritised actions, routing to the specific RegulatoryFlow skill that executes each action. It is the strategic layer that sits above the task skills (01–06) and domain skills (10–13).

## When to use

Trigger this skill when the user:
- Wants a bird's-eye view of their regulatory workflow
- Is starting a new regulatory project and needs a roadmap
- Is preparing a submission and wants to check they haven't missed anything
- Wants to prioritise competing regulatory tasks
- Has multiple documents in various states and needs to know what to focus on

## Journey States

A regulatory project moves through these states. The orchestrator identifies which state the user is in and what is needed to advance.

| State | Typical indicators | Priority next action |
|-------|-------------------|---------------------|
| **Pre-project** | No documents started; device concept or early design | Domain context (skill 10/11/12/13) → classification → submission strategy |
| **Document creation** | Technical file being built; documents in draft | skill 01 (outline) → skill 03 (template) → author → skill 02 (gap check) |
| **Pre-submission review** | Documents drafted; preparing for Notified Body or FDA | skill 02 (gap analysis) → skill 05 (risk review) → skill 04 (audit prep) |
| **Audit/Assessment active** | NB assessment or FDA inspection in progress or imminent | skill 04 (auditor questions) → evidence preparation |
| **Post-market** | Device on market; PMS cycle ongoing | skill 01 (PMSR/PSUR outline) → skill 06 (executive summary) → schedule review cycle |
| **Remediation** | Non-conformities or gaps found; corrective action needed | skill 02 (gap analysis of remediation) → skill 05 (risk prioritisation) |

## Regulatory Document Dependency Map

Some documents must exist before others can be written. The orchestrator uses this dependency map to sequence tasks correctly.

### EU MDR Technical File (MedTech General)

```
Classification determination
  └── GSPR Checklist (Annex I)
      ├── Risk Management Plan (ISO 14971)
      │     └── Risk Management Report
      ├── Clinical Evaluation Plan (CEP)
      │     └── Clinical Evaluation Report (CER)
      │           └── PMCF Plan
      ├── Biocompatibility Assessment (ISO 10993) [if applicable]
      ├── [SDP + SRS] if device contains software (IEC 62304)
      └── Technical File Index (Annex II)
            └── PMS Plan
                  └── PMSR (Class IIa) or PSUR (Class IIb/III)
```

### EU IVDR Technical Documentation (IVD)

```
Classification determination (Classes A–D)
  └── Performance Evaluation Report (PER)
      ├── Scientific Validity Report
      ├── Analytical Performance Report
      └── Clinical Performance Report
            └── PMPF Plan (Classes B, C, D)
  └── GSPR Checklist (Annex I)
  └── PMS Plan
        └── Periodic Safety Update Report
```

### FDA 510(k) / PMA Preparation (MedTech/IVD)

```
Device classification (21 CFR Part 862–892)
  └── Predicate identification (510(k)) or PMA strategy
      ├── Design controls documentation (§820.30)
      │     ├── Design inputs / SRS
      │     ├── Verification and validation records
      │     └── Design History File (DHF)
      ├── Risk management file (ISO 14971)
      ├── Performance testing / biocompatibility data
      └── 510(k) submission package
```

### EU/FDA SaMD / AI Pathway

```
SaMD qualification (IMDRF SaMD WG/N10)
  └── MDR Rule 11 class determination (EU)
  └── FDA software classification
      ├── IEC 62304 safety class assignment
      │     ├── Software Development Plan (SDP)
      │     ├── Software Requirements Specification (SRS)
      │     └── Software verification & validation records
      ├── Usability Engineering File (IEC 62366)
      ├── Cybersecurity Vulnerability Management Plan
      ├── PCCP (US FDA — for adaptive AI/ML)
      └── AI Model Card / Algorithm Bias Assessment Report
```

### Pharma GMP Documentation Suite

```
Site Master File (SMF)
  └── Validation Master Plan (VMP)
      ├── Equipment qualification records (IQ/OQ/PQ)
      ├── Process validation reports
      └── Computer System Validation (Annex 11)
  └── Batch Record templates → Batch Record Review Checklist
  └── Stability Study Protocol → Stability data → Shelf-life determination
  └── CAPA SOP → CAPA records
  └── Annual Product Quality Review (APQR)
  └── OOS Investigation SOP → OOS records
```

## Workflow

### Step 1 — Determine journey state

Ask the user:
- What sector and region? (if not already established)
- What is the device/product?
- What is the submission target? (CE Mark / 510(k) / PMA / FDA IND/NDA / MDSAP)
- What is the target submission date (if any)?
- Which documents already exist (draft or approved)?
- Which documents have been reviewed by an expert?
- Which documents have been reviewed by a Notified Body / FDA (if any)?

### Step 2 — Map the dependency chain

Using the appropriate dependency map above, identify:
- Documents that are **complete and approved** ✅
- Documents that are **drafted but not reviewed** ⚠️
- Documents that are **not yet started** ❌
- Documents that are **blocked** (cannot be started until a predecessor is complete) 🔒

### Step 3 — Generate the next-best-action plan

Prioritise actions using this logic:
1. **Safety-critical gaps first**: If any document required for patient safety (Risk Management Plan, GSPR Checklist, IEC 62304 safety class documentation) is missing, flag as Priority 1.
2. **Submission blockers second**: Documents without which the submission cannot proceed.
3. **Audit risk third**: Documents likely to be examined first in an NB or FDA review.
4. **Completeness fourth**: Documents that are nice-to-have or optional given the device's risk class.

### Step 4 — Route to the correct skill

For each recommended action, name the RegulatoryFlow skill that executes it and offer to invoke it.

## Output Format

```markdown
# Regulatory Journey Status: [Device/Product Name]
**[Sector] — [Region] | Target: [Submission type] | Target date: [INSERT or TBD]**

---

## Document Status Dashboard

| Document | Status | Dependency | Priority | Next Action |
|----------|--------|-----------|----------|-------------|
| [Document 1] | ✅ Complete / ⚠️ Draft / ❌ Not started / 🔒 Blocked | [Predecessor doc] | 1–5 | [Specific next step + skill to use] |
| [Document 2] | ... | ... | ... | ... |

---

## Next-Best-Action Plan

### Priority 1 — Do this first (Safety-Critical / Submission Blocker)

**Action**: [Specific task]  
**Why**: [Regulatory reason — what risk does this address?]  
**Skill to use**: `[skill name and number]`  
**Estimated effort**: [Low / Medium / High]

### Priority 2 — Do next

**Action**: [Specific task]  
**Why**: [Regulatory reason]  
**Skill to use**: `[skill name]`

### Priority 3 — Then

...

---

## Submission Readiness Assessment

| Category | Ready | Gaps |
|----------|-------|------|
| Safety-critical documents | ✅ / ⚠️ / ❌ | [If not ready: what's missing] |
| Technical file complete | ✅ / ⚠️ / ❌ | |
| Performance/clinical data | ✅ / ⚠️ / ❌ | |
| QMS documentation | ✅ / ⚠️ / ❌ | |
| Post-market surveillance ready | ✅ / ⚠️ / ❌ | |
| **Overall readiness** | ✅ Ready / ⚠️ Needs work / ❌ Not ready | |

---
⚠️ *Journey orchestration output requires validation by a qualified Regulatory Affairs professional. Submission readiness determinations are indicative — consult your Notified Body or regulatory counsel before finalising submission timelines.*
```

## Safety guardrails

- **Dependency enforcement**: Never recommend writing a dependent document before its predecessor exists (e.g., do not recommend drafting a CER before a CEP exists; do not recommend drafting a batch record before the manufacturing process is validated).
- **Submission readiness is not a green light**: The orchestrator assesses document status — it cannot assess document quality. A complete document set with poor content is not submission-ready. State this explicitly.
- **Regulatory calendar awareness**: If the user provides a submission date, flag if the remaining work is unlikely to be completable in the time available (e.g., NB assessment for Class III typically takes 6–18 months).
- **Human review mandatory**.

## Related skills

- `regulatoryflow-intake` (00) — start here if context is unknown
- All task skills (01–06) — the orchestrator routes to these for execution
- All domain skills (10–13) — for framework questions that arise during journey planning
