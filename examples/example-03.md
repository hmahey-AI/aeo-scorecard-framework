# AEO Scorecard — Example 03: inbox-provider review
*Anonymised: the publisher, the reviewed tool, competitors, people, prices and quotes are replaced with placeholders.*

Pass: live (v2.1 SHIPPED, October 2026) · Score: 91/100 (64.00/70) · exceptional (85-100) · PASS (0 HARD blockers)

> **v2.1 note (added after final sign-off, NOT a re-score).** At final sign-off an editorial decision removed the house rating suffix from the Verdict H2, so it shipped as the source wrote it, `The Verdict`. That gives back exactly P2-6 (A7 4.5 -> 4.25, weight 1): 64.25 - 0.25 = **64.00/70 = 91.43 -> 91/100**, still exceptional, 0 HARD. Nothing else changed between the v2 render and the live page (live render verified: 0 dashes, link contract 4/4, JSON-LD byte-identical, 14 nodes). The v2 scorecard below is kept as scored, for the record.

---

Pass: live (re-score v2, after the editorial fix-list rulings were applied) · Score: 92/100 (64.25/70) · exceptional (85-100) · PASS (0 HARD blockers)

# AEO Review Scorecard v2: Tool A (`/review/tool-a/`)

> **VERDICT AT A GLANCE (October 2026, re-score on the v2 private render)**
> **Score: 92/100** (64.25/70, 91.79) · grade band **exceptional (85-100)** · **HARD blockers: 0** · **Gate: PASS.**
> The bar is **>=70 AND 0 HARD failures**. Both halves clear. v1 was 82 / FAIL.
>
> **The HARD blocker is gone.** Features H3 `Automated Setup` now opens on the entity: *[opener: names Tool A as the subject that does the setup and the MX/SPF/DKIM/DMARC records]*. I re-walked every extraction unit: lede, KT, 11 H2 sections, 3 Features H3s, 3 Pros H3s, 5 Cons H3s, the Breakdown H3 + `[note]`, and 7 FAQs. **None opens on a bare referential pronoun.** HARD #3 PASSES.
>
> **Every approved edit rendered, and nothing unapproved changed.** I diffed the v1 and v2 renders line by line. The readable extraction is byte-identical to the build's stored readable-text file. All 28 approved edits (on 25 source lines) are on the page, plus the one inserted sentence, the 6 `&#45;` escapes, the 2 glossary wraps, the new SEO title, meta and excerpt, and the re-synced `FAQPage`. The source file itself is untouched (its mtime predates the edit run). **No approved edit failed to land.**
>
> **The applied set landed exactly where v1 projected.** v1 put P1 + all of P2 at 63.25/70. The three approved P3 items add P3-2 (+0.5), P3-5 (+0.375) and P3-7 (+0.125). **Net 64.25, to the quarter point.**
>
> **Contradictions:** C1 (spare per inbox) and C2 (the pricing-table tier range) are **closed on every surface**. C3's title half is closed; the dedicated-minimum body claim stays by editorial decision and is now sourced in the body. C5 is closed in FAQ 3, with two surfaces still worded without the "sending inboxes" scope (KT Risk L24, Overall ratingbar L137: approved as FAQ-3-only, so this is a note, not a miss). C8 is closed by editorial confirmation.
>
> **Two things to know, neither docked:**
> 1. The new How opener sits inside the mobile-hide class, so phones (<=767px) do not show it. That is house behaviour, but it limits the sentence's value on a mobile render.
> 2. The per-inbox fix produced wording that gives a free spare inbox *"with **each inbox**"* (L60, L69) or *"with every inbox"* (L88, L136, L145). The meaning is clear, but an extracted line reads close to a tautology.

**Run:** October 2026 (v2 re-score). WordPress review post, status **private**, `publisher.example/review/tool-a/`, author **the byline author**, post_date and both schema dates set to the same October 2026 timestamp.
**Evidence base:**
- The v2 private render (authenticated HTML capture). Article = the review-content container with every CTA-block element removed, plus the FAQ accordion. The readable-text extractor was re-run from scratch on both renders; v2 is byte-identical to the build's stored readable-text file, and was diffed against the same extraction of the v1 render. Every count below was re-measured from that file.
- The stored schema file: re-parsed, the `@id` graph re-resolved, and compared to the rendered `<head>`.
- Build files: the private-render verify report · the update result · the approved-edits file · the content-changes log (51 entries) · the review body HTML · the vs-rows file.
- The article source file (October 2026 export): unchanged. **All line numbers below refer to this file.**
- Same-day vendor captures: the vendor homepage, the vendor's agency page, and the four carousel screenshots.

**Timeline:** approved edits -> builders -> push -> render, in that order, within about two minutes. The render postdates every build file.
**Re-verified independently today:**
- Anonymous GET **404**.
- Exactly **1** `<h1>`.
- Exactly **1** `ld+json` block, in `<head>`, **byte-identical** to the stored file, 14 nodes.
- 0 unrendered shortcodes · 0 v1 CTA remnants.
- All **7** editorial internal links **200** (re-curled, browser UA, www host).
- Absent from the review sitemap (0 `tool-a` matches).
- **0 em / 0 en** dashes in body + FAQ.
- `&#45;` x6 in the stored body (5 spaced hyphens + the Verdict H2).

**Still not re-verifiable:** the Trustpilot permalink (bot wall; see v1 record). The quote is unchanged and verbatim against the Trustpilot capture.

---

## Measured facts (v1 -> v2)

| Check | v1 | v2 (now) | |
|---|---|---|---|
| **Article-owned words** | ~1,296 | **~1,358**: body 1,152 -> 1,191 (+39: How opener 24, entity swaps and the restored noun), FAQ 159 -> 182 (+23: swap cap 13, question words 6, FAQ 3 scope 4). *The private-render verify report's 1,433 includes inline `<style>` text.* Still **~32% under** the ~2,000 floor | unchanged dock |
| `Tool A` (entity name) in visible text | 38 | **49** (body 37, FAQ 12), ~3.6% density, 0 variants | ✓ |
| Entity in first 100 words | H1, dek word 1, lede word 18 | unchanged | **HARD #1** |
| **Sections opening on a bare pronoun** | **1** (`Automated Setup`) | **0** | **HARD #3 closed** |
| Subject-less extraction units | 5 (L31, L48, L75, L119, L130) | **0**, all five swapped as approved | closed |
| FAQ questions naming the entity | 3/7; FAQ 5 and 6 entity-free in Q and A | **7/7**. FAQ 5's answer still opens *"You can swap it…"* and FAQ 6's answer omits the entity; both fall under the FAQ carve-out now that the question names it (Competitor 1 review precedent, not docked) | closed |
| H2 sections with zero prose | 2 (How, Pricing) | **1** (Pricing; P3-1 declined). How now opens on an entity-led `<p>`, inside the mobile-hide class | half-closed |
| Headings | 11 H2 / 12 H3 | **11 H2 / 12 H3**, no skips, 11/11 anchored. Features H3 1 now carries the per-inbox spare wording | ok |
| Verdict H2 suffix | absent | **`The Verdict` + the house rating suffix**, plain hyphen via `&#45;`, `id="the-verdict"` unchanged | closed |
| Rendered dashes | 0 em / 5 en | **0 em / 0 en**. The 3 page-level em dashes outside the article (nav x2, script comment) are unchanged and not article content | closed |
| SEO title / meta / excerpt (dek) / H1 | 57 / 161 / 191 / 57 | **55 / 157 / 148 / 57**. Title *[Tool A review, year, $X per inbox on a shared server]*. Meta re-synced into `WebPage.description`, Open Graph and social-card tags. Rendered dek = 148 | closed |
| Editorial internal links | 5, all 200 | **7, all 200**. New: the reverse-DNS glossary entry on *"reverse DNS"* (L56, Pros H3 1) and the domain-monitoring glossary entry on the first *"domain monitoring"* in L132 (Verdict P3). Both dofollow, no `target`, each path once. DNS pillar x1, still on the first SPF/DKIM/DMARC (now inside the entity-led `Automated Setup` opener) · the publisher's own tool x1 · 0 dupes · 0 `/review/` | closed |
| Orphan concept-entities | `reverse DNS`, `domain monitoring` | **0** with an exact-match home | closed |
| Outbound | compliant | unchanged: `tool-a.example` x1 editorial + x1 in the CTA block's vs-table, Trustpilot x1, all `nofollow`. Followed outbound = publisher-owned only (a chat-channel link to the byline author, the publisher's LinkedIn) | **HARD #6** |
| Receipts | 1 (Support), 1 of 3 sections | unchanged (structural) | declared |
| Schema | 14 nodes, 0 unresolved | **14 nodes, 15 defined `@id`s, 21 refs, 0 unresolved**, 0 `BlogPosting`, `SoftwareApplication` + `operatingSystem: "Web"`, single `reviewRating` 2.5, flat `Offer` at $X USD. **`FAQPage` 7/7 byte-matches the accordion**, including the 4 edited questions, FAQ 3's scope and FAQ 5's swap cap. 4 carousel `ImageObject`s byte-match. `Offer.description` tier range now agrees with the table. `#vendor` unchanged (stub) | **HARD #7** |
| vs-rows | 7 | 7. `deliverability.evidence` = the Verdict P2 exclusions sentence, now ending *"with Tool A"* (re-synced in the same pass, as required); `pricing.label` = [$X per inbox + the entry tier range] | ok |
| Banned terms | 0 | **House banned-terms list: 0 hits** across page, schema, the vs-rows field and the source | ok |
| Ratings | 2.5 / 2.5 / 3.5 / 2 / 1.5 | unchanged, locked | ok |
| Private-render head | noindex, no canonical | unchanged (expected while private; check at go-live) | watch |

---

## HARD criteria (all seven re-walked)

| # | Criterion | v1 | v2 | Evidence |
|---|---|---|---|---|
| **1** | Central entity in the first 100 words | PASS | **PASS** | H1 (after the `Private:` prefix), dek word 1, lede word 18. |
| **2** | First-answer / BLUF block near the top | PASS | **PASS** | `## Key Takeaways` after the disclosure: 2.5 ring, 4 bars, the 67-word entity-led summary, 6 bullets. The USP bullet now states the spare per inbox. |
| **3** | No section opens on a bare vague pronoun | **FAIL** | **PASS** | `Automated Setup` -> *"Tool A handles the setup…"*; its S3 *"they don't give…"* follows the entity, so it is not an opener. All units walked below. |
| **4** | Author attributed to a real Person | PASS | **PASS** | *"Reviewed by [the byline author]"* -> `/about/author/` (200); `Review.author` -> `/about/author/#person`. |
| **5** | Single H1 | PASS | **PASS** | 1 `<h1>`, theme-emitted. |
| **6** | Every followed outbound link is intended | PASS | **PASS** | Both `tool-a.example` links and the Trustpilot permalink are `nofollow`; 0 followed competitor links. |
| **7** | Live JSON-LD valid | PASS | **PASS** | Parses, byte-identical to stored, `review` on `SoftwareApplication`, 0 `mentions[]` SoftwareApplication, single `reviewRating`, 0 unresolved `@id`s, body ends on the FAQ H2. |

### **HARD blockers: 0. Gate: PASS.**

### Section-opener walk (HARD #3, v2)

| Section | Opener on the v2 render | v1 -> v2 |
|---|---|---|
| Lede | *[opener: a generic hook about cheap inbox providers]* (entity at word 18) | ok -> ok |
| KT summary | *"Tool A offers private infrastructure inboxes…"* | ok -> ok |
| About | *[definitional opener naming Tool A as a cold-email inbox provider]*; P2 *"**Tool A's** sending server is shared…"*; the list now ends on the dedicated-server minimum, sourced *"(per their live chat)"* | A2 -> **ok** |
| How Tool A Works | **new** `<p>`: *[entity-led three-step summary of setup: choose domains, a single run creates inboxes and DNS, export to the sending tool]* (inside the mobile-hide class, hidden at <=767px) | no prose -> **ok** |
| Features H3 1 (the per-inbox spare) | *[entity-led: **with Tool A**, each purchased inbox comes with a free backup inbox]* | A2 -> **ok** |
| Features H3 2 | *"Tool A suggests N inboxes per domain…"* | ok -> ok |
| **Features H3 3 `Automated Setup`** | *[entity-led: **Tool A handles** the setup and the MX/SPF/DKIM/DMARC records]* | **HARD FAIL -> ok** |
| Pros H3 1-3 | Three entity-led openers: *[own mail servers + reverse DNS]* · *[only N inboxes per domain]* · *[a free warmed-up spare per inbox]* | ok -> ok |
| Cons H3 1-4 | *"Tool A doesn't watch…"* · *"Tool A plans run…"* · *"Tool A only offers…"* · *"Tool A never sends an alert."* | ok -> ok |
| Cons H3 5 | *[bring-your-own domains accepted **by Tool A** only from a single named registrar]* | A2 -> **ok** |
| Pricing | no prose (table + ratingbar); P3-1 declined | A2 -> A2 (ceiling) |
| Publisher section | the CTA block's vs-table, Breakdown table, `[note]` *[a worked example of N inboxes from Tool A]* | ok -> ok |
| Support | *"Support is accessible via -"* under the entity-named H2; *[entity-led: **Tool A's** typical response time, in hours]* | A2 -> **ok** |
| Verdict (with rating suffix) | *"Tool A is a good fit if…"*; P2 *[the exclusions sentence (warmup, placement testing, monitoring), now ending **with Tool A**]* | A2 -> **ok** |
| FAQ 1-7 | All 7 questions name the entity. A5 opens *"You can swap it…"* and A6 omits the entity (carve-out: the question names it) | A2 -> **ok** |

---

## Contradictions (status, not scored)

As in v1, contradictions are kept **out of the score** (per the scoring brief).

| # | Contradiction | v1 | v2 |
|---|---|---|---|
| **C1** | Spare per inbox vs per domain | OPEN | **CLOSED.** All 8 surfaces now read per inbox: KT USP L22 · Features H3 L47 · L48 · Pros L60 · Cons L69 · VfM ratingbar L88 · Overall ratingbar L136 · FAQ 3 L145. They agree with the dek, the lede, `SoftwareApplication.description`, the caption-3 screenshot *[vendor screenshot: one spare per active inbox]* and the vendor today. `every domain` / `each domain` / `inbox/domain` = **0** on the page. |
| **C2** | Pricing table's first tier started at 1, below the vendor minimum | OPEN | **CLOSED.** The table tier now starts at the vendor minimum = vs-row = `Offer.description` = vendor tier range. |
| **C3** | Dedicated-server minimum: live-chat figure vs the vendor page's much higher figure; title mixing the shared-tier $X price with dedicated | OPEN | **Title half CLOSED:** the title now ties the $X per-inbox price to a shared server, agreeing with the meta (*"offering shared servers"*) and with the $X tier. **Body half OPEN by editorial decision:** *[dedicated available from the live-chat minimum on request]* vs the vendor's agency page *[a much higher figure]*, now sourced in body L35 *"(per their live chat)"* as well as in caption 4. |
| C4 | "Private infrastructure" names both the default and the upgrade | OPEN | **OPEN, declined** (heading change not taken). |
| **C5** | Warmup: absolute vs scoped | OPEN | **CLOSED where approved:** FAQ 3 (the `FAQPage` unit) now *[scopes the no-warmup statement to your sending inboxes]*. **Residual, as approved (FAQ 3 only):** KT Risk L24 *[lists no warmup, no placement tests and no domain-health alerts]* and Overall ratingbar L137 *[lists no warmup, placement or monitoring]* still drop the "sending inboxes" scope. The Cons H3, VfM ratingbar, vs-row and FAQ 3 all carry it. Recorded for awareness only. |
| C6 | Swap presented without its cap | OPEN | **Half CLOSED.** The cap is on the page and in `FAQPage` (FAQ 5). Pros H3 3 *[states the swap without the cap]*. |
| C7 | Receipt scope (campaign work, March 2026) | OPEN | **OPEN, declined** (P3-8). |
| C8 | The publisher's `[note]` scope claim about the publisher's own service, incl. domains | OPEN | **CLOSED by editorial decision.** Confirmed as written; not an open contradiction. |
| C9 | Vendor homepage changed after research (a new warm-up tracker; a per-inbox backup card) | watch | **Declined note.** Watch at go-live. |
| C10 | FAQ 4 omits backup domains | OPEN | **OPEN, declined.** |

## Fact-check: the new How opener and the two new sourced claims

| Item | Verdict | Evidence |
|---|---|---|
| The inserted How opener *[entity-led three-step setup summary]* | **Verified** | The vendor's how-it-works screenshot (opened): *[vendor screenshot showing the same three numbered steps: pick domains, one run builds everything, export in the sending tool's import format]*. It restates caption 1 as a `<p>`, which does no harm. |
| FAQ 5 swap cap *[a share of the plan swappable per fixed period]* | **Verified, verbatim** | Vendor homepage FAQ *[the backup-inbox question]*, same-day homepage capture, October 2026. |
| L35 *"(per their live chat)"* | **Consistent** | Caption 4 *[the author's note that live chat quoted the dedicated minimum on request]* and the disclosure, which names live chat as a source. It conflicts with the vendor's public agency page (C3, open by editorial decision). |

---

## Scoring sheet (v2)

| # | Dimension | W | v1 | **v2** | Weighted | What moved, and what did not |
|---|---|---|---|---|---|---|
| **A1** | Central-entity salience | 3 | 4.5 | **4.5** | **13.5/15** | Entity count 38 -> 49, now in all 7 FAQ questions and every non-template opener except Pricing. **Unchanged docks (both declined):** (a) `#vendor` stub and no company/founder in prose (P3-3) **−0.25**; (b) `tool-a.example` never printed as a domain, against three documented SERP namesakes (P3-4) **−0.25**. |
| **A2** | Citation-ready architecture | 3 | 3.25 | **4.75** | **14.25/15** | **Closed:** (a) **HARD #3** (**+0.75**); (b) half: How now opens on an entity-led `<p>` (**+0.125**; hidden on phones, N1); (c) all five subject-less units (**+0.375**); (d) all 7 FAQ questions name the entity (**+0.25**). **Still docked:** (b) `Tool A Pricing` has no sentence (P3-1 declined) **−0.125**; (e) receipts in 1 of 3 required sections, structural **−0.125**. |
| **A3** | Query fan-out & attributes | 2 | 4.0 | **4.375** | **8.75/10** | **Closed:** (b) the swap cap is on the page and in `FAQPage` (**+0.25**); (d) half: FAQ 5 and 6 are standalone via their questions (**+0.125**). **Still docked (all declined):** (a) no domain price (P3-1) **−0.25**; (c) no legitimacy layer (P3-3) **−0.25**; (d) FAQ 2 still a one-line price answer *[$X per inbox per month; cheaper at scale]* (P3-6) **−0.125**. |
| **A4** | Entity homing & link graph | 2 | 4.25 | **4.5** | **9.0/10** | **Closed:** (b) `reverse DNS` and `domain monitoring` homed, 200, body prose, each path once (**+0.25**). **Still docked:** (a) review-to-review links = 0 by standing house rule, policy, not a fix **−0.5**. *Hold, not docked:* now 5 glossary links on a URL base that a planned URL restructure may move. |
| **A5** | Schema / @id readiness | 2 | 4.75 | **4.75** | **9.5/10** | Re-validated in full on the live `<head>`: everything in the facts table passes, `FAQPage` re-synced byte-for-byte, and the `Offer.description` / table disagreement (C2) is gone. **Unchanged dock:** `#vendor` stub (P3-3 declined) **−0.25**. |
| **A6** | Author E-E-A-T | 1 | 4.5 | **4.75** | **4.75/5** | **Closed:** (a) the dedicated-minimum claim is sourced in the body (L35) (**+0.125**); (d) the visible *"setup time.."* typo (**+0.125**). **Still docked:** (b) receipt date/scope uncaveated (P3-8 declined) **−0.125**; (c) thin evidence base, structural **−0.125**. |
| **A7** | Classic on-page | 1 | 3.75 | **4.5** | **4.5/5** | **Closed:** (b) 0 en dashes (**+0.25**); (c) Verdict suffix (**+0.25**); (d) meta 157 (**+0.125**); (e) dek 148 (**+0.125**). **Still docked:** (a) depth ~1,358 vs the ~2,000 floor, ~32% under (P3-9 declined) **−0.5**. Clean: single H1, 11 H2 / 12 H3, 11/11 anchored, title 55 in band, 0 house banned-terms hits, 0 unrendered shortcodes, real alt text. |
| | **TOTAL** | **14** | 57.50 | | **64.25/70 -> 91.79 -> 92/100** | **exceptional (85-100)** · **0 HARD** · **PASS** |

**Bar: >=70 AND 0 HARD failures. This page scores 92 with 0 HARD failures. PASS on both halves.**

---

## v1 -> v2 delta

| Dim | W | v1 | v2 | Δ | Weighted Δ (/100) | Driver |
|---|---|---|---|---|---|---|
| A1 | 3 | 4.5 | **4.5** | 0 | 0 | (both docks declined) |
| A2 | 3 | 3.25 | **4.75** | +1.5 | **+6.43** | P1-1 (+0.75) · P2-3 (+0.375) · P2-1 + P2-2 (+0.25) · P3-5 (+0.125) |
| A3 | 2 | 4.0 | **4.375** | +0.375 | **+1.07** | P3-2 (+0.25) · P2-1 (+0.125) |
| A4 | 2 | 4.25 | **4.5** | +0.25 | **+0.71** | P2-9, P2-10 |
| A5 | 2 | 4.75 | **4.75** | 0 | 0 | (dock declined) |
| A6 | 1 | 4.5 | **4.75** | +0.25 | **+0.36** | P3-7 via L35 (+0.125) · P2-4 (+0.125) |
| A7 | 1 | 3.75 | **4.5** | +0.75 | **+1.07** | P2-5 (+0.25) · P2-6 (+0.25) · P2-7 (+0.125) · P2-8 (+0.125) |
| **HARD** | | **1** | **0** | | | P1-1 |
| **TOTAL** | 14 | **82** (57.50) | **92** (64.25) | | **+9.64** | |

**Against the v1 prediction.** v1's per-fix lifts for the applied set: P1-1 +3.21 · P2-1 +0.89 · P2-2 +0.54 · P2-3 +1.61 · P2-4 +0.18 · P2-5 +0.36 · P2-6 +0.36 · P2-7 +0.18 · P2-8 +0.18 · P2-9 +0.36 · P2-10 +0.36 · P3-2 +0.71 · P3-5 +0.54 · P3-7 +0.18 = **+9.86 on paper, +6.75/70 = +9.64 on the exact arithmetic**. Actual: **+6.75/70**. Nothing over-delivered and nothing under-delivered. Two notes:
- **P3-7** was taken as the L35 no-coupling alternative. It sources the claim at its first statement (About), while the Cons H3 2 unit *[dedicated servers start at the live-chat minimum]* still carries no in-unit source. I credit the full +0.125, because the A6 dock was "the body never says so", and the body now does.
- **Depth** moved ~35% -> ~32% under. *Scorer's call:* not enough to step the dock down from −0.5.

---

## Applied items, checked on the render

| Item (approved) | Rendered evidence (v2) | Landed |
|---|---|---|
| P1-1 + P2-4, L52 | *[entity-led setup sentence]* … *"exact setup time."*; DNS-pillar anchor intact and still first | yes |
| P2-1 (question side), L150, L153 | *[FAQ question on a burned-out Tool A inbox]* · *[FAQ question on refunds from Tool A]* in accordion + `FAQPage` | yes |
| P2-2, L147, L156 | *"…do I need for Tool A?"* · *"…if I leave Tool A?"* | yes |
| P2-3, L31 / L48 / L75 / L119 / L130 | *"Tool A's sending server…"* · *[with Tool A, a free backup inbox per inbox bought]* · *"…to Tool A if…"* · *[Tool A's typical response time]* · *"…not included with Tool A."* + vs-row evidence re-synced | yes |
| P2-5 (build-side) | `&#45;` at L33, L37, L114, L132 x2; renders *"conditions -"*, *"downsides -"*, *"via -"*, *"for you - setup … management - then"*; 0 en dashes | yes |
| P2-6, L127 | `<h2 id="the-verdict">The Verdict [house rating suffix]</h2>` | yes |
| P2-7, L5 | meta 157 = `WebPage.description` = Open Graph = social card | yes |
| P2-8 (deletion), L9 | dek/excerpt 148: *[now ends on the need to warm your own sending inboxes]* | yes |
| P2-9, L56 | *"reverse DNS"* -> the reverse-DNS glossary entry (200) | yes |
| P2-10, L132 | first *"domain monitoring"* -> the domain-monitoring glossary entry (200) | yes |
| P3-2, L151 | FAQ 5 answer + `FAQPage.mainEntity[4]` carry the swap cap (a share of the plan per fixed period) | yes |
| P3-5 (INSERT) | How `<p>`, entity-led, inside the mobile-hide class | yes (hidden on phones) |
| P3-7 alt, L35 | *[the dedicated-server minimum, sourced "(per their live chat)"]* | yes |
| C1, L22 / 47 / 48 / 60 / 69 / 88 / 136 / 145 | all per inbox; L60 ends *"keep sending."* | yes |
| C2, L80 | table tier now starts at the vendor minimum | yes |
| C3 title, L3 | `<title>` *[Tool A review, year, $X per inbox on a shared server]* (55) | yes |
| C5, L145 | *[no-warmup statement scoped to your sending inboxes]* | yes |
| L58 | *"puts only N inboxes per domain"* | yes |
| C8 | `[note]` unchanged, as ruled | yes (no change) |

---

## New issues the edits introduced (none docked)

| # | Issue | Points | Detail |
|---|---|---|---|
| N1 | How opener hidden on phones | 0 (house) | The opener sits in the mobile-hide class (`display:none` at <=767px), with the whole section and its 4 captions. Credited in full, as on the Competitor 1 review v2. Raw-HTML retrievers read it; a phone-viewport render does not. |
| N2 | *"spare inbox with each inbox"* wording | 0 | L60 and L69, the two ratingbars (*"with each/every inbox"*) and FAQ 3 (*"with every inbox"*) all pair a free warmed-up spare inbox with each inbox. Correct and consistent, but an extracted line reads close to a tautology. Approved wording; noted only. |
| N3 | The dek no longer carries a con | 0 | The P2-8 deletion took *[the no-monitoring / no-alerts clause]* out of the dek. The KT, Cons, vs-row and meta (*"shared servers"*, *"domains cost extra"*) still carry the cons. |
| N4 | C5 and C6 residuals | 0 | See the contradictions table: KT Risk L24 and Overall ratingbar L137 (warmup scope); Pros H3 3 (swap cap). |
| N5 | Final sign-off: strike-or-keep on the How opener | (risk) | If the How opener is struck: A2 −0.125 -> **63.875/70 = ~91.3, still PASS**. No schema coupling: the opener has no schema mirror. |

---

## Remaining points (all declined by editorial decision, ceiling only)

No open fixes remain. Every unapplied item was declined and is **not re-proposed**; this table records only what each was worth.

| Declined item | Dim | Value (/70 · /100) |
|---|---|---|
| P3-3 identity sentence + `#vendor` | A1, A3, A5 | +1.75 · +2.50 |
| P3-1 Pricing opener with domain prices | A2, A3 | +0.875 · +1.25 |
| P3-4 print `tool-a.example` once | A1 | +0.75 · +1.07 |
| P3-9 depth to ~2,000 | A7 | +0.5 · +0.71 |
| P3-6 richer FAQ 2 answer | A3 | +0.25 · +0.36 |
| P3-8 receipt date/scope line | A6 | +0.125 · +0.18 |
| P2-1 answer-side alternative | (either/or with the applied question side) | 0 · 0 |
| C4 heading change · C10 FAQ 4 backup domains · C9 note | contradictions, not scored | 0 · 0 |
| **Declined total** | | **+4.25 · +6.07** |

**Structural docks (never fixes):** A4 review-to-review links −0.5 (1.43) · A2 receipts in 1 of 3 sections −0.125 (0.54) · A6 thin evidence base −0.125 (0.18).
**Ceiling: 64.25 + 4.25 = 68.50/70 = ~98.**

---

## House rulings respected (NOT docked)

- **Ratings locked** 2.5 / 2.5 / 3.5 / 2 / 1.5; arithmetic as in v1.
- **Review-to-review links = 0:** A4 −0.5 taken once, never a fix.
- **Verbatim rule:**
  - Every author-prose change sits in the approved-edits file keyed by source line, with old/new/why, and asserts its `old` string.
  - The source file is unchanged.
  - The one new sentence is logged separately as an insert.
  - Dash and Verdict-hyphen handling is build-side (`&#45;`), so the source characters stay verbatim.
- **No links in headings, shortcode bodies or the vs-table.** The two new links sit in body prose (Pros H3 1 paragraph, Verdict P3).
- **C8 confirmed by editorial decision:** not docked, not open.
- **Origin hedged:** nothing added about the vendor's origin; P3-3 was declined.
- **House banned-terms list: 0 hits.** No publisher price, guarantee, refund claim or internal-tool mention was added.
- **House mechanics, as in v1:** the `Private:` H1 prefix, the mobile duplicate lede, the mobile-hidden How section, and the hand-written vs-table as the CTA block's swap anchor.

## Method notes (scorer's calls, unchanged from v1 unless stated)

1. Contradictions are kept **out of the score**, per the scoring brief, so the v1 -> v2 movement owes nothing to C1/C2/C3/C5 closing.
2. A1(b) stays at −0.25 (namesake risk documented in this SERP), now a declined item.
3. A7 depth stays at −0.5. *Changed evidence:* ~35% -> ~32% under, which I judged too small to step the dock (see the delta notes).
4. Excerpt band ~155 (house band from the Competitor 1 review). The dek is now 148, so this no longer docks.
5. A6(a) was a dock for the missing in-body source of the dedicated-minimum claim. L35 closes it; the live-chat-vs-vendor-page conflict itself stays unscored (C3).

## Go-live housekeeping (not scored)

**Final sign-off:** decide strike-or-keep on the How opener (N5; there is no schema coupling).

**After the flip:**
- Confirm anonymous 200.
- Confirm `robots` = index,follow and a self-canonical (the private render carries `noindex, follow` and no canonical).
- Confirm review-sitemap inclusion.
- Confirm exactly 1 `ld+json` block (the save hook rewrites `dateModified` on save, which is expected).
- Run a cache-plugin flush **and** a CDN purge, then a Search Console inspection.

**Watch:** the vendor's homepage changed after research (C9: the new warm-up tracker), so re-read it if the page is revisited.

---

# v1 scorecard (October 2026, superseded by the v2 re-score above; condensed for the record)

Original v1 header line: `Pass: live · Score: 82/100 (57.50/70) · strong (70-84) · FAIL (1 HARD blockers)`

**v1 evidence:** the v1 private render and its verify report. The Trustpilot permalink returned 403 to curl and a bot wall to the scraping tool (2 attempts); it was resolved via an SEO-data API in September 2026.

**v1 HARD:** #3 FAIL, Features H3 `Automated Setup` opened *"They handle the setup…"* (L52). All other six criteria PASS.

**v1 scoring sheet:**

| Dim | W | v1 score | Weighted | v1 docks |
|---|---|---|---|---|
| A1 | 3 | 4.5 | 13.5 | `#vendor` stub / no identity −0.25 · domain never printed vs SERP namesakes −0.25 |
| A2 | 3 | 3.25 | 9.75 | HARD #3 −0.75 · 2 prose-less H2s −0.25 · 5 subject-less units −0.375 · FAQ 4/7 questions without entity, FAQ 5/6 entity-free −0.25 · receipts 1 of 3 −0.125 |
| A3 | 2 | 4.0 | 8.0 | no domain price −0.25 · no swap cap −0.25 · no legitimacy layer −0.25 · FAQ 5/6 not standalone + FAQ 2 thin −0.25 |
| A4 | 2 | 4.25 | 8.5 | review-to-review policy −0.5 · `reverse DNS` / `domain monitoring` orphans −0.25 |
| A5 | 2 | 4.75 | 9.5 | `#vendor` stub −0.25 |
| A6 | 1 | 4.5 | 4.5 | dedicated-minimum claim sourced only in a phone-hidden caption −0.125 · receipt scope/date −0.125 · thin evidence base −0.125 · *"setup time.."* −0.125 |
| A7 | 1 | 3.75 | 3.75 | depth ~35% under −0.5 · 5 en dashes −0.25 · no Verdict suffix −0.25 · meta 161 −0.125 · excerpt 191 −0.125 |
| **Total** | 14 | | **57.50/70 = 82** | **1 HARD · FAIL** |

**v1 fix-list outcome (editorial decision, October 2026):**
- **Applied:** P1-1, P2-1 (question side), P2-2, P2-3 (x5), P2-4, P2-5 (build-side), P2-6, P2-7, P2-8 (deletion), P2-9, P2-10, P3-2, P3-5, P3-7 (L35 alternative). Plus the C1, C2, C3-title and C5 fixes, and L58 / L119 wording.
- **Declined:** P3-1, P3-3, P3-4, P3-6, P3-8, P3-9, the P2-1 answer-side alternative, the C4 heading change, C10, the C9 note.
- **Confirmed as written:** C8.
- The exact old/new text of every applied edit lives in the approved-edits file.
