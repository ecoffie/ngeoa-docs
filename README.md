# Church Workforce Academy — Documentation Index

Florida **Goulds (Miami), Church of the Nazarene** pilot for **Next Generation Equipment Operators Academy** (NGEOA — marketing name; church is the legal entity).

## Live Sites

| Site | URL | Status |
|------|-----|--------|
| **Church Website** | https://newlifecitycenter.org | ✅ Live |
| **NGEOA Academy** | https://ngeoacademy.org | ✅ Live |
| **CRM Dashboard** | https://crm-eric-coffies-projects.vercel.app | ✅ Live (local SQLite for data) |

## Email

| Address | Forwards To | Status |
|---------|-------------|--------|
| info@newlifecitycenter.org | evankoffdev@gmail.com | ✅ Active |

---

## Living plan (discovery synced)

| Document | Description |
|----------|-------------|
| [**PRD-Workforce-Academy.md**](./PRD-Workforce-Academy.md) | Product requirements, discovery context, document map |
| [**EXECUTION-PLAN.md**](./EXECUTION-PLAN.md) | Phases, RACI (Brian / Earl / Cynthia), benchmarks, QC, skills |
| [**ROADMAP-AND-BUDGET.md**](./ROADMAP-AND-BUDGET.md) | 3–5 year framework; multi-site/network **on hold** until pilot gates |
| [**DASHBOARD-AND-OPERATIONS.md**](./DASHBOARD-AND-OPERATIONS.md) | Operations, data model, email strategy; points to CRM MVP |

## Operational playbooks

| Document | Description |
|----------|-------------|
| [**BRIAN-CHARTER-WEEKS-1-4.md**](./BRIAN-CHARTER-WEEKS-1-4.md) | PM weekly cadence, 10 touches/day, LOS targets, CRM fields, board one-pager |
| [**RESEARCH-GATES-AND-GO-NO-GO.md**](./RESEARCH-GATES-AND-GO-NO-GO.md) | Research backlog + **cohort scheduling gates** |
| [**EARL-CREDENTIAL-AUDIT.md**](./EARL-CREDENTIAL-AUDIT.md) | Instructor credential template |
| [**EQUIPMENT-OPTIONS-MATRIX.md**](./EQUIPMENT-OPTIONS-MATRIX.md) | Donate / loan / rent / partner yard |
| [**CRM-MVP-SPEC.md**](./CRM-MVP-SPEC.md) | CRM scope, stack, roles |

## Project Setup

| Document | Description |
|----------|-------------|
| [**PROJECT-SCOPE.md**](./PROJECT-SCOPE.md) | Full project scope and build plan |
| [**DESIGN-SYSTEM.md**](./DESIGN-SYSTEM.md) | Colors, typography, components |
| [**BRAND-PROTECTION-CHECKLIST.md**](./BRAND-PROTECTION-CHECKLIST.md) | Domain registration checklist |

## Code

| Path | Description | URL |
|------|-------------|-----|
| [`../church-website/`](../church-website/) | New Life City Center website | https://newlifecitycenter.org |
| [`../ngeoa-website/`](../ngeoa-website/) | NGEOA Academy website | https://ngeoacademy.org |
| [`../crm/`](../crm/README.md) | Next.js + Prisma + SQLite CRM | https://crm-eric-coffies-projects.vercel.app |

---

## Quick Start

### Run CRM Locally (with data persistence)
```bash
cd crm
npm install
npx prisma generate
npx prisma db push
npm run dev
# Open http://localhost:3000
```

### Deploy Updates
```bash
# Church site
cd church-website && npm run build && npx vercel --prod --yes

# NGEOA site
cd ngeoa-website && npm run build && npx vercel --prod --yes

# CRM
cd crm && npm run build && npx vercel --prod --yes
```

---

**Suggested reading order:** PRD → `BRIAN-CHARTER-WEEKS-1-4` → `RESEARCH-GATES-AND-GO-NO-GO` → CRM spec → `crm/README.md`.

| Version | Date | Notes |
|---------|------|-------|
| 2.0 | 2026-04-04 | Updated with live URLs and current status |
| 1.0 | 2026-04-04 | Initial documentation index |
