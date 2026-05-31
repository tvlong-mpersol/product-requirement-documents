---
status: final
last_updated: 2026-05-30
product: AquaPlan
type: Cross-platform AI-assisted aquarium & paludarium planner
platforms: [Web, Mobile, iPad]
multica_issues:
  - BPL-148
  - BPL-150
---

# AquaPlan — Documentation Index

> **AI SYSTEM INSTRUCTION:** This index maps all AquaPlan product documentation. The PRD covers all four core pillars (Style Guide, Business Context, UX/UI Flow, Unhappy Paths) in a single comprehensive document. For design implementation, see the Figma file created under BPL-150.

## 📄 Documents

| Document | Description | Multica Task |
|---|---|---|
| [BPL-148-aquaplan-prd.md](./BPL-148-aquaplan-prd.md) | Complete Product Requirements Document — business context, style guide, UX/UI flows with ASCII wireframes, and unhappy path handling | [BPL-148](mention://issue/ca83a738-a1b4-4e22-ab85-d90dafce218a) |

## 🗂️ PRD Table of Contents

1. **[Business Context](./BPL-148-aquaplan-prd.md#1-business-context)**
   - 1.1 Market Opportunity
   - 1.2 Competitor Landscape
   - 1.3 Differentiation Thesis
   - 1.4 Success Metrics

2. **[Global Style Guide](./BPL-148-aquaplan-prd.md#2-global-style-guide)**
   - 2.1 Design Philosophy — "The Zen of Water"
   - 2.2 Color Palette — Ocean Depth Palette + Living Accents
   - 2.3 Typography — Fraunces + Inter, Major Third scale
   - 2.4 Iconography — Lucide
   - 2.5 Spacing Scale — 4px base grid
   - 2.6 Border Radius
   - 2.7 Shadows
   - 2.8 Component Library Direction — Material 3 / Radix UI + Tailwind
   - 2.9 Illustration Style — Watercolor botanical
   - 2.10 Motion Language — Ripple, Card Enter, AI Pulse, Confidence Reveal

3. **[UX/UI Flow](./BPL-148-aquaplan-prd.md#3-uxui-flow)**
   - 3.1 Sitemap
   - 3.2 Core User Journeys
     - Journey 1: Onboarding Wizard (6 steps)
     - Journey 2: Plan Detail (accordion tabs + timeline)
     - Journey 3: Image → Plan (camera → AI analysis)
     - Journey 4: Q&A Chat
   - 3.3 Responsive Layouts
   - 3.4 Figma Design Specifications

4. **[Unhappy Path Handling](./BPL-148-aquaplan-prd.md#4-unhappy-path-handling)**
   - 4.1 AI Hallucination Risks
   - 4.2 Image Recognition Failures
   - 4.3 User Input Inconsistencies
   - 4.4 Offline & Persistence
   - 4.5 Paludarium-Specific Risks
   - 4.6 Legal & Ethical

## 🔗 Related Multica Tasks

| Task | Description | Status |
|---|---|---|
| [BPL-148](mention://issue/ca83a738-a1b4-4e22-ab85-d90dafce218a) | AquaPlan PRD — Research & Drafting | Final |
| [BPL-150](mention://issue/70477c81-f864-4595-80fd-1d55abef5805) | Create Figma file based on PRD | Done |

## 🎨 Design Tokens Summary

- **Palette:** Ocean Depth (abyss #0B1E36 → surface #E8F4FD)
- **Accents:** Coral #F97316, Seagrass #22C55E, Sand #FCD34D, Bubble #A78BFA
- **Type:** Fraunces (headings) + Inter (body), Major Third scale (12px–48px)
- **Grid:** 4px spacing, 8px border radius base
- **Icons:** Lucide
