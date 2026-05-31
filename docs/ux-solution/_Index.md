---
title: "AquaPlan UX Solution — Document Index"
status: final
last_updated: 2026-05-31
related_prd: "BPL-148"
source_issue: "BPL-150"
multica_epics:
  - "BPL-150"
related_screens:
  - home-dashboard
  - my-plans-list
  - settings-profile
  - plan-detail
  - empty-states
  - loading-states
  - error-states
---

# AquaPlan UX Solution — Document Index

> **Blueprint for Figma implementation** — all measurements in px, all tokens from the [Ocean Depth Palette](#), Major Third type scale, and 4px spacing grid.
> Reference: [BPL-148](mention://issue/ca83a738-a1b4-4e22-ab85-d90dafce218a) PRD vFinal (2026-05-30)
> Source: [BPL-150](mention://issue/70477c81-f864-4595-80fd-1d55abef5805) — Create Figma file for AquaPlan app based on PRD

---

## Document Map

| # | Document | Screens Covered | Responsive |
|---|---|---|---|
| 00 | [Design Rationale](00-design-rationale.md) | — | — |
| 01 | [Home Dashboard](01-home-dashboard.md) | Home Dashboard | Mobile 375px, Tablet 768px, Desktop 1024px+ |
| 02 | [My Plans List](02-my-plans-list.md) | Plans List, Search, Filters, Sort | Mobile 375px |
| 03 | [Settings / Profile](03-settings-profile.md) | Settings, Profile | Mobile 375px |
| 04 | [Plan Detail](04-plan-detail.md) | Plan Detail (Master-Detail) | Tablet 768px |
| 05 | [Desktop Home Dashboard](05-desktop-home-dashboard.md) | Home Dashboard (Desktop) | Desktop 1024px+ |
| 06 | [Empty States](06-empty-states.md) | Dashboard Empty, Plans Empty, Plan Detail Empty | Mobile 375px |
| 07 | [Loading & Processing States](07-loading-processing-states.md) | AI Generation, Image Analysis, Skeleton Screens | Mobile 375px |
| 08 | [Error States](08-error-states.md) | Connection Error, AI Failure, Validation Errors | Mobile 375px |
| 09 | [Animation Map](09-animation-map.md) | All screens — token reference | — |
| 10 | [Screen Transitions](10-screen-transitions.md) | Full app navigation flow | — |
| 11 | [Design Decisions](11-design-decisions.md) | Design Decision Rationale | — |

---

## Design Token Summary

| Token Category | Source | Values |
|---|---|---|
| **Color** | Ocean Depth Palette | abyss `#0B1E36`, deep `#1A3A5C`, reef `#2563EB`, shallows `#60A5FA`, surface `#E8F4FD` |
| **Accent** | Living Colors | coral `#F97316` (warnings), seagrass `#22C55E` (success), sand `#FCD34D` (caution), bubble `#A78BFA` (AI) |
| **Typography** | Major Third Scale | Fraunces (headings) + Inter (body), 12px–48px |
| **Spacing** | 4px Grid | 4, 8, 12, 16, 20, 24, 32, 40, 48, 56, 64, 80, 96, 120 |
| **Icons** | Lucide | 16px, 20px, 24px, 32px |
| **Motion** | Named tokens | ripple-tap (300ms), card-enter (400ms), ai-pulse (2000ms), confidence-reveal (500ms) |

---

## Responsive Breakpoints

| Breakpoint | Width | Grid | Navigation |
|---|---|---|---|
| Mobile | 375px | 4-column | Bottom Nav (64px H) |
| Tablet | 768px | 8-column | Sidebar (280px) + Content |
| Desktop | 1024px+ | 12-column (max 960px content) | Collapsible Sidebar (64px/320px) |

---

## Accessibility Reference

- Keyboard shortcuts documented per screen (see [Home Dashboard](01-home-dashboard.md) and [My Plans List](02-my-plans-list.md))
- Haptic feedback: light (card tap), medium (long-press context menu)
- Motion tokens with `prefers-reduced-motion` fallbacks
- WCAG 2.1 AA contrast ratios on all color pairs (Ocean Depth Palette verified)
- Focus indicators: reef-500 outline (2px) on all interactive elements
