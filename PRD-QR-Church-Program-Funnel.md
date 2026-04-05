# PRD: QR → New Life City Center — Program Discovery & Signup Funnel

**Document type:** Product Requirements Document  
**Status:** **Approved for build (v1.0)** — discovery locked; remaining §11 items can be filled in during implementation without blocking the build.  
**Last updated:** 2026-04-04  
**Owner:** New Life City Center / project maintainer  
**Primary surface:** Public church website — [https://newlifecitycenter.org](https://newlifecitycenter.org)  
**Codebase:** `church-website/` (Next.js)

### Implementation pointer (build started)

| Item | Location / notes |
|------|------------------|
| **QR URL** | `https://newlifecitycenter.org/connect` |
| **Page** | `church-website/src/app/connect/page.tsx` |
| **Interest form API** | `church-website/src/app/api/connect/route.ts` |
| **Email (production)** | Set `RESEND_API_KEY`, `CONNECT_NOTIFY_EMAIL`, `RESEND_FROM_EMAIL` on Vercel (see `church-website/README.md`) |
| **Yard-sign artwork** | Out of repo for now — in-house Canva/export; keep QR quiet zone per §7 NFR-3 |

**Finish later (non-blocking):** program-list owner (§11 Q4), auto-reply to visitor (§11 Q5), analytics, bilingual, CRM ingest.

### Related documents

| Document | Relationship |
|----------|--------------|
| [`PROJECT-SCOPE.md`](./PROJECT-SCOPE.md) | Live URLs, page inventory, stack |
| [`DESIGN-SYSTEM.md`](./DESIGN-SYSTEM.md) | Colors, typography, brand usage |
| [`PRD-Workforce-Academy.md`](./PRD-Workforce-Academy.md) | NGEOA program context; heavy equipment track lives on [ngeoacademy.org](https://ngeoacademy.org) |

---

## 0. Discovery decisions (locked — 2026-04-04)

Stakeholder answers captured from working session (voice transcript normalized where obvious).

| Topic | Decision |
|--------|----------|
| **QR destination** | **https://newlifecitycenter.org** — same church site; use a **dedicated path** for scanners (recommended: `/connect`) so the URL stays stable when homepage copy changes. |
| **One QR or many** | **One QR for everything** (single canonical URL on all collateral). |
| **First physical use** | **Yard sign** (outdoor viewing distance → larger QR / high contrast; validate scan from curb). |
| **What counts as “signed up”** | Visitor **submits the interest form**; **secretary is notified** (email). Actual enrollment may still be **completed in person** or by phone — messaging must say that clearly. |
| **Digital vs in-person** | Primary expectation: **come in person** (and/or call). Form = **express interest**, not full registration. |
| **Notification** | **Secretary** receives submissions (implementation: e.g. forward to church inbox / workflow TBD in build). |
| **Form fields** | Collect **name, phone, email, child’s age (when relevant), program of interest**. |
| **Audience** | **Youth, seniors, job seekers** (also neighbors and Spanish-speaking community in the area — **English-only copy for v1**). |
| **Bilingual** | **Not required for v1** (may revisit later). |
| **Program list ownership** | **Deferred** — not decided this session. |
| **Cross & stars** | **Very prominent** in the yard-sign artwork (balance with QR **quiet zone** and scannability). |
| **Design / print vendor** | **No** — produce assets **in-house** (e.g. Canva, export print-ready PDF). |
| **30–60 day success** | **Ship the designed experience** (yard sign + landing live) and **fuller classes / programs** (qualitative + attendance). |
| **Storing emails in a form** | **Approved** — church is OK collecting submissions via form (include brief privacy/use line). |
| **NGEOA / Academy** | **Sometimes stay on the church website** (summary/context on NLCC); **optional link out** to [ngeoacademy.org](https://ngeoacademy.org) when appropriate — not “always jump straight to Academy.” |

---

## 1. Executive summary

Deliver a **scan-to-signup path** for community members who encounter New Life City Center **offline** (bulletin, poster, flyer, event table, yard sign, T-shirt, vehicle magnet). A **QR code** encodes a single canonical URL to the **church website**. The **destination experience** must make it obvious **what programs exist** and **how to register or express interest** for each—without requiring church staff to reprint materials every time copy changes.

**Creative direction (locked):** Cross and stars are **very prominent** on print; QR must remain **scannable** (quiet zone, contrast). See §0.

---

## 2. Problem statement

- People at events or in the neighborhood often **do not** type long URLs or search the church name; **QR scanning** is the lowest-friction bridge from physical touchpoints to digital.
- Today the church site describes ministries and contact paths, but there is **no single “start here” journey** optimized for **“I just scanned a code—what do I do next?”**
- Staff need **one stable QR** that can remain on printed assets for months; **content updates** should happen on the website, not by redeploying print.

---

## 3. Goals & success measures

### 3.1 Goals

| ID | Goal |
|----|------|
| G-1 | **One canonical QR URL** used across approved print and digital collateral. |
| G-2 | Post-scan, a visitor can **identify programs** relevant to them within **one scroll** on mobile. |
| G-3 | Each program (or program category) has a **clear next step** (form, email, phone, or external link such as NGEOA apply). |
| G-4 | Visual identity on collateral aligns with **New Life City Center** brand (see design system). |

### 3.2 Success measures (v1)

| Metric | Definition | Target (initial) |
|--------|------------|------------------|
| Scan success | User loads intended page on mobile without 404 | 100% |
| Mobile usability | Primary CTAs visible without horizontal scroll; tap targets ≥44px | Pass QA checklist |
| Time-to-action | User reaches a signup/contact path from landing | ≤2 taps from landing |
| Content freshness | Program list updated within X days of schedule change | Owner **TBD** (deferred in discovery) |

*Analytics (optional later):* If/when privacy-friendly analytics are enabled, track visits to the landing path and outbound clicks to forms; not required for v1 launch.

---

## 4. Users & stories

| User | Need |
|------|------|
| **New visitor (QR)** | Immediately understand where they are, what programs exist, how to sign up. |
| **Parent / guardian** | Find children/youth pathways and safety-of-trust signals (times, contact). |
| **Community member** | Find outreach, classes, or special events without calling first. |
| **NGEOA prospect** | Be routed to the **academy** site or apply flow when appropriate. |
| **Church staff** | Maintain one QR; update web content; minimal support burden from “which link?” questions. |

**Representative user stories**

1. *As a visitor who scanned a flyer,* I want to see **program options and signup steps** so I can join without confusion.  
2. *As a visitor,* I want the page to work **on my phone** so I don’t abandon the flow.  
3. *As staff,* I want the **QR URL to stay the same** when we edit program text or add a ministry.

---

## 5. Scope

### 5.1 In scope (product)

- **Canonical URL:** `https://newlifecitycenter.org/<dedicated-path>` (recommend **`/connect`**) — single QR for all touchpoints; v1 **yard sign** first.
- **Mobile-first landing:** headline, programs, **interest form** (fields in §0), clear copy that **follow-up is in person / by phone** after secretary receives the email.
- **Form submission:** notify **secretary** (email integration via serverless API, form service, or approved church tool — **no credentials in client**).
- **Spam / abuse:** honeypot and/or provider CAPTCHA (FR-7).
- **NGEOA:** **On-page content** on church site; link to Academy **optional**, not the only path.
- **Brand-compliant yard-sign artwork** (in-house): QR + **very prominent** cross and stars; **human-readable URL** on sign; **yard-sign sizing** (larger than bulletin minimum).
- **Accessibility:** alt text if QR is embedded on web; **English only** for v1.

### 5.2 In scope (creative asset)

- **Visual elements:** QR code, **cross**, **stars** — **very prominent**; must preserve QR **quiet zone** and contrast (see `DESIGN-SYSTEM.md`).
- **Copy block** for yard sign + optional video (see §8).

### 5.3 Out of scope (unless added by amendment)

- Unique QR per ministry (campaign-level codes can be a future phase).
- Paid ad landing pages or A/B testing infrastructure.
- Native mobile app or push notifications.
- CRM auto-ingest of form leads (possible future integration with internal CRM—separate spec).

---

## 6. Functional requirements

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-1 | QR resolves to **HTTPS** church domain (`newlifecitycenter.org`) | P0 |
| FR-2 | Dedicated **landing route** (not homepage-only) optimized for scanners | P0 |
| FR-3 | Landing lists **programs/ministries**; each has clear context; **primary CTA** = **interest form** + **in-person / call** messaging | P0 |
| FR-4 | **Interest form** fields: **name, phone, email, child’s age** (conditional or optional field), **program of interest** | P0 |
| FR-5 | Form submission **emails secretary** (or routed inbox); sender receives optional auto-acknowledgment **TBD** | P0 |
| FR-6 | **NGEOA** described **on church site**; **optional** link to [ngeoacademy.org](https://ngeoacademy.org) — not required as only action | P1 |
| FR-7 | **Contact block** on mobile (phone, email, address/maps if available) | P1 |
| FR-8 | **Meta tags** (title, description) for “programs & connect” previews | P1 |
| FR-9 | **Spam protection** + short **privacy note** (how info is used) | P0 |

---

## 7. Non-functional requirements

| ID | Requirement |
|----|-------------|
| NFR-1 | **Performance:** LCP acceptable on mid-tier mobile (church site baseline). |
| NFR-2 | **Security:** No API keys or SMTP credentials in the browser; form posts to **server-side route** or **approved form provider**. |
| NFR-3 | **Print QR:** Bulletin minimum **≥ 1 inch / 2.5 cm**; **yard sign** must be **larger** and tested at **curb / driveway** distance; high contrast (dark on light). |
| NFR-4 | **Brand:** Use approved palette from `DESIGN-SYSTEM.md` (#F7941D, #002868, #1A1A1A, etc.). |

---

## 8. Content & copy (starter)

**Print / video line (editable):**

> Scan this code — it takes you to **New Life City Center** online. See our programs and **how to sign up** for each one.

**Short URL label (always print next to QR):**  
`newlifecitycenter.org/connect` *(example — final path must match implementation)*

---

## 9. Rollout phases

| Phase | Deliverable |
|-------|-------------|
| **P0** | Landing route + **interest form** + secretary email path; QR asset; **yard sign** proof (outdoor scan test); iOS + Android. |
| **P1** | Additional collateral (flyers, event table) reusing same QR; train volunteers on one-liner. |
| **P2** | Optional analytics; optional CRM hook; bilingual if leadership reopens. |

---

## 10. Acceptance criteria (QA gate)

- [ ] Scanning QR on **iOS** and **Android** opens the correct page with no certificate warnings.
- [ ] Page passes **mobile** check: readable type, no broken layout at 375px width.
- [ ] Every listed program has a **working** CTA (no dead links).
- [ ] NGEOA section matches policy: **on-site copy** + **optional** correct external URL.
- [ ] **Yard sign** test: scans at intended **outdoor** distance; indoor bulletin size tested separately if used.
- [ ] Brand colors and logo usage match `DESIGN-SYSTEM.md` (or documented exceptions).

---

## 11. Open questions (remaining)

| # | Question | Notes |
|---|----------|--------|
| Q1 | Final path slug: `/connect` vs `/programs` vs `/signup`? | Recommend `/connect`; confirm before print. |
| Q2 | **Exact secretary email** / routing (single address vs alias)? | Align with `info@newlifecitycenter.org` forwarding today. |
| Q3 | Form implementation: **Resend / Formspree / Vercel serverless + SMTP**? | Must meet NFR-2 (no secrets in browser). |
| Q4 | Who **owns** updating program list when seasons change? | **Deferred** in discovery — decide before launch. |
| Q5 | Auto-reply to submitter (“we received your interest”)? | **TBD** |

---

## 12. Document history

| Version | Date | Notes |
|---------|------|-------|
| 1.1 | 2026-04-04 | Locked discovery: yard sign, form + secretary, fields, English-only, NGEOA on church site, prominent cross/stars, in-house design |
| 1.0 | 2026-04-04 | Initial PRD from QR + cross/stars + program signup discovery |
