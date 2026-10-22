# AEO Scorecard — Example 02: inbox-provider review
*Anonymised: the publisher, the reviewed tool, competitors, people, prices and quotes are replaced with placeholders.*

**Node:** `overview/tool-a` · **Target:** `publisher.example/review/tool-a/` (`status: private`)
**Article:** the review draft (markdown)
**Contract:** the review outline (v4) + the canonical review outline
**Artifacts:** the converted review body (HTML) · the custom-fields payload (JSON) (71 blocks, 8 FAQs, 4 quotes, conversion OK)
**Reviewer:** `aeo-reviewer` · **Run 2** · July 2026

> **RUN 2: 77.1 / 100 — STRONG — ✅ PASS (0 HARD blockers)**
> Run 1: 54.3 / 100 — DEVELOPING — FAIL (1 HARD blocker). **Delta +22.8.**

---

## Run 1 → Run 2 delta

| Dim | Run 1 | Run 2 | Δ | Why it moved |
|---|---|---|---|---|
| A1 salience ×3 | 4 (12) | **5 (15)** | +3 | Byline component resolved; 64 entity mentions (was 50). **The row most open to challenge — see note below.** |
| A2 citation-ready ×3 | 3 (9) | **4 (12)** | +3 | 4 verbatim receipts placed; L142 contradiction fixed; 4 of 5 entity-less openers anchored. |
| A3 fan-out ×2 | 2 (4) | **3 (6)** | +2 | FAQs 4→8; no-API, the guarantee conflict, the cancellation dead link and the company facts are now on the page. |
| A4 links ×2 | 3 (6) | **3 (6)** | 0 | **No link work was done.** 6 internal links unchanged, orphans unchanged, density slipped to 5.1/1,000 as the article grew. |
| A5 schema ×2 | 2 (4) | **4 (8)** | +4 | `author→Person` now resolvable (verified at source); FAQ #4 truncation fixed at the converter; 8 complete FAQ payloads. |
| A6 E-E-A-T ×1 | 0 (0) | **4 (4)** | +4 | **HARD blocker cleared.** Real Person with real credentials. Off 5 only for the missing sourcing line. |
| A7 on-page ×1 | 3 (3) | **3 (3)** | 0 | +28% length is real, but still under the word floor and the Verdict H2 still lacks the house rating suffix. |
| **TOTAL** | **38/70 · 54.3** | **54/70 · 77.1** | **+16 / +22.8** | |

**Byline verified independently, not taken on assertion.** `GET /wp/v2/review/<id>?context=edit` → `"author"` set to a real user; `GET /wp/v2/users/<id>` → the byline author's name and bio [author bio quote supporting founder-of-the-publisher status, client experience and an outreach-industry credential]. The author page returns **200**, and a sibling review already binds `author` → `publisher.example/about/author/#person`. Same binding, same pattern. Confirmed.

**On A1 (4→5), the one row I'd defend least.** Every component the scorecard enumerates for A1 is now satisfied — entity in the first 100 words, byline, repeated naturally, H1/dek naming it. My run-1 dock had two causes; one is fixed, one is not (the opener still defines Tool A in the **past tense** [opener: a past-tense definition of Tool A's service category], L43, so the present-tense definition waits until L64). I scored to the rubric's literal components and logged the reservation rather than dock for something I am deliberately **not** prescribing, because fixing it means touching the locked first sentence. **The verdict does not hinge on this:** at A1=4 the total is 51/70 = **72.9, still PASS**. Push back on this row if you disagree; it changes the number, not the outcome.

---

## Scoring sheet — Run 2

| # | Dimension | W | Score | Weighted | Evidence |
|---|---|---|---|---|---|
| **A1** | Central-entity salience | 3 | **5** | **15**/15 | "Tool A" is word 2 (L43) and appears **64×** in 1,815 words; carried by H1, meta title, slug, dek (L45), **9 of 11 H2s**, and now a resolved byline. Reservation logged: past-tense opener. |
| **A2** | Citation-ready architecture | 3 | **4** | **12**/15 | First-answer intact (L43–45 + L51 BLUF + L53 ratings row). **4 named, permalinked receipts**, one in each of the four sections the outline mandates. Contradiction resolved at L142. New FAQ atoms are excellent: [FAQ atom: a direct "no" on API availability, naming Tool A] (L242), [FAQ atom: the published guarantee figure is not contractual] (L245). Off 5 for the FAQ #2 pronoun opener and quotes that sit beside claims rather than tied to them. |
| **A3** | Query fan-out & attributes | 2 | **3** | **6**/10 | FAQs **4→8**; no-API, the ToS-revokes-the-guarantee finding, the cancellation dead link (+$X receipt) and the founding-year/revenue facts are all now on the page. Still absent: the **two-product spine**, shared-IPs-no-dedicated-option as a Cons H3, mailboxes-per-domain, sending limits, the legal/security gap. **Body Cons still 3 H3s vs the outline's 11.** The gain came almost entirely from the FAQ block. |
| **A4** | Entity homing & link graph | 2 | **3** | **6**/10 | 6 internal links, all 200, up+across wired — **unchanged**. +5 outbound Trustpilot permalinks is a genuine verifiability gain. But orphans are untouched (**SPF/DKIM/DMARC** L95, Sequencer 1 L107, a marketing-automation platform, a CRM, Competitor 1), the publisher's price table still has no `/pricing` link, and density **fell** to 5.1/1,000 because the article grew and the link count did not. |
| **A5** | Schema / @id readiness | 2 | **4** | **8**/10 | `author→Person` resolvable ✓ · `about→Tool A` via custom fields ✓ · 5 `reviewRating` dims ✓ · **8 FAQs with complete answers**, FAQ #4's dropped `<ul>` fixed at the converter (custom-fields payload L98) ✓ · body ends on the FAQ H2 ✓. Off 5: no JSON-LD written yet, and `mentions[]`/DefinedTerm are still nowhere enumerated. |
| **A6** | Author E-E-A-T | 1 | **4** | **4**/5 | **Blocker cleared.** The byline author, credential-bearing bio, the page builder's author box, Person `@id` live. L47 [a first-person ownership disclosure] and the Excerpt's [first-person research claim] now resolve to a named founder. Off 5: **no sourcing line** in the lede, which canonical part 2 requires and which is the highest-value E-E-A-T sentence on a review node. |
| **A7** | Classic on-page | 1 | **3** | **3**/5 | Single H1 ✓, 11 H2 / 24 H3 clean ✓, anchors resolve ✓, meta 56/153 in band ✓, **zero em/en dashes** ✓. **1,168 prose + 144 quoted = 1,815 words** (+28%) but still under the 2,000–3,800 floor, and **Pros/Cons/Pricing/How-It-Works/Verdict are unchanged in length** — the growth is all FAQ and quotes. Verdict H2 still missing the house rating suffix (rating 4). |
| | **TOTAL** | **14** | | **54 / 70 → 77.1 / 100** | |

**Grade band: STRONG (70–84).**

---

## HARD criteria — Run 2

| # | Criterion | Result | Evidence |
|---|---|---|---|
| 1 | Central entity in first 100 words | **PASS** | "Tool A" is word 2 (L43); 4 occurrences in the first 100. |
| 2 | First-answer block near the top | **PASS** | Lede L43–45 + BLUF L51 + ratings row L53, all above the first H2. |
| 3 | No section opens on a bare vague pronoun | **PASS** (see note) | All 31 section openers checked again mechanically. Exactly one is pronoun-initial: **FAQ #2, L227**, an answer opening on a bare **"It"** [about shared IPs]. Ruled **not** a HARD fail because in an FAQPage the citable unit is the Q/A pair and the H3 above it [a question naming **Tool A** and asking whether it uses shared or dedicated IPs], so the entity does lead the extraction unit. Recorded as an A2 deduction with a one-line fix (P1-1). **Disclosure: run 1 did not scrutinise the FAQ openers — this is a newly-caught item in unchanged text, not a regression.** |
| 4 | Author attributed to a real Person | **PASS** (was FAIL) | The post's `author` field → the byline author, verified via the REST API in `context=edit`. Person page 200. |
| 5 | Single H1 | **PASS** | Exactly one `#` (L41); HTML body carries zero H1. |
| 6 | Every followed outbound link is intended | **PASS** | The one competitor link, `tool-a.example`, is `rel="nofollow noopener noreferrer"` (body HTML L22). The other 7 outbound URLs are all `trustpilot.com` — an evidence source, not a competitor — and the 3 markdown ones carry nofollow in the custom-fields payload (L94, L110). The 4 `[quote]` shortcode URLs pass through verbatim, so their `rel` is set by the shortcode renderer; confirm once at publish (P2-6). |

## **HARD blockers: NONE.**

---

## On the two deliberate non-fixes

**1. FAQ #9 "best Tool A alternative" — I agree with the hold, and your reasoning is better than my fix was.** Shipping it would have baked a contradiction about *the publisher's own service* into schema-eligible content. **But holding the FAQ does not contain the problem.** The shipped body already asserts it: L165 [a factual claim about the publisher's own service] conflicts with what the outline (§10) states about the same service. That sentence is live, one step from publish, and it is the one making the claim. Escalate it to the SEO lead as **"L165 may be wrong about the publisher's own service"**, not as "we deferred an FAQ." Promoted to P2-2 below.

**2. Legacy rate card — accepted, and I am withdrawing my run-1 fix as written.** I asked for the card inside a section that says pricing is call-gated, which would indeed have read as a contradiction. That was my error of shape, not yours. The residual AEO gap is also smaller than I claimed: FAQ #1 [current pricing is not public and is quoted only after a sales call] is already an honest, extractable answer to the query. **Downgraded from P1 to P3.** If the SEO lead ever authorises it, the correct framing is the outline's own [Tool A's only published rate card sits in an older help article], which is a **finding about pricing opacity**, not a price list, and does not contradict the call-gated line.

---

## Remaining fix-list

### P1 — the only substantive one

**1. FAQ #2 (L227) — pronoun opener on the weakest answer of the eight.**
Now: [an answer opening on a bare "It": shared IPs were used, but the method under the vendor's new service model is undefined]. Two problems in one line: the bare "It", and an evasive answer sitting among seven sharp ones. Both fix together using facts already on this page (KT L56) and in the outline:

> [Proposed answer: (1) a lead sentence naming Tool A and stating it uses shared IPs; (2) Tool A's help documentation states its IPs are pooled across customers and no dedicated-IP option exists; (3) the hedge: Tool A has not published how that changes under its new service model.]

Names the entity, keeps the hedge intact, and imports the shared-IP attribute the body still lacks — the single highest-value sentence available for one line of work.

### P2 — before publish

**2. Resolve the conflict about the publisher's own service at L165** (the body vs the outline). Not an AEO item; it is a claim about the publisher's own service and it is what blocked FAQ #9. Fix it and FAQ #9 unblocks itself.
**3. Verdict H2 → `## The Verdict` + the house rating suffix (rating 4).** Required by house rule, one edit, and a rating in a heading is a strong extractable signal.
**4. Orphan entities — untaken from run 1.** SPF/DKIM/DMARC (L95) is the strongest unlinked concept-entity on the page; Sequencer 1 (L107) shares a sentence with an already-linked Sequencer 2; the publisher's price table (L173–180) has no `/pricing` link. Wrapping existing words only — no new sentences. This is the only row that scored zero movement while the article grew.
**5. Sourcing line in the lede** (canonical part 2, currently absent). Would also let the page state plainly that no G2 rating is cited because G2 was blocked by bot protection, which the pre-publish check's audit already records.
**6. Publish-time schema.** Hand-write the `@graph` to the stored schema field via mysqli (review-CPT schema is **not** auto-emitted); `review` on **SoftwareApplication**, not BlogPosting; `operatingSystem` on every `mentions[]` SoftwareApplication; bind `author` → `publisher.example/about/author/#person`. Confirm the `[quote]` renderer emits `rel="nofollow noopener noreferrer"`.

### P3 — observations, not blocking

**7. Depth.** 1,168 words of reviewer prose against the 2,000–3,800 floor. Worth naming that the +28% came from FAQs and quotes while **every body section is unchanged in length** — the page a buyer actually reads did not grow.
**8. The two-product spine** remains the outline's self-declared "single biggest differentiator" and is still one clause in the lede. The outline's final check ("visible in Introduction, About, How It Works, Features, Pricing, Support, Verdict and FAQ") is unmet. Not blocking a PASS; it is the largest unclaimed info-gain left on the node.

---

## Verdict

### ✅ PASS

**77.1 / 100 · STRONG · 0 HARD blockers.** Clears the ≥70 publish bar on both conditions.

The fixes did what they were supposed to do and were verified at source rather than accepted on report: the byline resolves to a real credentialed Person the rest of the review corpus already uses, the four mandated receipts are placed with permalinks in exactly the four sections the outline names, the self-contradiction is gone, and the converter's list-dropping bug was fixed at source rather than patched in the payload.

Two rows deliberately did not move. **A4 got no work at all** — the link graph is identical to run 1 while the article grew 28%, so density fell. **A7 is still under the word floor**, and the growth landed in FAQs and quotes rather than the body. Neither blocks publish; both are the honest reading of where this node still sits against its own contract.

Nothing on the remaining list requires new prose, and nothing asks for a stylistic change to the locked draft.
