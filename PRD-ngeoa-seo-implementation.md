# PRD: NGEOA SEO Implementation

**Product:** SEO Strategy and Implementation for ngeoacademy.org
**Version:** 1.0
**Date:** 2026-04-05
**Author:** Claude (via Eric Coffie)
**Priority:** P1

---

## Overview

### Problem Statement

ngeoacademy.org is live but has no SEO optimization:
- No Google Search Console
- No structured data
- No optimized meta tags
- No content strategy
- No local SEO presence
- Potential students searching for "heavy equipment training Miami" won't find NGEOA

### Solution

Implement comprehensive SEO strategy to rank for relevant keywords and drive organic traffic from potential students, employers, and funders.

### Success Metrics

| Metric | Baseline | 90-Day Target | 12-Month Target |
|--------|----------|---------------|-----------------|
| Organic traffic | 0 | 100/month | 1,000/month |
| Keyword rankings (top 10) | 0 | 5 keywords | 20 keywords |
| Google Business clicks | N/A | 50/month | 200/month |
| Organic leads | 0 | 5/month | 25/month |

---

## Requirements

### R1: Technical SEO Foundation

**Google Search Console Setup:**
- Verify domain ownership (DNS TXT record)
- Submit sitemap.xml
- Request indexing for all pages
- Monitor for crawl errors

**Sitemap.xml:**
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://ngeoacademy.org/</loc>
    <lastmod>2026-04-05</lastmod>
    <priority>1.0</priority>
  </url>
  <url>
    <loc>https://ngeoacademy.org/program</loc>
    <lastmod>2026-04-05</lastmod>
    <priority>0.9</priority>
  </url>
  <url>
    <loc>https://ngeoacademy.org/apply</loc>
    <lastmod>2026-04-05</lastmod>
    <priority>0.9</priority>
  </url>
  <url>
    <loc>https://ngeoacademy.org/employers</loc>
    <lastmod>2026-04-05</lastmod>
    <priority>0.8</priority>
  </url>
  <url>
    <loc>https://ngeoacademy.org/about</loc>
    <lastmod>2026-04-05</lastmod>
    <priority>0.7</priority>
  </url>
  <url>
    <loc>https://ngeoacademy.org/contact</loc>
    <lastmod>2026-04-05</lastmod>
    <priority>0.7</priority>
  </url>
</urlset>
```

**Robots.txt:**
```
User-agent: *
Allow: /
Sitemap: https://ngeoacademy.org/sitemap.xml
```

**Page Speed Optimization:**
- Target: < 3 second load time
- Compress images (WebP format)
- Minify CSS/JS
- Enable caching
- Use Next.js image optimization

### R2: On-Page SEO

**Title Tags (Updated):**

| Page | Current | Optimized |
|------|---------|-----------|
| Home | NGEOA | Heavy Equipment Training Miami \| NGEOA Academy |
| Program | Program \| NGEOA | 8-Week Heavy Equipment Operator School \| NGEOA |
| Apply | Apply \| NGEOA | Apply for Heavy Equipment Training \| Free Application |
| Employers | Employers \| NGEOA | Hire Trained Equipment Operators \| NGEOA Partners |
| About | About \| NGEOA | About NGEOA \| Miami Heavy Equipment Training |
| Contact | Contact \| NGEOA | Contact NGEOA \| Goulds, Miami FL |

**Meta Descriptions (150-160 chars):**

| Page | Meta Description |
|------|------------------|
| Home | "Learn to operate excavators, loaders & backhoes in 8 weeks. NGEOA offers hands-on heavy equipment training in Miami. OSHA 10 included. Apply now!" |
| Program | "Our 8-week heavy equipment operator program covers excavators, front-end loaders, backhoes & skid steers. Get job-ready with OSHA 10 certification." |
| Apply | "Apply for NGEOA's heavy equipment training program. Free application. Eligibility: 18+, valid driver's license, pass background check. Start your career!" |
| Employers | "Partner with NGEOA to hire skilled equipment operators. Sponsor students, get first interview rights, and build your workforce pipeline." |
| About | "NGEOA is a ministry of New Life City Center in Goulds, Miami. We train the next generation of heavy equipment operators for construction careers." |
| Contact | "Contact NGEOA Academy in Goulds, Miami. Get information about heavy equipment training, enrollment, and employer partnerships." |

**Header Tags (H1, H2, H3):**

Each page should have:
- 1 H1 tag (primary keyword)
- 2-5 H2 tags (supporting keywords)
- H3 tags for subsections

**Example - Home Page:**
```
H1: Heavy Equipment Operator Training in Miami
  H2: 8-Week Hands-On Training Program
  H2: Equipment You'll Learn
  H2: Who Should Apply
  H2: Employer Partnerships
  H2: Start Your Career Today
```

### R3: Structured Data (Schema.org)

**Organization Schema:**
```json
{
  "@context": "https://schema.org",
  "@type": "EducationalOrganization",
  "name": "Next Generation Equipment Operators Academy",
  "alternateName": "NGEOA",
  "url": "https://ngeoacademy.org",
  "logo": "https://ngeoacademy.org/logo.png",
  "description": "Heavy equipment operator training program in Miami, Florida",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "[Church Address]",
    "addressLocality": "Goulds",
    "addressRegion": "FL",
    "postalCode": "[ZIP]",
    "addressCountry": "US"
  },
  "parentOrganization": {
    "@type": "Church",
    "name": "New Life City Center",
    "url": "https://newlifecitycenter.org"
  }
}
```

**Course Schema (Program Page):**
```json
{
  "@context": "https://schema.org",
  "@type": "Course",
  "name": "Heavy Equipment Operator Training Program",
  "description": "8-week hands-on training program covering excavator, loader, backhoe, and skid steer operation",
  "provider": {
    "@type": "EducationalOrganization",
    "name": "NGEOA"
  },
  "hasCourseInstance": {
    "@type": "CourseInstance",
    "courseMode": "onsite",
    "duration": "P8W",
    "offers": {
      "@type": "Offer",
      "category": "Tuition"
    }
  },
  "occupationalCredentialAwarded": "OSHA 10 Certification"
}
```

**Local Business Schema:**
```json
{
  "@context": "https://schema.org",
  "@type": "LocalBusiness",
  "name": "NGEOA Academy",
  "image": "https://ngeoacademy.org/building.jpg",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "[Address]",
    "addressLocality": "Miami",
    "addressRegion": "FL"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": "[LAT]",
    "longitude": "[LONG]"
  },
  "telephone": "[Phone]",
  "openingHours": "Mo-Fr 08:00-17:00"
}
```

### R4: Keyword Strategy

**Primary Keywords (Target in first 90 days):**

| Keyword | Volume | Difficulty | Target Page |
|---------|--------|------------|-------------|
| heavy equipment training miami | 200/mo | Low | Home |
| heavy equipment operator school florida | 500/mo | Medium | Home |
| excavator training near me | 1,000/mo | Medium | Program |
| heavy equipment training programs | 800/mo | Medium | Program |
| free heavy equipment training miami | 100/mo | Low | Apply |

**Secondary Keywords (Target in months 3-6):**

| Keyword | Volume | Difficulty | Target Page |
|---------|--------|------------|-------------|
| cdl heavy equipment training | 300/mo | Medium | Program |
| construction training programs | 400/mo | Medium | Home |
| nccer heavy equipment certification | 150/mo | Low | Program |
| heavy equipment operator jobs miami | 500/mo | Medium | Future blog |
| backhoe training classes | 200/mo | Low | Program |
| front end loader training | 150/mo | Low | Program |

**Long-Tail Keywords (Content Topics):**

| Keyword | Content Type |
|---------|--------------|
| how to become a heavy equipment operator | Blog post |
| heavy equipment operator salary florida | Blog post |
| is heavy equipment training worth it | Blog post |
| heavy equipment training for beginners | FAQ |
| what equipment do construction workers use | Blog post |

### R5: Local SEO

**Google Business Profile:**
- Create/claim listing
- Add all business info
- Upload photos (equipment, facility, students)
- Add categories: "Vocational school", "Training center"
- Enable messaging
- Request reviews

**Local Directories:**
- Yelp
- Apple Maps
- Bing Places
- Yellow Pages
- Manta
- Chamber of Commerce
- Local training directories

**Local Citations (NAP Consistency):**
```
Name: NGEOA Academy (or Next Generation Equipment Operators Academy)
Address: [Consistent address everywhere]
Phone: [Consistent phone everywhere]
```

**Local Content:**
- Create pages for nearby cities:
  - `/heavy-equipment-training-homestead`
  - `/heavy-equipment-training-miami-dade`
  - `/heavy-equipment-training-south-miami`

### R6: Content Strategy

**Blog Launch (2 posts/month):**

| Month | Post 1 | Post 2 |
|-------|--------|--------|
| Month 1 | "How to Become a Heavy Equipment Operator in Florida" | "Heavy Equipment Operator Salary: What to Expect in 2026" |
| Month 2 | "5 Types of Heavy Equipment and What They're Used For" | "Is Heavy Equipment Training Worth It?" |
| Month 3 | "What to Expect in Heavy Equipment Operator School" | "OSHA 10 Certification: What You Need to Know" |

**Blog Post Template:**
```markdown
# [Keyword-Rich Title]

## Introduction
[Hook + keyword mention]

## [H2 Section 1]
[Content with internal links]

## [H2 Section 2]
[Content with relevant stats]

## [H2 Section 3]
[Content with list or table]

## FAQ
### [Question with long-tail keyword]
[Answer]

## Conclusion + CTA
[Summary + "Apply Now" link]

---
*Ready to start your career? [Apply to NGEOA today](/apply).*
```

**FAQ Page:**
- 15-20 questions about the program
- Schema markup for each Q&A
- Internal links to relevant pages

### R7: Link Building Strategy

**Internal Links:**
- Every blog post links to /program and /apply
- Cross-link related content
- Use keyword-rich anchor text

**External Link Targets:**

| Source | Approach |
|--------|----------|
| Church of Nazarene district | Request link on district site |
| New Life City Center | Link from church site |
| Local news | Press release for program launch |
| Construction associations | Partnership mentions |
| Community college | Partnership page |
| CareerSource | Training provider listing |
| Employer websites | Partner mentions |

**Guest Post Targets:**
- Construction industry blogs
- Workforce development sites
- Miami local news/blogs

---

## Technical Implementation

### Next.js SEO Components

**Head Component Updates:**
```tsx
// app/layout.tsx
export const metadata = {
  title: {
    default: 'Heavy Equipment Training Miami | NGEOA Academy',
    template: '%s | NGEOA Academy'
  },
  description: 'Learn to operate excavators, loaders & backhoes...',
  openGraph: {
    type: 'website',
    locale: 'en_US',
    url: 'https://ngeoacademy.org',
    siteName: 'NGEOA Academy',
  },
  robots: {
    index: true,
    follow: true,
  },
}
```

**Per-Page Metadata:**
```tsx
// app/program/page.tsx
export const metadata = {
  title: '8-Week Heavy Equipment Operator School',
  description: 'Our 8-week heavy equipment operator program...',
}
```

**Structured Data Component:**
```tsx
// components/JsonLd.tsx
export function JsonLd({ data }) {
  return (
    <script
      type="application/ld+json"
      dangerouslySetInnerHTML={{ __html: JSON.stringify(data) }}
    />
  )
}
```

---

## Monitoring & Reporting

**Monthly SEO Report:**
- Organic traffic (Google Analytics)
- Keyword rankings (Google Search Console)
- Google Business Profile views/clicks
- Backlinks acquired
- Content published
- Technical issues fixed

**Tools:**
- Google Search Console (free)
- Google Analytics 4 (free)
- Google Business Profile (free)
- Screaming Frog (free up to 500 pages)

---

## Timeline

| Phase | Duration | Deliverables |
|-------|----------|--------------|
| Week 1 | 3 days | Technical SEO setup (GSC, sitemap, robots) |
| Week 1 | 2 days | On-page SEO (titles, metas, headers) |
| Week 2 | 3 days | Structured data implementation |
| Week 2 | 2 days | Google Business Profile setup |
| Week 3 | 5 days | First 2 blog posts |
| Week 4 | 3 days | Local directory submissions |
| Ongoing | 2 days/week | Content creation + monitoring |

---

## Acceptance Criteria

- [ ] Google Search Console verified and sitemap submitted
- [ ] All pages have optimized title tags and meta descriptions
- [ ] Structured data implemented (Organization, Course, LocalBusiness)
- [ ] Google Business Profile created and optimized
- [ ] First 2 blog posts published
- [ ] 10+ local directory listings submitted
- [ ] Monthly reporting dashboard set up
- [ ] Ranking for at least 1 target keyword in top 20

---

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2026-04-05 | Initial PRD |
