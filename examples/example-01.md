# AEO Scorecard — Example 01: inbox-provider review
*Anonymised: the publisher, the reviewed tool, competitors, people, prices and quotes are replaced with placeholders.*

**Run:** Pass 1 (pre-go-live, on the private review bytes — internal links + JSON-LD stored)
**Page:** publisher.example/review/tool-a/ (status: private)
**Central entity:** Tool A · **Representative query:** "Tool A review"
**Date:** August 2026

## Scoring sheet

| # | Dimension | Weight | Score (0–5) | Weighted | Evidence |
|---|---|---|---|---|---|
| A1 | Central-entity salience | 3 | 4 | 12/15 | "Tool A" is in H1, the byline, and every H2 (About/Features/Pricing/Support/Verdict/Alternative). It lands inside the first 100 words (sentence 2: [a sentence positioning Tool A as a multi-inbox provider, set against other providers]). One crisp central entity. Held at 4 because sentence 1 opens on a generic hook ([opener: a generic hook about diversification]) rather than the entity itself. |
| A2 | Citation-ready architecture | 3 | 4 | 12/15 | Key Takeaways block (summary + 5-dim ratings + 6 stat-bullets) is a strong first-answer near the top. Sections lead with the entity/attribute, not vague pronouns. Paragraphs are short and mostly one-fact. Minor: the opener is a context hook; the crisp definition sits in KT + About rather than sentence 1. |
| A3 | Query fan-out & attribute coverage | 2 | 4 | 8/10 | Covers intent (About: what it is), comparison (the publisher's comparison table + price/mailbox breakdown), use-case + pain (Verdict, Cons), and how/why PAA (5 FAQs: warmup after N days, monitoring/burn, BYOD, shared-pool safety of the vendor's shared-SMTP product, is-$X-cheap-for-a-reason). All required inbox-provider attributes present (inbox types, pricing, warmup, monitoring, support, setup, BYOD, shared-pool). Independent-data angle is thin (no G2/Trustpilot/Reddit trail exists for this tool — a stated fact, not a gap in coverage). |
| A4 | Entity homing & link graph | 2 | 4 | 8/10 | 4 internal links home concept-entities to hubs: the publisher's own tool page, the infrastructure pillar, a warmup-tools roundup, and the homepage (up + across). No followed in-body competitor link (outbound tool-a.example anchor not added; custom-field visit button only). Could add 1 sibling-review cross-link (in go-live list). |
| A5 | Schema / @id readiness | 2 | 5 | 10/10 | 12-node @graph stored + valid, every @id resolves. author→Person (the byline author), WebPage→about→SoftwareApplication (applicationCategory BusinessApplication, operatingSystem Web), standalone Review w/ reviewRating 2 + itemReviewed, FAQPage(5), BreadcrumbList(3), 4 ImageObjects. Review sits on SoftwareApplication (not BlogPosting) — both recurring rich-result bugs avoided. Emits in-head on go-live (page currently private). |
| A6 | Author E-E-A-T | 1 | 5 | 5/5 | Attributed to a real Person entity, the byline author (@id byte-matches schema Person; jobTitle set to a founder-level title; sameAs LinkedIn). First-person operator authority + explicit competitor disclosure. Not "Team" or the content-ops owner. |
| A7 | Classic on-page | 1 | 4 | 4/5 | Single H1 (CPT title), logical H2/H3 nesting, SEO-plugin title distinct from H1 (54c) + metadesc 127c, slug /review/tool-a/, TOC anchors resolve. Slightly light on prose depth (deliberately concise; acceptable — no competing reviews to be thin against). |
| | **TOTAL** | **14** | | **59/70 → 84/100** | |

## Result

**AEO score: 84/100 — STRONG** (70–84 band). Publish bar (≥70) cleared.

### HARD criteria (must-pass)
1. Central entity in first 100 words — ✅ (sentence 2, ~word 26)
2. First-answer / direct-answer block near top — ✅ (Key Takeaways)
3. No section opens on a bare vague pronoun — ✅
4. Author attributed to a real Person — ✅ (the byline author)
5. Single H1 — ✅
6. Every followed outbound link intended — ✅ (no in-body competitor outbound; booking link + internal links all intended)

**0 blockers.**

### Optional lifts (not required to pass)
- A1 → 5: open sentence 1 with the entity ([a one-line definition: Tool A as a multi-inbox reseller of Google, Microsoft and shared-infrastructure inboxes]) before the diversification hook.
- A3/A7: a short line naming the independent-data gap (no G2/Trustpilot/Reddit trail) would add a differentiating fact + attribute depth.
- A4 → 5: one inbound/outbound cross-link to a sibling review (e.g., Competitor 1 / Competitor 2).
