# Study Diaries — SEO Setup & Technical Optimization Case Study

> A self-directed SEO case study on a live website: setting up organic search from zero, diagnosing a critical indexing bug, and auditing/fixing technical issues with Google Search Console and Semrush.

**Live site:** [https://www.studydiaries.org/]

## TL;DR

Study Diaries is a study-abroad information site for Azerbaijani students that I built and optimized from scratch as a personal project to demonstrate technical and on-page SEO skills. Starting from zero organic visibility, I set up Google Search Console and Semrush, found and fixed a `noindex` bug that was hiding the homepage from Google, and cleaned up on-page and technical issues.

| Metric | Baseline | 13–22 Aug 2026 |
|---|---|---|
| Impressions | 1 | 23 |
| Clicks | 0 | 4 |
| CTR | 0% | 17.4% |
| Avg. position | 64 | 24.1 |

<img width="844" height="307" alt="gsc-performance-13-22aug" src="https://github.com/user-attachments/assets/c6966ace-4b0b-4c15-963a-440db4c21f14" />





**Skills demonstrated:** Technical SEO · Google Search Console · Semrush · Indexation Analysis · URL Inspection · XML Sitemaps · On-Page SEO · Hreflang · SEO Troubleshooting · Technical Auditing

---

## Project Overview

- **Focus:** SEO setup, on-page optimization, technical SEO, organic search visibility
- **Platform:** Hostinger AI Builder (manual mode)
- **Tools:** Google Search Console, Semrush, Hostinger AI Builder
- **Status:** Ongoing

### The Challenge

As a newly created website, Study Diaries had no existing organic search visibility or historical performance data. The goal wasn't to chase rankings immediately — it was to build a strong SEO foundation so Google could:

- Discover the website
- Crawl important pages
- Understand the website structure
- Index relevant content
- Begin generating organic search impressions

Shortly after Google Search Console was configured, Google confirmed the site had started receiving search impressions. The baseline was minimal (1 impression, 0 clicks), so rather than treating average position as a meaningful KPI at that stage, I prioritized making sure the site was technically accessible and optimized for future growth.

---

## 1. On-Page SEO Optimization

Implemented directly through Hostinger AI Builder (manual mode):

- **Meta descriptions** — Added page-specific meta descriptions to give search engines clearer context and improve how pages are presented in results, supporting future CTR rather than acting as a direct ranking factor.
- **Image alt text** — Added descriptive alt text across site imagery to improve semantic context, accessibility, and image-search optimization.
- **Internal linking** — Added internal links to CTA elements to connect users with relevant pages, improving navigation for users and crawl pathways for search engines.

---

## 2. Google Search Console Setup

An XML sitemap was submitted and successfully processed:

| Status | Submitted | Last read | Pages discovered |
|---|---|---|---|
| Success | 17 Aug 2026 | 20 Aug 2026 | 7 |

### Diagnosing an indexing issue

An initial audit showed **11 indexed pages** and **10 non-indexed pages**. I reviewed each exclusion type individually to separate legitimate exclusions from real SEO problems — and found a critical issue on the homepage: it was **excluded by a `noindex` tag**.

A live URL inspection confirmed this wasn't stale Search Console data but an active issue:

| | Crawl allowed | Page fetch | Indexing allowed | Reason |
|---|---|---|---|---|
| **Before fix** | Yes | Successful | No | `noindex` detected in robots meta tag |

Google could reach the homepage fine — the site itself was telling Google not to index it. This mattered because the homepage anchors brand discovery, navigation, and internal linking.

**Root cause:** the homepage had been accidentally configured in Hostinger AI Builder as *"Hide page from search results."*

**Fix:** disabled that setting and republished the site.

| | Result |
|---|---|
| **Before** | URL not available to Google — `noindex` detected in robots meta tag |
| **After** | URL available to Google — page can be indexed |

Other pages flagged as *"Crawled — currently not indexed"* were tested individually via live URL inspection and confirmed to be technically accessible with no active indexing restriction.

### Performance impact

| Period | Impressions | Clicks | CTR | Avg. position |
|---|---|---|---|---|
| Initial baseline | 1 | 0 | 0% | 64 |
| 13–22 Aug 2026 | 23 | 4 | 17.4% | 24.1 |

---

## 3. Semrush Technical Audit

Semrush thematic reports showing 100% crawlability, 98% HTTPS, 97% international SEO, 100% Core Web Vitals, 97% site performance, 100% internal linking and markup

<img width="1380" height="359" alt="semrush-thematic-reports" src="https://github.com/user-attachments/assets/49a58c9c-3573-4e7a-80f5-06b65a5c1b6f" />

Initial audit: **95% site health**, 12 pages crawled, 23 warnings, **0 errors or broken pages** — a strong technical foundation. Rather than chasing a 100% score automatically, I investigated each warning individually to separate real SEO problems from low-priority issues, false positives, and platform-managed limitations.

### Fixed: excessive homepage `<title>` length

The brand name was duplicated in the title tag.

- **Before:** `Study Abroad Guides for Azerbaijani Students | Study Diaries | Study Diaries`
- **After:** `Study Abroad Guides for Azerbaijani Students | Study Diaries`

**Result after recrawl:**
- Long-title warning resolved
- Warnings: 23 → 22
- Site Health: 95% → 96%

### Investigated and monitored

- **Hreflang language mismatch** — Semrush flagged Azerbaijani pages (correct `az` hreflang) as being detected as Turkish. After investigation, I kept the correct `az` implementation rather than changing it just to satisfy the audit tool, and classified it as a likely automated language-classification issue to monitor.
- **Low word count** — Rather than padding every flagged page, I triaged by page purpose: utility pages (e.g. Contact) were deprioritized, while key informational/landing pages were flagged as opportunities for future content expansion.
- **Unminified JS/CSS** — Flagged resources were platform-managed via Hostinger/Zyro infrastructure; no unsupported manual changes were made given overall performance remained strong.
- **HTTPS/HSTS** — SSL was active and secure; the remaining deduction relates to HSTS configuration, which is limited by the hosting platform's server-level controls.

---

## Key Takeaways

- A single misconfigured setting (homepage `noindex`) can quietly block a site from search entirely — indexation should be verified early, not assumed.
- Audit tools like Semrush surface useful signals, but not every warning deserves a fix; prioritizing by actual SEO impact (vs. chasing a perfect score) is part of the job.
- Small technical fixes (title tag cleanup, indexing restore) had a measurable, fast impact on impressions, clicks, and average position.

## Next Steps

- Expand content on key informational and landing pages flagged for low word count
- Continue monitoring the hreflang classification issue in Semrush
- Track keyword-level performance in GSC as impressions grow beyond the initial baseline
- Build additional internal links from new content back to priority landing pages
