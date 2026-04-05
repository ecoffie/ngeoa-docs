# New Life City Center / NGEOA — Design System

**Status:** Unified brand (using NGEOA logo until church logo is created)
**Program Full Name:** Next Generation Equipment Operators Academy

---

## Live Implementations

| Site | URL | Uses This Design System |
|------|-----|-------------------------|
| Church Website | https://newlifecitycenter.org | ✅ |
| NGEOA Website | https://ngeoacademy.org | ✅ |
| CRM Dashboard | https://crm-eric-coffies-projects.vercel.app | ✅ |

---

## Brand Colors

### Primary Palette

| Name | Hex | RGB | Usage |
|------|-----|-----|-------|
| **NGEOA Orange** | `#F7941D` | 247, 148, 29 | Primary accent, CTAs, highlights |
| **Black** | `#1A1A1A` | 26, 26, 26 | Primary text, headers |
| **White** | `#FFFFFF` | 255, 255, 255 | Backgrounds, reversed text |

### Secondary Palette

| Name | Hex | RGB | Usage |
|------|-----|-----|-------|
| **Equipment Yellow** | `#FFD200` | 255, 210, 0 | Accents, icons, equipment imagery |
| **Steel Gray** | `#4A4A4A` | 74, 74, 74 | Secondary text, borders |
| **Sky Blue** | `#E8F4FC` | 232, 244, 252 | Backgrounds, cards |
| **Navy Blue** | `#002868` | 0, 40, 104 | Headers, hero backgrounds |
| **Flag Red** | `#BF0A30` | 191, 10, 48 | Alerts, errors, patriotic accent |

### Functional Colors

| Name | Hex | Usage |
|------|-----|-------|
| **Success Green** | `#10B981` | Success states, completed |
| **Warning Amber** | `#F59E0B` | Warnings, in-progress |
| **Error Red** | `#EF4444` | Errors, blocked |
| **Info Blue** | `#3B82F6` | Information, links |

---

## Typography

### Font Stack

```css
/* Primary - Headers & Body */
font-family: 'Inter', 'Segoe UI', system-ui, -apple-system, sans-serif;

/* Monospace (code, data) */
font-family: 'JetBrains Mono', 'Fira Code', 'Consolas', monospace;
```

### Type Scale

| Name | Size | Weight | Usage |
|------|------|--------|-------|
| **Display** | 48px / 3rem | 700 | Hero headlines |
| **H1** | 36px / 2.25rem | 700 | Page titles |
| **H2** | 30px / 1.875rem | 600 | Section headers |
| **H3** | 24px / 1.5rem | 600 | Subsection headers |
| **H4** | 20px / 1.25rem | 600 | Card titles |
| **Body** | 16px / 1rem | 400 | Paragraph text |
| **Body Small** | 14px / 0.875rem | 400 | Secondary text, captions |
| **Caption** | 12px / 0.75rem | 400 | Labels, metadata |

---

## Tailwind CSS 4 Implementation

Both websites use Tailwind CSS 4 with this configuration:

```css
/* globals.css */
@import "tailwindcss";

@theme {
  --color-primary: #F7941D;
  --color-secondary: #002868;
}
```

### Button Classes

```css
.btn-primary {
  @apply bg-[#F7941D] hover:bg-orange-600 text-white font-semibold py-3 px-6 rounded-lg transition-colors;
}

.btn-secondary {
  @apply bg-[#002868] hover:bg-blue-900 text-white font-semibold py-3 px-6 rounded-lg transition-colors;
}

.btn-outline {
  @apply border border-gray-300 hover:bg-gray-50 text-gray-700 font-semibold py-3 px-6 rounded-lg transition-colors;
}
```

---

## Component Patterns

### Hero Section (Navy gradient)

```jsx
<section className="bg-gradient-to-br from-[#002868] to-[#001a4d] text-white py-24">
  <h1 className="text-4xl md:text-5xl font-bold">
    Title <span className="text-[#F7941D]">Highlighted</span>
  </h1>
</section>
```

### Stats Bar (Orange)

```jsx
<section className="bg-[#F7941D] py-12">
  <div className="text-white text-center">
    <div className="text-3xl font-bold">$45K+</div>
    <div className="text-white/80">Average Starting Salary</div>
  </div>
</section>
```

### Card Grid

```jsx
<div className="bg-white rounded-xl p-6 shadow-sm hover:shadow-md transition-shadow">
  <div className="text-4xl mb-4">🚜</div>
  <h3 className="text-xl font-semibold text-[#1A1A1A]">Title</h3>
  <p className="mt-2 text-gray-600">Description</p>
</div>
```

---

## Pipeline Stage Colors (CRM)

| Stage | Background | Text | Tailwind |
|-------|------------|------|----------|
| Identified | `#F3F4F6` | `#1F2937` | `bg-gray-100 text-gray-800` |
| Contacted | `#DBEAFE` | `#1E40AF` | `bg-blue-100 text-blue-800` |
| Conversation | `#FEF3C7` | `#92400E` | `bg-yellow-100 text-yellow-800` |
| Committed | `#D1FAE5` | `#065F46` | `bg-green-100 text-green-800` |
| Documented | `#D1FAE5` | `#065F46` | `bg-emerald-100 text-emerald-800` |
| Paused | `#FFEDD5` | `#9A3412` | `bg-orange-100 text-orange-800` |
| Lost | `#FEE2E2` | `#991B1B` | `bg-red-100 text-red-800` |

---

## Logo Files

### Current (Simple Text Logo)

| File | Location | Usage |
|------|----------|-------|
| favicon.svg | `/public/favicon.svg` | Browser tab icon |
| logo.svg | `/public/logo.svg` | Header (not used) |

### Future (Full NGEOA Logo)
- [ ] `logo-full-color.svg` — Primary
- [ ] `logo-full-color.png` — Fallback (transparent)
- [ ] `logo-white.svg` — For dark backgrounds
- [ ] `logo-icon.svg` — Equipment only (small uses)

---

## Accessibility

- All text meets WCAG 2.1 AA contrast ratios
- Primary orange (#F7941D) on white: Use for large text only (3:1)
- For body text on white: Use black (#1A1A1A) (15:1)
- Orange buttons: White text (#FFFFFF)

---

| Version | Date | Notes |
|---------|------|-------|
| 2.0 | 2026-04-04 | Updated with live site implementations |
| 1.0 | 2026-04-04 | Initial design system from NGEOA logo |
