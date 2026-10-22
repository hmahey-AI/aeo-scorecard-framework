# Design — AEO scorecard gate (pre-publish check + publish build)

**Date:** 2026-08 · **Status:** approved (design gate)

## Purpose

Add a hard publish gate that scores a near-final review against the locked 7-dimension AEO rubric
and returns a prioritized fix-list. It reuses the locked article rubric
([`AEO-ARTICLE-SCORECARD.md`](../rubric/AEO-ARTICLE-SCORECARD.md)), forked to a review-specific
variant ([`AEO-REVIEW-SCORECARD.md`](../rubric/AEO-REVIEW-SCORECARD.md)). Nothing is invented: the
dimensions, weights, HARD criteria and grade bands carry over unchanged.

## Non-goals

- No change to the research, drafting or editing stages. The gate only reads; it never rewrites.

---

## Rubric (reused)

7 dimensions (A1 central-entity salience ×3, A2 citation-ready ×3, A3 query fan-out ×2,
A4 entity homing & links ×2, A5 schema/@id readiness ×2, A6 author E-E-A-T ×1, A7 classic
on-page ×1). Weight sum 14, `SCORE% = Σ(score×weight)/70×100`.
**Publish bar: ≥70 AND 0 HARD blockers.**

## Agent

[`agent/aeo-reviewer.md`](../agent/aeo-reviewer.md) reads the enriched article + the article's
own brief/outline (for the declared central entity, representative query, required attributes,
and link targets) + the rubric. It emits a filled scorecard, a prioritized fix-list, and a
PASS/FAIL verdict. Two modes:
- **`pass=plan-readiness`** (pre-publish article check): A1/A2/A3/A6/A7 authoritative; A4/A5
  scored as plan-readiness (anchor phrases + entity homes present, `@id` graph derivable).
- **`pass=live`** (publish build): A4 (internal links resolve 200, followed links intended) + A5
  (JSON-LD parses, every `@id` resolves) re-scored for real on the private post.

## Pass 1 — pre-publish article check

- Runs as one more auditor alongside the existing technical-SEO, content-quality and
  factual-accuracy auditors.
- Output: `AEO-SCORECARD-{tool}.md` next to the article.
- **Gate:** the article check passes only with AEO ≥70 **and** 0 HARD blockers. A fail goes back
  to the editor with the AEO fix-list.

## Pass 2 — publish build (before go-live)

- Runs after internal links and schema are in place on the **private** post, before go-live.
- Re-scores A4 live + A5 live. It catches the two recurring review-schema rich-result bugs
  (`review` placed on BlogPosting instead of SoftwareApplication; a `mentions[]`
  SoftwareApplication missing `operatingSystem`) as A5 HARD failures.
- **Gate:** any HARD blocker (especially live schema) blocks go-live until fixed. The
  authoritative `/100` is appended to the same scorecard file as a Pass 2 section.

---

## Risk / rollback

Additive only: no existing behavior removed. The gate can be waived explicitly (and logged) if a
run needs to bypass it.
