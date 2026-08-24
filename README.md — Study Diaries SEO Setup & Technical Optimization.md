# Study Diaries — SEO Setup & Technical Optimization Case Study

> A self-directed SEO case study on a live website: establishing an organic search foundation, diagnosing and resolving a homepage indexing issue, and auditing technical SEO with Google Search Console and Semrush.

**Live site:** [studydiaries.org](https://www.studydiaries.org/)

## TL;DR

Study Diaries is a study-abroad information website for Azerbaijani students that I built and optimized as a personal project to develop and demonstrate practical SEO skills.

Starting with almost no organic search visibility, I set up Google Search Console and Semrush, identified and resolved a homepage `noindex` issue, implemented foundational on-page SEO, and conducted a technical SEO audit.

| Metric | Initial Baseline | 13–22 Aug 2026 |
|---|---:|---:|
| Impressions | 1 | 23 |
| Clicks | 0 | 4 |
| CTR | 0% | 17.4% |
| Avg. position | 64 | 24.1 |

### Key Outcomes

- ✅ Identified and resolved a homepage `noindex` issue
- ✅ Validated homepage indexability using Google Search Console Live URL Inspection
- ✅ Submitted and verified an XML sitemap
- ✅ Investigated index coverage rather than treating every exclusion as an error
- ✅ Implemented meta descriptions, image alt text, and internal linking
- ✅ Improved Semrush Site Health from **95% → 96%**
- ✅ Reduced Semrush audit warnings from **23 → 22**
- ✅ Maintained **0 errors and 0 broken pages**
- ✅ Recorded the site's first organic clicks in Google Search Console

**Skills demonstrated:** Technical SEO · Google Search Console · Semrush · Indexation Analysis · URL Inspection · XML Sitemaps · On-Page SEO · Hreflang · SEO Troubleshooting · Technical Auditing

---

## Project Overview

- **Focus:** SEO setup, on-page optimization, technical SEO, organic search visibility
- **Platform:** Hostinger AI Builder (manual mode)
- **Tools:** Google Search Console, Semrush, Hostinger AI Builder
- **Status:** Ongoing

### The Challenge

As a newly created website, Study Diaries had little existing organic search visibility or historical performance data.

The initial goal wasn't to chase rankings immediately. It was to establish a strong SEO foundation that would allow Google to:

- Discover the website
- Crawl important pages
- Understand the website structure
- Index relevant content
- Begin generating organic search impressions

Shortly after Google Search Console was configured, the website began receiving search impressions.

The initial baseline was minimal — **1 impression, 0 clicks, 0% CTR, and an average position of 64**. Because this represented only one impression, average position was not treated as a meaningful ranking KPI.

Instead, I prioritized ensuring that the website was technically accessible and optimized for future organic growth.

---

## 1. On-Page SEO Optimization

I implemented several foundational on-page SEO elements directly through Hostinger AI Builder.

### Meta Descriptions

Added page-specific meta descriptions to provide search engines with clearer context about important pages and improve how those pages may be presented in search results.

Rather than treating meta descriptions as a direct ranking factor, I used them to improve search-result relevance and support future organic click-through rates.

### Image Alt Text

Added descriptive alt text to relevant website imagery to improve semantic context, accessibility, and image-search optimization.

### Internal Linking

Added internal links to CTA elements to connect users with relevant sections and pages.

The goal was to improve user navigation while creating clearer pathways between related content for search-engine crawlers.

---

## 2. Google Search Console Setup

Google Search Console was used to establish an organic-search measurement and technical SEO framework.

An XML sitemap was submitted and successfully processed:

| Status | Submitted | Last Read | Initially Discovered Pages |
|---|---|---|---:|
| Success | 17 Aug 2026 | 20 Aug 2026 | 7 |

Search Console was then used to monitor and investigate page indexing, crawlability, and organic search performance.

At the time of the initial investigation, Google reported:

- **11 indexed pages**
- **10 non-indexed URLs**

Rather than attempting to index every URL, I evaluated the exclusion types individually to distinguish legitimate exclusions from actual SEO problems.

### Diagnosing a Homepage Indexing Issue

The investigation uncovered an important issue affecting the homepage:

**Excluded by `noindex` tag**

I performed a Google Search Console **Live URL Inspection** to determine whether this represented historical data or an active technical issue.

The live test confirmed:

| Crawl Allowed | Page Fetch | Indexing Allowed | Reason |
|---|---|---|---|
| Yes | Successful | **No** | `noindex` detected in robots meta tag |

Google could successfully crawl and fetch the homepage, but the website itself was explicitly instructing Google not to index it.

This was particularly important because the homepage is a central page for brand discovery, website navigation, and internal linking.

### Root Cause

Study Diaries was built using Hostinger AI Builder.

After investigating the page-level SEO settings, I discovered that the homepage had accidentally been configured as:

> **"Hide page from search results"**

This setting generated the `noindex` directive detected by Google Search Console.

### Fix

I:

1. Disabled the **"Hide page from search results"** setting
2. Made the homepage visible to search engines
3. Republished the website
4. Performed another Google Search Console Live URL Inspection

### Validation

| | Result |
|---|---|
| **Before** | ❌ URL not available to Google — `noindex` detected in robots meta tag |
| **After** | ✅ URL available to Google — page can be indexed |

The before-and-after Live URL tests confirmed that the technical indexing restriction had been successfully removed.

Other important pages previously classified as **"Crawled — currently not indexed"** were also tested individually.

The live tests confirmed that these pages were accessible to Google and technically eligible for indexing, indicating that there was no active technical indexing restriction affecting them.

#### Before

![Google Search Console homepage noindex issue](images/gsc-noindex-before.png)

#### After

![Google Search Console homepage indexable after fix](images/gsc-indexable-after.png)

### Early Organic Search Performance

Following the technical SEO setup and indexing investigation, Google Search Console began recording increased search activity.

| Period | Impressions | Clicks | CTR | Avg. Position |
|---|---:|---:|---:|---:|
| Initial baseline | 1 | 0 | 0% | 64 |
| 13–22 Aug 2026 | **23** | **4** | **17.4%** | **24.1** |

![Google Search Console performance from 13–22 August 2026](images/gsc-performance-august-2026.png)

*Google Search Console performance, 13–22 August 2026.*

Because Study Diaries is a newly launched website and the dataset is still small, these figures are treated as **early organic visibility signals rather than evidence of a stable ranking trend**.

The progression nevertheless shows that Google has begun displaying Study Diaries pages in search results and that the website has started receiving its first organic clicks.

---

## 3. Semrush Technical SEO Audit

After completing the initial Google Search Console setup and indexing investigation, I conducted a technical SEO audit using Semrush.

![Semrush thematic reports showing technical SEO scores](images/semrush-thematic-reports.png)

The initial audit reported:

- **Site Health:** 95%
- **Pages crawled:** 12
- **Warnings:** 23
- **Errors:** 0
- **Broken pages:** 0

The absence of critical errors and broken pages indicated that the website already had a strong technical foundation.

Rather than attempting to achieve a 100% audit score automatically, I investigated individual warnings to determine whether they represented genuine SEO problems, low-priority findings, false positives, or platform-managed limitations.

### Fixed: Excessive Homepage `<title>` Length

Semrush identified excessive text in the homepage title element.

The brand name was unnecessarily repeated.

**Before:**

`Study Abroad Guides for Azerbaijani Students | Study Diaries | Study Diaries`

**After:**

`Study Abroad Guides for Azerbaijani Students | Study Diaries`

I corrected the title through Hostinger AI Builder.

### Validation

After Semrush recrawled the website:

- ✅ Long-title warning resolved
- Warnings decreased from **23 → 22**
- Site Health increased from **95% → 96%**

This followed a practical SEO workflow:

**Identify → Investigate → Implement → Recrawl → Validate**

---

## Additional Technical Findings

### Hreflang Language Mismatch

Semrush reported that several Azerbaijani pages using the correct `az` hreflang value were being detected as Turkish.

After investigating the warning, I retained the correct Azerbaijani `az` implementation rather than changing it simply to satisfy the audit tool.

The issue was classified as a likely automated language-classification problem and marked for monitoring.

### Low Word Count

Several pages were flagged for low word count.

Instead of expanding every page purely to satisfy an audit score, I evaluated the affected pages according to their purpose.

Utility pages such as Contact pages were considered lower priority, while important informational and landing pages were identified as opportunities for future content expansion.

### Unminified JavaScript & CSS

Semrush identified unminified CSS and JavaScript resources delivered through the Hostinger/Zyro infrastructure.

Because these resources were platform-managed and overall website performance remained strong, I did not make unsupported manual modifications simply to eliminate the warning.

### HTTPS / HSTS

The website's SSL certificate was active and secure.

The remaining HTTPS deduction was associated with HSTS configuration. Because Study Diaries operates through Hostinger AI Builder, server-level configuration options are limited.

This was therefore classified as a low-priority technical/security enhancement rather than an urgent SEO issue.

---

## Key Takeaways

- A single misconfigured setting such as a homepage `noindex` directive can prevent an important page from appearing in search results. Indexability should be verified rather than assumed.

- Google Search Console's Live URL Inspection can help distinguish historical indexing reports from active technical restrictions.

- SEO audit tools such as Semrush provide useful signals, but not every warning requires a fix. Findings should be investigated and prioritized according to actual SEO impact.

- Platform limitations need to be considered before implementing technical changes. Removing an audit warning is not worth introducing unnecessary website risk.

- Following the technical fixes, Google Search Console began recording increased impressions and the site's first organic clicks. Continued monitoring is necessary as more data accumulates before drawing conclusions about long-term ranking performance.

---

## Next Steps

- Expand useful content on priority informational and landing pages
- Continue monitoring the hreflang classification issue in Semrush
- Track keyword-level performance in Google Search Console as impressions increase
- Monitor clicks, CTR, search queries, landing pages, and average positions
- Build additional contextual internal links as new content is published
- Conduct competitor keyword-gap research
- Analyze competitor backlinks and identify legitimate link-building opportunities
- Periodically rerun the Semrush technical audit after significant website changes

---

## Skills Demonstrated

`Technical SEO` · `Google Search Console` · `Semrush` · `Indexation Analysis` · `URL Inspection` · `XML Sitemaps` · `On-Page SEO` · `Internal Linking` · `Hreflang` · `SEO Troubleshooting` · `Technical SEO Auditing` · `SEO Prioritization`

---

**Project:** Study Diaries  
**Role:** SEO / Digital Marketing  
**Status:** Ongoing