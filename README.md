# AEO Scorecard

A pre-publish **Answer Engine Optimization (AEO)** gate for articles and reviews. It answers one
question about a finished page: **can an LLM or AI-search layer retrieve and cite this page, or
is it just readable prose?**

Each page is scored on **7 weighted dimensions** (0–5 each, normalized to /100), with HARD
criteria that block publishing regardless of the score. The scorecard runs in two passes: a
plan-readiness pass after the human edit, and a live pass on the built private page before
go-live.

## The 7 dimensions

| Dim | Name | Weight |
|---|---|---|
| A1 | Central-entity salience | ×3 |
| A2 | Citation-ready architecture | ×3 |
| A3 | Query fan-out & attribute coverage | ×2 |
| A4 | Entity homing & link graph | ×2 |
| A5 | Schema / `@id` readiness | ×2 |
| A6 | Author E-E-A-T | ×1 |
| A7 | Classic on-page | ×1 |

`SCORE% = Σ(score × weight) / 70 × 100` · **Publish bar: ≥70 and 0 HARD blockers.**
Grade bands: 85–100 exceptional · 70–84 strong · 55–69 adequate · 40–54 developing ·
<40 content-only.

## Layout

| Path | What it is |
|------|-----------|
| [`rubric/EVALUATION-FRAMEWORK.md`](rubric/EVALUATION-FRAMEWORK.md) | The 9-dimension entity-SEO framework for a whole content plan. Everything else descends from it |
| [`rubric/AEO-ARTICLE-SCORECARD.md`](rubric/AEO-ARTICLE-SCORECARD.md) | The article-level rubric (parent) |
| [`rubric/AEO-REVIEW-SCORECARD.md`](rubric/AEO-REVIEW-SCORECARD.md) | The review fork (`/review/{tool}/`); dimensions and weights carried over unchanged |
| [`agent/aeo-reviewer.md`](agent/aeo-reviewer.md) | An LLM agent prompt that scores one article and returns a filled scorecard, a fix-list and PASS/FAIL |
| [`spec/aeo-scorecard-design.md`](spec/aeo-scorecard-design.md) | How the two-pass gate plugs into a publishing pipeline |
| [`examples/`](examples/) | Filled scorecards from real review runs, anonymised (more being added) |

## Lineage

`EVALUATION-FRAMEWORK` → `AEO-ARTICLE-SCORECARD` (articles) → `AEO-REVIEW-SCORECARD` (reviews).
The dimensions, weights, HARD criteria and grade bands carry over unchanged down the chain; only
the evidence notes change per content type.

The framework is derived from the course *AI Search & LLMs — Entity SEO and Knowledge Graph
Strategies for Brands (2026)*; chapter and lesson references are kept in the framework file.

## About the examples

The examples are real scorecards from reviews of cold-email inbox providers. The publisher, the
reviewed tool, competitors, people, prices and quotes are replaced with placeholders (`Tool A`,
`Competitor 1`, `$X`). Scores, evidence and fix-lists are unchanged.

## License

[CC BY 4.0](LICENSE). You can share and adapt this work, including commercially, as long as you give
appropriate credit and link back to this repository.
