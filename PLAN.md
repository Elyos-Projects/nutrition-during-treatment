# Nutrition-During-Treatment — PLAN.md

> Status: Draft · Version: 0.1.0 · Last updated: 2026-06-28 · Owner: TBD (maintainer) · Lane: donated

An open-access, plain-language, **source-cited** collection of nutrition guidance for people
**undergoing active cancer treatment** (chemotherapy, radiation, surgery, immunotherapy, stem-cell
transplant) and their caregivers — synthesized **only** from authoritative bodies, reviewed and
**signed off by a credentialed oncology dietitian** (registered dietitian with the Board Certified
Specialist in Oncology Nutrition credential, RDN/RD-CSO) with **oncologist and patient-advocate
review** on clinical and patient-facing surfaces. Every assertion carries provenance to a primary
source. The product is **education, not medical advice**: every page tells the reader this is not a
substitute for their care team and surfaces verified red-flag/escalation guidance.

This is a **HIGH risk-tier** project under `docs/good-deed-definition.md` (health/safety, patient-
facing) and falls under the binding **cancer-research domain guardrails** (Track 8 of the roadmap):
open-access / aggregate / de-identified data **only**; controlled-access and identifiable patient
data are out of scope; per-source license verification; no medical advice; expert sign-off before any
patient-facing content ships.

---

## Executive summary

People in cancer treatment face nutrition problems that materially change outcomes: treatment-induced
nausea, mucositis (sore mouth), taste changes, appetite loss, diarrhea/constipation, dysphagia, and —
most consequentially — **cancer cachexia and malnutrition**, which are associated with worse
treatment tolerance, more dose reductions, and worse survival. Authoritative, evidence-based guidance
exists (NCI/PDQ, ESPEN oncology nutrition guidelines, ACS, ASCO/Cancer.Net, the Academy of Nutrition
and Dietetics, WCRF/AICR, Macmillan, NHS), but it is fragmented across many bodies, written at a
reading level most patients struggle with, sometimes contradictory across years and jurisdictions
(e.g., the "neutropenic diet" has been substantially walked back), and surrounded online by a sea of
**dangerous misinformation** ("sugar feeds cancer," "alkaline diet cures cancer," extreme fasting,
megadose supplements that interfere with treatment). The need is a **trustworthy, plain-language,
cited synthesis that a patient can actually read at 2 a.m. — and that knows the boundary of its own
authority and pushes the reader to their care team for anything individualized or urgent.**

The single most important design fact is that **this project does not give medical or personalized
nutritional advice and is engineered so it cannot be steered into doing so.** It does not prescribe
calorie or protein targets for an individual, recommend supplements or doses, advise on drug–nutrient
interactions, or endorse any "anti-cancer" diet. It explains *what authoritative bodies say in
general*, always cited, always framed as education, and always with an explicit "this is not medical
advice — talk to your oncology care team / dietitian" boundary and, where relevant, a **verified
red-flag escalation block** (when to call the care team or seek emergency care). The **safety /
"not medical advice" / red-flag policy layer and the provenance model are the first build items and
hard product requirements**, treated as safety-critical and adversarially tested — not a disclaimer
footer.

Because most authoritative patient-nutrition content is **copyrighted** (ACS, ESPEN, ASPEN, ASCO,
the Academy, WCRF, Macmillan, Cancer Research UK, and much of NICE), the **central licensing gate** is
that we **do not republish their text**. We extract non-copyrightable *facts*, write our own original
plain-language synthesis, and **cite every claim** to the primary source; we reproduce wording only
from sources whose license clearly permits it (NCI/PDQ public domain; NHS/UK content under the Open
Government Licence; WHO under CC BY-NC-SA with its share-alike/non-commercial caveats). Each source's
reuse terms are **verified and recorded before its content informs anything that ships.** Our original
synthesis is released **CC-BY-4.0**.

This is a **HIGH risk-tier** project: no patient-facing nutrition content ships without recorded
sign-off by a **credentialed oncology dietitian (RDN/RD-CSO)**, with **oncologist** review on any
clinically loaded surface (e.g., food safety during neutropenia, cachexia, enteral/parenteral
nutrition, drug–nutrient interactions) and **patient-advocate** review for readability, tone, and
lived-experience accuracy. Inaccuracy *and* misuse are both top risks, and the safety layer is the
release gate.

Honesty note: **no clinical partner, distributing organization, or credentialed reviewer is yet
secured.** Every delivery-dependent task is marked `TO BE SECURED` with `verifiedNeed: false` until a
real beneficiary channel and reviewer are confirmed. The project is **not "shipped" on merge**; it is
shipped only when real patients receive and use the content through a credible channel, with the
oncology-dietitian sign-off and safety controls verified.

**Partner/reviewer-acquisition plan (dated) and build-vs-mothball decision rule.** Outreach is
time-boxed against the build, not open-ended: by **2026-08-15** the pilot topic set and reviewer
profile are fixed and ≥ 3 candidate reviewers (oncology RDN/CSO via the Academy's Oncology Nutrition
DPG or an NCI-designated cancer center) plus ≥ 2 candidate distribution partners (infusion-center
dietetics team, a cancer-support nonprofit such as a Cancer Support Community affiliate, or a hospital
patient-education office) are in active conversation; by **2026-10-15** a credentialed oncology
dietitian reviewer is secured (gates M2 content); by **2026-12-15** a distribution partner/steward is
secured (gates M5). **Decision rule:** if no oncology-dietitian reviewer is secured by the M2 entry
date, M2 content work does **not** start and the project holds at M1 (pipeline + safety layer + an
illustrative, clearly-marked-DRAFT topic). If no distribution partner is secured by **~2027-03-31**,
the project does **not** publish patient-facing content to no one: it either (a) **pivots** the
last-mile beneficiary (hand the cited, expert-reviewed corpus to an existing trusted publisher —
e.g., contribute back to an open patient-education library — as a reference deed) or (b) **mothballs**
to maintenance-only, recorded in governance.

---

## Problem & beneficiaries

**Who is helped (directly):** adults in **active cancer treatment** and the **caregivers/family** who
shop and cook for them — disproportionately people without access to an oncology dietitian (a scarce
resource; many treatment centers have one RDN for hundreds of patients, and community/rural clinics
often have none), people managing treatment at home between appointments, and lower-health-literacy
and non-English-speaking patients underserved by existing materials.

**Who is helped (ultimately):** the broader public and the clinicians who serve them — an open,
cited, plain-language commons reduces the burden on overstretched oncology-nutrition services and
gives other patient-education programs, translators, and clinics a trustworthy base to build on.

**The need.** Malnutrition affects a large share of patients during treatment and is associated with
worse tolerance and outcomes; nausea, mucositis, taste changes, and appetite loss are among the most
common and distressing side effects, and they are precisely the ones diet can help manage. Patients
routinely turn to the open internet for "what can I eat," where authoritative guidance is buried under
misinformation and predatory "anti-cancer diet" content. Authoritative material exists but is
scattered, reading-level-inaccessible, occasionally out of date, and rarely available in the patient's
language. A trustworthy, cited, plain-language synthesis — explicitly bounded as education and wired
to push individualized/urgent questions to the care team — is missing.

**Verified need / partner:** **TO BE SECURED.** No clinical partner, distributing organization, or
credentialed oncology-dietitian reviewer has yet agreed to co-develop or adopt this. Target partner
profiles: an infusion-center or cancer-center **dietetics team**; a **cancer-support nonprofit**
(e.g., a Cancer Support Community / Gilda's Club affiliate, Macmillan-style support service, or a
disease-specific advocacy org); a hospital **patient-education office**; or the Academy of Nutrition
and Dietetics **Oncology Nutrition DPG** for credentialed review. Until one is secured, the project
builds the safety/provenance foundation, the pipeline, and an *illustrative* set of topics marked
clearly as DRAFT/for-review, and marks all delivery/adoption work `TO BE SECURED`. Outreach is
**dated** (see the acquisition plan above) and a **build-vs-mothball/pivot rule** governs slippage.

---

## Goals and non-goals

**Goals**

- Produce an open-access, **plain-language**, **source-cited** library of nutrition-during-treatment
  education synthesized only from authoritative bodies, with provenance on every assertion.
- Ship a **safety / "not medical advice" / red-flag layer** that is provably present and correct on
  every patient-facing surface and verified by adversarial testing and expert review.
- Have all patient-facing content **signed off by a credentialed oncology dietitian (RDN/RD-CSO)**,
  with oncologist review on clinically loaded surfaces and patient-advocate review for readability.
- Make the content **accessible**: target reading level, WCAG 2.2 AA, machine-readable + human-
  readable, and translation-ready with reviewed translations.
- Reach **real patients** through a credible distribution channel and record that the content helped
  them manage a treatment side effect or eat better during treatment.
- Maintain a **runtime staleness fail-safe** so guidance that has passed its review window is flagged
  or withheld until re-verified and re-signed-off (oncology guidance changes).

**Non-goals**

- **Not medical, clinical, or personalized nutrition advice.** No individualized calorie/protein/
  fluid targets, no meal plans prescribed to a person, no "you should eat X for your situation."
- **Not supplement/dose/interaction advice.** No recommending supplements, doses, or judgments about
  a specific drug–nutrient or herb–drug interaction — those route to the pharmacist/dietitian/team.
- **Not diagnosis, treatment, or triage.** It never tells a user their symptom is/ isn't serious; it
  surfaces verified red flags and says "contact your care team / seek care."
- **Not an "anti-cancer diet," cure, or alternative-medicine platform.** No endorsement of alkaline,
  ketogenic-as-therapy, juicing-cure, extreme-fasting, or "starve the tumor" claims; where it
  addresses them it states, with citations, what the evidence actually shows and defers to the team.
- **Not built on patient data.** No identifiable, individual-level, or controlled-access data; only
  open-access authoritative guidance and aggregate/de-identified public statistics.
- **Not a chatbot that answers free-text personal medical questions** at launch (a future, heavily
  guardrailed Q&A surface is explicitly out of MVP scope and gated on the safety layer).
- **Not a republisher** of copyrighted authoritative content — facts are extracted and re-expressed,
  not copied (see *Data, licensing & compliance*).

---

## Success metrics (outcomes)

Outcome-centric and beneficiary-first. Page views / sessions are explicitly **not** success.

| Metric | Baseline | Target | How measured |
|---|---|---|---|
| Assertions carrying a primary-source citation | none | **100%** of patient-facing claims | Citation-coverage check in CI ("no source, no claim") + expert spot-check |
| Patient-facing content with recorded oncology-dietitian (RDN/CSO) sign-off | none | **100%** before publish | Reviewers ledger / governance log |
| Clinically-loaded surfaces with recorded oncologist sign-off | none | **100%** (food safety, cachexia, enteral/parenteral, drug–nutrient cautions) | Reviewers ledger |
| Reading level | unmeasured | **≤ grade 8** (Flesch–Kincaid / equivalent); plain-language checklist passed | Readability check in CI + advocate review |
| Safety red-team: personalized/dangerous-advice leakage | n/a | **0** instances of personalized dosing, supplement/interaction advice, or pro-misinformation output, across the red-team suite | Adversarial eval in CI + expert audit |
| Red-flag/escalation block present where required | n/a | **100%** of symptom/side-effect topics carry a verified "when to contact your care team / seek emergency care" block | Template/lint check + expert review |
| Helpline & crisis/escalation info verified current | n/a | **100%** verified against the official source within the review window; **0** stale numbers served | Helpline-verification check + staleness test |
| "Not medical advice" + care-team-boundary banner present | n/a | **100%** of patient-facing pages | Banner lint check in CI |
| Stale-content containment | n/a | **0** claims served past `validUntil` without auto-flag/withhold and re-sign-off | Staleness test against `lastVerified`/`validUntil` |
| Memory-/source-grounded vs. blank-slate quality delta (eval) | n/a | grounded+cited clearly beats blank-slate on accuracy, groundedness, and safety | LLM-judge + expert-rubric eval harness |
| Patient comprehension (pilot) | none | **≥ 80%** of pilot readers correctly answer key comprehension/teach-back items per tested topic | Comprehension test with pilot patients (partner-mediated, consented, de-identified) |
| Patients reached + helped (the deed) | 0 | content distributed to real patients through a partner; **≥ 10** attested instances of it helping manage a side effect or eat better | Partner-mediated, consented, de-identified outcome capture |
| Translation fidelity (per translated language) | n/a | back-translation review passes; bilingual oncology-RDN/advocate sign-off recorded | Translation QA + reviewer sign-off |

The **defining success outcome** (Definition of Shipped): real patients receive and use the content
through a credible channel and it demonstrably helped them manage a treatment side effect or eat
better during treatment — with oncology-dietitian sign-off recorded, the safety/red-flag controls
verified, and provenance intact.

---

## Scope

**In scope**

- A structured, cited content library covering **nutrition management of common treatment side
  effects** (nausea/vomiting, mucositis/sore mouth, taste & smell changes, dry mouth, appetite loss,
  diarrhea, constipation, swallowing difficulty), **eating-enough/weight-loss & cachexia awareness
  (general, non-prescriptive)**, **hydration**, and **food safety during treatment** (including the
  evolved guidance on neutropenia).
- A **safety/escalation layer**: verified red-flag "contact your care team / seek emergency care"
  blocks, verified helpline/crisis and authoritative-resource links, and the persistent "not medical
  advice — talk to your care team" boundary.
- **Caution content** that accurately, with citations, addresses supplements/herbs (defer to
  pharmacist/dietitian) and unproven "anti-cancer" diets (what the evidence shows; defer to the team).
- **"Questions to ask your oncology dietitian / care team"** prompt lists (a safe, non-prescriptive
  way to drive individualized questions to the right professional).
- The **source registry + license-verification protocol**, the **provenance model**, the
  **claim-extraction pipeline**, the **staleness fail-safe**, **readability** tooling, an **eval +
  safety red-team**, **accessibility** (WCAG 2.2 AA), and **translation** framework with reviewed
  translations.
- Both **human-readable** (static site / printable handouts) and **machine-readable** (structured
  JSON/YAML with citations) outputs, released open access.

**Out of scope (explicitly will NOT do)**

- **Personalized advice of any kind** — individual calorie/protein/fluid targets, personal meal
  plans, "what should *I* eat," symptom triage, or telling a user whether their situation is serious.
- **Supplement, dose, or drug–nutrient/herb–drug interaction recommendations** for an individual.
- **Endorsing or detailing "anti-cancer," cure, or alternative-medicine diets** as therapy.
- **Pediatric** oncology nutrition and **specialized clinical nutrition support** (detailed enteral/
  parenteral protocols) beyond high-level, defer-to-team explainers — these are higher-stakes and
  deferred/handled only as clearly-bounded education.
- **Any patient/identifiable or controlled-access data** (dbGaP/EGA/biobanks/individual records).
- **Republishing copyrighted source text** (we synthesize and cite; see licensing).
- A **free-text medical Q&A chatbot** at launch.
- **Survivorship / post-treatment long-term diet** as a primary focus (boundary with the roadmap's
  `survivorship-resources`; cross-link, don't duplicate).

When a request falls in the out-of-scope/refused set (e.g., "how much protein should I eat," "is this
supplement safe with my chemo," "will keto cure my cancer"), the content/tool **declines to answer
individually**, explains why in plain terms, points to what authoritative bodies say *in general* with
citations, and **routes the person to their oncology dietitian / care team** — and, for anything
urgent, to the verified escalation block. This **redirect-to-the-right-professional behavior is the
project's ethical core**, held to explicit acceptance criteria and a coverage metric, not a nicety.

---

## Solution approach & architecture

This is primarily a **content/data pipeline**, not an application, so the architecture is a curation-
to-publication pipeline with safety and provenance enforced as code-checked gates.

**Stack / tooling.** TypeScript, ESM, pnpm workspaces (Elyos convention). Content authored as
Markdown with structured **YAML front-matter** (the content schema) and compiled to a machine-readable
**JSON** corpus and a human-readable **static site** / printable handouts. Validation, citation-
coverage, banner-lint, readability, staleness, and helpline-verification checks run as **CI gates**.
Any LLM assistance used in drafting/extraction sits behind a thin, provider-neutral client (model
selection and pricing per the Claude API skill; agent-neutral core per `CLAUDE.md`) and **never
substitutes for the human expert sign-off** — it is an authoring aid, not an authority. Code MIT;
content/data **CC-BY-4.0**.

**Pipeline components**

1. **Safety / "not medical advice" / red-flag layer (`safety/`) — built first.** A safety-critical
   subsystem expressed as (a) a **policy spec** (the refused/declined set: personalized advice,
   dosing, interactions, diagnosis/triage, anti-cancer-diet endorsement; the required boundary
   framing; the escalation rules), (b) **enforced templates** — every patient-facing content type
   *must* carry the "not medical advice / talk to your care team" banner and, for symptom topics, a
   verified red-flag escalation block — checked by a lint gate that **fails the build** if missing,
   and (c) an **adversarial safety red-team** (see eval) ensuring no surface or any LLM-assisted
   drafting path produces personalized/dangerous output. Fail-safe default: when a claim's safety
   framing or citation is uncertain, it is **withheld**, not published.

2. **Source registry + license-verification protocol (`sources/registry.*`).** A registry of
   authoritative bodies with, per source: name, jurisdiction, URL, **verified license/reuse terms**,
   reuse-mode (`reproduce-allowed` vs `cite-and-synthesize-only`), retrieval date, and a recorded
   legal-status note. **No source informs shipped content until its reuse terms are verified and
   recorded.** This is the central licensing gate (details in *Data, licensing & compliance*).

3. **Provenance model + claim store (`content/` + `provenance`).** Every assertion is a structured
   *claim* backed by one or more `Source` records (citation + provenance + verified reuse terms +
   `lastVerified` + `validUntil`). A **citation-coverage check** enforces "**no source, no claim**":
   a patient-facing claim without an attached, license-verified source fails CI and cannot publish.

4. **Claim-extraction & synthesis pipeline (`pipeline/`).** Authoritative guidance is read; *facts*
   are extracted (non-copyrightable) and re-expressed as **original plain-language** claims with
   citations. For `reproduce-allowed` sources (e.g., NCI/PDQ public domain), limited quotation is
   permitted with attribution; for `cite-and-synthesize-only` sources, **no wording is copied**.
   LLM-assisted extraction is checked by a human and never bypasses expert sign-off.

5. **Readability & accessibility (`a11y/`).** Reading-level checks (target ≤ grade 8), a plain-
   language checklist, and WCAG 2.2 AA conformance for the rendered site/handouts; large-print /
   print-friendly variants.

6. **Staleness fail-safe.** Each `Source` carries `lastVerified` + `validUntil` from a per-source-type
   review interval (e.g., formal clinical guidelines re-verified ~annually; rapidly-changing items and
   helplines on a shorter cadence). At **publish/build time**, a claim whose backing source is past
   `validUntil` is **flagged** ("past review window — verify before relying") or **withheld** for
   high-severity topics, and routed to re-verification; it cannot return to normal service until
   re-verified and **re-signed-off** by the expert (fresh `lastVerified`/`validUntil`).

7. **Helpline / escalation verification.** Crisis/escalation and authoritative-resource links
   (e.g., poison-control for supplement overdose, distress/crisis lines, "call your care team" and
   emergency-care guidance) are **verified against the official source** within the review window; a
   helpline-verification check fails the build on a stale/unverified entry.

8. **Eval + safety red-team (`scripts/eval.ts`).** (a) **Accuracy/groundedness/readability eval** —
   source-grounded+cited content vs. blank-slate, judged on accuracy, groundedness/citation, fit, and
   reading level; (b) **safety red-team** — adversarial prompts attempting to extract personalized
   advice, dosing, interactions, triage, or pro-misinformation output, asserting **0** leakage and
   correct redirect-to-care-team behavior.

9. **Translation framework (`i18n/`).** Translation-ready content with **back-translation review** and
   **bilingual oncology-RDN/advocate sign-off** per language; cultural-food-context adaptation noted.

**Key decisions**

- Safety + provenance are first-class, code-checked release gates — not a disclaimer footer.
- **Synthesize-and-cite, never republish** copyrighted source text; reproduce only from clearly
  permissive licenses; the license gate runs before content can ship.
- Human expert sign-off (oncology RDN/CSO, plus oncologist/advocate by surface) is the hard release
  gate; LLM assistance is an authoring aid only.
- Depth-and-accuracy first on a small pilot topic set, then breadth; never breadth without review.
- Privacy by construction: the project handles **no patient data**; any pilot comprehension/outcome
  data is partner-mediated, consented, and de-identified.

---

## Data, licensing & compliance

**THIS IS THE CRITICAL SECTION — conservative by default.**

**Cancer-domain guardrails (binding, restated).** Per the roadmap's Track 8 and `CLAUDE.md`: use
**only open-access / aggregate / de-identified** material. **Controlled-access and identifiable
patient data are entirely out of scope** (no dbGaP, EGA, biobanks, EHRs, or individual records — and
this project does not need them). Aggregate public statistics (e.g., SEER/GLOBOCAN, if used for
context only) are acceptable as aggregate data with attribution. **No medical advice;** patient-facing
content is education only, expert-reviewed, with the boundary banner and provenance on every claim.

**Source material — authoritative bodies (illustrative; each verified before use):**

| Source | Type | Typical reuse status (MUST verify per item) | Reuse mode |
|---|---|---|---|
| **NCI / PDQ** (cancer.gov) | US Govt patient & health-professional summaries | Generally **public domain** (US Govt work); PDQ is a trademark; verify per page | `reproduce-allowed` (with attribution) |
| **NHS** (nhs.uk) | UK patient information | Much content under **Open Government Licence v3.0** (excl. logos/photos) — verify | `reproduce-allowed` (OGL attribution) |
| **WHO** | Global guidance/factsheets | Typically **CC BY-NC-SA 3.0 IGO** — **non-commercial + share-alike**, incompatible with CC-BY reproduction | `cite-and-synthesize-only` (do not reproduce text into CC-BY output) |
| **ESPEN** oncology nutrition guidelines | Clinical guideline (journal, Elsevier) | **Copyrighted** | `cite-and-synthesize-only` |
| **ASPEN** | Clinical nutrition guidance | **Copyrighted** | `cite-and-synthesize-only` |
| **American Cancer Society (ACS)** | Patient info | **Copyrighted, all rights reserved** | `cite-and-synthesize-only` |
| **ASCO / Cancer.Net** | Patient info | **Copyrighted** | `cite-and-synthesize-only` |
| **Academy of Nutrition and Dietetics** | Patient/professional | **Copyrighted** | `cite-and-synthesize-only` |
| **WCRF / AICR** | Diet & cancer guidance | **Copyrighted** | `cite-and-synthesize-only` |
| **Macmillan / Cancer Research UK** | UK patient info | **Copyrighted** | `cite-and-synthesize-only` |
| **NICE** (UK) | Guidelines | Mixed; **copyright asserted**, reuse limited — verify per item | `cite-and-synthesize-only` (default) |

**The central licensing decision.** Most authoritative patient-nutrition content is **copyrighted**.
Therefore the default is **synthesize-and-cite, never republish**: we extract non-copyrightable
*facts* and write **original plain-language** text, citing the primary source for each claim. We
reproduce wording **only** from sources whose license clearly permits it (NCI/PDQ public domain; NHS
under OGL with attribution). **WHO's CC BY-NC-SA is non-commercial + share-alike and therefore
incompatible with our CC-BY output for *reproduced text*** — WHO is `cite-and-synthesize-only` (cite
facts; do not paste its text). Each source's terms are **verified and recorded in the registry before
its content informs anything that ships**; a license check gates the build.

**Provenance model.** Each claim → one or more `Source` records: source name, jurisdiction, exact
citation (title, section, year/version), URL, retrieval date, **verified reuse terms + reuse mode**,
`lastVerified`, `validUntil`. The citation-coverage check enforces no-source-no-claim; the license
check enforces no-unverified-source.

**Staleness is fail-safe, not best-effort** (see architecture §6): claims past `validUntil` are
flagged or withheld until re-verified and re-signed-off — oncology nutrition guidance changes (the
neutropenic-diet reversal is the canonical example of why silent staleness is dangerous).

**Output licensing.** Original synthesis (content/data/docs): **CC-BY-4.0** (attribution to primary
sources preserved in each item). Code/tooling: **MIT**. We do not relicense or sublicense source
material; reproduced public-domain/OGL text retains its required attribution.

**Privacy / PII stance (conservative).** The project stores **no patient data** and needs none. It
uses only published authoritative guidance and (for context only) aggregate public statistics. Any
**pilot comprehension/outcome data is partner-mediated, fully consented, de-identified, and
aggregate** — collected and held by the clinical partner under their IRB/governance, never by this
project as identifiable data. No secrets, tokens, or PII in logs, receipts, or committed files
(`CLAUDE.md`). Reviewers are credited (with consent) in a reviewers ledger.

**Attribution.** Every shipped item lists its primary sources; CC-BY redistribution preserves
attribution. Reproduced OGL/PD text carries its required attribution string.

---

## Quality, review & risk gates

**Risk tier: HIGH** (health/safety, patient-facing) per `docs/good-deed-definition.md`, which requires
**credentialed expert sign-off before merge/publish**, plus the binding cancer-domain guardrails.
Pure tooling/infra tasks (schema, CI, site generator) are low–medium; **anything a patient reads is
HIGH** and gated on oncology-dietitian sign-off.

**Required reviews before a deed is "done":**

- **Maintainer** review on all PRs (engineering quality, agent-neutral core, no PII/secrets, CI green:
  `pnpm build && pnpm test && pnpm lint`).
- **Credentialed oncology dietitian (RDN/RD-CSO) sign-off** — recorded before **any** patient-facing
  nutrition content ships. **No oncology-dietitian sign-off, no publish.**
- **Oncologist sign-off** on clinically-loaded surfaces — food safety/neutropenia, cachexia/weight
  loss, hydration red flags, enteral/parenteral explainers, supplement/drug–nutrient cautions.
- **Patient-advocate review** for readability, tone, lived-experience accuracy, and that the
  care-team boundary and escalation blocks read clearly and non-alarmingly.
- **Safety / red-team review** — the adversarial suite passes in CI **and** the expert audits that no
  surface yields personalized/dangerous advice or pro-misinformation output.
- **License review** — each source's reuse terms verified and recorded before its content ships.

**Every patient-facing surface carries** the persistent **"This is general education, not medical
advice — talk to your oncology care team / dietitian"** banner, and every symptom/side-effect topic
carries a **verified red-flag escalation block**.

**Definition of Shipped (project):** real patients receive and use the content through a credible
distribution channel and it demonstrably helped them manage a treatment side effect or eat better —
with oncology-dietitian (and surface-appropriate oncologist/advocate) sign-off recorded, the safety/
red-flag/banner controls verified, helplines verified current, provenance intact, and content within
its review window.

---

## Roadmap & milestones

Phased: safety + provenance + licensing foundation first; pipeline next; expert-gated content only
behind those gates; distribution to real patients last and gated on a secured partner.

- **M0 — Safety, provenance & licensing foundation (cold-start).**
  *Goal:* the safety/"not medical advice"/red-flag policy, the content schema + provenance model, the
  source-registry + license-verification protocol, and the repo/CI skeleton exist before any content.
  *Exit:* safety policy spec merged (expert-reviewed); content schema + provenance model + banner/
  red-flag enforced templates; source registry + license-verification protocol; pnpm/TS/ESM skeleton
  with green CI (build/test/lint + citation-coverage + banner-lint stubs); **pilot topic set and
  reviewer profile fixed** so M2 builds against the right corpus and reviewer.

- **M1 — Pipeline, provenance enforcement & accessibility tooling.**
  *Goal:* the claim-extraction/synthesis pipeline with enforced provenance, staleness, readability.
  *Exit:* claim-extraction pipeline + "no source, no claim" citation-coverage check; license check
  (no unverified source); staleness fail-safe (`lastVerified`/`validUntil`); readability check
  (≤ grade 8) + plain-language checklist; helpline-verification check stub. **Kill-gate:** a *minimal*
  grounded-vs-blank-slate + safety check on a couple of fixture topics runs here as an early go/no-go
  — if grounded+cited+safe doesn't clearly beat blank-slate, HIGH-tier content investment pauses.

- **M2 — Core side-effect content (expert-gated).**
  *Goal:* the pilot side-effect topics, cited and **oncology-dietitian-signed-off**.
  *Exit:* pilot-topic sources vetted + provenance recorded (license-verified); core topics (nausea/
  vomiting, sore mouth/mucositis, taste changes, appetite loss, diarrhea/constipation) drafted,
  cited, readability-passing, banner+escalation present, and **RDN/CSO signed off** (oncologist sign-
  off where clinically loaded); kill-gate confirmed on real cited content.

- **M3 — Safety/escalation layer + caution content.**
  *Goal:* verified escalation/helplines and the high-misinformation-surface caution content.
  *Exit:* food safety/neutropenia content (oncologist-reviewed; reflects evolved guidance); verified
  red-flag escalation blocks + verified helplines across topics; supplement/herb and unproven-diet
  caution content (accurate, cited, defer-to-team); "questions to ask your dietitian/care team"
  prompt lists — all expert-signed-off.

- **M4 — Eval, accessibility & translation readiness.**
  *Goal:* prove quality/safety and harden for real readers.
  *Exit:* eval shows grounded+cited+safe clearly beats blank-slate; **safety red-team 0 leakage**;
  WCAG 2.2 AA + print/large-print variants; machine-readable corpus published; translation framework
  with first language piloted via back-translation + bilingual RDN/advocate sign-off.

- **M5 — Distribution & beneficiary handoff (the deed).**
  *Goal:* real patients receive and benefit.
  *Exit (Definition of Shipped):* a secured partner distributes the content to real patients;
  comprehension test passes (≥ 80% on key items); ≥ 10 attested instances of it helping; safety/
  provenance controls verified; outcomes recorded. *(Gated on a secured partner — TO BE SECURED.)*

- **M6 — Sustain & scale (post-delivery).**
  *Goal:* durable maintenance and careful expansion (more topics, more languages).
  *Exit:* maintenance rotation + review-cadence (guideline re-verification + re-sign-off) + outcomes
  dashboard; expert-gated process for adding topics/languages; helpline re-verification schedule.

Dependencies flow M0 → M1 → M2 → M3 → M4 → M5 → M6. The **pilot topic set + reviewer profile decision
is made in M0 and gates M2–M6**; M2 content blocks on M0 (safety/schema/license protocol), the chosen
topics, and the secured oncology-dietitian reviewer; M5 blocks on a secured distribution partner.

---

## Work breakdown

The itemized, schema-mapped backlog lives in **`TASKS.md`**: ~19 tasks across M0–M6 plus a future
backlog, each mapped to the Elyos Task JSON schema, with per-task acceptance criteria for the most
important items, milestone Definitions of Done, and a complete, schema-valid example Task JSON for the
first M0 task (the safety / "not medical advice" / red-flag policy spec). The first build item is that
safety policy spec, reflecting its status as a hard product requirement; a **pilot topic-set/reviewer
selection** and a **minimal grounded-vs-blank-slate + safety kill-gate** at M1 are sequenced so
HIGH-tier content investment is gated on both a chosen corpus and an early thesis/safety check.

---

## Governance, roles & stakeholders

- **Maintainer (Owner): TBD.** Owns the pipeline, schema, agent-neutral core, CI gates, and merge
  quality.
- **Reviewers / rotation:** at least one engineering reviewer plus a designated **safety/red-team
  reviewer** who audits that no surface yields personalized/dangerous advice, independent of authors.
- **Credentialed oncology dietitian (RDN/RD-CSO): TO BE SECURED** — signs off all patient-facing
  nutrition content before publish; tracked in the reviewers ledger with credentials and consent.
- **Oncologist reviewer: TO BE SECURED** — signs off clinically-loaded surfaces (food safety/
  neutropenia, cachexia, hydration red flags, enteral/parenteral, drug–nutrient cautions).
- **Patient-advocate reviewer: TO BE SECURED** — readability, tone, lived-experience accuracy,
  clarity of the care-team boundary and escalation blocks.
- **Steward (last-mile owner): TO BE SECURED** — owns the distribution-partner relationship and the
  hand-off/adoption that constitutes shipping, and the consented, de-identified outcome capture.
- **Partner / requestor: TO BE SECURED** — clinical dietetics team, cancer-support nonprofit, hospital
  patient-education office, or advocacy org.
- **Independence / COI & sign-off mechanics:** reviewers disclose material COIs (e.g., ties to a
  supplement maker or a specific "diet" program) and **recuse** from related content. Sign-off is
  **version-scoped** — it attaches to a specific content version + citation set and does **not** carry
  forward to edits, which require re-sign-off (dovetails with the staleness model). **Name-use limits:**
  a reviewer's name/credentials may be published in the reviewers ledger only for the versions they
  approved, with consent, and may not imply endorsement of content they did not review.
  **Disagreement fallback:** the oncology dietitian / oncologist holds a **veto on whether HIGH-tier
  content is clinically safe to publish** — a maintainer cannot override a "do not ship" on substance;
  disagreements are logged and escalated to Elyos governance / a second credentialed reviewer, and a
  **second reviewer is preferred before relying on contested clinical content**.
- **Community / board:** edge cases, the cancer-domain guardrails, and license decisions go through
  Elyos governance.

---

## Dependencies & integrations

- **Authoritative sources:** NCI/PDQ, NHS, WHO, ESPEN, ASPEN, ACS, ASCO/Cancer.Net, Academy of
  Nutrition and Dietetics, WCRF/AICR, Macmillan, Cancer Research UK, NICE — each with **verified
  reuse terms and recorded provenance** before use (see licensing).
- **Aggregate statistics (context only):** SEER / GLOBOCAN (aggregate, attributed) if needed for
  framing — not the core of this content project.
- **External services:** Anthropic Claude API (drafting/extraction aid only, behind a neutral LLM
  client; model/pricing per the Claude API skill); static-site hosting for the human-readable output.
- **Elyos pieces:** `packages/schema` (Task JSON), `CLAUDE.md` (work rules + cancer guardrails +
  refusal rules), `docs/good-deed-definition.md` (risk tiers), Elyos governance for license/edge
  cases; cross-links to roadmap siblings (`survivorship-resources`, `question-prompt-lists`,
  `oncology-glossary-multilingual`, `prevention-info-open`).
- **Human/decision dependencies (critical path):** the **pilot topic-set + reviewer profile decision
  (M0, gates M2–M6)**; a secured **oncology-dietitian reviewer** (blocks M2 content); a secured
  **distribution partner/steward** (blocks M5).

---

## Risks & mitigations

| Risk | Likelihood | Impact | Mitigation | Owner |
|---|---|---|---|---|
| Content is read/used as personalized medical advice and causes harm | High | Critical | Safety layer built first; persistent "not medical advice/talk to your team" banner on every page; refuse-and-redirect for individual questions; safety red-team asserts 0 personalized/dangerous leakage; oncology-dietitian + oncologist sign-off | Safety reviewer / Expert |
| Inaccurate or outdated nutrition claim (e.g., stale neutropenic-diet guidance) | High | Critical | Primary-source citation required (no-source-no-claim); credentialed expert sign-off; **runtime staleness fail-safe** flags/withholds claims past `validUntil` until re-signed-off; oncologist review on clinical surfaces | Expert reviewer |
| Steered toward misinformation / "anti-cancer diet" or supplement endorsement | Medium | Critical | Out-of-scope set enforced; caution content states what evidence shows + defers to team; safety red-team covers misinformation prompts; COI recusal for diet/supplement ties | Safety reviewer / Expert |
| Copyright violation by reproducing source text | Medium | High | **Synthesize-and-cite, never republish**; reproduce only from PD/OGL sources; per-source license verified + recorded before use; license check gates build | Maintainer / Expert |
| Dangerous symptom under-escalated (e.g., dehydration, neutropenic fever, refeeding) | Medium | Critical | Verified red-flag escalation blocks on every symptom topic (template-enforced); oncologist review; verified helplines/emergency guidance; staleness applies to escalation info | Expert / Maintainer |
| Stale/incorrect helpline or crisis number served | Medium | High | Helpline-verification check (100% verified within window); 0 stale numbers served; shorter review cadence for helplines | Maintainer / Steward |
| No distribution partner secured → cannot reach Definition of Shipped | High | High | Honest `TO BE SECURED`/`verifiedNeed:false`; **dated acquisition plan** (reviewer by 2026-10-15, partner by 2026-12-15) + **build-vs-mothball/pivot rule** at ~2027-03-31 (contribute corpus to an existing trusted publisher, or mothball) | Steward / Maintainer |
| No credentialed oncology-dietitian reviewer secured → M2 blocked | Medium | High | Recruit via the Academy's Oncology Nutrition DPG, NCI-designated cancer centers, advocacy orgs; hard gate: no HIGH content ships without sign-off; hold at M1 meanwhile | Maintainer |
| Translation introduces error/dangerous nuance shift | Medium | High | Back-translation review + bilingual oncology-RDN/advocate sign-off per language; cultural-food-context notes; per-language staleness | Expert / Steward |
| LLM-assisted drafting hallucinates a claim or citation | Medium | High | LLM is an aid only; human extraction check; no-source-no-claim; expert sign-off; eval/groundedness checks | Maintainer |
| Reader over-restricts diet (fear-driven) from caution content | Low–Med | Medium | Plain, non-alarming tone (advocate review); emphasize "eating enough matters," defer specifics to dietitian; comprehension testing | Advocate / Expert |

---

## Security & privacy

**Threat surface.** Misuse as personalized medical advice (primary harm vector); ingestion/spread of
misinformation; copyright exposure from reproduced text; stale clinical guidance or helplines; LLM
hallucination in drafting; supply-chain/secrets in the tooling repo. The project holds **no patient
data**, so cross-tenant/PII-leak surfaces are minimal by design.

**Misuse threat model (the "I just want a number" reader).** The most likely "attack" is a
well-meaning reader (or a future Q&A surface) pushing for individualized output: "just tell me how
many grams of protein," "is this supplement OK with my chemo," "give me a meal plan." The safety layer
and red-team explicitly model this: any individualizing request is **declined and redirected** to the
care team/dietitian with the general, cited information and (if urgent) the escalation block; LLM-
assisted authoring paths are red-teamed for the same so no draft path emits personalized advice.

**Controls.** Safety layer as a code-checked, adversarially-tested release gate (top control).
Banner-lint + red-flag-template lint **fail the build** if missing. No-source-no-claim citation
coverage + license verification gate content. Staleness + helpline-verification gates prevent serving
out-of-date clinical/escalation info. **No PII collected**; any pilot data is partner-held, consented,
de-identified, aggregate. **No secrets/tokens/PII in logs, receipts, or committed files** (`CLAUDE.md`).
Dependency + secret scanning in CI. Any LLM client is server-side/agent-neutral and cannot override
the safety templates; its outputs are human- and gate-checked.

**Abuse/misuse prevention.** The refused/declined set (personalized advice, dosing, interactions,
diagnosis/triage, anti-cancer-diet/cure endorsement, supplement endorsement) is enforced via the
safety layer + red-team + expert audit — not merely documented — and the project never claims to
replace a clinician.

---

## Sustainability & maintenance

After delivery, a named **maintenance rotation** owns the pipeline and corpus; the **steward** owns
the partner relationship and consented, de-identified outcome tracking. Content carries a **review
cadence**: each source's `lastVerified`/`validUntil` drives the **runtime staleness fail-safe** so
content past its window is auto-flagged or withheld until re-verified and **re-signed-off** by the
oncology dietitian (and oncologist for clinical surfaces) — guidance changes (the neutropenic-diet
reversal is the cautionary tale). **Helplines/escalation info are on a shorter re-verification
cadence.** Outcomes (patients reached, attested help, comprehension results) are tracked via the
partner and surfaced on an outcomes dashboard — **not** page views. Topic/language expansion follows a
documented, expert-gated process and only after the pilot set is stable. The safety red-team is
maintained as living tests and expanded as new misuse/misinformation vectors appear.

---

## Open questions

- **Pilot topic set & reviewer profile — decided in M0, not deferred** (gates M2–M6). Proposed pilot:
  the 5–6 highest-impact, lowest-clinical-risk side-effect topics (nausea/vomiting, sore mouth, taste
  changes, appetite loss, diarrhea/constipation), with food-safety/neutropenia and cachexia handled in
  M3 under oncologist review. **Decision rule + deadline (2026-08-15) are fixed**; the specific
  reviewer remains TO BE SECURED.
- **Jurisdiction/framing:** guidance differs across US/UK/EU bodies and units (e.g., kcal vs kJ),
  food availability, and helpline numbers. Lead with US (NCI/PDQ public-domain base) or UK (NHS OGL
  base)? Proposal: anchor reproduced text on the most permissively-licensed base for the chosen
  jurisdiction and clearly localize escalation/helpline info per region.
- **How far to go on cachexia/weight-loss** without crossing into personalized advice? Proposal:
  general, non-prescriptive awareness ("why eating enough matters; tell your team about weight loss")
  + strong defer-to-dietitian; oncologist-reviewed.
- **Pediatric oncology nutrition** — out of MVP scope (higher stakes). Add later only with pediatric-
  oncology dietitian review? (Open.)
- **Compensation/crediting for credentialed reviewers** — volunteer vs a future funded lane for review
  hours (with a hard budget cap) without compromising independence?
- **Future Q&A surface** — if/when a guardrailed Q&A is built, it inherits the safety layer; scope and
  go/no-go are an explicit future decision, not MVP.
- **Distribution channel** — printed handouts in infusion suites vs a static site vs both; which best
  reaches the underserved (rural/low-literacy/non-English) target?

---

## References

- Proposal: roadmap Track 8b entry `nutrition-during-treatment` in `planning/ROADMAP.md`
  (no standalone `governance/proposals/nutrition-during-treatment.md` yet — **TO BE WRITTEN**).
- Elyos work rules, cancer guardrails & refusal guardrails: `CLAUDE.md`
- Good-deed definition & risk tiers: `docs/good-deed-definition.md`
- Task JSON schema: `packages/schema/src/schemas.ts`
- Portfolio roadmap + Track 8 cancer domain guardrails: `planning/ROADMAP.md`
- Sibling Elyos HIGH-risk plan for house style: `planning/projects/public-official-guide/{PLAN,TASKS}.md`
- Authoritative sources (verify reuse terms per item): NCI/PDQ (cancer.gov), NHS (nhs.uk), WHO,
  ESPEN oncology nutrition guidelines, ASPEN, ACS, ASCO/Cancer.Net, Academy of Nutrition and
  Dietetics (Oncology Nutrition DPG), WCRF/AICR, Macmillan, Cancer Research UK, NICE.

---

## Appendix A — Improvements applied

The following 25 specific improvements were identified during drafting and **have been applied** to
this plan and to `TASKS.md` (not merely listed). Each cites where it now lives.

1. **Safety layer sequenced as the first build item**, not a disclaimer — it is a code-checked release
   gate (Exec summary; Architecture §1; M0; TASKS `safety-001`).
2. **"No source, no claim" citation-coverage check** in CI so no patient-facing claim ships without a
   license-verified primary source (Architecture §3; Success metrics; M1).
3. **Central licensing decision made explicit — "synthesize-and-cite, never republish"** copyrighted
   text, with a per-source reuse-mode table (Data/licensing). Resolves the dominant legal risk.
4. **WHO CC BY-NC-SA flagged as incompatible with CC-BY reproduction** and set to
   `cite-and-synthesize-only` — a specific, easy-to-miss license trap caught (Data/licensing table).
5. **Runtime staleness fail-safe** (`lastVerified`/`validUntil`) with the **neutropenic-diet reversal**
   as the concrete cautionary example (Architecture §6; Sustainability; Risks).
6. **Red-flag/escalation block template-enforced** on every symptom topic, lint-gated (Architecture §1;
   Quality gates; Success metrics; M3 `escalation-010`).
7. **Helpline/crisis-info verification gate** — 100% verified within window, 0 stale numbers served,
   on a shorter re-verification cadence (Architecture §7; Success metrics; Sustainability).
8. **Dated reviewer/partner-acquisition plan + build-vs-mothball/pivot rule** so the project never
   ships HIGH content to no one (Exec summary; Problem; Risks; TASKS `partner-016`).
9. **Three-reviewer model by surface** — oncology RDN/CSO (all content), oncologist (clinical),
   patient-advocate (readability/tone) — instead of a single vague "expert" (Governance; Quality gates).
10. **Version-scoped sign-off + name-use limits + COI recusal** (esp. supplement/diet ties) for
    reviewers (Governance) — prevents stale or implied endorsement.
11. **Disagreement fallback / expert veto** on clinical-safety-to-publish, with escalation and a
    preferred second reviewer (Governance; mirrors the public-official-guide rigor).
12. **Reading-level target (≤ grade 8) made a measurable, CI-checked gate** plus a plain-language
    checklist and advocate review (Architecture §5; Success metrics; M1 `readability-006`).
13. **Comprehension / teach-back testing with pilot patients** (≥ 80% on key items) as an outcome
    metric — measures understanding, not page views (Success metrics; M5).
14. **Outcome metrics are beneficiary-centric** (patients reached + attested help) with vanity metrics
    explicitly excluded (Success metrics; Sustainability).
15. **Privacy-by-construction: no patient data held**; any pilot data is partner-mediated, consented,
    de-identified, aggregate (Data/licensing; Security & privacy) — satisfies the cancer guardrails.
16. **Explicit out-of-scope/declined set** (personalized targets, dosing, interactions, triage,
    anti-cancer-diet/cure, supplement endorsement) with **refuse-and-redirect-to-care-team** behavior
    as the ethical core, held to a coverage metric (Scope; Security; Success metrics).
17. **Safety red-team modeling the "just give me a number" reader** and LLM-assisted drafting paths —
    asserting 0 personalized/dangerous leakage (Security threat model; Eval; Success metrics; M4).
18. **Minimal grounded-vs-blank-slate + safety kill-gate at M1** so HIGH-tier content investment is
    gated on an early thesis/safety check, not discovered late (M1; Work breakdown).
19. **LLM positioned strictly as an authoring aid behind an agent-neutral client, never an authority**,
    and never bypassing human expert sign-off (Architecture; Key decisions; Risks).
20. **Misinformation handled head-on** — caution content states what the evidence shows, cited, and
    defers to the team, rather than ignoring fad diets readers will encounter (Scope; Risks; M3).
21. **Survivorship / pediatric / clinical-nutrition-support boundaries drawn** and cross-linked to
    roadmap siblings to avoid scope creep and over-reach (Scope; Non-goals; Dependencies).
22. **Jurisdiction/units/localization flagged** (US vs UK base, kcal/kJ, region-specific helplines)
    with a licensing-driven anchoring proposal (Open questions; Data/licensing).
23. **Machine-readable + human-readable + print/large-print outputs** so the corpus serves both
    patients and downstream programs, with WCAG 2.2 AA (Architecture; Scope; M4 `a11y-014`).
24. **Translation with back-translation review + bilingual oncology-RDN/advocate sign-off** and
    per-language staleness — translation treated as HIGH risk, not a string swap (Architecture §9;
    Risks; M4 `i18n-015`).
25. **Definition of Shipped = real patients helped through a credible channel** (delivered-not-merged),
    with the full gate stack verified — adopted as the project's success definition (Exec summary;
    Quality gates; Success metrics; M5).

---

## Review sign-off

**Reviewer:** drafting senior staff engineer + TPM (self-review pass for completeness & correctness).
**Date:** 2026-06-28. **Scope:** PLAN.md (17 required sections + Appendix A) and TASKS.md.

**Completeness check.** All 17 required H2 sections present and in order: Executive summary; Problem &
beneficiaries; Goals and non-goals; Success metrics (outcomes); Scope; Solution approach &
architecture; Data, licensing & compliance; Quality, review & risk gates; Roadmap & milestones; Work
breakdown; Governance, roles & stakeholders; Dependencies & integrations; Risks & mitigations;
Security & privacy; Sustainability & maintenance; Open questions; References. Plus Appendix A (25
applied improvements) and this sign-off. ✔

**Cancer-guardrail check.** Open-access/aggregate/de-identified-only stance stated and enforced;
controlled-access/identifiable patient data explicitly out of scope; per-source license verification
is a build gate; "not medical advice" + care-team boundary on every page; oncology-dietitian +
oncologist + advocate review for HIGH content; helplines verified; provenance on every assertion.
The **Data/licensing** and **Quality gates** sections lead with these guardrails as required. ✔

**Schema check.** TASKS.md maps every task to the Task JSON schema fields; the example JSON validates
against `packages/schema/src/schemas.ts` (all required fields present; enums valid; `verifiedNeed:
false`; donated lane so no `fundedBudgetUsd` required). ✔

**Corrections made during review.**
- Reconciled the success-metric "memory-grounded" wording (this is a content project, not an app):
  reframed as **source-grounded+cited vs. blank-slate** in metrics, architecture, and the M1 kill-gate.
- Ensured **every symptom/side-effect topic** (not just M3 items) is covered by the red-flag template
  gate, and that **staleness applies to escalation/helpline info**, not only nutrition claims.
- Made the **license check a distinct CI gate** from citation-coverage (a source can be cited but its
  reuse terms unverified — both must pass) and reflected this in TASKS `pipeline-004`/`sources-007`.
- Confirmed the **example task's `outputLicense` is CC-BY-4.0** (it's a document/policy deliverable),
  while code tasks use **MIT** and content/data use **CC-BY-4.0**, per the licensing section.
- Verified **no task asserts a secured partner/reviewer**: all delivery-dependent tasks carry
  `requestor: TO BE SECURED` and `verifiedNeed: false`.

**Residual items requiring a human decision** (tracked in *Open questions* / Risks): secure the
oncology-dietitian reviewer (gates M2) and distribution partner (gates M5); choose jurisdiction/base
for reproduced text; confirm pilot topic set; decide reviewer compensation model. **Sign-off:
APPROVED as a Draft v0.1.0** for circulation to a credentialed oncology dietitian and a candidate
distribution partner — **not** approved for any patient-facing publication until the HIGH-tier expert
sign-off and partner gates are met.
