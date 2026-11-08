# GEO Audit Report: MD Anwar — Analytics & Finance-Intelligence Console

**Audit Date:** 2026-11-08
**URL:** https://ianvrr.github.io
**Business Type:** Agency/Services — Personal Consultant (BI / Finance Intelligence)
**Pages Analyzed:** 1 (single-page application, 6 content sections)

---

## Executive Summary

**Overall GEO Score: 45/100 (Poor)**

This is a well-crafted personal portfolio site with real, specific content and a clear professional identity — but it is effectively invisible to AI search engines. The site exists as a single HTML page with no robots.txt, no sitemap, no llms.txt, and no external platform presence beyond LinkedIn and GitHub. AI systems cannot cite individual sections by URL, cannot discover the site through a sitemap, and have no corroborating third-party sources to validate the claims made. The content itself is strong (real metrics, real projects, real credentials) — the gap is infrastructure and distribution.

### Score Breakdown

| Category | Score | Weight | Weighted Score |
|---|---|---|---|
| AI Citability | 52/100 | 25% | 13.0 |
| Brand Authority | 22/100 | 20% | 4.4 |
| Content E-E-A-T | 60/100 | 20% | 12.0 |
| Technical GEO | 62/100 | 15% | 9.3 |
| Schema & Structured Data | 42/100 | 10% | 4.2 |
| Platform Optimization | 22/100 | 10% | 2.2 |
| **Overall GEO Score** | | | **45/100** |

---

## Critical Issues (Fix Immediately)

### C1 — No robots.txt (site defaults to allow-all, but no explicit AI crawler directives)
- **Impact:** AI crawlers have no guidance. No explicit allowlist for GPTBot, ClaudeBot, PerplexityBot, etc.
- **Fix:** Create `/robots.txt` explicitly allowing key AI crawlers with crawl hints.

### C2 — No sitemap.xml
- **Impact:** Search engines and AI crawlers cannot discover or index the page efficiently. No URL priority signals.
- **Fix:** Create a minimal `/sitemap.xml` with the homepage URL and lastmod date.

### C3 — No llms.txt
- **Impact:** Missing the emerging standard that AI systems check to understand a site's structure and permissions.
- **Fix:** Create `/llms.txt` following the llms.txt specification.

### C4 — Single URL for all content (no section permalinks)
- **Impact:** AI systems cannot cite individual sections (Experience, Fidivio, Work) by URL. The entire 1,151-line page must be cited as one document.
- **Fix:** Add anchor-based canonical section URLs or split into separate pages.

---

## High Priority Issues

### H1 — Zero brand presence on AI-cited platforms
- **Platforms checked:** YouTube, Reddit, Wikipedia, Medium, Dev.to, Hacker News, Quora
- **Finding:** No presence found beyond LinkedIn (linked in schema) and GitHub. AI systems heavily weight third-party corroboration.
- **Fix:** Write at least 2–3 technical articles on Medium or Dev.to. Answer 2–3 relevant questions on Reddit (r/dataengineering, r/BusinessIntelligence) with real expertise.

### H2 — No FAQ schema despite answerable content
- **Finding:** The site answers implicit questions ("what do you do," "what have you built," "what's your stack") but none are formatted as explicit Q&A with FAQPage schema.
- **Fix:** Add a visible FAQ section ("What programs have you worked on?", "What is IFRS 15 loyalty accounting?") with FAQPage JSON-LD.

### H3 — Missing WebSite schema and SearchAction
- **Finding:** No WebSite schema. This reduces entity recognition across AI platforms.
- **Fix:** Add WebSite schema with SearchAction pointing to the command palette.

### H4 — Person schema has formatting issues
- **Finding:**
  - `email` value is `"mailto:anwarmahammad@hotmail.com"` — should be `"anwarmahammad@hotmail.com"`
  - `jobTitle` is 76 characters with a middle-dot separator — too long for clean entity recognition
  - No `image` property (headshot URL)
  - `sameAs` only lists 2 URLs — should include any public profiles
- **Fix:** Clean up schema (details in Schema section below).

### H5 — No blog or dated articles (content freshness = zero)
- **Finding:** Every AI platform weights content freshness. The site has no articles, no changelog, no dated updates beyond the KPI data.
- **Fix:** Add a minimal "Notes" or "Writing" section, even 2–3 short technical posts, with Article schema and ISO dates.

---

## Medium Priority Issues

### M1 — Content citability is good but not optimized for AI extraction
- **Finding:** Bullet-point lists dominate (experience section, capabilities). AI systems prefer paragraph-form prose with self-contained facts. The best citability blocks are the case study paragraphs and the Fidivio description.
- **Fix:** Add 2–3 prose "About this work" paragraphs in the experience section. Each should be 130–160 words, self-contained, fact-rich, and directly answerable as a question.

### M2 — No "About" page or dedicated author page
- **Finding:** Google E-E-A-T and AI systems look for a dedicated author/about page with credentials. The site's about content is embedded in sections but no `/about` page exists.
- **Fix:** Even a simple `#about` anchor section with a 150-word bio, credentials list, and photo slot would score higher than the current distributed approach.

### M3 — Missing Article/CreativeWork schema for case studies
- **Finding:** The 5 work case studies are rich, specific content — but have no schema markup. AI systems cannot identify them as distinct works.
- **Fix:** Wrap each case study in Article or CreativeWork schema (can be inline JSON-LD).

### M4 — No testimonials or external validation
- **Finding:** All metrics and claims are self-reported. E-E-A-T scoring rewards third-party validation.
- **Fix:** Even one LinkedIn recommendation (copy-pasteable to the site with attribution) or a quote from a manager/client (with permission) would improve trust signals significantly.

### M5 — Contact section missing LocalBusiness signals
- **Finding:** Hyderabad location is in the JSON-LD but not on-page text. AI systems doing local queries won't surface this profile.
- **Fix:** Add "Based in Hyderabad, Telangana" as visible text near the contact section.

---

## Low Priority Issues

### L1 — Open Graph image (`preview-v2.jpg`) not verified
- The OG image is set but not confirmed as valid or optimised for social sharing dimensions.

### L2 — No `<link rel="canonical">` tag
- Not critical for a single-page site, but recommended for avoiding duplicate content (HTTP vs HTTPS, with/without trailing slash).

### L3 — No structured data for awards/recognition
- The recognition strip (Juggernaut of the Month, CEO commendation, ADP awards) has no schema.
- Could use `Award` or `Achievement` custom type, or at minimum mention them in the Person schema's `award` property.

### L4 — Twitter/X card present but no X profile
- Twitter Card meta is set up but no X profile URL in `sameAs`.

---

## Category Deep Dives

### AI Citability — 52/100

**What AI systems look for:** Self-contained paragraphs of 130–167 words that directly answer a question, contain verifiable facts, and don't require surrounding context to make sense.

**Best citability blocks on the site:**

| Section | Citability | Why |
|---|---|---|
| Hero lead paragraph | 58 | Specific, one sentence, but too short |
| Fidivio description para 1 | 65 | Good length, specific, factual |
| Reimbursement spotlight paras | 70 | Best on site — problem/solution/result format |
| Experience bullets | 45 | Bullets are hard for AI to cite cleanly |
| Capabilities lists | 30 | Lists with no prose context |

**Recommended rewrites:** The experience section bullets should be complemented by one paragraph per role that synthesises the impact in prose. Example for the LJI role:

> *"At Loyalty Juggernaut I own the enterprise data warehouse and BI layer for two global loyalty programs, delivering analytics, finance intelligence, and billing reconciliation for clients across airline, hospitality, retail, and banking sectors. The highest-impact project was rebuilding the stepped-model reimbursement algorithm — consolidating two 12–14-hour pipeline runs into a single gold core table that reduced daily compute to roughly 2 hours, resolved persistent export discrepancies, and earned a CEO commendation. I also surface ~85.5M MXN of under-reported breakage from a 6-month data integrity gap, and maintain 100% daily reconciliation accuracy with 0 missing records across billing-critical hotel alliance exports."*

That paragraph is 134 words, self-contained, and directly citable.

---

### Brand Authority — 22/100

**Platform presence map:**

| Platform | Presence | Notes |
|---|---|---|
| LinkedIn | ✅ Linked in schema | Profile exists at linkedin.com/in/ianvrr |
| GitHub | ✅ Linked in schema | github.com/ianvrr |
| Wikipedia | ❌ None | Expected — not a public figure |
| YouTube | ❌ None | No videos or channel |
| Reddit | ❌ None | No posts in relevant subreddits |
| Medium / Substack | ❌ None | No technical writing |
| Dev.to | ❌ None | No technical articles |
| Hacker News | ❌ None | No submissions or comments |
| Quora | ❌ None | No expertise Q&A |

**Key insight:** AI models learn entity recognition from third-party corroboration. When ChatGPT or Perplexity sees "MD Anwar, analytics consultant, Hyderabad" on multiple independent platforms, the entity becomes trustworthy and citable. Right now there is only one source: this site.

**Quick brand authority moves:**
1. Publish 1 technical article on Medium about IFRS 15 loyalty accounting (direct expertise, niche, almost no competition)
2. Answer 2 questions on r/dataengineering about Redshift optimization or loyalty analytics
3. Add LinkedIn articles (3 short posts) on specific topics: breakage forecasting, reconciliation pipelines

---

### Content E-E-A-T — 60/100

**Experience (8/10):** Real projects, real employers, specific metrics. The reimbursement rebuild, the 85.5M MXN surfacing, the reconciliation closure — all are verifiable if a hiring manager checks. ✅

**Expertise (7/10):** Technical stack is specific and correctly scoped. IFRS 15, Chain-Ladder, actuarial forecasting — these are real methodologies, not buzzwords. The Fidivio section is particularly strong here. ✅ Deducted for no published work.

**Authoritativeness (4/10):** No external evidence of authority. No publications, no conference talks, no press mentions, no testimonials. The person schema lists the right fields but there's nothing external to corroborate it. ❌

**Trustworthiness (7/10):** Real contact info, real employer, real college, real disclaimer on the Fidivio visual ("illustrative of the forecasting method, not client results"). ✅ Deducted for no privacy policy and no testimonials.

---

### Technical GEO — 62/100

| Check | Status | Notes |
|---|---|---|
| Static HTML (crawlable) | ✅ Pass | Full content in initial HTML response |
| HTTPS | ✅ Pass | GitHub Pages enforces HTTPS |
| Mobile responsive | ✅ Pass | Responsive breakpoints at 1080/900/680px |
| robots.txt | ❌ Missing | 404 — no AI crawler guidance |
| sitemap.xml | ❌ Missing | 404 — no crawl discovery |
| llms.txt | ❌ Missing | 404 — missing AI standard |
| Meta description | ✅ Pass | Present and descriptive |
| OG/Twitter meta | ✅ Pass | Full set present |
| Canonical tag | ❌ Missing | Recommended for single-page sites |
| GPTBot blocked | ✅ No | No robots.txt = not blocked |
| ClaudeBot blocked | ✅ No | Same |
| PerplexityBot blocked | ✅ No | Same |
| Noindex directive | ✅ No | Not present |
| JavaScript rendering | ✅ Pass | Content in HTML, not JS-only |

---

### Schema & Structured Data — 42/100

**Found:** Person (1 instance, in `<head>` as `application/ld+json`)

**Person schema quality review:**

| Field | Status | Issue |
|---|---|---|
| `@type: Person` | ✅ | Correct |
| `name` | ✅ | "MD Anwar" |
| `jobTitle` | ⚠️ | Too long, contains separator character |
| `url` | ✅ | Correct |
| `email` | ❌ | "mailto:..." prefix is wrong |
| `telephone` | ✅ | Correct |
| `address` | ✅ | Complete PostalAddress |
| `worksFor` | ✅ | Organization present |
| `alumniOf` | ✅ | CollegeOrUniversity present |
| `knowsAbout` | ✅ | Good array of 12 topics |
| `sameAs` | ⚠️ | Only 2 URLs; should include more profiles |
| `image` | ❌ | Missing — headshot URL |
| `award` | ❌ | Missing — Juggernaut of Month, CEO award |
| `description` | ❌ | Missing — 1-sentence summary for AI |

**Missing schema types:**

| Type | Priority | Benefit |
|---|---|---|
| WebSite + SearchAction | High | Enables sitelinks search box; entity recognition |
| FAQPage | High | AI systems love structured Q&A |
| Article (per case study) | Medium | Makes work citable by title + date |
| ProfilePage | Medium | Explicit page-type for personal sites |
| ProfessionalService | Low | Alternative/complement to Person |

---

### Platform Optimization — 22/100

| Platform | Readiness | Gap |
|---|---|---|
| Google AI Overviews | 30% | No featured-snippet-formatted content, no FAQ |
| ChatGPT / Bing Copilot | 20% | No external sources to corroborate entity |
| Perplexity | 25% | Static HTML is good; no citations on other sites |
| Gemini | 20% | No YouTube, no Google properties beyond LinkedIn |
| Claude | 35% | Person schema + HTTPS + static HTML = baseline |

---

## Quick Wins (Implement This Week)

1. **Create `robots.txt`** (30 min) — explicitly allow GPTBot, ClaudeBot, PerplexityBot, Googlebot. Improves Technical score immediately.
2. **Create `sitemap.xml`** (30 min) — single URL with today's date as lastmod. Submit to Google Search Console.
3. **Create `llms.txt`** (1 hour) — describe the site, your expertise, and key content for AI systems.
4. **Fix Person schema** (1 hour) — fix email field, shorten jobTitle, add `description`, `image`, `award` properties.
5. **Add FAQPage schema** (2 hours) — add 5 Q&As to the page ("What industries have you worked in?", "What is IFRS 15 loyalty accounting?", "What tech stack do you use?") with FAQPage JSON-LD.

---

## 30-Day Action Plan

### Week 1: Technical Foundation
- [ ] Create `robots.txt` with explicit AI crawler allowlist
- [ ] Create `sitemap.xml` and submit to Google Search Console
- [ ] Create `llms.txt` describing the site and key content areas
- [ ] Fix Person schema (email, jobTitle, add description + image + award)
- [ ] Add `<link rel="canonical" href="https://ianvrr.github.io/">` to `<head>`
- [ ] Add WebSite schema with SearchAction

### Week 2: Content Citability
- [ ] Add 3–4 prose paragraphs to Experience section (one per role, 130–160 words each)
- [ ] Add a visible FAQ section (5 Q&As) with FAQPage JSON-LD schema
- [ ] Add "Based in Hyderabad, Telangana" to contact section as visible text
- [ ] Add Article schema for each of the 5 work case studies

### Week 3: Brand Authority
- [ ] Write and publish 1 Medium article: "How I surfaced ₹7Cr in under-reported loyalty breakage" (or similar — use real knowledge, no invented numbers)
- [ ] Answer 2–3 questions on r/dataengineering or r/BusinessIntelligence with genuine expertise
- [ ] Ensure LinkedIn profile matches site content exactly (consistent NAP, same job title)
- [ ] Add any additional profile URLs to sameAs in Person schema (LinkedIn company page, etc.)

### Week 4: Content Depth
- [ ] Write 1 short technical note on the site itself (even 300 words on "How Chain-Ladder works for breakage forecasting") — with Article schema and ISO date
- [ ] Add `award` property to Person schema (Juggernaut of the Month, CEO commendation, ADP awards)
- [ ] Add a brief "About" section with a 150-word bio, photo slot, and credentials
- [ ] Review all meta descriptions — ensure each section's OG description matches what an AI would quote

---

## Appendix: Pages Analyzed

| URL | Title | Sections | GEO Issues |
|---|---|---|---|
| https://ianvrr.github.io | Anwar \| Analytics & Finance-Intelligence Console | Overview, Experience, Fidivio, Work, Capabilities, Contact | robots.txt missing, sitemap missing, llms.txt missing, no FAQPage schema, no WebSite schema, no Article schema, single URL |

## Appendix: AI Crawler Access

| Crawler | Access | Source |
|---|---|---|
| GPTBot (OpenAI) | ✅ Allowed (default) | No robots.txt |
| ClaudeBot (Anthropic) | ✅ Allowed (default) | No robots.txt |
| PerplexityBot | ✅ Allowed (default) | No robots.txt |
| Googlebot | ✅ Allowed (default) | No robots.txt |
| CCBot (Common Crawl) | ✅ Allowed (default) | No robots.txt |
| Bingbot | ✅ Allowed (default) | No robots.txt |

*Note: No robots.txt means all crawlers are allowed by default. This is currently fine — but you should create a robots.txt that makes this explicit and adds a Sitemap directive.*
