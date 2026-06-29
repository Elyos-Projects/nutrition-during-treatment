# Competitive + Improvement Analysis — `nutrition-during-treatment`

> Analyst review of `PLAN.md` (Draft v0.1.0, 2026-06-28) and `TASKS.md` for the Elyos cancer-research
> good-deed project: an open-access, plain-language, source-cited, oncology-RD-reviewed library of
> nutrition guidance for people in **active cancer treatment**. HIGH risk-tier, patient-facing; cancer
> guardrails apply. Web-researched, cited.

---

## 1. Correctness & completeness review of PLAN.md

The plan is unusually strong for a v0.1: it correctly identifies the dominant risks (misuse as
personalized advice, stale clinical guidance, copyright), sequences the safety layer first, makes
oncology-RD (RDN/RD-CSO) sign-off a hard blocking gate, mandates no-source-no-claim provenance, and
draws honest `TO BE SECURED` lines around the unsecured partner/reviewer. The following are concrete
gaps, errors, and weak spots.

**A. The RD-review gate is concrete and blocking — but has thin escape valves.**
- The gate is well-specified (version-scoped sign-off, COI recusal, expert veto on "is it clinically
  safe to publish," preferred second reviewer). **Gap:** there is no defined behavior for *single-
  reviewer dependency*. One volunteer RDN/CSO is a single point of failure for the entire HIGH-tier
  corpus and for re-sign-off at every staleness cycle. The plan should require **≥ 2 credentialed
  reviewers before relying on any clinically-loaded content** (it only "prefers" a second), and define
  what happens to *already-published* content if the sole reviewer leaves (auto-flag to "review
  window lapsed"? withhold?). Tie this to the staleness fail-safe explicitly.
- **Gap:** reviewer *competence scope* is not bounded. An oncology RDN is not automatically qualified
  on drug–nutrient/herb–drug interactions (that is pharmacist territory) or on enteral/parenteral
  protocols. The plan names an oncologist for "clinical surfaces" but **does not name an oncology
  pharmacist** — the correct authority for the single highest-risk content class (supplement–chemo and
  herb–drug interactions). This is a real gap given MSK's interaction database is curated *by a
  pharmacist* ([MSK About Herbs](https://www.mskcc.org/cancer-care/diagnosis-treatment/symptom-management/integrative-medicine/herbs)).
  Recommend adding a **pharmacist reviewer (or explicit defer-entirely-to-pharmacist rule)** for the
  `unproven-011` supplement/herb content.

**B. Supplement–chemo / drug–nutrient interaction safety — under-built relative to its risk.**
- The plan's stance (don't judge individual interactions; defer to pharmacist/dietitian) is correct
  and safe. **But** `unproven-011` lumps "supplements/herbs" and "anti-cancer diets" into one medium
  task. The interaction domain is genuinely contested in the literature — e.g., the antioxidant-during-
  chemo/radiation debate has reviews on *both* sides (some claiming no interference/benefit, others
  showing increased recurrence/death risk) ([NCCIH antioxidants](https://www.nccih.nih.gov/health/antioxidant-supplements-what-you-need-to-know);
  [scoping review, PMC11663640](https://pmc.ncbi.nlm.nih.gov/articles/PMC11663640/)). The plan needs an
  explicit rule that for contested-evidence topics the content **states the controversy and defers**,
  and must **not** synthesize a false "the evidence shows X" consensus. NCI's own
  [Cancer Therapy Interactions With Foods and Dietary Supplements (PDQ)](https://www.cancer.gov/about-cancer/treatment/cam/patient/dietary-interactions-pdq)
  is a public-domain authoritative anchor that should be in the source registry and is currently not
  named.
- **Missing:** an explicit pointer/handoff to a maintained interaction database (MSK About Herbs is
  free, weekly-updated, consumer+clinician). The plan should *link to* such a tool rather than try to
  replicate volatile per-substance interaction data it cannot keep current.

**C. Neutropenic / food-safety nuance — directionally right, one subtlety missing.**
- The plan correctly treats the "neutropenic diet" walk-back as the canonical staleness example and
  routes food safety to oncologist review. The evidence base is solid: systematic reviews and a 2025
  RCT find no benefit of the neutropenic/low-bacterial diet over standard FDA safe-food-handling
  ([PubMed 31608705](https://pubmed.ncbi.nlm.nih.gov/31608705/);
  [scoping review PMC11514644](https://pmc.ncbi.nlm.nih.gov/articles/PMC11514644/);
  [Frontiers PMC8959862](https://pmc.ncbi.nlm.nih.gov/articles/PMC8959862/)).
- **Subtlety to flag:** "neutropenic diet abandoned" is itself an over-simplification readers can
  misread as "no food precautions needed." The content must thread *standard food-safety still
  applies* (FDA safe handling) while *the restrictive low-bacterial diet is not evidence-supported* —
  and note that some centers/protocols (esp. **HSCT/transplant and pediatric**) still impose
  restrictions. Pediatric food-safety guidance remains genuinely unsettled
  ([MDPI Nutrients 16/7/966](https://www.mdpi.com/2072-6643/16/7/966)). Since the plan defers pediatric
  to backlog, it should add a caution that adult guidance must not be read across to children.

**D. Debunking dangerous myths — present, but needs a non-backfire methodology.**
- Addressing "sugar feeds cancer," alkaline, keto-as-therapy, juicing, extreme fasting is in scope
  (`unproven-011`) and well-grounded ([Cancer Research UK food myths](https://www.cancerresearchuk.org/about-cancer/causes-of-cancer/cancer-myths-questions/food-myths);
  [BDA Cancer Diets: Myths and More](https://www.bda.uk.com/resource/cancer-diets-myths-and-more.html)).
  **Gap:** myth-debunking can *backfire* (repeating the myth reinforces it) and can *scare patients
  into under-eating* (the plan flags the over-restriction risk only as "Low–Med"). The plan should
  mandate a **"truth sandwich" / lead-with-the-fact** template and require advocate + comprehension
  testing specifically on myth pages. Also missing: a nuance the evidence demands — "sugar feeds
  cancer" is false as a *starvation strategy*, yet excess added sugar/obesity has real risk links;
  the content must not overcorrect into "sugar is fine, eat anything."

**E. The "not medical advice" boundary — strong design, two engineering gaps.**
- Banner-lint + refuse-and-redirect + red-flag templates are correctly code-checked gates, and the
  "just give me a number" threat model is explicit. Good.
- **Gap 1 (static vs. interactive):** the MVP is *static content*, where "refuse-and-redirect" is
  trivially safe — there is no free-text input to steer. The genuinely hard safety problem (a reader
  pushing for a number) only exists in the **deferred Q&A surface (`qa-023`)**. The plan slightly
  over-claims that the static corpus is "engineered so it cannot be steered" — for static content the
  real risk is not steering but **a reader self-applying general guidance as if personal**. The
  mitigation for *that* is comprehension testing + framing, which the plan has, but it should
  re-scope the threat language so reviewers don't get a false sense that the steering problem is
  solved when the Q&A surface is the actual locus.
- **Gap 2 (LLM-drafting leakage):** the red-team covers LLM-assisted drafting paths — good — but there
  is **no rule that the published artifact must contain zero un-cited LLM-introduced facts**. "Human
  checks the extraction" is necessary but not a gate. Add a CI/diff check that every shipped sentence
  maps to a claim with a source (the no-source-no-claim check must operate at sentence granularity,
  not just "page has citations").

**F. Source authority + currency — registry is right; freshness/versioning is under-specified.**
- The licensing table is excellent and the WHO CC BY-NC-SA share-alike trap is correctly caught.
- **Gap:** `validUntil` intervals are described qualitatively ("~annually," "shorter for helplines")
  but not **pinned to source-side change events**. Guidelines change on the guideline-body's schedule,
  not a calendar. The registry should capture **source version/edition** (e.g., ESPEN practical
  guideline 2021 — note the plan/TASKS reference a 2024 ESPEN update that **does not appear to exist;
  the current practical guideline is 2021** [ESPEN PDF](https://www.espen.org/files/ESPEN-Guidelines/ESPEN-practical-guideline-clinical-nutrition-in-cancer.pdf))
  and a check for "newer edition published" — not only "our review clock expired." **Correctness flag:
  scrub any implied "ESPEN 2024" reference to the actual 2021 version.**

**G. Malnutrition / cachexia screening + referral — the biggest content omission.**
- This is the most consequential clinical gap. The plan treats cachexia/weight-loss as backlog
  (`cachexia-019`, "general, non-prescriptive awareness") and otherwise centers side-effect symptom
  management. **But malnutrition is the highest-impact, outcome-changing issue** (worse treatment
  tolerance, dose reductions, survival) and authoritative bodies converge on **early screening +
  prompt RD referral** ([ESPEN](https://www.espen.org/files/ESPEN-Guidelines/ESPEN-practical-guideline-clinical-nutrition-in-cancer.pdf);
  national survey on inadequate oncology nutrition coverage [PMC6893237](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6893237/)).
  A patient-facing project that helps people *eat through nausea* but **doesn't prominently teach
  "unintentional weight loss / not eating for days is a red flag — get referred to a dietitian"** is
  optimizing the comfortable middle and missing the highest-stakes signal. Recommend **promoting a
  malnutrition-awareness + "ask for a dietitian referral / validated screen (e.g., MUST, PG-SGA done
  by a clinician)" red-flag block out of backlog into the M2/M3 core**, framed non-prescriptively
  (awareness + escalation, not self-diagnosis).

**H. Accessibility / health-literacy / multilingual — well-conceived, two refinements.**
- ≤ grade-8 reading level as a CI gate, WCAG 2.2 AA, print/large-print, back-translation + bilingual
  RDN sign-off, and an audio/read-aloud backlog item are all present and strong.
- **Refinement 1:** Flesch–Kincaid ≤ grade 8 is a weak proxy — it rewards short sentences and misses
  jargon/concept load. Pair it with a **plain-language concept checklist + teach-back comprehension**
  (the plan has comprehension testing at M5; pull a lightweight version earlier, into M2 advocate
  review). Note the population skews older/sicker/cognitively-taxed mid-treatment — design for "2 a.m.,
  exhausted reader," which the exec summary nicely names but the metrics don't fully operationalize.
- **Refinement 2:** translation picks "first language" abstractly. Tie language choice to the
  **secured partner's actual patient population** (don't translate to Spanish if the pilot clinic is
  majority Vietnamese-speaking). Currently i18n is gated only on tooling, not on beneficiary data.

**I. Metrics — mostly outcome-centric; a few are unfalsifiable or partner-blocked.**
- "100% of claims cited," "0 personalized-advice leakage," "0 stale helplines," "≤ grade 8" are
  crisp and checkable. Good.
- **Weak/risky:** "≥ 10 attested instances of it helping" and "≥ 80% comprehension" are **entirely
  partner-gated** — with no partner secured, nearly every *outcome* metric is unmeasurable, meaning the
  project can complete M0–M4 (a large body of work) while every success metric reads "n/a / 0
  baseline." That's honest but means the **build-vs-mothball decision (2027-03-31) is the real
  success gate**, and it deserves a leading-indicator metric (e.g., "≥ 1 partner in active pilot
  conversation by M2 entry") so the team isn't flying blind until M5. The "grounded vs. blank-slate"
  eval delta is also somewhat circular for a *cited-content* project (of course cited beats
  uncited) — its real value is the **safety** half (0 leakage); weight it accordingly.

**J. Smaller items.**
- Helpline/escalation is US/UK-centric; "poison control," "911/999," distress lines differ by country
  — the localization rule exists but should be a *blocking* check per shipped locale, not a note.
- No explicit **conflict-of-interest screen on sources** (e.g., supplement-industry-funded "evidence")
  — the registry verifies license/currency but not funding bias. Add a source-credibility/COI field.
- The plan defers a **free-text Q&A chatbot** entirely (correct for MVP) but Savor Health's *Ina*
  shows the market expects exactly that — see §2/§4 for why static-first is actually a differentiator,
  not a weakness, if framed deliberately.

---

## 2. Competitive landscape

Nutrition-during-treatment information is **abundant but fragmented, copyrighted, reading-level-
inaccessible, and rarely RD-reviewed-and-openly-licensed all at once**. Key players:

**1. NCI / PDQ — "Nutrition in Cancer Care" (cancer.gov).** The authoritative US base.
[Patient + health-professional versions](https://www.cancer.gov/about-cancer/treatment/side-effects/nutrition),
[NCI nutrition landing](https://www.cancer.gov/about-cancer/treatment/side-effects/appetite-loss/nutrition-hp-pdq),
plus the public-domain [Cancer Therapy Interactions With Foods and Dietary Supplements (PDQ)](https://www.cancer.gov/about-cancer/treatment/cam/patient/dietary-interactions-pdq).
*Strengths:* authoritative, evidence-graded, **public domain (reproducible)**, dual patient/clinician
versions, regularly updated. *Weaknesses:* written above most patients' reading level, dense, US-only
framing/units, not translated broadly, no plain-language "2 a.m." design, no print-handout polish.

**2. American Cancer Society (ACS).** Patient-facing
[Nutrition during/after treatment](https://www.cancer.org/cancer/survivorship/coping/nutrition.html),
[Food Safety During Treatment](https://www.cancer.org/cancer/survivorship/coping/nutrition/weak-immune-system.html),
and a downloadable [Nutrition for the Person with Cancer During Treatment booklet](https://www.cancer.org/content/dam/cancer-org/cancer-control/en/booklets-flyers/nutrition-for-the-patient-with-cancer-during-treatment.pdf).
*Strengths:* readable, practical (small frequent meals, high-cal/high-protein), trusted brand, free
booklet. *Weaknesses:* **copyrighted, all-rights-reserved** (can't reuse/translate freely), US-centric,
limited languages, not openly machine-readable.

**3. ASCO / Cancer.Net.** Patient nutrition content co-developed with ACS, oncologist-reviewed.
*Strengths:* clinically credible, patient-oriented. *Weaknesses:* copyrighted, English-dominant, not
an open commons; overlaps ACS.

**4. Academy of Nutrition and Dietetics — Oncology Nutrition DPG (ON DPG).**
[oncologynutrition.org](https://www.oncologynutrition.org/about-us) + 60+ patient handouts via the
[eatRIGHT store](https://www.eatrightstore.org/product-type/booklets-and-handouts/oncology-nutrition-educational-handouts-and-resources).
*Strengths:* RD-authored, symptom-specific handouts and recipes (nausea, sore mouth, diarrhea),
the gold standard for clinician-facing oncology nutrition; **the most likely credentialed-reviewer
recruiting channel** (the plan correctly names it). *Weaknesses:* much content is **paywalled/
member- or purchase-gated and copyrighted**, clinician-oriented, not an open patient commons, limited
translation.

**5. ESPEN — Practical Guideline: Clinical Nutrition in Cancer (2021).**
[ESPEN PDF](https://www.espen.org/files/ESPEN-Guidelines/ESPEN-practical-guideline-clinical-nutrition-in-cancer.pdf);
43 recommendations, flow charts. *Strengths:* rigorous, the European clinical reference, screen-early
emphasis. *Weaknesses:* **copyrighted (Elsevier), clinician-facing, not plain-language**, not for
patients directly. (Note: current version is 2021 — no 2024 update located; correct any plan reference.)

**6. WCRF / AICR.** [Cancer-prevention & after-diagnosis recommendations](https://pmc.ncbi.nlm.nih.gov/articles/PMC7217975/).
*Strengths:* authoritative diet-and-cancer evidence syntheses, "avoid supplements for prevention,"
post-diagnosis guidance. *Weaknesses:* **prevention/survivorship-oriented, not active-treatment
symptom management** (adjacent, not core), copyrighted.

**7. Macmillan / Cancer Research UK / NHS (UK).**
[Macmillan eating problems](https://www.macmillan.org.uk/cancer-information-and-support/impacts-of-cancer/eating-problems),
[CRUK food myths](https://www.cancerresearchuk.org/about-cancer/causes-of-cancer/cancer-myths-questions/food-myths).
*Strengths:* very readable, empathetic, strong myth-busting, NHS content under **Open Government
Licence (reusable)**. *Weaknesses:* Macmillan/CRUK **copyrighted**, UK-centric (units, foods,
helplines), limited languages.

**8. Memorial Sloan Kettering — "About Herbs."**
[mskcc.org/aboutherbs](https://www.mskcc.org/cancer-care/diagnosis-treatment/symptom-management/integrative-medicine/herbs)
+ app; 290 monographs, **pharmacist-curated, updated weekly**, dual consumer/clinician. *Strengths:*
the authoritative free supplement/herb–drug interaction reference. *Weaknesses:* not plain-language
for low-literacy readers, narrow (supplements only, not whole-diet/side-effects), copyrighted. **This
is a complement to link to, not compete with.**

**9. Supplement-interaction databases (Natural Medicines, NCCIH).**
[NCCIH antioxidants](https://www.nccih.nih.gov/health/antioxidant-supplements-what-you-need-to-know).
*Strengths:* evidence-graded interaction data. *Weaknesses:* Natural Medicines is **subscription/
paywalled**; clinician-oriented; evidence is genuinely contested.

**10. Savor Health — "Ina," the Intelligent Nutrition Assistant (the direct AI competitor).**
[savorhealth.com](https://savorhealth.com/); SMS/text AI built on oncology RD-CSO expertise, with live
RD oversight; partnered with LUNGevity, CancerCare; [JCO CCI national-implementation study](https://ascopubs.org/doi/10.1200/CCI.24.00085);
3,310 users 2019–2023, 87% report symptom-management help, 80% improved QoL. *Strengths:* **on-demand,
personalized, 24/7, RD-backed, clinically validated, exactly the interactive experience patients
want.** *Weaknesses:* **proprietary/closed, not open-licensed, not a public commons, partner-gated
access, gives personalized advice** (which Elyos deliberately won't) — and being personalized + AI
raises exactly the safety-surface Elyos is engineered to avoid. Ina is the clearest signal of demand
and the clearest contrast to Elyos's "open, static, cited, non-personalized" thesis.

**Landscape verdict:** authoritative content exists everywhere, but **no single resource is
simultaneously (a) open-licensed + machine-readable, (b) plain-language ≤ grade 8 + multilingual,
(c) RD-reviewed with per-claim provenance, and (d) safety-engineered with explicit myth-debunking.**
That intersection is empty — and it's where Elyos sits.

---

## 3. Gaps we can fill

1. **An open, reusable commons.** Every readable source (ACS, ASCO, Macmillan, ON DPG handouts) is
   copyrighted; every open source (NCI/PDQ, NHS) is reading-level-inaccessible or jurisdiction-bound.
   A **CC-BY-4.0, plain-language synthesis with attribution** that clinics, translators, and other
   nonprofits can freely adapt/print/embed is genuinely missing.
2. **Plain-language + low-literacy + multilingual together.** Authoritative + readable + translated +
   accessible (WCAG, large-print, audio) in one place — the "2 a.m. exhausted caregiver" design — does
   not exist as an open resource.
3. **Per-claim provenance ("no source, no claim").** Patients can't tell credible from predatory
   content online; **every sentence traceable to NCI/ESPEN/etc.** is a trust feature nobody offers
   patient-side.
4. **Myth-vs-evidence done safely and openly.** A cited, non-alarming, non-backfiring debunk of
   "sugar feeds cancer," alkaline, keto-as-therapy, juicing, fasting — that *also* protects against
   fear-driven under-eating — fills the space between predatory "anti-cancer diet" sites and dense
   clinical reviews.
5. **Machine-readable structured corpus.** A cited JSON/YAML knowledge base other patient-education
   programs, translators, and (later, carefully) tools can build on — no incumbent publishes this.
6. **A deliberately safe non-personalized lane.** Where Ina personalizes (and carries that risk),
   Elyos fills the **"trustworthy general information that knows its own boundary and routes you to a
   real RD"** gap — safer to distribute at scale, and an honest answer to the RD-scarcity problem
   (one RD per hundreds of patients; many rural clinics have none).
7. **The malnutrition-awareness + referral nudge** (per §1G) as open, plain-language content — turning
   the most outcome-relevant clinical signal into something a caregiver can recognize and act on.

---

## 4. Differentiators to win

1. **Open license + provenance + RD sign-off, together.** No competitor offers all three; it's the
   defensible core.
2. **Safety-engineered as code, not disclaimer.** Banner-lint, red-flag templates, no-source-no-claim,
   staleness fail-safe, and a safety red-team in CI — a verifiable trust artifact incumbents (static
   web pages) and AI tools (opaque models) can't easily show.
3. **Plain-language + multilingual + accessible by construction**, not as an afterthought.
4. **Non-personalized by design = safe to distribute everywhere.** The deliberate refusal to give
   numbers/doses/interaction judgments is the feature that lets a clinic hand it to every patient
   without clinical liability — the inverse of Ina's personalization risk.
5. **Honest delivery bar ("delivered, not merged").** Success = real patients helped through a real
   channel, with a mothball/pivot rule rather than vanity publication — credibility most "content
   farms" lack.
6. **Composable commons.** Machine-readable + CC-BY means it can *feed* incumbents (contribute to an
   open patient-education library) rather than only compete — a realistic last-mile if no distribution
   partner lands.

---

## 5. Claude API leverage

**Where Claude clearly helps (authoring aid, behind the agent-neutral client, never the authority):**
1. **Source-grounded synthesis with inline citations.** Claude reads authoritative sources and drafts
   **original plain-language claims each tagged to its primary source**, enforcing the no-source-no-
   claim discipline at draft time (extractive-then-rewrite, with the source span attached). Strong fit
   for the M1 pipeline.
2. **Reading-level + plain-language rewriting.** Claude is excellent at lowering reading level to
   ≤ grade 8, simplifying jargon, and applying a "truth-sandwich" template to myth pages — then the
   FK/checklist CI gate and advocate verify. Iterate draft→check→redraft.
3. **Translation + back-translation drafting.** Claude drafts translations and the back-translation for
   the bilingual-RDN review loop, with cultural-food-context notes — accelerating a HIGH-risk, expensive
   step (human bilingual RDN still signs off).
4. **Myth-vs-evidence framing + adversarial red-team generation.** Claude both drafts the cited
   debunks *and* **generates the safety red-team** ("just give me a number," "is my supplement OK with
   chemo," "will keto cure me") to stress-test that content/Q&A always refuses-and-redirects.
5. **Claim-diffing for staleness.** When a source updates, Claude flags which existing claims the new
   edition affects — feeding the re-verification queue.
6. **Comprehension-item drafting** for teach-back tests.

**Where Claude must NOT decide (hard boundaries — these are the project's ethical core):**
- **No individualized nutrition/medical advice.** No calorie/protein/fluid targets, meal plans, doses,
  or "what should *I* eat." Claude drafts *general, cited* education only.
- **No supplement–drug / herb–drug interaction judgments.** This is contested even in the literature
  (antioxidants-during-chemo debate) and is **pharmacist/RD territory** — Claude must surface what
  authoritative bodies say *in general*, defer to the care team, and link MSK About Herbs; never
  adjudicate a specific interaction.
- **Oncology-RD (RDN/CSO) sign-off is a blocking gate.** Claude output is an authoring aid; nothing
  patient-facing ships without recorded human credentialed sign-off (oncologist/pharmacist on clinical
  surfaces, advocate on readability).
- **Every claim sourced to an authoritative body; zero fabricated facts or citations.** Hallucinated
  claims/citations are a top risk — enforce sentence-level no-source-no-claim + human extraction check;
  Claude never invents a source or a number.
- **Flag-don't-answer for high-risk/individual queries.** For any individualizing or urgent request,
  decline, give general cited info, route to the care team, and surface the escalation block — never
  attempt triage or a personalized answer.
- **No "anti-cancer diet" / cure endorsement, ever**, and no false "the evidence shows" consensus on
  genuinely contested topics — state the controversy and defer.

---

## 6. Ten concrete optimizations

1. **Add an oncology pharmacist reviewer** (or a hard "defer entirely to pharmacist" rule) for the
   supplement/herb interaction content, and **require ≥ 2 credentialed reviewers** before relying on
   any clinically-loaded content (remove the single-reviewer single-point-of-failure).
2. **Promote malnutrition-awareness + "ask for a dietitian referral / weight-loss red flag"** out of
   backlog into core M2/M3 — it's the highest-outcome-impact, currently-underweighted signal.
3. **Make no-source-no-claim operate at sentence granularity** (every shipped sentence maps to a
   sourced claim), not page-level — closing the LLM-introduced-uncited-fact gap.
4. **Add a contested-evidence rule + template:** where authoritative bodies disagree (antioxidants,
   some supplements), state the controversy and defer; forbid synthesizing a false consensus.
5. **Adopt a "truth-sandwich"/lead-with-fact template for all myth pages** + require comprehension
   testing specifically on them to prevent backfire and fear-driven under-eating.
6. **Capture source version/edition + "newer edition published" check** in the registry (not just a
   review-clock) and **fix any "ESPEN 2024" reference to the actual 2021 guideline.**
7. **Link to maintained external tools** (MSK About Herbs, NCI dietary-interactions PDQ) instead of
   trying to replicate volatile per-substance interaction data; add both PDQ interaction pages to the
   registry as public-domain anchors.
8. **Add a leading-indicator outcome metric** ("≥ 1 partner in active pilot conversation by M2 entry")
   so the project isn't metric-dark until M5, and explicitly tie translation-language choice to the
   secured partner's actual patient demographics.
9. **Add a source COI/funding-bias field** to the registry (screen out supplement-industry-funded
   "evidence") alongside license + currency.
10. **Pull a lightweight teach-back/comprehension check into M2 advocate review** (not only M5), and
    treat FK ≤ grade 8 as necessary-not-sufficient alongside a concept-load checklist for the
    "exhausted 2 a.m. reader."

---

## 7. Parallel & perpendicular spin-offs

**Parallel (same engine, adjacent content):**
- **`survivorship-resources`** — post-treatment/long-term diet (WCRF/AICR territory); the plan already
  draws the boundary and should cross-link. Same pipeline, lower acuity.
- **`question-prompt-lists`** — the "questions to ask your dietitian/care team" lists generalize into a
  cross-project safe-redirection pattern (the ethical core reused).
- **`food-safety-open`** — the neutropenia/food-safety content is a natural standalone open module
  (FDA safe-handling, dispel the low-bacterial-diet myth) usable beyond oncology.
- **`ewing-family-guide` / disease-specific guides** — plug nutrition modules into specific-cancer or
  pediatric guides (pediatric needs its own reviewer profile — already backlog `pediatric-024`).
- **`oncology-glossary-multilingual`** — shared translation + plain-language tooling.

**Perpendicular (the engine itself, generalized):**
- **A clinician-reviewed, openly-licensed, provenance-tracked patient-health-info engine** — the
  safety layer + provenance model + staleness fail-safe + readability/translation pipeline + expert
  sign-off ledger is a **reusable platform** for *any* high-stakes patient-education domain (cardiac
  rehab, diabetes, mental-health first-aid). The single most valuable perpendicular asset; the nutrition
  corpus is the first instance.
- **An open "myth-vs-evidence" content kit** (truth-sandwich template + cited-debunk pattern + red-team)
  reusable across health misinformation domains.
- **Partnerships:** Academy ON DPG (reviewer pipeline + handout co-development), NCI-designated cancer
  centers, Cancer Support Community / Gilda's Club, CancerCare, LUNGevity (note: already Savor/Ina
  partners — potential channel *or* incumbent friction), hospital patient-education offices, and BDA/UK
  dietitian bodies for the UK/NHS-OGL track.

---

## 8. Open questions for the maintainer

1. **Will you secure a pharmacist reviewer (or commit to full defer-to-pharmacist) for interaction
   content** — given an oncology RD is not the right authority for drug–nutrient/herb–drug judgments?
2. **Single vs. multiple credentialed reviewers:** can the project ship HIGH-tier content behind a
   *single* volunteer RDN/CSO, and what happens to published content if that reviewer departs?
3. **Should malnutrition-awareness + referral be core (M2/M3), not backlog**, given it's the highest-
   outcome-impact content?
4. **Jurisdiction anchor:** US/NCI-PDQ (public-domain reproducible) vs UK/NHS-OGL base — and does the
   secured partner's population decide it (and the first translation language)?
5. **Static-only vs. eventual guardrailed Q&A:** given Savor Health's *Ina* shows strong demand for
   interactive personalized support, is "deliberately non-personalized static commons" the permanent
   thesis, or a phase-1 with a gated Q&A roadmap?
6. **Distribution reality:** if no partner by 2027-03-31, is the *preferred* fallback contributing the
   cited corpus to an existing open patient-education library (vs. mothball) — and should you pre-
   negotiate that recipient *now* rather than as a last resort?
7. **Reviewer compensation:** volunteer vs. a hard-capped funded-lane for review hours — and how to
   protect independence either way?
8. **How do you measure "helped"** in a way that survives the no-patient-data guardrail beyond partner-
   attested anecdotes — is there a consented, de-identified proxy you can define now?
