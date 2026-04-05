# PRD: NGEOA Grant Pipeline Management

**Product:** Grant Identification, Application, and Reporting System
**Version:** 1.0
**Date:** 2026-04-05
**Author:** Claude (via Eric Coffie)
**Priority:** P1

---

## Overview

### Problem Statement

NGEOA needs external funding to launch and sustain operations. Current state:
- No systematic grant search process
- No application tracking
- No deadline calendar
- No reporting templates for funders
- No documentation of outcomes for future applications

### Solution

Create a grant pipeline management system including:
- Grant opportunity database
- Application calendar with automated reminders
- Template library for common application components
- Outcome tracking for funder reports
- Integration with CRM for seamless data flow

### Success Metrics

| Metric | Target |
|--------|--------|
| Grant applications submitted (Year 1) | 10+ |
| Funding secured (Year 1) | $100K+ |
| Grant win rate | 25%+ |
| Report deadlines met | 100% |

---

## Requirements

### R1: Grant Database

**File:** `/docs/grant-database.md` (Updated quarterly)

**Fields per Grant:**

| Field | Example |
|-------|---------|
| Grant Name | Strengthening Community Colleges Round 6 |
| Funder | DOL Employment and Training Administration |
| Funder Type | Federal / State / Private Foundation / Corporate |
| Amount Range | $1M - $5M |
| Deadline | 05/20/2026 |
| Eligibility | Community colleges; nonprofits as partners |
| Focus Areas | Workforce development, skilled trades |
| Status | Researching / Drafting / Submitted / Awarded / Declined |
| Link | grants.gov/search-results-detail/361307 |
| Fit Score | High / Medium / Low |
| Notes | Requires community college lead partner |

### R2: Grant Calendar

**Format:** 12-month rolling calendar

| Month | Grant | Funder | Deadline | Status |
|-------|-------|--------|----------|--------|
| Apr 2026 | RESTART Initiative | DOL-ETA | 04/15/2026 | Drafting |
| May 2026 | SCC Round 6 | DOL-ETA | 05/20/2026 | Researching |
| May 2026 | Miami Foundation | Local | 05/01/2026 | To Apply |
| Jun 2026 | Caterpillar Foundation | Corporate | Rolling | Drafting |
| ... | ... | ... | ... | ... |

**Automated Reminders:**
- 60 days before: Start drafting
- 30 days before: Review draft
- 14 days before: Final review
- 7 days before: Submit
- 1 day after: Confirm receipt

### R3: Application Template Library

**Common Components (Reusable):**

1. **Organization Description** (500 words)
   - New Life City Center overview
   - NGEOA program description
   - Mission and vision
   - Governance structure

2. **Statement of Need** (1000 words)
   - Construction workforce shortage data
   - Miami-Dade unemployment statistics
   - Equity gaps in skilled trades
   - Economic impact of training

3. **Program Description** (1500 words)
   - 8-week curriculum overview
   - Training methodology
   - Equipment and facilities
   - Instructor qualifications
   - Student support services

4. **Goals and Objectives** (SMART format)
   - Goal 1: Train X students in Year 1
   - Objective 1.1: Enroll X students by [date]
   - Objective 1.2: Graduate X% of enrolled students
   - Goal 2: Achieve X% job placement rate
   - Goal 3: Establish X employer partnerships

5. **Evaluation Plan**
   - Data collection methods
   - Outcome metrics
   - Reporting schedule
   - Third-party evaluation (if required)

6. **Sustainability Plan**
   - Employer sponsorships
   - Tuition revenue
   - Diversified funding
   - Community college partnership

7. **Budget Template**
   - Personnel
   - Equipment
   - Supplies
   - Facilities
   - Indirect costs
   - Match (if required)

8. **Budget Narrative**
   - Line-item justifications
   - Cost reasonableness
   - Matching fund sources

9. **Logic Model**
   ```
   INPUTS → ACTIVITIES → OUTPUTS → OUTCOMES (Short) → OUTCOMES (Long)

   - Funding        - Recruit students   - 50 enrolled     - 80% complete    - Career employment
   - Equipment      - Deliver training   - 40 graduated    - 75% placed      - Family stability
   - Instructors    - Job placement      - 30 employed     - Wage increase   - Community impact
   - Facilities     - Employer outreach  - 10 partners     - Employer ROI    - Reduced poverty
   ```

10. **Letters of Support**
    - Template for employers
    - Template for community partners
    - Template for government officials

### R4: Funder-Specific Requirements

**DOL Grants (RESTART, SCC):**
- DUNS/UEI required
- SAM.gov registration required
- SF-424 forms
- Indirect cost rate agreement (or de minimis)
- Single Audit (if >$750K federal)

**Private Foundations:**
- Varies by foundation
- Often shorter applications
- May require site visit
- Relationship-dependent

**Corporate Foundations:**
- Usually online application
- Focus on alignment with company mission
- Often prefer local impact
- May include employee engagement

**Florida DEO/CareerSource:**
- ETPL listing may be required
- State-specific forms
- Performance metrics alignment
- Regional coordination

### R5: Outcome Tracking Integration

**CRM Fields for Student Outcomes:**

| Field | Type | When Collected |
|-------|------|----------------|
| Enrollment Date | Date | Day 1 |
| Completion Date | Date | Week 8 |
| Completion Status | Dropdown | Week 8 |
| OSHA 10 Cert Date | Date | Week 1 |
| Employment Status | Dropdown | 30/60/90 days |
| Employer Name | Text | At placement |
| Starting Wage | Currency | At placement |
| Wage at 6 Months | Currency | 6-month follow-up |
| Retention at 6 Months | Boolean | 6-month follow-up |
| Retention at 12 Months | Boolean | 12-month follow-up |

**Reports Generated:**
- Enrollment summary
- Completion rates
- Placement rates
- Wage data
- Employer satisfaction
- Student satisfaction

### R6: Grant Reporting Templates

**Quarterly Progress Report:**
```markdown
# NGEOA Progress Report - Q[X] 20[XX]

## Grant: [Grant Name]
## Reporting Period: [Start] - [End]

## Narrative Summary
[2-3 paragraphs on key activities and progress]

## Goal Progress

| Goal | Target | Actual | % Complete |
|------|--------|--------|------------|
| Students enrolled | X | X | X% |
| Students completed | X | X | X% |
| Students employed | X | X | X% |
| Employers partnered | X | X | X% |

## Expenditures

| Category | Budget | Spent This Period | Cumulative | Remaining |
|----------|--------|-------------------|------------|-----------|
| Personnel | $X | $X | $X | $X |
| Equipment | $X | $X | $X | $X |
| ... | ... | ... | ... | ... |

## Challenges & Solutions
[Any issues encountered and how addressed]

## Next Quarter Plans
[Key activities planned]

## Success Stories
[1-2 student or employer stories]
```

**Annual Report:**
- Full year narrative
- Complete outcome data
- Financial summary
- Lessons learned
- Sustainability update

---

## Technical Requirements

### File Structure

```
/docs/grants/
├── grant-database.md
├── grant-calendar.md
├── templates/
│   ├── organization-description.md
│   ├── statement-of-need.md
│   ├── program-description.md
│   ├── goals-objectives.md
│   ├── evaluation-plan.md
│   ├── sustainability-plan.md
│   ├── budget-template.xlsx
│   ├── budget-narrative.md
│   ├── logic-model.md
│   └── letter-of-support-template.docx
├── applications/
│   ├── 2026-04-restart/
│   ├── 2026-05-scc/
│   └── ...
└── reports/
    ├── q1-2026/
    ├── q2-2026/
    └── ...
```

### Automation

**Slash Commands:**
- `/ngeoa-grant-search [keyword]` — Search Grants.gov for relevant opportunities
- `/ngeoa-grant-status` — Show current pipeline status
- `/ngeoa-grant-report [grant] [period]` — Generate report template with CRM data

**Cron Jobs:**
- Weekly: Search Grants.gov for new workforce development grants
- Monthly: Update grant calendar
- Per deadline: Send reminder emails

### CRM Enhancements

**New Grant Application Entity:**

| Field | Type |
|-------|------|
| Grant Name | Text |
| Funder | Lookup (Organization) |
| Amount Requested | Currency |
| Application Deadline | Date |
| Submission Date | Date |
| Status | Dropdown |
| Decision Date | Date |
| Amount Awarded | Currency |
| Reporting Schedule | Text |
| Files | Attachments |

---

## Dependencies

| Dependency | Status | Owner |
|------------|--------|-------|
| UEI registration | Check | Eric |
| SAM.gov registration | Check | Eric |
| 501(c)(3) status (church) | Verify | Pastor |
| Indirect cost rate | Research | Eric |
| CRM grant module | Build | Claude |

---

## Acceptance Criteria

- [ ] Grant database created with 20+ opportunities
- [ ] 12-month calendar built with key deadlines
- [ ] Template library complete (all 10 components)
- [ ] CRM outcome tracking fields added
- [ ] Quarterly report template created
- [ ] At least 1 grant application drafted
- [ ] Automated reminders configured

---

## Priority Grant Targets (90 Days)

| Grant | Deadline | Fit | Action |
|-------|----------|-----|--------|
| RESTART Initiative | 04/15/2026 | HIGH | Check eligibility for reentry focus |
| Caterpillar Foundation | Rolling | HIGH | Direct outreach |
| Home Depot Foundation | Varies | MEDIUM | Program alignment |
| Miami Foundation | 05/01/2026 | MEDIUM | Community impact angle |
| CareerSource ITAs | Ongoing | HIGH | ETPL application first |

---

## Timeline

| Phase | Duration | Deliverable |
|-------|----------|-------------|
| Week 1 | 3 days | Grant database + calendar |
| Week 1-2 | 4 days | Template library (first 5 components) |
| Week 2-3 | 4 days | Template library (remaining 5) |
| Week 3 | 3 days | CRM integration |
| Week 4 | 3 days | First application draft |
| Ongoing | Weekly | Grant search + calendar updates |

---

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2026-04-05 | Initial PRD |
