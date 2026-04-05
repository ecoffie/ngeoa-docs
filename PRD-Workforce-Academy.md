# PRD: Next Generation Equipment Operators Academy — Church-Led Workforce Upskilling (Florida)

**Document type:** Product Requirements Document  
**Status:** Draft v1.1 (discovery synced)  
**Horizon:** Pilot through multi-site scale (3–5 years) — **multi-site and 70+ church network paused** until Goulds pilot meets go/no-go gates  
**Primary reference model:** NGEOA consulting execution blueprint (30-day launch, 8–12 week training, employer pipeline)

### Discovery context (locked)

| Item | Decision |
|------|----------|
| **Pilot site** | **Goulds (Miami), Church of the Nazarene** — official street address TBD for MOUs/grants |
| **Legal entity** | Existing **501(c)(3)** church (**50+ years**); **church board** = final go/no-go; **NGEOA** is **marketing name** only |
| **Core team** | **Brian** — PM (tasks, calls, letters of support, pipeline); **Earl Coffey Jr.** — lead trainer (credential audit: `EARL-CREDENTIAL-AUDIT.md`); **Cynthia** — church secretary + outreach |
| **Funding** | **No church program budget today**; **all volunteer** until revenue exists; grants/workforce TBD via research |
| **Equipment** | **None in hand** — donation, loan, rental, or partner yard required before hands-on cohort (see `EQUIPMENT-OPTIONS-MATRIX.md`) |
| **Employers** | **No warm relationships yet** — outbound pipeline is primary lever |
| **First cohort** | **Soft** target only; **no fixed start date** until `RESEARCH-GATES-AND-GO-NO-GO.md` gates pass (directional June discussed, not committed) |
| **Facility** | Church has **land/facility**; goal to raise **facility utilization** beyond weekend-only use |
| **Top risk** | **Execution reliability** — thin volunteer bench; mitigations in execution plan + weekly board reporting |

---

## 1. Executive summary

Build and operate a **nonprofit workforce training pipeline** (heavy equipment operators: safety, hands-on operation, employer placement) that is **hosted or championed by Church of Nazarene congregations** in Florida. The program must support **disciplined execution** (daily outreach, enrollment, training, placement), **measurable outcomes**, and **controlled expansion** from a **single pilot** to **five active locations**, with a **pathway to engage 70+ churches** statewide as partners, sites, or referral nodes.

**Current focus:** **Single pilot** at Goulds; expansion workstreams are **documented but not active** until the pilot clears documented gates.

This PRD defines **what** must exist to succeed; companion documents define **execution**, **roadmap/budget**, and **dashboard/operations**.

---

## 2. Problem statement

- Entry-level candidates need **credentialed, safety-first training** and **employer connections** in construction, logistics, waste, and related sectors.
- Churches and community partners need a **repeatable operating model** (roles, cadence, metrics) so workforce ministry **scales without collapsing quality or compliance**.
- Leadership needs **visibility** across tasks, budget, and risks—without relying on ad hoc chat threads.

---

## 3. Goals & success measures

### 3.1 Pilot / Phase 1 (single site, ~30-day launch window to “operational”)

| Metric | Target (from source model; tune per locale) |
|--------|---------------------------------------------|
| Employer hiring partners | 3–5 committed |
| Cohort size | 10–15 students |
| Training status | Launched (classroom + supervised hands-on per curriculum) |
| Placement pipeline | Interviews secured for enrolled participants |
| Engagement | ≥75% cohort engagement (attendance + assignment completion) |
| Documentation | Daily/weekly logs; signed letters of support; grant/workforce submissions tracked |

### 3.2 Program depth (8–12 week training track)

| Metric | Target (source model) |
|--------|------------------------|
| Job placement rate | 75–80% (define “placed” in §8) |
| Starting wage band | Align to local market (e.g. $18–30/hr where applicable) |

### 3.3 Multi-site (5 locations)

- **Consistent** curriculum, safety, intake, and data reporting across sites.
- **Site-level** P&L visibility; **network-level** rollup for funders and governance.

### 3.4 Network (70+ Florida churches)

- Clear **partner tiers** (host, referral, employer connector, in-kind only)—each with minimum commitments and reporting.

---

## 4. Users & stakeholders

| User / stakeholder | Needs |
|--------------------|--------|
| **Students** | Clear eligibility, schedule, safety, job placement support |
| **Employers** | Predictable skill outputs, communication, interview pipeline |
| **Program Manager (PM)** | Single execution plan, task list, daily cadence, escalation path |
| **Executive Director / sponsor** | Funding, partnerships, narrative for donors and workforce boards |
| **Operations** | Site, equipment, logistics, vendor management |
| **Instructor(s)** | Curriculum, safety authority, student evaluation |
| **Admin** | Enrollment, CRM, reporting, document control |
| **Finance** | Budget vs actual, grant compliance, audit trail |
| **Church leadership (per site)** | Alignment with mission, facilities use, volunteer coordination |
| **State / regional church network** | Replication playbook, brand/governance, risk controls |

---

## 5. Scope

### 5.1 In scope

- **Recruit → Train → Certify → Place → Scale** operating model.
- **RACI** across ED, PM, Operations, Instructor, Admin.
- **Employer pipeline:** daily outreach cadence, partner agreements, interview scheduling.
- **Funding mix:** workforce boards, foundations, grants, employer partnerships (specific entities TBD by region).
- **Safety:** PPE, daily briefings, supervised hands-on (OSHA-aligned training as specified by curriculum).
- **Reporting:** enrollment, completion, placement, wages; narrative for funders.
- **Multi-site governance:** standards, audits, shared dashboard.
- **Communication loop:** responsible parties receive **task/reminder emails**; responses **update a central activity database** (see `DASHBOARD-AND-OPERATIONS.md`).

### 5.2 Out of scope (unless added later)

- Legal representation for employment disputes (refer out).
- Equipment purchase strategy without a capital sub-plan.
- Guaranteed job offers (pipeline and support, not placement guarantee unless contractually defined).

---

## 6. Functional requirements

| ID | Requirement |
|----|-------------|
| FR-1 | **Cohort management:** applications, screening, enrollment, roster, attendance. |
| FR-2 | **Employer CRM:** organizations, contacts, calls, follow-ups, outcomes (interview, hire). |
| FR-3 | **Daily PM cadence:** log ≥10 employer touches/day (or defined alternative KPI), team sync, daily report. |
| FR-4 | **Curriculum & safety:** lesson plans, evaluations, incident/near-miss reporting. |
| FR-5 | **Placement tracking:** interviews, offers, start dates, wage at hire. |
| FR-6 | **Document vault:** letters of support, MOUs, grant submissions, certifications. |
| FR-7 | **Multi-site:** site ID on every record; permissions by role and site. |
| FR-8 | **Dashboard:** tasks, milestones, budget lines, RAG (red/amber/green) status per workstream. |
| FR-9 | **Email bridge:** outbound notifications to owners; **inbound parsing or structured reply** to update task status (see technical notes in dashboard doc). |
| FR-10 | **Audit:** who changed what, when (especially financial and placement data). |

---

## 7. Non-functional requirements

| ID | Requirement |
|----|-------------|
| NFR-1 | **Reliability:** core data available during business hours; backups. |
| NFR-2 | **Security:** least-privilege roles; protect PII and financial data. |
| NFR-3 | **Compliance:** align with funder/grant retention rules; labor and training regulations as applicable. |
| NFR-4 | **Accessibility:** stakeholder-facing forms readable on mobile. |

---

## 8. Definitions & assumptions

- **“Operational” (30 days):** training calendar live, minimum enrolled cohort, employer pipeline active—not necessarily full 8–12 week completion.
- **“Placed”:** define as hired in-field within X days of completion, or industry apprenticeship—**must be fixed in v1.1**.
- **“Location”:** a church or partner facility with lead pastor/board approval, designated PM or site lead, and budget code.
- **Reconcile timelines:** marketing materials may cite **8–12 week** training while **launch** is a **30-day** sprint to operations—both can be true; PRD assumes **pilot launch** and **full cohort cycle** are tracked as separate milestones.

---

## 9. Risks & mitigations (program level)

| Risk | Mitigation |
|------|------------|
| Low employer uptake | Increase outreach volume, sector focus, warm intros via LBA-style orgs (local equivalents) |
| Enrollment shortfall | Community partners, church referral tiers, workforce referrals |
| Site / equipment delay | Early setup week; contingency site; rental strategy |
| Volunteer burnout | Clear RACI, paid PM/admin where possible, phased scale |
| Data chaos | Single dashboard + email workflow; weekly data review |
| Reputational (safety or placement claims) | Under-promise; documented safety SOPs; accurate metrics |

---

## 10. Dependencies

- Confirmed **training site** and **equipment access** (own, lease, partner).
- **Instructor** credentials and insurance.
- **501(c)(3)** or fiscal sponsor path for grants (validate per implementation).
- **Regional workforce** and **industry** relationships (Florida-specific pipeline).

---

## 11. Open questions (resolve before build)

1. ~~Fiscal sponsor vs independent nonprofit~~ — **Resolved:** existing church 501(c)(3) is the entity; marketing brand separate.
2. ~~Exact geography for pilot~~ — **Goulds, Miami**; **street address** still to file.
3. **Dashboard** — **Custom MVP** chosen: Next.js + Prisma + SQLite (see `CRM-MVP-SPEC.md`, scaffold under `crm/`). Airtable/Sheets remain fallback.
4. **Email-to-database** — **Deferred:** v1 uses exports / magic links when implemented; see `DASHBOARD-AND-OPERATIONS.md`.
5. **Placement definition** and **instructional hours** — **Open** until research closes (`RESEARCH-GATES-AND-GO-NO-GO.md`).

---

## 12. Document map

| Document | Purpose |
|----------|---------|
| `EXECUTION-PLAN.md` | Phases, tasks, benchmarks, QC, skills matrix |
| `ROADMAP-AND-BUDGET.md` | 3–5 years, five locations, 70+ church network, budget framework |
| `DASHBOARD-AND-OPERATIONS.md` | Dashboard, email loop, data model, reporting cadence |
| `BRIAN-CHARTER-WEEKS-1-4.md` | PM daily/weekly cadence, CRM fields, LOS tracker, board template |
| `RESEARCH-GATES-AND-GO-NO-GO.md` | Research backlog, cohort scheduling gates |
| `EARL-CREDENTIAL-AUDIT.md` | Instructor credential template |
| `EQUIPMENT-OPTIONS-MATRIX.md` | Equipment path comparison |
| `CRM-MVP-SPEC.md` | CRM scope, stack, roles |
| `../crm/README.md` | Runnable CRM scaffold |

---

## 13. Approval

| Role | Name | Date |
|------|------|------|
| Sponsor / ED | | |
| PM Lead | | |
| Finance | | |
