# Per-Article AEO Scorecard — the pre-publish SEO/AEO gate

**What this is.** A single-article scorecard that answers "**is this finished article SEO/AEO-inclined, or just readable prose?**" It is the article-level companion to the plan-level [`EVALUATION-FRAMEWORK.md`](EVALUATION-FRAMEWORK.md) (the 9-dimension /100 course rubric) — it keeps only the dimensions that are *evaluable on one finished page* and re-weights them for an article.

**When it runs (LOCKED).** **After the human edit, as part of the pre-publish check.** The pre-publish check = **a human-voice read + this AEO scorecard (+ a plagiarism check)** on the *same edited text*. The human-voice read asks "does it read human?"; this asks "can a machine retrieve and cite it?" They are complementary and both run on the editor's final version, never on the first draft. Running it before the human edit is a dry-run only — the authoritative score is on the edited article, because **the human edit is the step most likely to break AEO** (see the failure modes below).

**Two passes (learned from the first validation run).** Internal links + JSON-LD are inserted at the **publish build**, which runs *after* the pre-publish check. So A4/A5 cannot be scored on *live* links/schema at the pre-publish check — scoring them there would falsely penalize every article for infra that legitimately doesn't exist yet. Therefore:
- **Pass 1 — pre-publish check (after the human edit):** the **prose-level, edit-fragile** dims are authoritative — **A1, A2, A3, A6, A7**. **A4/A5 are scored as PLAN-READINESS** only (are the anchor phrases + entity homes present in the prose, and is the `@id` graph derivable), never as live links/schema. This is the pass that protects AEO from the human edit.
- **Pass 2 — final lock (on the built page, before go-live):** the **full** sheet, now with **A4 live internal links + A5 live JSON-LD** scored for real (after the publish build). This is the authoritative /100.
Report both; a low A4/A5 at Pass 1 with the plan present is EXPECTED and not a fail.

**Why after the human edit specifically.** The four things a human edit silently destroys:
1. **Buries the first-answer** — the editor reworks the opener into a "hook" and the direct snippet answer moves down or dissolves.
2. **Pronoun drift** — entity names ("email deliverability", "SPF/DKIM/DMARC") get replaced with "it / this / that" for flow → the section stops being citable for its entity.
3. **Fact-atoms merge** — crisp one-fact paragraphs get woven into flowing multi-claim prose → no longer quotable as a standalone fact.
4. **Entity drops out of the opening** — the central entity vanishes from the first 100 words.
The scorecard watches for exactly these.

---

## The 7 dimensions (article-applicable subset of the 9-dim framework)

Each scored **0–5** (same scale as the parent framework), × weight. Weighted total normalized to **/100**.

| Dim | Name | Weight | Maps to | What it checks on the FINISHED article |
|---|---|---|---|---|
| **A1** | **Central-entity salience** | **×3** | D1 + D2 | ONE declared central entity; present in the **first 100 words** + byline + repeated naturally through the body (not a fuzzy topic). H1 *or* an H1-adjacent dek/first-answer names it. |
| **A2** | **Citation-ready architecture** | **×3** | D3 | **First-answer / snippet block opens the page.** Each section leads with its entity, not a vague pronoun. ~**One verifiable, self-contained fact per paragraph** (quotable in isolation). Related entities named in-text. |
| **A3** | **Query fan-out & attribute coverage** | **×2** | D3 | The **representative query** is answered directly. Query-variation angles covered (intent · comparison · use-case · pain-point · how/why PAA). **Required-attributes** complete vs the central entity. FAQ answers are entity-rich and standalone. |
| **A4** | **Entity homing & link graph** | **×2** | D2 + D4 | **Zero orphan entities** — every named concept-entity homes to a hub. **Pass 1 (pre-publish):** the anchor phrases + entity homes are present in the prose and map to the outline's link targets (plan-readiness). **Pass 2 (final lock):** internal links to pillar/cluster are LIVE; contextual bridge **up** + **across** wired; external tools **mention-only / nofollow**. |
| **A5** | **Schema / @id readiness** | **×2** | D4 | **Pass 1 (pre-publish):** the **graph PLAN** is derivable — `author→Person`, `article→about→central entity`, DefinedTerms + `mentions` identifiable, FAQ FAQPage-shaped (schema-**ready**). **Pass 2 (final lock):** the JSON-LD is LIVE + parses + every `@id` resolves. |
| **A6** | **Author E-E-A-T** | **×1** | D7 | Attributed to a **real Person entity** (byline byte-matchable to the Person `@id` in the page schema, NOT the content-ops owner). First-person operator authority; credible-diagnosis, not hype. |
| **A7** | **Classic on-page** | **×1** | — | Single H1; logical H2/H3 nesting; title/meta shape; permalink/slug set; internal anchors resolve; depth ≈ the SERP-derived target (not thin, not bloated). |

**Weight sum = 14 · max weighted = 70.** `SCORE% = (Σ score×weight) / 70 × 100`.

**Grade bands (mirror the parent framework):**
`85–100` exceptional · `70–84` strong · `55–69` adequate · `40–54` developing · `<40` content-only (reads fine, but the AI-search layer is missing).

**Publish bar: ≥ 70 (strong).** Below 70 → back to the editor with the fix-list, same loop as a failed human-voice read.

---

## HARD criteria (must-pass — a fail here is a BLOCKER regardless of the weighted score)

These are the non-negotiables; the article cannot pass the pre-publish check with any of them broken, even at a 75 weighted score:

1. **Central entity in the first 100 words** (A1). If the human edit dropped it, block.
2. **A first-answer / direct-answer block exists** near the top (A2). Snippet/AEO shape.
3. **No section opens on a bare vague pronoun** ("It's important…", "This is why…") where the entity should lead (A2).
4. **Author attributed to a real Person** (A6) — never the content-ops owner, never "Team".
5. **Single H1** (A7).
6. **Every followed outbound link is intended** (A4) — no accidental followed link to a competitor on an informational node (D7).

---

## Scoring sheet (filled per article)

| # | Dimension | Weight | Score (0–5) | Weighted | Evidence / fix |
|---|---|---|---|---|---|
| A1 | Central-entity salience | 3 | | /15 | |
| A2 | Citation-ready architecture | 3 | | /15 | |
| A3 | Query fan-out & attribute coverage | 2 | | /10 | |
| A4 | Entity homing & link graph | 2 | | /10 | |
| A5 | Schema / @id readiness | 2 | | /10 | |
| A6 | Author E-E-A-T | 1 | | /5 | |
| A7 | Classic on-page | 1 | | /5 | |
| | **TOTAL** | **14** | | **/70 → /100** | |

**Output of a run:** the filled sheet + weighted `/100` + grade band + any HARD-criterion BLOCKERs + a **prioritized fix-list** (each fix = the sentence/section + the specific change), so the editor's next pass is targeted. The reviewer reads the article against **its own outline / brief** for the intended central entity, representative query, required attributes, and link targets — the scorecard is graded against the node's own contract, not a generic ideal.

---

## How it plugs into the pre-publish check

```
Human edit (the editor's final version) ........................ ✋ human gate
   │
   ▼
pre-publish check  (after the human edit, on the edited text)
   ├─ Human-voice read → reads human                  (your house check)
   ├─ AEO scorecard    → ≥70 strong, 0 HARD blockers  (aeo-reviewer + THIS sheet)
   └─ Plagiarism check → original
   │   any fail → back to editor with the notes + AEO fix-list
   ▼
publish build  ·  fact verify · assets · internal links · schema  →  Pass 2  →  go-live
```

The human-voice read and AEO can conflict — the most human-reading phrasing sometimes buries the entity or merges fact-atoms. When they do, the fix is a **surgical re-word** that satisfies both (name the entity *and* keep the human cadence), never a choice of one over the other. That reconciliation is the editor's, guided by both reports.

**Reusable across nodes and content types.** Articles/guides/pillars run the full sheet. Reviews/alternatives add nothing here but inherit the same gate. Interactive tool pages need a separate layout check instead; this prose scorecard does not apply to them.
