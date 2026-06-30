# RegulatoryFlow Plugin

**Regulatory Affairs workflow skills for MedTech, IVD, SaMD & AI, and Pharma.**

Built on the [ADHOCON Regulatory Prompt Library](https://github.com/rlwadh/regulatory-prompt-library) — 2,250 structurally validated, framework-aware prompts covering FDA, EU MDR, IVDR, ISO 13485, IEC 62304, EU AI Act, and ICH.

---

## What it does

RegulatoryFlow gives you a full set of regulatory document skills organized by **task type**. Each skill automatically applies the right regulatory framework (EU/US/Global × sector) — no generic advice, no cross-contamination of standards.

| Skill | Trigger | What it produces |
|-------|---------|-----------------|
| `00-intake` | "I need help with a regulatory document" | Captures sector, region, artifact — routes to the right skill |
| `01-document-drafter` | "Draft an outline for my [document]" | Hierarchical outline with specific article citations |
| `02-gap-analysis` | "Gap analysis for my [document]" | Compliance gap checklist vs. applicable standards |
| `03-template-builder` | "Create a template for my [document]" | Compliant template with [INSERT DATA] placeholders |
| `04-audit-prep` | "Auditor questions for my [document]" | Likely notified body / FDA auditor question list |
| `05-risk-reviewer` | "Risk review strategy for my [document]" | Risk-based document review plan |
| `06-executive-summary` | "Executive summary for my [document]" | Structure for leadership / submission summaries |
| `10-medtech-general` | "MDR compliance question" | MedTech General domain expertise (MDR, FDA QSR, IMDRF) |
| `11-ivd` | "IVDR / IVD question" | IVD domain expertise (IVDR, FDA 809, MDCG) |
| `12-samd-ai` | "AI regulation / SaMD question" | SaMD & AI expertise (IEC 62304, PCCP, EU AI Act, NIST) |
| `13-pharma-gmp` | "GMP question" | Pharma domain expertise (EudraLex, FDA cGMP, ICH) |
| `99-orchestrator` | "What should I work on next?" | Journey state + next-best-action for your RA workflow |

---

## Regulatory Framework Coverage

### MedTech General
| Region | Standards |
|--------|-----------|
| EU | EU MDR 2017/745, ISO 13485:2016, ISO 14971:2019, MEDDEV 2.7/1 Rev 4 |
| US | FDA 21 CFR Part 820 (QSR), 21 CFR Part 11, ISO 14971:2019, FDA Human Factors Guidance |
| Global | IMDRF/GRRP WG/N47 (Essential Principles), ISO 13485:2016 (MDSAP) |

### IVD
| Region | Standards |
|--------|-----------|
| EU | EU IVDR 2017/746, ISO 13485:2016, ISO 14971, MDCG Guidelines for IVDs |
| US | FDA 21 CFR Part 809 (IVDs), 21 CFR Part 820, CLIA Regulations |
| Global | IMDRF/IVD WG/N64 (IVD Essential Principles), GHTF/SG5/N7 |

### SaMD & AI
| Region | Standards |
|--------|-----------|
| EU | EU MDR 2017/745 (Rule 11), IEC 62304:2006+A1:2015, IEC 82304-1, EU AI Act |
| US | FDA 21 CFR Part 820, FDA AI/ML Action Plan, FDA PCCP Guidance, NIST AI RMF |
| Global | IMDRF/SaMD WG/N41 (SaMD Clinical Evaluation), ISO/IEC 42001, IEC 62304 |

### Pharma
| Region | Standards |
|--------|-----------|
| EU | EudraLex Vol 4 (EU GMP), EU GMP Annex 11, EMA Scientific Guidelines |
| US | FDA 21 CFR Part 210/211 (cGMP), 21 CFR Part 11, FDA Data Integrity Guidance |
| Global | ICH Q7 (API), ICH Q9 (Risk Management), ICH Q10 (Pharma QS), PIC/S GMP Guide |

---

## Supported Artifacts

**MedTech General:** Risk Management Plan · Clinical Evaluation Plan (CEP) · Post-Market Surveillance (PMS) Plan · Technical File Index (Annex II) · Biocompatibility Assessment (ISO 10993) · GSPR Checklist

**IVD:** Performance Evaluation Report (PER) · Scientific Validity Report · Analytical Performance Report · Clinical Performance Report · PMPF Plan

**SaMD & AI:** Software Development Plan (SDP) · Software Requirements Specification (SRS) · Cybersecurity Vulnerability Management Plan · PCCP · AI Model Card / Datasheet · Algorithm Bias Assessment Report · Usability Engineering File (IEC 62366)

**Pharma:** Site Master File (SMF) · Validation Master Plan (VMP) · OOS Investigation SOP · Batch Record Review Checklist · APQR · Stability Study Protocol · CAPA SOP

---

## Disclaimer

All outputs require review by a qualified Regulatory Affairs professional. These skills do not constitute regulatory advice. Always verify against the latest official texts (EUR-Lex, FDA.gov, ISO, IMDRF). Human-in-the-loop review is mandatory before any submission or regulatory filing.

---

*Based on the AdHoCon Regulatory Prompt Library (MIT License). Author: Rudolf Wagner, ISO 17024 Certified Expert.*
