# AEO Review Scorecard — the pre-publish AEO gate (review CPT)

**What this is.** A single-article scorecard that answers "**is this finished review
AEO-retrievable, or just readable prose?**" It runs against a review at `/review/{tool}/` in
two passes and is a **hard gate on publish**.

**Origin.** This is the review-specific fork of
[`AEO-ARTICLE-SCORECARD.md`](AEO-ARTICLE-SCORECARD.md) (the locked article rubric,
itself the article-level companion to [`EVALUATION-FRAMEWORK.md`](EVALUATION-FRAMEWORK.md)). The
dimensions, weights, HARD criteria, and grade bands are carried verbatim; the *evidence notes*
are specialized to the review CPT (byline→Person, review-on-SoftwareApplication schema,
`mentions[]`, FAQPage, the outbound-to-tool nofollow rule).

**Graded against the node's own contract.** Score the article against **its own brief/outline**
for the intended central entity (the reviewed tool), representative query, required attributes,
and link targets — never a generic ideal.

---

## When it runs (two passes)

| Pass | Stage | A1/A2/A3/A6/A7 | A4 (links) | A5 (schema) |
|---|---|---|---|---|
| **1 — plan-readiness** | pre-publish article check (alongside the other auditors) | authoritative | plan-readiness | plan-readiness |
| **2 — live** | publish build (private post, before go-live) | carried from Pass 1 | LIVE (200 + intended) | LIVE (JSON-LD parses, `@id` resolves) |

**Pass 1** protects AEO from the human edit and gates the article check. A low A4/A5 at
Pass 1 with the plan present is EXPECTED and NOT a fail — internal links + JSON-LD are finalized
in the publish build, after the article check.
**Pass 2** re-scores the two infra dims for real on the built private post and gates go-live.

**Why AEO can conflict with the human-voice read.** The most human-reading phrasing sometimes buries the
entity or merges fact-atoms. The fix is always a **surgical re-word that satisfies both** (name
the entity *and* keep the human cadence), never a choice of one over the other.

---

## The 7 dimensions

Each scored **0–5** × weight. Weighted total normalized to **/100**.

| Dim | Name | W | What it checks on the finished review |
|---|---|---|---|
| **A1** | Central-entity salience | **×3** | The reviewed tool is the ONE central entity; present in the **first 100 words** + byline + repeated naturally through the body; named by H1 or an H1-adjacent dek/first-answer. |
| **A2** | Citation-ready architecture | **×3** | A **first-answer / BLUF block opens the page**. Each section (Features/Pros/Cons/Pricing/Support/Verdict/FAQ) leads with the entity, not a vague pronoun. ~**one verifiable, self-contained fact per paragraph**. Receipts (G2/Reddit/Trustpilot `[quote]`) tie to the claim they support. |
| **A3** | Query fan-out & attributes | **×2** | The **representative query** ("{tool} review", "is {tool} legit/worth it") is answered directly. Comparison / use-case / pain-point / how/why angles covered. **Required review attributes** complete (pricing, mailbox type, IP model, warmup, support). FAQ answers are entity-rich and standalone. |
| **A4** | Entity homing & link graph | **×2** | **Zero orphan concept-entities** (SPF/DKIM/DMARC, named competitors, warmup, etc.). **Pass 1:** anchor phrases + entity homes present and map to the outline's link targets. **Pass 2:** internal links to pillar/cluster LIVE (200); up + across wired; the one outbound link to the reviewed tool is **`nofollow`** and every other followed outbound is intended (no accidental followed competitor link). |
| **A5** | Schema / @id readiness | **×2** | **Pass 1:** the graph PLAN is derivable — `author→Person`, `review→about→{tool}` (via the review's tool-name / visit-URL fields), the 5 `reviewRating` dims, `mentions[]`, FAQ FAQPage-shaped. **Pass 2:** JSON-LD is LIVE, parses, every `@id` resolves; **`review` sits on SoftwareApplication (NOT BlogPosting)**; **every `mentions[]` SoftwareApplication has `operatingSystem`**; single `reviewRating`; body ends on the FAQ H2. |
| **A6** | Author E-E-A-T | **×1** | Attributed to a **real Person** (byline byte-matchable to a live Person `@id`, e.g. `/about/{author}/#person` — NEVER "Team" or the content-ops owner). First-person operator authority; credible diagnosis, not hype; a sourcing line in the lede. |
| **A7** | Classic on-page | **×1** | Single H1; logical H2/H3 nesting; title/meta in band; slug set; anchors resolve; house style rules hold (example house rules: **zero em/en dashes**; the Verdict H2 carries a house rating suffix); depth ≈ the SERP-derived target (example house budget ~2,000–3,800w). |

**Weight sum = 14 · max weighted = 70.** `SCORE% = Σ(score×weight) / 70 × 100`.

**Grade bands:** `85–100` exceptional · `70–84` strong · `55–69` adequate · `40–54` developing ·
`<40` content-only.

**Publish bar: ≥ 70 (strong) AND 0 HARD blockers.**

---

## HARD criteria (a fail here BLOCKS regardless of the weighted score)

1. **Central entity in the first 100 words** (A1).
2. **A first-answer / BLUF block exists near the top** (A2).
3. **No section opens on a bare vague pronoun** where the entity should lead (A2). (FAQ Q/A
   pairs: the H3 question is the extraction unit, so a pronoun answer is an A2 deduction, not a
   HARD fail — but flag it with the one-line fix.)
4. **Author attributed to a real Person** (A6) — never "Team", never the content-ops owner.
5. **Single H1** (A7).
6. **Every followed outbound link is intended** (A4) — the reviewed-tool link is `nofollow`; no
   accidental followed competitor link.
7. **(Pass 2 only) Live JSON-LD is valid** — parses, `review` on SoftwareApplication, every
   `mentions[]` SoftwareApplication has `operatingSystem`, all `@id`s resolve. (This is the
   codified guard for the two recurring Google rich-result bugs.)

---

## Scoring sheet (filled per run)

| # | Dimension | W | Score (0–5) | Weighted | Evidence / fix |
|---|---|---|---|---|---|
| A1 | Central-entity salience | 3 | | /15 | |
| A2 | Citation-ready architecture | 3 | | /15 | |
| A3 | Query fan-out & attributes | 2 | | /10 | |
| A4 | Entity homing & link graph | 2 | | /10 | |
| A5 | Schema / @id readiness | 2 | | /10 | |
| A6 | Author E-E-A-T | 1 | | /5 | |
| A7 | Classic on-page | 1 | | /5 | |
| | **TOTAL** | **14** | | **/70 → /100** | |

**Output of a run:** the filled sheet + weighted `/100` + grade band + any HARD BLOCKERs + a
**prioritized fix-list** (P1/P2/P3, each fix = the sentence/section + the specific change), so
the next pass is targeted. Fixes must respect the house verbatim rule (the author's words are preserved): prefer
**wrapping existing words** / surgical re-words; never inject new prose to satisfy AEO.
