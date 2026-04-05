# PRD: NGEOA Employer Job Placement Partnerships

**Product:** Employer Partnership Program for Graduate Job Placement
**Version:** 1.0
**Date:** 2026-04-05
**Author:** Claude (via Eric Coffie)
**Priority:** P0
**Model:** Nonprofit Ministry (No Tuition)

---

## Overview

### Context

NGEOA is a **nonprofit ministry** of New Life City Center. The program:
- Does NOT charge students tuition
- Is funded through grants, donations, and church support
- Focuses on serving underemployed community members
- Measures success by job placements, not revenue

### Problem Statement

NGEOA needs employer partners who will:
- Commit to interviewing/hiring graduates
- Provide Letters of Support for grant applications
- Potentially donate equipment time or materials
- Help validate curriculum meets industry needs

### Solution

Create a simple employer partnership program focused on **job placement commitments** rather than tuition sponsorship.

### Success Metrics

| Metric | Target |
|--------|--------|
| Employer partners signed | 10+ |
| Letters of Support collected | 5+ |
| Job placement rate | 80%+ |
| Employer satisfaction | 4/5 rating |

---

## Requirements

### R1: Employer Value Proposition

**What We Offer Employers (Free):**

| Benefit | Description |
|---------|-------------|
| Pre-screened candidates | Background check, drug test, eligibility verified |
| Trained operators | 8 weeks hands-on + OSHA 10 |
| First interview access | Meet graduates before public job posting |
| No recruiting fees | Free access to hiring pipeline |
| Community goodwill | Support workforce ministry |
| Input on curriculum | Shape training to your needs |

**What We Ask (No Cost):**

| Ask | Commitment |
|-----|------------|
| Letter of Support | 1-page letter for grant applications |
| Hiring commitment | Interview all qualified graduates |
| Job site visit | Host 1 field trip for students (optional) |
| Feedback | Share performance feedback on hires |

### R2: Partnership Tiers (No Cost to Employer)

| Tier | Commitment | Benefits |
|------|------------|----------|
| **Hiring Partner** | Interview graduates | Access to candidate pool, logo on website |
| **Training Partner** | Host job site visit | Above + curriculum input |
| **Equipment Partner** | Donate equipment time | Above + prominent recognition |
| **Founding Partner** | All of above + advisory role | Above + advisory board seat |

### R3: Letter of Support Template

```
[COMPANY LETTERHEAD]

[Date]

To Whom It May Concern:

[Company Name] is pleased to support the Next Generation Equipment
Operators Academy (NGEOA), a workforce training ministry of New Life
City Center in Goulds, Miami.

The construction industry in South Florida faces a significant shortage
of skilled heavy equipment operators. Programs like NGEOA that train
local residents for these careers help address this critical workforce gap.

As an employer in [industry], we commit to:
- Interviewing qualified graduates of the NGEOA program
- Considering NGEOA graduates for open equipment operator positions
- Providing feedback to help improve the training program

We believe NGEOA's hands-on training approach, combined with OSHA 10
certification, will produce job-ready candidates for our industry.

We support NGEOA's application for [grant name if known] and encourage
funders to invest in this valuable community program.

Sincerely,

[Name]
[Title]
[Company]
[Phone]
[Email]
```

### R4: Partnership Agreement (Simple)

```
NGEOA EMPLOYER PARTNERSHIP AGREEMENT

This agreement confirms the partnership between:

EMPLOYER: ________________________________
CONTACT: ________________________________
EMAIL: ________________________________
PHONE: ________________________________

NGEOA PROGRAM (New Life City Center)

EMPLOYER COMMITS TO:
[ ] Interview qualified NGEOA graduates for equipment operator positions
[ ] Provide a Letter of Support for grant applications
[ ] Offer feedback on graduate job performance
[ ] (Optional) Host a job site visit for students

NGEOA COMMITS TO:
[ ] Share graduate profiles with partner employers first
[ ] Ensure all graduates have OSHA 10 certification
[ ] Conduct background checks and drug screening
[ ] Provide ongoing support during onboarding period

This partnership involves no financial obligation from either party.

SIGNATURES:

Employer: _________________________ Date: _________

NGEOA Director: _________________________ Date: _________
```

### R5: Employer Outreach List

**Target Companies (Miami-Dade Area):**

| Company | Type | Contact Approach |
|---------|------|------------------|
| **Excavation/Site Work** | | |
| Bergeron Land Development | General contractor | Direct outreach |
| Miller Construction | Site development | Direct outreach |
| Coastal Construction | General contractor | Direct outreach |
| **Equipment Rental** | | |
| United Rentals | Equipment rental | Corporate partnership |
| Sunbelt Rentals | Equipment rental | Corporate partnership |
| H&E Equipment | Equipment rental | Corporate partnership |
| **Utilities** | | |
| Florida Power & Light | Utility | Workforce programs |
| Miami-Dade Water & Sewer | Government | Workforce programs |
| **Road/Infrastructure** | | |
| Ranger Construction | Road building | Direct outreach |
| AJAX Paving | Road/bridge | Direct outreach |
| **Equipment Dealers** | | |
| Ring Power (CAT dealer) | Equipment sales | Equipment partnership |
| Linder Industrial | Equipment sales | Equipment partnership |

### R6: Outreach Email Template

**Subject:** Partnership Opportunity: Trained Equipment Operators for [Company]

```
Hi [Name],

I'm reaching out from the Next Generation Equipment Operators Academy
(NGEOA), a new workforce training program in South Miami.

We're training local residents to become job-ready equipment operators
through an 8-week hands-on program. Graduates receive OSHA 10
certification and training on excavators, loaders, backhoes, and skid steers.

We're looking for employer partners who can:
- Interview our graduates for open positions
- Provide a Letter of Support for our grant applications

There's no cost to partner with us. We simply want to connect our
trained graduates with employers who need skilled operators.

Would you be open to a 15-minute call to discuss how this could help
your hiring pipeline?

Best,
[Name]
NGEOA Program Director
[Phone]
[Email]
ngeoacademy.org
```

---

## CRM Integration

### Organization Fields (Add to Existing)

| Field | Type | Values |
|-------|------|--------|
| Partnership Tier | Dropdown | Hiring / Training / Equipment / Founding |
| LOS Status | Dropdown | Not Requested / Requested / Received / Declined |
| LOS File | Attachment | PDF upload |
| Hiring Commitment | Checkbox | Yes/No |
| Site Visit Offered | Checkbox | Yes/No |
| Graduates Hired | Number | Count |
| Last Contact Date | Date | Auto-update |

### Pipeline Stages (Existing - Confirm Alignment)

| Stage | Meaning for Employers |
|-------|----------------------|
| Identified | Potential partner found |
| Contacted | Initial outreach made |
| Conversation | Discussing partnership |
| Committed | Verbal agreement |
| Documented | LOS signed |
| Paused | On hold |
| Lost | Declined partnership |

---

## Website Updates

### /employers Page Revisions

**Remove:** Any language about sponsorship fees or pricing

**Add:**
- Clear "no cost to you" messaging
- Partnership benefits list
- Simple partnership form (name, company, email, interest level)
- Testimonials (when available)
- "Become a Partner" CTA

**Partnership Form Fields:**
- Company name
- Contact name
- Email
- Phone
- Estimated operators needed (next 12 months)
- Interest in: [ ] Hiring [ ] Site visit [ ] Equipment donation [ ] Advisory role

---

## Outreach Process

### Week 1-2: Research & List Building
- Build list of 25+ target employers
- Research contacts (LinkedIn, company websites)
- Add to CRM as "Identified"

### Week 3-4: Initial Outreach
- Send personalized emails to 25 contacts
- Follow up with phone calls
- Move to "Contacted" in CRM

### Week 5-6: Meetings & Commitments
- Conduct discovery calls/meetings
- Present partnership opportunity
- Collect verbal commitments

### Week 7-8: Documentation
- Send partnership agreements
- Request Letters of Support
- Add to website partners section

### Ongoing
- Monthly check-ins with active partners
- Invite to graduation events
- Share success stories

---

## Acceptance Criteria

- [ ] Partnership tiers defined (no-cost model)
- [ ] Letter of Support template created
- [ ] Partnership agreement template created
- [ ] 25+ employers in CRM pipeline
- [ ] Outreach email template ready
- [ ] /employers page updated (no pricing)
- [ ] 5+ employer meetings conducted
- [ ] 2+ Letters of Support collected

---

## Dependencies

| Dependency | Status | Owner |
|------------|--------|-------|
| CRM employer fields | Add | Claude |
| /employers page content | Update | Claude |
| Employer contact research | Do | Brian/Cynthia |
| Letters of Support usage | Clarify | Grant writer |

---

## Timeline

| Phase | Duration | Deliverable |
|-------|----------|-------------|
| Week 1 | 2 days | Templates created (LOS, agreement, email) |
| Week 1 | 3 days | CRM fields added, pipeline updated |
| Week 2 | 3 days | Employer research, list of 25 targets |
| Week 2 | 2 days | Website /employers page updated |
| Week 3-4 | Ongoing | Outreach begins |

---

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2026-04-05 | Initial PRD (nonprofit model) |
