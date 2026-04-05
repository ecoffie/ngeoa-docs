# NGEOA Project — Full Scope & Build Plan

**Church:** New Life City Center (Goulds, Miami)
**Denomination:** Church of the Nazarene
**Program:** NGEOA (Heavy Equipment Operator Training)
**Maintainer:** Eric Coffie (primary), volunteer team (secondary)

---

## Current Status

### ✅ COMPLETED

| Component | URL | Status |
|-----------|-----|--------|
| **Church Website** | https://newlifecitycenter.org | ✅ Live |
| **NGEOA Website** | https://ngeoacademy.org | ✅ Live |
| **CRM Dashboard** | https://crm-eric-coffies-projects.vercel.app | ✅ Live |
| **Church Email** | info@newlifecitycenter.org | ✅ Active (forwards to evankoffdev@gmail.com) |
| **Domain: Church** | newlifecitycenter.org (Cloudflare) | ✅ Registered |
| **Domain: NGEOA** | ngeoacademy.org (Namecheap) | ✅ Registered |
| **QR Connect Page** | https://newlifecitycenter.org/connect | ✅ Live |
| **Supabase Database** | nlcc-crm (PostgreSQL) | ✅ Connected |
| **Friday Report Automation** | Cron + Puppeteer PDF | ✅ Deployed |

### ⏳ PENDING

| Component | Notes |
|-----------|-------|
| **NGEOA Email** | info@ngeoacademy.org |
| **Email delivery for forms** | Need Resend API key configured on Vercel |

---

## What We Built

| Component | Description | Priority | Status |
|-----------|-------------|----------|--------|
| **Church Website** | Public-facing site for New Life City Center | P1 | ✅ Done |
| **NGEOA Website** | Training program landing page (separate site) | P1 | ✅ Done |
| **Church Email** | info@newlifecitycenter.org | P1 | ✅ Done |
| **Internal CRM/Dashboard** | Contact tracking, pipeline, tasks, LOS tracking | P1 | ✅ Done |
| **QR /connect Page** | Yard sign QR landing with interest form | P1 | ✅ Done |
| **Supabase Database** | Cloud PostgreSQL for CRM persistence | P1 | ✅ Done |
| **Automated Friday Report** | PDF export + email delivery for board | P1 | ✅ Done |
| **NGEOA Email** | info@ngeoacademy.org | P2 | ⏳ Pending |
| **Mock Data Demo** | Show funders what the system will do with sample data | P2 | ⏳ Pending |
| **Cohort Outcome Tracking** | Track student placements post-completion | P2 | ⏳ Pending |

---

## User Model (Simplified)

| Role | Access | What They See |
|------|--------|---------------|
| **Admin (Eric/Claude)** | Full CRM access | Everything — input data, manage pipeline, generate reports |
| **Board/Pastor** | None (receive reports) | Friday PDF via email |
| **Public** | Website only | Church info, program info, application form |

**No login system needed for v1.** CRM is internal tool. Board gets emailed PDFs.

---

## Technical Stack

| Layer | Choice | Notes |
|-------|--------|-------|
| **Websites** | Next.js 16 (separate repos) | church-website + ngeoa-website |
| **CRM/Dashboard** | Next.js 15 + Prisma + PostgreSQL | Tailwind CSS 4 |
| **Database** | Supabase (PostgreSQL) | Cloud persistence for Vercel |
| **Email Provider** | Cloudflare Email Routing | Free forwarding |
| **Hosting** | Vercel | Custom domains configured |
| **PDF Generation** | Puppeteer + @sparticuz/chromium | Friday reports |
| **Transactional Email** | Resend | Form submissions (when configured) |

---

## Domain & Email Setup

### Live Domains

| Site | Domain | Registrar | DNS |
|------|--------|-----------|-----|
| **Church** | newlifecitycenter.org | Cloudflare | Vercel |
| **NGEOA** | ngeoacademy.org | Namecheap | Vercel |

### Email Structure

**Church (Active):**
- info@newlifecitycenter.org → evankoffdev@gmail.com

**NGEOA (Future):**
- info@ngeoacademy.org
- apply@ngeoacademy.org
- employers@ngeoacademy.org

### Social Media

- Facebook: [New Life City Center in Goulds](https://www.facebook.com/people/New-Life-City-Center-in-Goulds/61551355378531/)

---

## Website Pages

### Church Website (newlifecitycenter.org)

| Page | Path | Status |
|------|------|--------|
| Home | / | ✅ Done |
| About | /about | ✅ Done |
| Services | /services | ✅ Done |
| Ministries | /ministries | ✅ Done |
| Connect (QR / programs / form) | /connect | ✅ Done |
| Contact | /contact | ✅ Done |
| Give | /give | ✅ Done |

### NGEOA Website (ngeoacademy.org)

| Page | Path | Status |
|------|------|--------|
| Home | / | ✅ Done |
| Program | /program | ✅ Done |
| Apply | /apply | ✅ Done |
| Employers | /employers | ✅ Done |
| About | /about | ✅ Done |
| Contact | /contact | ✅ Done |

---

## CRM Dashboard Pages

| Page | Path | Status |
|------|------|--------|
| Dashboard Home | / | ✅ Done |
| Organizations | /organizations | ✅ Done |
| Add Organization | /organizations/new | ✅ Done |
| Organization Detail | /organizations/[id] | ✅ Done |
| Tasks | /tasks | ✅ Done |
| Add Task | /tasks/new | ✅ Done |
| Letters of Support | /letters | ✅ Done |
| Friday Report | /report | ✅ Done |
| PDF Generation API | /api/report/generate | ✅ Done |

---

## CRM Features

| Feature | Status |
|---------|--------|
| Organizations (employers, partners, funders) | ✅ Done |
| Pipeline stages (identified → documented) | ✅ Done |
| Contacts per organization | ✅ Done |
| Activity/touch logging | ✅ Done |
| Tasks with owners (Brian, Cynthia, Earl) | ✅ Done |
| Overdue task flagging | ✅ Done |
| Letters of Support tracking | ✅ Done |
| Friday Report with RAG status | ✅ Done |
| Print/PDF export | ✅ Done |
| Automated PDF generation (Puppeteer) | ✅ Done |
| Vercel cron (Fridays 2 PM UTC) | ✅ Done |
| Supabase cloud database | ✅ Done |

---

## QR Code Assets

Located in `church-website/public/qr/`:

| File | Size | Use |
|------|------|-----|
| `connect-qr-print.png` | 1200px | Yard sign (high-res print) |
| `connect-qr.svg` | Scalable | Any size without quality loss |
| `connect-qr-web.png` | 400px | Website/digital use |

**QR URL:** `newlifecitycenter.org/connect`

---

## Environment Variables

### CRM (Vercel)

| Variable | Description |
|----------|-------------|
| `DATABASE_URL` | Supabase pooler connection string |
| `DIRECT_URL` | Supabase direct connection string |
| `RESEND_API_KEY` | For Friday report email (optional) |
| `RESEND_FROM_EMAIL` | Sender address for reports |
| `REPORT_RECIPIENT_EMAIL` | Board/pastor email for reports |
| `CRON_SECRET` | Auth for cron endpoint |

### Church Website (Vercel)

| Variable | Description |
|----------|-------------|
| `RESEND_API_KEY` | For /connect form email |
| `RESEND_FROM_EMAIL` | Sender address |
| `CONNECT_NOTIFY_EMAIL` | Secretary email (default: info@newlifecitycenter.org) |

---

## Running Locally

### CRM
```bash
cd "/Users/ericcoffie/church of nazarene project/crm"
npm install
npx prisma generate
npm run dev
# Open http://localhost:3000
```

### Church Website
```bash
cd "/Users/ericcoffie/church of nazarene project/church-website"
npm install
npm run dev
# Open http://localhost:3000
```

### NGEOA Website
```bash
cd "/Users/ericcoffie/church of nazarene project/ngeoa-website"
npm install
npm run dev
# Open http://localhost:3000
```

---

## Deployment Commands

```bash
# Church Website
cd church-website && npm run build && npx vercel --prod --yes

# NGEOA Website
cd ngeoa-website && npm run build && npx vercel --prod --yes

# CRM Dashboard
cd crm && npm run build && npx vercel --prod --yes
```

---

## Brand Colors

| Color | Hex | Usage |
|-------|-----|-------|
| **Orange (Primary)** | #F7941D | CTAs, highlights, accents |
| **Navy (Secondary)** | #002868 | Headers, backgrounds |
| **Yellow (Accent)** | #FFD200 | Warnings, highlights |
| **Black** | #1A1A1A | Text |

---

## Next Steps

1. **Configure Resend** for email delivery (CRM reports + /connect form)
2. **Set up NGEOA email** (info@ngeoacademy.org)
3. **Seed mock data** for funder demos
4. **Print yard sign** with QR code

---

| Version | Date | Notes |
|---------|------|-------|
| 3.0 | 2026-04-05 | Supabase database + Friday PDF automation complete |
| 2.0 | 2026-04-04 | Updated with completed items and live URLs |
| 1.0 | 2026-04-04 | Initial scope from requirements call |
