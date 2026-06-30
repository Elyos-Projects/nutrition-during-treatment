# Nutrition-During-Treatment — TASKS.md

> Status: Draft · Version: 0.1.0 · Last updated: 2026-06-28 · Owner: TBD (maintainer) · Lane: donated

Backlog for **Nutrition-During-Treatment** (slug: `nutrition-during-treatment`), an open-access,
plain-language, **source-cited** library of nutrition guidance for people in **active cancer
treatment** and their caregivers — synthesized only from authoritative bodies, **oncology-dietitian
(RDN/RD-CSO) signed off**, with oncologist/advocate review by surface, framed as **education, not
medical advice**, with verified red-flag escalation and provenance on every assertion. See `PLAN.md`.

This is a **HIGH risk-tier**, patient-facing project under the binding **cancer-domain guardrails**:
open-access/aggregate/de-identified data only; per-source license verification; expert sign-off before
any patient-facing content ships. The **safety / "not medical advice" / red-flag policy spec and the
provenance/licensing model are the first build items**. No clinical partner, distribution channel, or
credentialed reviewer is yet secured, so delivery-dependent tasks carry `requestor: TO BE SECURED` and
`verifiedNeed: false`.

## How these tasks map to Elyos

Each task below becomes an Elyos **Task JSON** validated against `packages/schema/src/schemas.ts`.
Field mapping:

- **id** — stable slug `nutrition-during-treatment-<area>-NNN` (e.g. `nutrition-during-treatment-safety-001`).
- **title** — the task title in the milestone table.
- **project** — `nutrition-during-treatment`.
- **type** — one of `code | research | writing | data | design-spec | maintenance`.
- **lane** — `donated` (default; no funded tasks planned. Any `funded` task must add `fundedBudgetUsd`
  with a hard cap).
- **priority** — `high | medium | low`.
- **domain** — array, e.g. `["cancer","nutrition","health","patient-education","content"]`.
- **riskTier** — `low | medium | high`. **Anything a patient reads is `high`**; pipeline/infra is
  `low–medium`; license/source vetting is `high` (legal + clinical sensitivity).
- **urgent** — boolean (no urgent tasks at cold-start).
- **deliverable** — `pr | dataset | document | translation`.
- **tokenEstimate** — `small | medium | large` (maps to the Size column).
- **status** — `open | in-progress | review | delivered | done` (all start `open`).
- **context / objective / acceptanceCriteria[] / resources[] / output** — per task.
- **requestor** — partner/steward/reviewer; `TO BE SECURED` where unknown.
- **verifiedNeed** — `true` only once a specific partner/need is confirmed; currently `false`
  everywhere (no partner/reviewer secured).
- **outputLicense** — code: **MIT**; content/data/docs: **CC-BY-4.0** (per `PLAN.md` Data/licensing).

Size legend: small ≈ `small`, med ≈ `medium`, large ≈ `large`.
Reviewer "Oncology RDN/CSO" = credentialed registered dietitian, Board Certified Specialist in
Oncology Nutrition (HIGH-tier sign-off, **TO BE SECURED**). "Oncologist" and "Advocate" reviewers are
likewise **TO BE SECURED**.

---

## Milestone M0 — Safety, provenance & licensing foundation (cold-start)

| ID | Title | Type | Size | Risk | Deliverable | Depends on | Reviewer |
|---|---|---|---|---|---|---|---|
| nutrition-during-treatment-scope-000 | Pilot topic-set + reviewer-profile selection (gates M2–M6) | research | small | medium | document | — | Maintainer + Oncology RDN/CSO |
| nutrition-during-treatment-safety-001 | Safety / "not medical advice" / red-flag policy specification | design-spec | medium | high | document | — | Oncology RDN/CSO + Oncologist + Safety reviewer |
| nutrition-during-treatment-schema-002 | Content schema + provenance model + repo/CI skeleton (pnpm/TS/ESM) | code | medium | low | pr | — | Maintainer |
| nutrition-during-treatment-licensing-003 | Source registry + per-source license-verification protocol | research | medium | high | document | — | Maintainer + Oncology RDN/CSO |

**Acceptance criteria — key tasks**

- **nutrition-during-treatment-scope-000** (pilot topic-set + reviewer profile)
  - Selects the pilot topic set (proposal: nausea/vomiting, sore mouth/mucositis, taste changes,
    appetite loss, diarrhea/constipation) scored for **high patient impact** and **lowest clinical
    risk first**; defers food-safety/neutropenia and cachexia to M3 under oncologist review.
  - Fixes the **reviewer profile** (oncology RDN/CSO + oncologist + patient-advocate) and the
    jurisdiction/base for reproduced text (US/NCI-PDQ vs UK/NHS-OGL) per licensing.
  - Records the decision + the **2026-08-15 decision deadline**; the specific reviewer remains
    `TO BE SECURED`. Gates M2–M6 sequencing.

- **nutrition-during-treatment-safety-001** (safety policy spec) — *first build item*
  - Enumerates the **declined/out-of-scope set** in concrete, testable terms: personalized calorie/
    protein/fluid targets or meal plans; supplement/dose recommendations; drug–nutrient/herb–drug
    interaction judgments; diagnosis/triage/"is this serious"; endorsement of anti-cancer/cure/
    alternative diets; supplement endorsement.
  - Defines the **refuse-and-redirect behavior**: decline the individual question, give the general
    cited information, and route to the oncology dietitian/care team (+ escalation block if urgent).
  - Specifies the **persistent "not medical advice / talk to your care team" banner** required on
    every patient-facing surface, and the **red-flag escalation-block template** required on every
    symptom/side-effect topic (when to call the care team / seek emergency care).
  - Defines the **safety red-team taxonomy** (incl. the "just give me a number," supplement-safety,
    interaction, triage, and "cure diet" vectors, plus LLM-assisted drafting paths) and the **0
    personalized/dangerous-leakage** target.
  - Mandates the expert sign-off gate (RDN/CSO on all content; oncologist on clinical surfaces;
    advocate on readability) and the fail-safe "withhold when uncertain" default.
  - Signed off by an oncology RDN/CSO + oncologist (recorded in the reviewers ledger).

- **nutrition-during-treatment-licensing-003** (source registry + license protocol)
  - Establishes the registry schema: per source — name, jurisdiction, URL, **verified reuse terms**,
    `reuse-mode` (`reproduce-allowed` | `cite-and-synthesize-only`), retrieval date, legal-status note.
  - Records the verified status for the initial bodies (NCI/PDQ = public domain → reproduce-allowed;
    NHS = OGL → reproduce-allowed with attribution; **WHO = CC BY-NC-SA → cite-and-synthesize-only**;
    ACS/ESPEN/ASPEN/ASCO/Academy/WCRF/Macmillan/CRUK/NICE = copyrighted → cite-and-synthesize-only).
  - States the **central rule: synthesize-and-cite, never republish** copyrighted text; reproduce only
    from clearly-permissive licenses. **No source informs shipped content until verified + recorded.**

- **nutrition-during-treatment-schema-002** (schema + skeleton)
  - Content schema (Markdown + YAML front-matter): topic, audience, claims[] each with `sources[]`,
    `reviewStatus`, `reviewer`, `lastVerified`, `validUntil`, `riskFlags`, banner + escalation slots.
  - pnpm/TS/ESM monorepo; CI runs `build/test/lint` + **stubs** for citation-coverage, banner-lint,
    readability, and staleness checks (green on an empty/fixture corpus).

**M0 Definition of Done:** safety policy spec (RDN/CSO + oncologist signed off) + content schema +
provenance model + **enforced banner/red-flag templates** + source registry & license-verification
protocol merged; pnpm/TS/ESM skeleton with green CI (incl. check stubs); **pilot topic set + reviewer
profile fixed** so M2 builds against the right corpus and reviewers.

---

## Milestone M1 — Pipeline, provenance enforcement & accessibility tooling

| ID | Title | Type | Size | Risk | Deliverable | Depends on | Reviewer |
|---|---|---|---|---|---|---|---|
| nutrition-during-treatment-pipeline-004 | Claim-extraction/synthesis pipeline + "no source, no claim" + license check + staleness fail-safe | code | large | medium | pr | 002, 003 | Maintainer |
| nutrition-during-treatment-readability-006 | Readability (≤ grade 8) + plain-language checklist + banner/escalation lint gates | code | medium | low | pr | 002 | Maintainer + Advocate |
| nutrition-during-treatment-eval-013a | Minimal grounded-vs-blank-slate + safety kill-gate (a few fixtures) | code | small | medium | pr | 004 | Maintainer + Oncology RDN/CSO |

**Acceptance criteria — key tasks**

- **nutrition-during-treatment-pipeline-004** (pipeline + provenance/license/staleness)
  - Extracts *facts* from authoritative sources and re-expresses them as **original plain-language**
    claims with citations; reproduces wording **only** from `reproduce-allowed` sources (attributed).
  - **Citation-coverage check** ("no source, no claim") fails the build if any patient-facing claim
    lacks an attached source.
  - **License check** (distinct gate) fails the build if any cited source's reuse terms are not
    verified+recorded in the registry, or if `cite-and-synthesize-only` text appears reproduced.
  - **Staleness fail-safe**: claims past `validUntil` are flagged or withheld (high-severity) until
    re-verified + re-signed-off; a staleness test asserts nothing serves as current past its window.

- **nutrition-during-treatment-readability-006** (readability + lint gates)
  - Reading-level check enforces **≤ grade 8** (Flesch–Kincaid or equivalent) on patient-facing text;
    plain-language checklist documented.
  - **Banner-lint** fails the build if the "not medical advice / talk to your care team" banner is
    missing from any patient-facing page; **escalation-lint** fails if a symptom topic lacks a
    red-flag block.

- **nutrition-during-treatment-eval-013a** (minimal kill-gate)
  - Runs a couple of fixture topics **source-grounded+cited** vs. **blank-slate**; reports accuracy/
    groundedness/readability + a basic safety check as an early **go/no-go**: if grounded+cited+safe
    doesn't clearly beat blank-slate, HIGH-tier content (M2) **pauses** for review.

**M1 Definition of Done:** extraction/synthesis pipeline with **citation-coverage + license + staleness
+ readability + banner/escalation** gates all enforced (not stubs); helpline-verification check stub
in place; the **minimal grounded-vs-blank-slate + safety kill-gate passes** before M2 content
investment.

---

## Milestone M2 — Core side-effect content (expert-gated)

| ID | Title | Type | Size | Risk | Deliverable | Depends on | Reviewer |
|---|---|---|---|---|---|---|---|
| nutrition-during-treatment-sources-007 | Vet + record provenance/license for pilot-topic sources | data | medium | high | dataset | 000, 003, 004 | Oncology RDN/CSO + Maintainer |
| nutrition-during-treatment-content-008 | Core side-effect content (nausea, sore mouth, taste, appetite, bowel changes), cited + reviewed | writing | large | high | document | 001, 004, 006, 007 | Oncology RDN/CSO (+ Oncologist where clinical) + Advocate |

**Acceptance criteria — key tasks**

- **nutrition-during-treatment-sources-007** (pilot-topic source vetting)
  - Reuse terms verified + recorded per source before enabling (PD/OGL `reproduce-allowed` vs
    copyrighted `cite-and-synthesize-only`); provenance recorded (source, jurisdiction, citation,
    version/year, URL, retrieval date, legal-status note, `lastVerified`/`validUntil`).
  - Only license-verified sources enabled for the pilot topics; recorded sign-off before use.

- **nutrition-during-treatment-content-008** (core side-effect content)
  - Each topic is **plain-language (≤ grade 8)**, **every claim cited** to a license-verified source,
    carries the **"not medical advice / talk to your care team" banner** and a **red-flag escalation
    block**, and is **non-prescriptive** (general guidance, defers individual questions to the
    dietitian/team).
  - **Refuses/omits** personalized targets, dosing, interaction judgments, and any cure/anti-cancer
    framing; addresses misinformation only by stating what evidence shows + deferring to the team.
  - **Oncology RDN/CSO sign-off recorded** for every topic (oncologist sign-off for any clinically
    loaded statement); advocate readability sign-off recorded.
  - Kill-gate (eval-013a) re-confirmed on this real cited content before M3.

**M2 Definition of Done:** pilot-topic sources vetted + provenance/license recorded; the core
side-effect topics drafted, cited, readability-passing, banner + escalation present, non-prescriptive,
and **oncology-dietitian signed off** (oncologist where clinical; advocate for readability); the
kill-gate still shows grounded+cited+safe ahead.

---

## Milestone M3 — Safety/escalation layer + caution content

| ID | Title | Type | Size | Risk | Deliverable | Depends on | Reviewer |
|---|---|---|---|---|---|---|---|
| nutrition-during-treatment-foodsafety-009 | Food safety + neutropenia content (reflects evolved guidance) | writing | medium | high | document | 007, 008 | Oncologist + Oncology RDN/CSO + Advocate |
| nutrition-during-treatment-escalation-010 | Red-flag escalation blocks + verified helplines/crisis & authoritative-resource links | data | medium | high | dataset | 001, 008 | Oncologist + Oncology RDN/CSO |
| nutrition-during-treatment-unproven-011 | Supplement/herb + unproven-diet caution content (evidence-based, defer-to-team) | writing | medium | high | document | 007, 008 | Oncology RDN/CSO + Oncologist + Advocate |
| nutrition-during-treatment-questions-012 | "Questions to ask your oncology dietitian / care team" prompt lists | writing | small | medium | document | 008 | Oncology RDN/CSO + Advocate |

**Acceptance criteria — key tasks**

- **nutrition-during-treatment-foodsafety-009** (food safety / neutropenia)
  - Reflects **current** evidence (incl. the walk-back of the strict "neutropenic diet"); cited;
    **oncologist-reviewed**; carries escalation block (e.g., neutropenic-fever guidance routes to the
    care team / emergency care) and the not-medical-advice banner.

- **nutrition-during-treatment-escalation-010** (escalation + helplines)
  - Every symptom/side-effect topic has a **verified red-flag block** (e.g., can't keep fluids down,
    signs of dehydration, fever during low-count periods, rapid weight loss) routing to care team /
    emergency care — clinically reviewed.
  - Helpline/crisis & authoritative-resource links (poison control for supplement overdose, distress/
    crisis lines, official patient-info portals) **verified against the official source** within the
    review window; **helpline-verification check passes (0 stale)**; shorter re-verification cadence
    set.

- **nutrition-during-treatment-unproven-011** (supplement/diet caution)
  - States, **with citations**, what authoritative bodies/evidence say about common supplements/herbs
    and "anti-cancer" diets (alkaline, ketogenic-as-therapy, juicing, extreme fasting); **does not
    endorse, dose, or judge interactions**; routes to the pharmacist/dietitian/care team.
  - Non-alarming tone (advocate-reviewed); emphasizes eating enough; expert sign-off recorded.

**M3 Definition of Done:** food-safety/neutropenia content (oncologist-reviewed, current); verified
red-flag escalation blocks + verified helplines across topics; supplement/unproven-diet caution
content (accurate, cited, defer-to-team); question-prompt lists — all expert-signed-off, banner +
escalation present.

---

## Milestone M4 — Eval, accessibility & translation readiness

| ID | Title | Type | Size | Risk | Deliverable | Depends on | Reviewer |
|---|---|---|---|---|---|---|---|
| nutrition-during-treatment-eval-013 | Full eval: accuracy/groundedness/readability + safety red-team (0 leakage) | code | medium | medium | pr | 008, 009, 010, 011, 013a | Maintainer + Oncology RDN/CSO + Safety reviewer |
| nutrition-during-treatment-a11y-014 | WCAG 2.2 AA site + machine-readable corpus + print/large-print handouts | code | medium | medium | pr | 008, 010 | Maintainer + Advocate |
| nutrition-during-treatment-i18n-015 | Translation framework + first language (back-translation + bilingual sign-off) | translation | medium | high | translation | 008, 010, 014 | Oncology RDN/CSO (bilingual) + Advocate |

**Acceptance criteria — key tasks**

- **nutrition-during-treatment-eval-013** (full eval + safety red-team)
  - Source-grounded+cited content vs. blank-slate judged on accuracy, groundedness/citation, fit, and
    reading level; grounded+cited must **clearly beat** blank-slate.
  - **Safety red-team**: adversarial prompts (personalized targets, supplement safety, interactions,
    triage, cure-diet, LLM-drafting paths) assert **0 personalized/dangerous leakage** and correct
    redirect-to-care-team behavior; runs in CI; new bypass vectors become regression cases.

- **nutrition-during-treatment-i18n-015** (translation)
  - First language translated with **back-translation review** + **bilingual oncology-RDN/advocate
    sign-off**; cultural-food-context notes; **region-specific helplines/escalation** localized and
    verified; per-language `lastVerified`/`validUntil` set. Treated as HIGH risk, not a string swap.

**M4 Definition of Done:** full eval shows grounded+cited+safe clearly beats blank-slate with **0
safety-red-team leakage**; WCAG 2.2 AA site + machine-readable corpus + print/large-print variants;
first translation completed with back-translation + bilingual sign-off and localized verified
escalation/helplines.

---

## Milestone M5 — Distribution & beneficiary handoff (the deed)

| ID | Title | Type | Size | Risk | Deliverable | Depends on | Reviewer |
|---|---|---|---|---|---|---|---|
| nutrition-during-treatment-partner-016 | Secure distribution partner/steward + consented comprehension test with pilot patients | research | medium | high | document | 013, 014, 015 | Steward + Oncology RDN/CSO |
| nutrition-during-treatment-handoff-017 | Distribution + closed-loop outcome (patients use it; attested help recorded) | maintenance | medium | high | document | 016 | Steward + Oncology RDN/CSO + Advocate |

**Acceptance criteria — key tasks**

- **nutrition-during-treatment-partner-016** (secure partner + comprehension test)
  - A real distribution channel (dietetics team, cancer-support nonprofit, hospital patient-education
    office, or advocacy org) is secured; steward assigned; `verifiedNeed` flips to `true`.
  - **Comprehension/teach-back test** with pilot patients (partner-mediated, consented, de-identified)
    passes **≥ 80%** on key items per tested topic; safety/banner/escalation controls confirmed in
    the distributed form; all shipped content has recorded expert sign-off.
  - Driven by the **dated acquisition plan** (reviewer by 2026-10-15, partner by 2026-12-15). If no
    partner by **~2027-03-31**, apply the **build-vs-mothball/pivot rule** (PLAN exec summary):
    contribute the cited, reviewed corpus to an existing trusted publisher as a reference deed, or
    mothball to maintenance-only — recorded in governance — rather than publish to no one.

- **nutrition-during-treatment-handoff-017** (closed loop — the deed)
  - Content is distributed to real patients through the partner; **≥ 10 attested instances** of it
    helping someone manage a side effect or eat better during treatment are recorded (partner-
    mediated, consented, de-identified).
  - Safety/red-flag/banner controls verified in production; provenance intact; content within review
    window.

**M5 Definition of Done:** project-level **Definition of Shipped** met — real patients receive and use
the content through a credible channel and it demonstrably helped them, with oncology-dietitian (and
surface-appropriate oncologist/advocate) sign-off recorded, safety/provenance/escalation controls
verified, helplines current, outcomes recorded. *(Gated on a secured partner — TO BE SECURED.)*

---

## Milestone M6 — Sustain & scale (post-delivery)

| ID | Title | Type | Size | Risk | Deliverable | Depends on | Reviewer |
|---|---|---|---|---|---|---|---|
| nutrition-during-treatment-ops-018 | Review cadence + maintenance rotation + outcomes dashboard + topic/language expansion process | maintenance | medium | medium | document | 017 | Maintainer + Steward + Oncology RDN/CSO |

**Acceptance criteria — nutrition-during-treatment-ops-018**
- Review cadence defined and **enforced at runtime** via `lastVerified`/`validUntil` (guideline
  re-verification + re-sign-off; **shorter cadence for helplines/escalation**).
- Named maintenance rotation; outcomes dashboard tracks **patients reached + attested help +
  comprehension results** (not page views); documented, expert-gated process for adding topics and
  languages; safety red-team maintained as living tests.

**M6 Definition of Done:** project sustainably maintained with outcomes tracked, a rotation owning it,
a runtime-enforced review cadence for clinical content/helplines, and a gated expansion process.

---

## Backlog / future

| ID | Title | Type | Size | Risk | Deliverable | Notes |
|---|---|---|---|---|---|---|
| nutrition-during-treatment-cachexia-019 | Cancer cachexia / weight-loss awareness (general, non-prescriptive) | writing | medium | high | document | Oncologist-reviewed; strong defer-to-dietitian |
| nutrition-during-treatment-nutrition-support-020 | Enteral/parenteral nutrition high-level explainer (defer-to-team) | writing | small | high | document | Bounded education only; oncologist-reviewed |
| nutrition-during-treatment-audio-021 | Read-aloud audio / text-aligned narration of core topics | data | medium | medium | dataset | Accessibility; low-literacy reach; cross-link `read-aloud-audio` |
| nutrition-during-treatment-langN-022 | Additional language translations | translation | large | high | translation | Per-language back-translation + bilingual sign-off |
| nutrition-during-treatment-qa-023 | Guardrailed Q&A surface (future; inherits safety layer) | code | large | high | pr | Explicit future go/no-go; not MVP |
| nutrition-during-treatment-pediatric-024 | Pediatric oncology nutrition (separate review profile) | writing | large | high | document | Higher stakes; pediatric-oncology RDN review |

---

## Generated task index

> Auto-generated by the Elyos task-decomposition agent on 2026-06-29.
> All 25 files in `tasks/` are schema-valid (validated against `packages/schema/dist/index.js`).
> Fan-out dimensions: none (all task IDs explicitly enumerated in TASKS.md).
> Note: `questions-012` and `audio-021` riskTier overridden to `high` (from `medium` in table above)
> per the binding guardrail: any patient-facing nutrition/oncology content = riskTier:high.

| File | ID | Type | Risk | Deliverable | Status |
|---|---|---|---|---|---|
| nutrition-during-treatment-scope-000.json | nutrition-during-treatment-scope-000 | research | medium | document | open |
| nutrition-during-treatment-safety-001.json | nutrition-during-treatment-safety-001 | design-spec | high | document | open |
| nutrition-during-treatment-schema-002.json | nutrition-during-treatment-schema-002 | code | low | pr | open |
| nutrition-during-treatment-licensing-003.json | nutrition-during-treatment-licensing-003 | research | high | document | open |
| nutrition-during-treatment-pipeline-004.json | nutrition-during-treatment-pipeline-004 | code | medium | pr | open |
| nutrition-during-treatment-readability-006.json | nutrition-during-treatment-readability-006 | code | low | pr | open |
| nutrition-during-treatment-eval-013a.json | nutrition-during-treatment-eval-013a | code | medium | pr | open |
| nutrition-during-treatment-sources-007.json | nutrition-during-treatment-sources-007 | data | high | dataset | open |
| nutrition-during-treatment-content-008.json | nutrition-during-treatment-content-008 | writing | high | document | open |
| nutrition-during-treatment-foodsafety-009.json | nutrition-during-treatment-foodsafety-009 | writing | high | document | open |
| nutrition-during-treatment-escalation-010.json | nutrition-during-treatment-escalation-010 | data | high | dataset | open |
| nutrition-during-treatment-unproven-011.json | nutrition-during-treatment-unproven-011 | writing | high | document | open |
| nutrition-during-treatment-questions-012.json | nutrition-during-treatment-questions-012 | writing | high | document | open |
| nutrition-during-treatment-eval-013.json | nutrition-during-treatment-eval-013 | code | medium | pr | open |
| nutrition-during-treatment-a11y-014.json | nutrition-during-treatment-a11y-014 | code | medium | pr | open |
| nutrition-during-treatment-i18n-015.json | nutrition-during-treatment-i18n-015 | writing | high | translation | open |
| nutrition-during-treatment-partner-016.json | nutrition-during-treatment-partner-016 | research | high | document | open |
| nutrition-during-treatment-handoff-017.json | nutrition-during-treatment-handoff-017 | maintenance | high | document | open |
| nutrition-during-treatment-ops-018.json | nutrition-during-treatment-ops-018 | maintenance | medium | document | open |
| nutrition-during-treatment-cachexia-019.json | nutrition-during-treatment-cachexia-019 | writing | high | document | open |
| nutrition-during-treatment-nutrition-support-020.json | nutrition-during-treatment-nutrition-support-020 | writing | high | document | open |
| nutrition-during-treatment-audio-021.json | nutrition-during-treatment-audio-021 | data | high | dataset | open |
| nutrition-during-treatment-langN-022.json | nutrition-during-treatment-langN-022 | writing | high | translation | open |
| nutrition-during-treatment-qa-023.json | nutrition-during-treatment-qa-023 | code | high | pr | open |
| nutrition-during-treatment-pediatric-024.json | nutrition-during-treatment-pediatric-024 | writing | high | document | open |

---

## Example task JSON

Complete, schema-valid Task JSON for the first M0 build item
(`nutrition-during-treatment-safety-001`):

```json
{
  "id": "nutrition-during-treatment-safety-001",
  "title": "Safety / not-medical-advice / red-flag policy specification",
  "project": "nutrition-during-treatment",
  "type": "design-spec",
  "lane": "donated",
  "priority": "high",
  "domain": ["cancer", "nutrition", "health", "patient-education", "safety"],
  "riskTier": "high",
  "urgent": false,
  "deliverable": "document",
  "tokenEstimate": "medium",
  "status": "open",
  "context": "Nutrition-During-Treatment is an open-access, plain-language, source-cited library of nutrition guidance for people in active cancer treatment and their caregivers, synthesized only from authoritative bodies (NCI/PDQ, NHS, ESPEN, ACS, etc.). It is a HIGH risk-tier, patient-facing project under the binding cancer-domain guardrails: open-access/aggregate/de-identified data only, per-source license verification, and credentialed oncology-dietitian sign-off before any patient-facing content ships. The project does NOT give medical or personalized nutrition advice and must be engineered so it cannot be steered into doing so. This cold-start task writes the safety / not-medical-advice / red-flag policy that all later content and tooling must implement and be tested against, before any content is authored. No clinical partner or credentialed reviewer is yet secured.",
  "objective": "Write the authoritative safety policy specification that all later content and pipeline checks implement and are tested against: the declined/out-of-scope set (personalized targets, dosing, drug-nutrient/herb-drug interaction judgments, diagnosis/triage, anti-cancer/cure-diet or supplement endorsement), the refuse-and-redirect-to-care-team behavior, the persistent 'not medical advice / talk to your care team' banner required on every patient-facing surface, the red-flag escalation-block template required on every symptom topic, the safety red-team taxonomy and 0-personalized/dangerous-leakage target, and the expert-review gate (oncology RDN/CSO on all content, oncologist on clinical surfaces, advocate on readability) with a fail-safe withhold-when-uncertain default.",
  "acceptanceCriteria": [
    "Enumerates the declined/out-of-scope set in concrete, testable terms: personalized calorie/protein/fluid targets or meal plans; supplement/dose recommendations; drug-nutrient or herb-drug interaction judgments; diagnosis/triage/'is this serious'; endorsement of anti-cancer/cure/alternative diets or supplements",
    "Defines the refuse-and-redirect behavior: decline the individual question, provide the general cited information, route to the oncology dietitian/care team, and add the escalation block when the situation may be urgent",
    "Specifies the persistent 'this is general education, not medical advice - talk to your care team/dietitian' banner required on every patient-facing surface (lint-enforced) and the red-flag escalation-block template required on every symptom/side-effect topic",
    "Defines the safety red-team taxonomy (including the 'just give me a number', supplement-safety, interaction, triage, and cure-diet vectors, plus LLM-assisted drafting paths) and the 0 personalized/dangerous-leakage target",
    "Mandates the expert sign-off gate (oncology RDN/CSO on all patient-facing content, oncologist on clinically-loaded surfaces, patient-advocate on readability) and the fail-safe 'withhold when citation or safety framing is uncertain' default",
    "Reviewed and signed off by a credentialed oncology dietitian (RDN/RD-CSO) and an oncologist, recorded in the reviewers ledger"
  ],
  "resources": [
    "planning/projects/nutrition-during-treatment/PLAN.md",
    "CLAUDE.md",
    "docs/good-deed-definition.md",
    "packages/schema/src/schemas.ts",
    "planning/ROADMAP.md",
    "planning/projects/public-official-guide/PLAN.md"
  ],
  "output": "A reviewed safety-policy-specification document (the not-medical-advice / red-flag charter) defining the declined set, refuse-and-redirect behavior, the required banner and escalation-block templates, the safety red-team taxonomy, and the expert-review/withhold gates - the contract that the content schema (nutrition-during-treatment-schema-002), the pipeline gates (nutrition-during-treatment-pipeline-004), and the eval/red-team (nutrition-during-treatment-eval-013) implement and verify.",
  "requestor": "TO BE SECURED",
  "verifiedNeed": false,
  "outputLicense": "CC-BY-4.0"
}
```
