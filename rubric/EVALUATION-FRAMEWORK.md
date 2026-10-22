# The Entity-SEO / AI-Search Content-Plan Scorecard
### A reusable "parameter" to evaluate ANY content plan for entity SEO, knowledge-graph, and LLM-citation readiness

Derived from *AI Search & LLMs — Entity SEO and Knowledge Graph Strategies for Brands (2026)*, all 6 chapters. Use it to score a content plan **before** it ships and to re-audit quarterly.

---

## How to score

- **9 dimensions**, each scored **0–5** (the course's own schema-quality scale), then multiplied by a weight.
- **Weighted total out of 100.** The weights reflect where the course puts emphasis: roughly half on content architecture (D1–D3) and half on entity infrastructure + brand authority + citation ops (D4–D9), because "structure alone doesn't get you cited."

**0–5 scale (applied per dimension):**
| Score | Meaning |
|---|---|
| **5** | Best-in-class. Systematic, complete, automated, measured. |
| **4** | Solid. All essentials + most recommended practices; minor gaps. |
| **3** | Adequate. Minimum viable; recommended practices missing. |
| **2** | Minimal. Partial/ad-hoc; real gaps. |
| **1** | Broken/token. Present in name only. |
| **0** | Absent. Not in the plan at all. |

**Grade bands:** 85–100 exceptional · 70–84 strong · 55–69 adequate · 40–54 developing · <40 content-only (ignores the AI-search layer).

---

## The 9 dimensions

### D1 — Central Entity & Ontology Definition — weight ×3
*Is there ONE clearly declared central entity and an ontological core the whole plan hangs off?*
- [ ] Single central entity declared (not a fuzzy topic); "ontological core" of fundamental, unchanging concepts defined (Ch2 L7).
- [ ] Entity catalogue across the 6 categories: organization, leadership/people, products/services, locations, events, concepts (Ch3 L2/L3).
- [ ] Industry-appropriate priority set (corporate → leadership+products; service → location+expertise) (Ch3 L1).
- [ ] EAV coverage: each entity's required attributes/predicates defined (Ch1 L2; Ch3 L10).

### D2 — Entity Coverage, Salience & Audit — weight ×2
*Does the plan measure how machines currently see the site's entities and fix gaps first?*
- [ ] Top-10 pages run through **Google NLP API**; primary/brand entity salience **>0.5** on its own pages (Ch2 L3/L4).
- [ ] **Competitive entity gap analysis** (3–5 competitors) (Ch2 L4).
- [ ] **Zero orphan entities**; every entity mention links to a definitive hub (Ch2 L4).
- [ ] The 5 killer gaps checked: missing primary entity, ambiguity, no related entities, mislabeled type, orphan (Ch2 L5).
- [ ] "Fix before building schema" sequencing respected (Ch2 L4).

### D3 — Query Fan-Out & Citation-Ready Content Architecture — weight ×2
*Is content shaped so LLMs can retrieve and quote it?*
- [ ] **7 query-variation categories** covered (name, intent, comparison, use-case, location, industry, pain-point) (Ch2 L6).
- [ ] **Hub-and-spoke / pillar→cluster→FAQ** with cross-linking (Ch2 L6/L7).
- [ ] Citation-ready writing: exact entity names early, **one verifiable fact per paragraph**, related entities named, no vague pronouns (Ch2 L6).
- [ ] **First-answer / featured-snippet shape** + FAQ with entity-rich answers (Ch2 L7).
- [ ] Citation-readiness test applied pre-publish (Ch2 L7).

### D4 — Schema & Knowledge-Graph Infrastructure (@id graph) — weight ×3
*Is there a connected entity graph, not just isolated schema blocks? This is the course's biggest lever.*
- [ ] JSON-LD entity graph using **`@id` references** (define once, reference everywhere) — not disconnected per-page schema (Ch3 L4/L5).
- [ ] **6 relationship patterns** wired (CEO→org, product→org, article→author, article→topic, org→audience, org→location) (Ch3 L4).
- [ ] **Bidirectional links** (A→B ⇒ B→A) (Ch5 L5).
- [ ] Persistent **ID URL namespace** (e.g. `data.site.com/person/…`) (Ch3 L10).
- [ ] Schema types beyond Article/FAQ: Organization, Person, Product/Service, Place, Event, Concept/DefinedTerm (Ch3 L3).
- [ ] Relationships planned **before** content is written (Ch3 L10).

### D5 — Knowledge-Graph Presence & Multi-Source Fact Validation — weight ×2
*Does Google/LLM-land actually know this entity exists, corroborated by multiple sources?*
- [ ] Brand entity checked in **Google KG API** (has KG ID; confidence >1,000) (Ch2 L3).
- [ ] Knowledge-panel status checked (incognito) (Ch3 L8).
- [ ] Core facts (**tuples**) validated across **≥2 authoritative sources** — the KG inclusion bar (Ch4 L2).
- [ ] Path to **Wikidata/Wikipedia** entry (notability build if not yet eligible) (Ch2 L6; Ch3 L10).
- [ ] KG popularity score used to prioritize entities in the map (Ch4 L3).

### D6 — Cross-Platform Entity Distribution & Consistency — weight ×2
*One entity, identical representation, everywhere.*
- [ ] **`sameAs`** to LinkedIn, Wikidata, GBP, industry directories, speaker/author profiles (Ch5 L6; Ch6 L4).
- [ ] **Canonical name + identical property formats** across all pages AND platforms (Ch5 L5; Ch6 L7).
- [ ] **Google Business Profile** matching the KG (even for remote/software brands) (Ch6 L4).
- [ ] Person entities (founders/experts) distributed + optimized, not just the org (Ch6 L3/L4).

### D7 — Brand Authority & Co-Citation for LLMs — weight ×2
*Is authority being actively engineered, or left to chance?*
- [ ] **5–7 canonical brand statements** used verbatim everywhere (category, "Unlike…", quantified benefit, precise audience, authority claim) (Ch6 L2).
- [ ] **8–10 target attributes**, each with a systematic content ecosystem (Ch6 L2).
- [ ] **Competitive LLM intelligence**: reverse-engineer top-10 authorities LLMs already cite (Ch6 L5).
- [ ] **Co-citation** plan (comparison/roundup content + genuine community participation) (Ch6 L5).
- [ ] **1 strategic partnership/quarter** (integration, co-content, joint case study) (Ch6 L5).
- [ ] Every content piece **attributed to a person entity** w/ author schema (Ch6 L3/L7).

### D8 — Measurement, Monitoring & LLM-Citation Tracking — weight ×1.5
*Is success measured on entity + citation terms, not just rankings?*
- [ ] **4-layer measurement**: technical validity → entity recognition (NLP confidence >0.85) → LLM citation score (5 Qs, 3/2/1/0) → business impact (Ch3 L8).
- [ ] **Manual LLM citation testing** weekly (10 core queries on ChatGPT/Claude/Copilot; track who's cited) (Ch6 L6).
- [ ] Graph-health metrics: entity count, relationship density, orphans, schema completeness (Ch6 L6).
- [ ] Branded-query tracking (top-20, position→top-3, CTR) + AI-Overview inclusion (Ch6 L6).
- [ ] Trend-based (not daily); alerts on failure (Ch2 L6).

### D9 — Governance, Maintenance & Scale — weight ×0.5
*Will it survive contact with a growing site without a "hero"?*
- [ ] **Maintenance cadence**: immediate (≤1 hr) / weekly / monthly / quarterly defined (Ch5 L7).
- [ ] **Zero-tolerance schema validation** in the workflow; **validation before production** (Ch3 L8; Ch6 L1).
- [ ] **Distributed ownership** + automated pipeline from a central entity registry — no hero dependency (Ch6 L1).
- [ ] Expansion gate: don't scale new entities until core hits **>95% validity + LLM recognition** (Ch3 L7).

---

## Scoring sheet

| # | Dimension | Weight | Score (0–5) | Weighted |
|---|---|---|---|---|
| D1 | Central Entity & Ontology | 3 | | /15 |
| D2 | Entity Coverage, Salience & Audit | 2 | | /10 |
| D3 | Query Fan-Out & Citation-Ready Architecture | 2 | | /10 |
| D4 | Schema & KG Infrastructure (@id graph) | 3 | | /15 |
| D5 | KG Presence & Multi-Source Validation | 2 | | /10 |
| D6 | Cross-Platform Distribution & Consistency | 2 | | /10 |
| D7 | Brand Authority & Co-Citation | 2 | | /10 |
| D8 | Measurement & LLM-Citation Tracking | 1.5 | | /7.5 |
| D9 | Governance, Maintenance & Scale | 0.5 | | /2.5 |
| | **TOTAL** | **18** | | **/100** |

> Rule of thumb from the course: a plan can score well on D1–D3 (content) and still fail in AI search if D4–D8 (entity infrastructure + authority + citation ops) are empty — "structure alone doesn't get you cited; you must activate entities across the web."
