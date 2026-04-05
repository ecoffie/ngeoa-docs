# CRM / Dashboard MVP — Scope, Stack, and Roles

**Context:** Pilot at **Goulds (Miami), Church of the Nazarene**; team wants a **simple** tool because stakeholders are **not highly computer-savvy**. **v1 visibility:** default to **safest** — **aggregates** for pastors/funders; **PII** (student names, contacts) restricted to **core** until policy is finalized.

---

## 1. MVP scope (must ship)

| Module | Features |
|--------|----------|
| **Contacts** | Organizations (employers, partners); people; `pipeline_stage`; notes; `next_action` + due date |
| **Tasks** | Title, owner (Brian, Cynthia, Earl, other), due date, status (open/done/blocked) |
| **Letters of support** | Org, status, requested date, file link |
| **Weekly snapshot** | Export or print: touch counts, pipeline stage counts, LOS status, RAG |
| **Roles** | `core` (full detail) vs `stakeholder` (aggregates only) — see §4 |

**Deferred (v2):** email parse-from-reply; full accounting; student enrollment module (can be spreadsheet until gates clear).

---

## 2. Recommended stack (chosen for this implementation)

| Layer | Choice | Rationale |
|-------|--------|-----------|
| **App** | **Next.js** (App Router) + **TypeScript** | One codebase; easy to host; forms and dashboards are first-class |
| **Database** | **SQLite** via **Prisma** (file `data/ngeoa.db` or env `DATABASE_URL`) | No separate DB server for a small volunteer team; backup = copy file |
| **Auth** | **NextAuth.js** credentials or a **shared password** for `core` + separate **read-only** link/token for stakeholders | Keeps MVP simple; upgrade to OAuth later |
| **Email** | **Resend** or **SMTP** (optional v1.1) | Weekly digest automation |
| **Hosting** | **Vercel** (or any Node host) | Matches PRD note; SQLite on serverless may need **Turso/libsql** if you outgrow single instance — migrate when needed |

**Alternative (zero code):** **Airtable** or **Google Sheets + Apps Script** — use if no one can deploy. Tradeoff: weaker RBAC unless paid tiers.

**This repo:** Scaffold lives under [`/Users/ericcoffie/church of nazarene project/crm/`](../crm/) — see `crm/README.md`.

---

## 3. Data entities (aligns with `DASHBOARD-AND-OPERATIONS.md`)

- `Organization` — type employer | partner | funder | other  
- `Contact` — linked to org  
- `Activity` / touch log — date, type, notes  
- `Task` — assignee, due, status  
- `LetterOfSupport` — org, status, dates  
- `User` — role `core` | `stakeholder`

---

## 4. Role-based visibility (v1 default)

| Data | `core` | `stakeholder` |
|------|--------|-----------------|
| Employer names & contacts | Yes | **Summary only** (counts by stage) unless board opts in |
| Student PII | When module exists | **No** |
| Tasks | Yes | **Milestone counts** / RAG |
| Budget | If added later | **Aggregate** |

Board can **widen** stakeholder access in writing; update this doc when they do.

---

## 5. Email workflow (later)

- **v1:** Manual “export PDF / screenshot” for Friday board packet.  
- **v1.1:** Magic link “mark task done” from email.  
- **v2:** Inbound parse webhook.

---

## 6. Success criteria for “CRM MVP done”

- [ ] Brian can log **10 touches/day** without friction  
- [ ] Friday **one-pager** can be produced in &lt; 10 minutes  
- [ ] **Stakeholder** login shows **no** raw employer PII unless toggled  
- [ ] SQLite file is **backed up** weekly (church policy)

---

| Version | Date | Notes |
|---------|------|-------|
| 1.0 | 2026-04-04 | Stack + scope locked for implementation |
