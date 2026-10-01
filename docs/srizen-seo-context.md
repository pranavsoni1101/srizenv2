# Srizen SEO Context for Claude Code (v3, updated 1 Oct 2026)

Place this file in the repo root (or merge into CLAUDE.md). Claude Code must read it fully before making any SEO change. Items marked [CONFIRM] still need the owner's input and must not be treated as fact.

---

## 1. Business context (confirmed)

- **Brand:** Srizen
- **What it is:** A UX/UI-led web and app development studio run by Pranav (sole operator)
- **Domain:** `https://srizen.com` (canonical: https, non-www, no exceptions)
- **Stack and hosting:** Next.js on Vercel, styled with Tailwind CSS
- **Services Srizen wants to be found for (final list):**
  1. **Web design and web development** (Pranav's core skillset, so these are PRIMARY keyword targets, UX/UI-led)
  2. **SaaS development for clients** (building SaaS products and SaaS marketing sites for clients). Srizen does NOT offer its own SaaS product at the moment (that needs R&D), so never describe one.
  3. **Technical consulting**
  4. **SEO improvements**
  5. **Website maintenance and care plans** (the searchable name; keeping sites and codebases maintainable, fast and secure)
- **Public case study approved:** TSAR Perfumes only (Shopify theme development for an Indian DTC fragrance brand). No other client may be named, linked or given results in new content.
  - **Owner-supplied result (publishable):** Rebuilt the cart and checkout flow around observed drop-off points, taking checkout completions from 15 to 27 per 100 add-to-carts within two weeks, with no increase in ad spend.
  - **Arithmetic check:** 15 to 27 is an 80% increase ((27-15)/15), not 75%. [CONFIRM] Owner to confirm the correct figures. Until then publish only the raw numbers (15 to 27 per 100 add-to-carts) and do NOT print a percentage.
  - Keep the claim exactly as supplied: no added metrics, revenue figures or testimonials.
- **Legal and business status:**
  - Pranav holds an ABN as a sole trader in his own name. The ABN is NOT registered under Srizen.
  - Registering "Srizen" as a business name under his ABN is pending.
  - Until that is done: do not write "ABN", "Pty Ltd", "registered business" or "trading as Srizen" anywhere (copy, footer, schema, directory listings). After registration, the owner will supply the exact wording.
  - No publishable street address or service area. So: no LocalBusiness schema, no address, no `areaServed` claims, no Google Business Profile, no "Canberra" location pages. City-level mention is approved: the About page may say the founder is based in Canberra, Australia (city only, never a street address).
- **Strategic goal:** Build Australian industry credibility, then scale from India with global reach. Do not imply an Australian office or Australian-registered clients.
- **Budget:** Near zero for marketing. All tactics must be free or very low cost. Organic and AI-search visibility are the main channels.

## 2. Baseline (Google Search Console, last 12 months to 30 Sep 2026, web search)

| Metric | Value |
|---|---|
| Clicks | 55 |
| Impressions | 799 |
| CTR | about 6.9% |
| Best month (impressions) | Sep 2026 (119 impressions, 8 clicks) |

**Key findings (these drive the priorities below):**
1. **Almost all visibility is branded.** The query "srizen" accounts for 35 clicks and 374 impressions. There is effectively no non-brand discovery yet, so the real work is earning visibility for service queries.
2. **Brand collision.** "srizen cleaning" (24 impressions) and misspellings ("srijen") show Google is unsure what Srizen is. Entity clarity (Organization schema, consistent description, `sameAs` links, clear homepage H1 and title) is a high priority.
3. **Duplicate hostnames are indexed.** `https://srizen.com/` and `https://www.srizen.com/...` both appear (the www version holds /about, /srizen-effect, /showcase, /contact, and even a www home page). This splits signals and conflicts with the chosen non-www canonical. Fixing this is Task 1.
4. **Geography:** India 35 clicks / 431 impressions; Australia 9 clicks / 30 impressions (30% CTR, strong but tiny); United States 4 clicks / 128 impressions (3.1% CTR, a gap worth closing); Malaysia 78 impressions with 1 click.
5. **Pages:** Home 50 clicks. `/about` has 337 impressions but 0.89% CTR (likely appearing as a brand sitelink, check the title and description). `/srizen-effect` 140 impressions. `/showcase` 90 impressions with no clicks. `/contact` 34 impressions with no clicks.
6. **Devices:** Mobile has more impressions (472) than desktop (322) but a lower CTR (4.9% vs 9.6%). Check mobile snippets and mobile page experience.
7. **Existing public showcase pages** exist for Ascent Industrial and a personal portfolio. Leave them as they are. Do not expand them, add schema or results to them, or promote them until the owner confirms client approval.

Claude Code must store this baseline in `SEO_LOG.md` and compare against it every month. Do not extrapolate or forecast traffic numbers.

## 3. SEO objectives

1. Fix technical and entity foundations so Google and AI engines understand exactly what Srizen is.
2. Rank for service-intent queries around the core services (web design and development first), starting with long-tail terms where a new site can realistically win.
3. Convert visits into emails (primary), contact form submissions (secondary), and call bookings (tertiary).
4. Earn visibility in AI answer engines (Google AI Overviews, ChatGPT, Perplexity, Claude) through citable, factual content.
5. Use Srizen's own site as proof of work: publish its real Core Web Vitals and SEO practices.

## 4. Keyword strategy (starting framework, validate with data)

Claude Code must not invent search volumes or difficulty scores. Use only Search Console data, Keyword Planner, or exports the owner provides. Otherwise label ideas as unverified.

**Clusters, one per service (web design and development are primary):**
- **Web design and development (primary):** UX/UI-led web design, custom web development, Next.js web development, Shopify development, website redesign, web design for small business
- **Technical consulting:** Next.js consultant, technical consulting for startups, web architecture review, website performance audit
- **SaaS:** SaaS web app development, SaaS UX design, MVP development with Next.js, SaaS marketing site design
- **SEO improvements:** technical SEO for Next.js, Next.js SEO audit, Core Web Vitals optimisation, SEO for startups and small businesses
- **Website maintenance:** website maintenance plans, Next.js maintenance, codebase refactoring, technical debt cleanup
- **Brand protection:** "srizen", "srizen web studio", "srizen agency" (own these results and disambiguate from unrelated "Srizen" uses)

**Rules:**
- One primary keyword and 2 to 4 secondary keywords per page. No two pages share a primary keyword.
- Transactional terms go on service pages, informational terms on guides.
- Prefer long-tail, specific queries first. Competing for broad terms like "web design agency" is not realistic yet.

## 5. Technical SEO standards (non-negotiable)

### 5.1 Hostname, crawlability, indexation
- **301 redirect `www.srizen.com` to `srizen.com`** (set the primary domain in Vercel so the www host redirects, and force https). One hop only, no chains.
- Every canonical, `og:url`, sitemap entry and schema `url` uses `https://srizen.com/...`. Set `metadataBase: new URL('https://srizen.com')`.
- In Search Console, verify as a Domain property, submit `https://srizen.com/sitemap.xml`, and use URL Inspection to request reindexing of key pages after the redirect is live.
- Valid `robots.txt` that allows crawling, references the sitemap, and blocks only non-public paths (API routes, preview deployments).
- Generate `sitemap.xml` with `app/sitemap.ts`. Include only canonical, indexable, 200-status URLs with honest `lastmod`.
- `noindex` for thank-you pages and any internal search. Block Vercel preview deployments from indexing (`X-Robots-Tag: noindex` on non-production) so they never compete with production.
- Custom 404 page that returns a real 404 status and links to key pages.

### 5.2 Next.js and Tailwind specifics
- Use the Metadata API (`metadata` / `generateMetadata`) for per-page title, description, canonical, Open Graph and Twitter cards.
- Use Server Components and static generation (SSG/ISR) for marketing pages so full content is in the initial HTML. Never hide primary content behind client-only rendering.
- `next/image` with explicit dimensions, AVIF/WebP and accurate `sizes`. Use `priority` only on the LCP image.
- `next/font` with `display: swap`, subsetting and few weights.
- Dynamic OG images via `opengraph-image.tsx`.
- Tailwind: confirm the production build purges unused CSS, avoid shipping large unused component libraries, and keep client JavaScript small (audit with `@next/bundle-analyzer`).
- Load analytics with `next/script` (`afterInteractive` or `lazyOnload`). Keep third-party scripts to a minimum.

### 5.3 Performance and Core Web Vitals (75th percentile, mobile)
- **LCP** under 2.5s, **INP** under 200ms, **CLS** under 0.1.
- Run Lighthouse and PageSpeed Insights on the homepage and each service page before and after changes. Aim for 90+ on Performance, Accessibility, Best Practices and SEO. Field data (Search Console CWV report) outranks lab data when they disagree.
- Publish Srizen's own real scores on the site once achieved (credible proof for the SEO and consulting services).

### 5.4 Mobile, security, accessibility
- Mobile-first, correct viewport meta, tap targets of at least 44px. Mobile CTR is currently lower than desktop, so review mobile titles, descriptions and above-the-fold content.
- HTTPS with HSTS and sensible security headers via `next.config` or `vercel.json`.
- WCAG 2.2 AA: landmarks, one `<h1>` per page, logical heading order, alt text, visible focus, contrast, labelled form fields.

### 5.5 URL structure
Short, lowercase, hyphenated, no parameters on indexable pages. Proposed structure:
- `/services/web-design`
- `/services/web-development`
- `/services/saas-development`
- `/services/technical-consulting`
- `/services/seo-improvements`
- `/services/website-maintenance`
- `/work/tsar-perfumes` (the only case study, pending approved results)
- `/blog/[slug]`
- `/about`, `/contact`
- Existing URLs (`/about`, `/contact`, `/showcase`, `/srizen-effect`) already have impressions. Never change or delete an existing indexed URL without a 301 redirect to the closest replacement.

## 6. On-page SEO standards

For every page Claude Code must produce and verify:
- **Title:** 50 to 60 characters, primary keyword first, brand last ("| Srizen"). Unique.
- **Meta description:** 140 to 160 characters, benefit-led, with a call to action. Unique.
- **H1:** exactly one, matches intent, includes the primary keyword naturally.
- **Heading hierarchy:** logical H2/H3, using question-style headings where they match real queries.
- **Intro:** answer the core query in the first 100 words.
- **Internal links:** 3 to 8 contextual links with descriptive anchors. No orphan pages, everything within 3 clicks of home.
- **Images:** descriptive filenames, alt text, compressed.
- **Open Graph and Twitter Card:** title, description, 1200x630 image.
- **CTA:** the primary CTA is **email** (a visible `mailto:hello@srizen.com` link with the address shown as text). Secondary is the contact form. Tertiary is call booking. Show the email prominently on every service page and in the footer.
- **Content depth:** service pages roughly 800 to 1,500 words of useful, specific content. Usefulness over length.
- **Neobrutalist design and SEO (the site theme is neobrutalism):** keep keyword-led, searchable wording in the `<title>`, H1, H2s and body text, and put playful or punchy brand lines in a separate styled element (a tagline, badge or sub-heading), never as the only H1. Example: H1 "Website Maintenance and Care Plans" with a decorative tag line "Keep it alive. Keep it fast." Heavy borders, hard shadows and bold colours must keep WCAG 2.2 AA contrast, visible focus states, and must not cause layout shift (reserve sizes, no late-loading display fonts). Text must be real HTML text, never baked into images.
- **Homepage:** the H1, title and first paragraph must state plainly what Srizen is ("UX/UI-led web and app development studio" plus its core services: web design, web development, SaaS development, technical consulting, SEO improvements and website maintenance) to resolve brand ambiguity.

## 7. Structured data (JSON-LD)

Implement as JSON-LD, validate with Google's Rich Results Test and the Schema Markup Validator. Mark up only content visible on the page. Never fabricate reviews, ratings, awards or addresses.

- **Organization** (homepage): `name`, `url` (https://srizen.com), `logo`, a clear `description`, `founder` (Person), `sameAs` (see below), `contactPoint` (email: hello@srizen.com). **No address, no legal name, no ABN.**
- **Person** (Pranav): `name`, `jobTitle`, `url`, `sameAs`, `alumniOf` / `knowsAbout` only with facts the owner confirms.
- **WebSite:** `SearchAction` only if real site search exists.
- **Service** on each service page: `name`, `description`, `provider` (Organization), `serviceType`. Omit `areaServed` until a service area is confirmed.
- **BreadcrumbList** on all non-home pages.
- **Article / BlogPosting** on blog posts with real author and dates.
- **FAQPage** only where a visible FAQ exists.
- **CreativeWork** for the TSAR Perfumes case study only (only the owner-supplied result, see section 1).
- **Review / AggregateRating:** skip unless real, verifiable, on-page reviews exist.
- **Do not use** LocalBusiness or ProfessionalService with address fields.

**What `sameAs` is:** a list inside the Organization/Person schema containing the URLs of Srizen's and Pranav's official profiles elsewhere on the web (for example LinkedIn, GitHub, Instagram, Behance, Clutch, X). It tells Google and AI engines "all of these profiles are the same entity as this website", which is one of the strongest free ways to fix the brand confusion with "srizen cleaning". It must list only real profiles that exist and are controlled by the owner. [CONFIRM] Owner to supply the URLs (candidates: personal site pranavsoni.com, LinkedIn, GitHub, Instagram, Behance/Dribbble, Clutch). Until supplied, omit `sameAs` rather than guessing.

## 8. Content and E-E-A-T strategy

- Show real experience: the TSAR Perfumes case study (problem, process, design decisions, tech, real results with approval).
- Author bylines with a real bio for Pranav and links to his profiles.
- About, Contact, Privacy and Terms pages. Be transparent about how Srizen works.
- **Content pillars (mapped to services):**
  1. Next.js technical SEO and Core Web Vitals (supports SEO improvements, technical consulting)
  2. SaaS website and web app UX (supports SaaS)
  3. Keeping a Next.js codebase maintainable (supports maintainability)
  4. Practical guides: "how much does website maintenance cost", "Next.js SEO checklist"
- Prefer original, specific, experience-led articles (real audits, before/after numbers from Srizen's own site). No thin or generic AI-written filler. Every article gets human review, sources, a byline and an honest updated date.
- Refresh top pages every 6 to 12 months.

## 9. Visibility on a zero budget (free tactics only)

- **Search engines:** verify Search Console (Domain property) and Bing Webmaster Tools (import from Search Console). Submit the sitemap to both. Bing data also feeds several AI assistants.
- **Entity and profile building:** create or complete consistent profiles (same name, same one-line description, link to srizen.com) on LinkedIn (company page and personal), GitHub (org or profile README), Behance or Dribbble, Clutch and similar free directories. Each one is a `sameAs` candidate.
- **Earned links:** talks and write-ups through GDG ANU and the ANU community, open-source contributions, helpful answers on communities (Reddit, Indie Hackers, Stack Overflow) where genuinely useful and non-spammy, a "built by Srizen" credit in client site footers with the client's permission.
- **International:** no `hreflang` (single English site). Use Australian English on About and pages aimed at Australian visitors, neutral English elsewhere.
- White-hat only. No link buying, PBNs, comment spam or fake reviews.

## 10. AI search and generative engine optimisation (GEO)

- **Policy (confirmed): allow all AI crawlers** for maximum reach. In `robots.txt`, do not block GPTBot, ClaudeBot, PerplexityBot, Google-Extended, Applebot-Extended, CCBot or similar.
- Publish `llms.txt` at the site root summarising Srizen, its core services, and key pages (a low-cost experiment, not a ranking factor).
- Write clear, quotable, factual definitions and summaries at the top of pages. Keep entity naming consistent (Srizen, Pranav, service names) everywhere.
- Keep clean semantic HTML and strong structured data. Cite sources, show authorship and dates.

## 11. Measurement

- **Search Console** (Domain property) and **Bing Webmaster Tools**: submit sitemap, monitor Pages (indexing), Core Web Vitals and Performance.
- **GA4 or a privacy-friendly alternative:** track conversion events in this order of value: `mailto:` link clicks, contact form submits, call booking clicks. Respect consent requirements.
- **Monthly review** against the baseline in section 2: clicks, impressions, CTR, average position, non-brand vs brand queries, indexed pages, CWV pass rate, conversions.
- Export Search Console data monthly into the repo (`/seo/gsc/YYYY-MM/`) so history is not lost to the 16-month window.

## 12. Claude Code operating instructions

**Always:**
1. Audit the repo first (routing, metadata, schema, sitemap, robots, redirects, images, scripts) and summarise findings before changing anything.
2. Produce a prioritised task list (Critical, High, Medium, Low) with reasons.
3. Commit in small reviewable steps with clear messages (for example `seo: redirect www to apex and fix canonicals`).
4. After each batch of changes run build, lint, type check and Lighthouse. Report before and after numbers.
5. Validate structured data and list warnings.
6. Keep `SEO_LOG.md` in the repo (baseline, changes, dates, reasons, measured results). Append, never overwrite.

**Never:**
- Invent statistics, testimonials, awards, results, addresses, ABNs or credentials.
- State or imply that Srizen is a registered business name, company or Australian-registered entity until the owner supplies approved wording.
- Name, link or show results for any client other than TSAR Perfumes in new content.
- Keyword-stuff, hide text, cloak, build doorway pages or break Google Search Essentials.
- Change or remove an indexed URL without a 301.
- Overwrite hand-written copy without flagging it. Propose edits instead.
- Use em dashes in any copy, comments or commit messages. Use commas or hyphens.

**Voice:** clear, confident, human, specific, benefit-led. No jargon piles, no filler.

## 13. First tasks, in order

1. **Hostname fix:** set `srizen.com` as the primary domain in Vercel with www redirecting (301) to it, force https. Verify with `curl -I`.
2. **Canonicals and metadataBase:** every page canonical to `https://srizen.com/...`. Confirm no page canonicals to www.
3. **robots.txt and sitemap.ts:** allow all crawlers (including AI), reference the sitemap, only canonical URLs.
4. **Search Console:** re-submit sitemap, request indexing for home, /about, /contact, /showcase, /srizen-effect. Verify Bing Webmaster Tools.
5. **Homepage entity clarity:** rewrite H1, title, meta description and intro to state what Srizen is and its core services. Add Organization and Person JSON-LD (no address, `sameAs` once URLs are supplied).
6. **Fix `/about` snippet:** it has 337 impressions and 0.89% CTR. Review its title and description.
7. **Service pages:** build the six service pages with unique titles, descriptions, H1s, Service schema, internal links and the email-first CTA.
8. **TSAR Perfumes case study** with approved, real results only.
9. **Performance pass:** Lighthouse and bundle analysis on home and service pages, fix LCP, INP and CLS issues.
10. **`llms.txt`, 404 page, security headers, preview-deployment noindex.**
11. **First two articles** from the content pillars.
12. **Create `SEO_LOG.md`** with the section 2 baseline.

## 14. Deliverables checklist

- [ ] Hostname redirect live, no www URLs indexed
- [ ] Technical audit report with prioritised fixes
- [ ] robots.txt (AI crawlers allowed), sitemap, canonicals, redirects verified
- [ ] Metadata on every page
- [ ] JSON-LD (Organization, Person, Service, BreadcrumbList, Article, case study) validated
- [ ] Core Web Vitals passing on key templates
- [ ] Accessibility pass (WCAG 2.2 AA)
- [ ] Keyword map with one primary keyword per page
- [ ] Six service pages and the TSAR case study live
- [ ] Email-first conversion tracking set up
- [ ] Search Console and Bing connected, baseline logged
- [ ] 90-day content calendar
- [ ] `SEO_LOG.md` maintained

## 15. Remaining open items for the owner

1. Confirm the TSAR result figures: 15 to 27 completions per 100 add-to-carts is an 80% lift, not 75%. Which is correct?
2. URLs for the `sameAs` profiles (LinkedIn, GitHub, Instagram, Behance/Dribbble, Clutch, pranavsoni.com, etc.).
3. Date and approved wording once "Srizen" is registered as a business name.
4. Approve the maintenance service naming (see recommendation in the project notes: searchable name "Website Maintenance and Care Plans" with a neobrutalist display tag line).
