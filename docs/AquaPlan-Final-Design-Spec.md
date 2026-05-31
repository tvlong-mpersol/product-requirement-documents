---
title: "AquaPlan — Final Design Specification"
status: final
last_updated: 2026-05-31
related_prd: "BPL-148"
source_issue: "BPL-150"
multica_epics:
  - "BPL-148"
  - "BPL-150"
related_screens:
  - home-dashboard
  - my-plans-list
  - settings-profile
  - plan-detail
  - onboarding-wizard
  - image-to-plan
  - qa-chat
  - empty-states
  - loading-states
  - error-states
  - animation-map
document_owner: "Doc-Housekeeper"
audience: "Figma implementation team, frontend engineering"
---

# AquaPlan — Final Design Specification

> **Authoritative design spec for Figma file generation.** Cross-platform AI-assisted aquarium & paludarium planner app (Web, Mobile, iPad).  
> Source PRD: [BPL-148](mention://issue/ca83a738-a1b4-4e22-ab85-d90dafce218a) | Wireframes Issue: [BPL-150](mention://issue/70477c81-f864-4595-80fd-1d55abef5805)

---

## Document Structure

This specification compiles all four PRD gates into a single authoritative document:

| Gate | Section | Source | Detail |
|------|---------|--------|--------|
| 1 | [Business Context](#1-business-context) | PRD §1 | Market data, competitor landscape, differentiation thesis, success metrics |
| 2 | [Global Style Guide](#2-global-style-guide) | PRD §2 | Ocean Depth Palette, typography, spacing, icons, motion, components |
| 3 | [UX/UI Flow](#3-uxui-flow) | PRD §3 + Expanded Wireframes | Sitemap, core journeys, responsive layouts, expanded screen specs |
| 4 | [Unhappy Path Handling](#4-unhappy-path-handling) | PRD §4 | AI hallucination, image failures, offline/persistence, paludarium risks, legal |

### Modular Documentation Map

Gate 3 (UX/UI Flow) is supported by 13 modular documents in [`docs/ux-solution/`](docs/ux-solution/_Index.md):

| # | Document | Content |
|---|----------|---------|
| 00 | [Design Rationale](docs/ux-solution/00-design-rationale.md) | Competitor UX gap analysis |
| 01 | [Home Dashboard](docs/ux-solution/01-home-dashboard.md) | Mobile / Tablet / Desktop wireframes, interaction flows, keyboard shortcuts |
| 02 | [My Plans List](docs/ux-solution/02-my-plans-list.md) | Search, filter chips, sort, swipe actions |
| 03 | [Settings / Profile](docs/ux-solution/03-settings-profile.md) | Grouped settings hierarchy |
| 04 | [Plan Detail](docs/ux-solution/04-plan-detail.md) | Tablet master-detail layout, draggable divider |
| 05 | [Desktop Home Dashboard](docs/ux-solution/05-desktop-home-dashboard.md) | 12-column grid, collapsible sidebar (64px/320px) |
| 06 | [Empty States](docs/ux-solution/06-empty-states.md) | Welcome, No Plans, Empty Q&A, Empty Search |
| 07 | [Loading & Processing States](docs/ux-solution/07-loading-processing-states.md) | AI pulse, Image Scan overlay, Skeleton cards |
| 08 | [Error States](docs/ux-solution/08-error-states.md) | Offline banner, AI Unavailable, Image Not Recognized |
| 09 | [Animation Map](docs/ux-solution/09-animation-map.md) | 14 motion tokens, 7 haptic points, transition map, gesture zones |
| 10 | [Screen Transitions](docs/ux-solution/10-screen-transitions.md) | Full app navigation flow map |
| 11 | [Design Decisions](docs/ux-solution/11-design-decisions.md) | Design decision rationale |

> **Note for Figma implementation:** The modular documents contain pixel-accurate ASCII wireframes with measurement annotations. All tokens reference the Ocean Depth Palette, Major Third type scale, and 4px spacing grid defined in [Gate 2](#2-global-style-guide).

---

## 1. Business Context

### 1.1 Market Opportunity

The aquarium hardware market is valued at **$12.63B (2023) → $19.2B by 2031** (CAGR 6.17%). Household segment holds 66.18% share ($8.36B, 2024). Asia-Pacific leads with 34.37% market share. 14.7M US households own pet fish. Up to 90% of marine aquarium fish are wild-caught — a growing sustainability concern.

### 1.2 Competitor Landscape

**7 Key Players (Web/Content):**

| Competitor | Type | Strengths | Gaps |
|---|---|---|---|
| **AqAdvisor** | Free stocking calculator | Compatibility algorithm, shareable URLs | No AI, no image recognition, no paludarium, no mobile |
| **Tropica** | Plant authority | Easy/Medium/Advanced difficulty symbols | Content-only, no planning tools, no AI |
| **Aquarium Co-Op** | Content + ecommerce | YouTube community, strong SEO | No app, no planning tool, no AI |
| **Buce Plant** | Ecommerce | High-quality plant photos, strong community | Pure ecommerce, zero planning features |
| **2Hr Aquarist** | Blog | Science-based aquascaping guides | Blog only, no tools, intermediate+ audience |
| **Practical Fishkeeping** | Magazine | Expert Q&A, gear reviews | Paywall (£5.99/mo), no tools |
| **Borneo IoT** (GitHub ★74) | Open-source hardware | LED PWM controller (Flutter) | Hardware-only, zero planning/AI |

**Direct App Competitors:**

| Competitor | Type | Strengths | Gaps |
|---|---|---|---|
| **Aquarium AI** | AI chatbot + fish ID | Harmony Score™, BYO AI keys | Requires user's own API key |
| **AquaLens** | Water test + fish ID | Freemium, most feature-complete tracker | No beginner education, no paludarium |
| **Aquabuildr** | Stocking builder | Pre-built tanks, compatibility algorithm | No AI features |
| **Danio** (GitHub, unreleased) | Flutter edu app | 72 lessons, gamification, GPT-4o | Unreleased, freshwater-only |
| **cd-caio/aquarium-builder** | 3D tank builder | Three.js, paludarium support | Single-file hobby project, Portuguese-only, no AI |

**Key finding:** 363 aquarium app repos on GitHub — all <10 stars except Borneo IoT. Zero paludarium apps commercially. **No production-ready AI aquarium planner exists.**

### 1.3 Differentiation Thesis

1. **No one combines AI planning + image recognition + Q&A in one app.** Market is fragmented across content sites, calculators, and ecommerce. AI-first unified experience has zero direct competitors.
2. **Paludarium is a blue ocean.** No app, tool, or planning resource exists for paludarium builders. First mover captures an untapped, fast-growing niche.
3. **"I saw this tank, help me replicate it" is unserved.** Current workflow: see photo → post on Reddit → wait hours/days → manually research → still unsure. AI reduces days to seconds.
4. **Material reuse logic is novel.** No tool asks "what do you already have?" and minimizes new purchases — directly addressing beginner budget concerns.
5. **Free + cross-platform (Flutter/React) is the right wedge.** All prominent tools are web-only or content sites. Free installable app captures the massive beginner audience.

### 1.4 Success Metrics

| Pattern | Why It Works | Reference |
|---|---|---|
| Algorithmic compatibility checking | Beginner's #1 fear is killing fish; warnings build trust | AqAdvisor |
| Difficulty-tiered guidance | Removes decision paralysis for newcomers | Tropica |
| Community + content flywheel | YouTube + blog builds loyalty → repeat visits → purchases | Aquarium Co-Op |
| Shareable/bookmarkable plans | Drive organic growth via forums, Reddit | AqAdvisor |
| Visual-first presentation | High-quality images sell the dream before the product | Buce Plant |

---

## 2. Global Style Guide

### 2.1 Design Philosophy

**"The Zen of Water"** — The interface must embody the same calm, clarity, and natural balance that an aquarium brings to a room. Beginners come anxious about mistakes that harm living creatures. The design must radiate trust, simplicity, and gentle guidance — never overwhelming.

**Core Principles:**
- **Calm > Exciting** — Muted ocean tones, generous whitespace, deliberate pacing
- **Guide > Dictate** — Suggestions, not commands. Explain the "why" behind every recommendation
- **Progress > Perfection** — Celebrate small wins. "Your tank is cycling!" beats "Complete these 47 steps"
- **Transparent > Magical** — Always show AI confidence scores. Never hide uncertainty

### 2.2 Color Palette

**Ocean Depth Palette (Primary):**

| Token | Hex | Use |
|---|---|---|
| `--color-abyss` | `#0B1E36` | Nav bars, footers, deep backgrounds |
| `--color-deep` | `#1A3A5C` | Card backgrounds, secondary surfaces |
| `--color-reef` | `#2563EB` | Primary actions, links, active states |
| `--color-shallows` | `#60A5FA` | Hover states, secondary accents |
| `--color-surface` | `#E8F4FD` | Light backgrounds, inputs |

**Living Element Accents:**

| Token | Hex | Use |
|---|---|---|
| `--color-coral` | `#F97316` | Warnings, compatibility alerts, destructive actions |
| `--color-seagrass` | `#22C55E` | Success, safe/compatible indicators, confirmed steps |
| `--color-sand` | `#FCD34D` | Caution, medium confidence, "needs attention" |
| `--color-bubble` | `#A78BFA` | AI features, generation states, chat bubbles |

**Light / Dark Mode Semantic Tokens:**

| Token | Light | Dark |
|---|---|---|
| `--bg-primary` | `#FFFFFF` | `#0B1E36` |
| `--bg-secondary` | `#E8F4FD` | `#1A3A5C` |
| `--text-primary` | `#0B1E36` | `#F8FAFC` |
| `--text-secondary` | `#475569` | `#94A3B8` |
| `--border` | `#CBD5E1` | `#334155` |

### 2.3 Typography

**Font Stack:**
- **Headings:** Fraunces (serif, warmth + authority) — weights 400, 600, 700
- **Body:** Inter (sans-serif, legibility at small sizes) — weights 400, 500, 600

**Scale (Major Third, 1.25):**

| Token | Size | Line Height | Use |
|---|---|---|---|
| `--text-xs` | 12px | 16px | Captions, confidence badges |
| `--text-sm` | 14px | 20px | Secondary text, metadata |
| `--text-base` | 16px | 24px | Body, inputs, list items |
| `--text-lg` | 20px | 28px | Card titles, emphasized body |
| `--text-xl` | 25px | 32px | Section headers |
| `--text-2xl` | 31px | 40px | Page titles (mobile) |
| `--text-3xl` | 39px | 48px | Page titles (desktop) |
| `--text-4xl` | 48px | 56px | Hero, onboarding headlines |

### 2.4 Iconography

**Library:** Lucide Icons (MIT-licensed, consistent 1px stroke, 24×24 viewBox)

**Key Mappings:**

| Screen/Feature | Icon |
|---|---|
| Home | `layout-dashboard` |
| My Plans | `clipboard-list` |
| New Plan | `plus-circle` |
| Q&A Chat | `message-circle` |
| Settings | `settings` |
| Tank | `waves` |
| Plant | `sprout` |
| Fish | `fish` |
| AI | `sparkles` |
| Camera/Capture | `camera` |
| Warning | `alert-triangle` |
| Success/Check | `check-circle` |

### 2.5 Spacing Scale

4px base unit: `4, 8, 12, 16, 20, 24, 32, 40, 48, 56, 64, 80, 96, 120`

### 2.6 Border Radius

| Token | Value | Use |
|---|---|---|
| `--radius-sm` | 4px | Inputs, badges, small chips |
| `--radius-md` | 8px | Cards, dialogs, buttons |
| `--radius-lg` | 12px | Modals, image containers |
| `--radius-xl` | 16px | Large cards, onboarding screens |
| `--radius-full` | 9999px | Pills, avatar, progress indicators |

### 2.7 Shadows

| Token | Value | Use |
|---|---|---|
| `--shadow-sm` | `0 1px 2px rgba(11,30,54,0.05)` | Cards (light mode) |
| `--shadow-md` | `0 4px 6px rgba(11,30,54,0.07)` | Elevated cards, dropdowns |
| `--shadow-lg` | `0 10px 15px rgba(11,30,54,0.1)` | Modals, sheets |
| `--shadow-glow` | `0 0 20px rgba(167,139,250,0.4)` | AI generation pulse |

### 2.8 Component Library Direction

- **Flutter:** Material 3 theming with custom `aquaplan_theme` extension on `ThemeData`. `ColorScheme.fromSeed()` with abyss-primary. Custom `AIConfidenceBadge`, `PlanCard`, `TankTypeSelector` widgets.
- **React:** Tailwind CSS with custom `aquaplan` preset extending default theme. Radix UI primitives (Dialog, Tabs, Select, Tooltip) with the Zen of Water design tokens mapped to Tailwind config.

### 2.9 Illustration Style

- Watercolor-inspired botanical illustrations for empty states and onboarding
- Gradient mesh backgrounds evoking underwater light rays (caustics)
- Subtle animated SVG elements (floating bubbles, swaying plants)

### 2.10 Motion Language

| Motion | Duration | Easing | Use |
|---|---|---|---|
| Ripple tap | 300ms | `ease-out` | Button press feedback |
| Card enter | 400ms | `ease-out` | Staggered list appearance |
| Page transition | 250ms | `ease-in-out` | Navigation pushes |
| AI pulse | 2000ms | `ease-in-out` (loop) | Generation/waiting state glow |
| Bubble float | 3000ms | `linear` (loop) | Ambient background animation |
| Confidence reveal | 500ms | `ease-out` | Score percentage fill |

---

## 3. UX/UI Flow

### 3.1 Sitemap

```
Home Dashboard
├── Create New Plan (Onboarding Wizard)
│   ├── Step 1: Welcome & Project Name
│   ├── Step 2: Tank Type (Aquarium / Paludarium / Riparium)
│   ├── Step 3: Tank Size & Dimensions
│   ├── Step 4: Existing Materials (What do you already have?)
│   ├── Step 5: Goals & Preferences (Fish-only, Planted, Community, Biotope)
│   └── Step 6: AI Generation → Plan Created
├── My Plans (List)
│   └── Plan Detail
│       ├── Reference Image
│       ├── Materials Tab (Livestock, Plants, Hardscape, Equipment)
│       ├── Setup Steps Tab (Day-by-day timeline)
│       ├── Schedule Tab (Maintenance calendar)
│       └── Notes Tab
├── Image → Plan (Quick Capture)
│   ├── Camera / Photo Library
│   ├── AI Analysis (Scan overlay with progress)
│   ├── Identified Materials (with confidence scores)
│   └── Generate Plan
├── Q&A Chat
│   ├── Suggested Questions
│   ├── Chat Thread
│   └── Feedback (👍👎)
└── Settings / Profile
```

### 3.2 Core User Journeys

#### Journey 1: Onboarding — Create First Plan

**Screen: [Onboarding Wizard — Step 1 (Welcome)](docs/ux-solution/01-home-dashboard.md)**

1. User selects Tank Type (Aquarium / Paludarium / Riparium) from three illustrated cards
2. Sets tank size via slider (5–150 gal) + dimension inputs (L×W×H)
3. Selects existing materials from multi-select chips (Tank, Filter, Heater, Lights, Substrate, Hardscape, Plants, Livestock)
4. Chooses goals from checkbox options (Low-maintenance, Shrimp-safe, Breeding, Show tank, Budget-friendly)
5. AI Generation screen with ripple animation, "Crafting your plan..." and rotating tips
6. Plan Created → navigates to Plan Detail

> **Implemented in Task** [BPL-148](mention://issue/ca83a738-a1b4-4e22-ab85-d90dafce218a) | **Expanded wireframes in** [BPL-150](mention://issue/70477c81-f864-4595-80fd-1d55abef5805)

#### Journey 2: Plan Detail

**Screen: [Plan Detail](docs/ux-solution/04-plan-detail.md)**

- Hero reference image (200px height, AI-generated aquarium visualization)
- Overall compatibility score badge (🟢/🟡/🔴 with percentage)
- Tab bar: Materials | Setup Steps | Schedule | Notes
- Accordion sections: Livestock, Plants, Hardscape, Equipment — each with compatibility indicators (✓ compatible, ⚠️ warning, tap for details)
- Floating action: "Ask AI about this plan"

#### Journey 3: Image → Plan

**Screen: [Image → Plan](docs/ux-solution/07-loading-processing-states.md)**

- Camera viewfinder with animated focus frame corner brackets
- Photo library picker alternative
- Tips overlay: "Photograph whole tank", "Good lighting helps", "Get close to plants"
- AI Analysis screen: scan overlay with progress, staggered result reveals
- Results: Material cards with confidence badges (🟢 >85%, 🟡 70–85%, 🔴 <70%)
- "Add to plan" toggle per item → "Generate full plan" CTA

#### Journey 4: Q&A Chat

**Screen: [Q&A Chat](docs/ux-solution/06-empty-states.md)**

- Suggested question chips (horizontal scroll)
- Chat thread with Markdown-rendered bot responses
- User messages (right-aligned) with optional auto-detected context
- Feedback row: 👍👎 after each bot response
- Input bar with send button at bottom

### 3.3 Responsive Layouts

| Breakpoint | Width | Grid | Navigation | Expanded Spec |
|---|---|---|---|---|
| Mobile | 375px–767px | 4-column, 16px margin/gutter | Bottom Nav (64px H, 5 tabs) | [01 Home Dashboard](docs/ux-solution/01-home-dashboard.md) |
| Tablet | 768px–1023px | 8-column, 24px margin/gutter | Sidebar (280px) + Content | [04 Plan Detail](docs/ux-solution/04-plan-detail.md) |
| Desktop | 1024px+ | 12-column (max 960px content) | Collapsible Sidebar (64px/320px) | [05 Desktop Home](docs/ux-solution/05-desktop-home-dashboard.md) |

### 3.4 Expanded Screen Coverage

The modular documents in [`docs/ux-solution/`](docs/ux-solution/_Index.md) provide pixel-accurate wireframes for all states:

| Document | Screens | Key Specifications |
|---|---|---|
| [01 Home Dashboard](docs/ux-solution/01-home-dashboard.md) | Home Dashboard (Mobile/Tablet/Desktop) | 3 breakpoints, keyboard shortcuts (`Ctrl+N`, `Ctrl+I`, `Ctrl+K`), Quick Start cards (140×120px), Recent Plans carousel (260×160px), Daily Tip card, Quick Stats row |
| [02 My Plans List](docs/ux-solution/02-my-plans-list.md) | Plans List, Search, Filters | Search bar with 300ms debounce, filter chips (OR logic, horizontal scroll), swipe actions (Share/Duplicate/Delete), sort dropdown, long-press context menu |
| [03 Settings / Profile](docs/ux-solution/03-settings-profile.md) | Settings, Profile | Grouped sections with hierarchy, profile photo, account management |
| [04 Plan Detail](docs/ux-solution/04-plan-detail.md) | Plan Detail (Tablet Master-Detail) | Draggable divider between list and detail panes, accordion sections with compatibility badges |
| [05 Desktop Home](docs/ux-solution/05-desktop-home-dashboard.md) | Desktop Home Dashboard | 12-column grid (960px max), collapsible sidebar (64px→320px), keyboard shortcuts, multi-pane layout |
| [06 Empty States](docs/ux-solution/06-empty-states.md) | Welcome, No Plans, Empty Q&A, Empty Search | Watercolor illustrations, "Create Plan" CTA |
| [07 Loading States](docs/ux-solution/07-loading-processing-states.md) | AI Generation, Image Analysis, Skeletons | AI pulse animation (2000ms), scan overlay with progress, skeleton cards with shimmer |
| [08 Error States](docs/ux-solution/08-error-states.md) | Offline, AI Unavailable, Image Not Recognized | Persistent offline banner, retry buttons, graceful degradation |
| [09 Animation Map](docs/ux-solution/09-animation-map.md) | All screens | 14 motion tokens, 7 haptic feedback points, full transition map, gesture zones |
| [10 Screen Transitions](docs/ux-solution/10-screen-transitions.md) | Full app navigation | All screen-to-screen transitions with directions and durations |
| [11 Design Decisions](docs/ux-solution/11-design-decisions.md) | — | Rationale behind key UX decisions |

### 3.5 Key Component Measurements

| Component | Height | Padding | Radius | Typography |
|---|---|---|---|---|
| Primary Button | 48px | 16px H | 8px | Inter 500 16px |
| Card | — | 16px | 8px | Inter base |
| Tab | 48px | — | 2px indicator | Inter 500 14px |
| Text Input | 48px | 12px H | 4px | Inter base 16px |
| Bottom Nav | 64px | — | — | Inter 400 11px |
| Sidebar | — | — | — | 320px expanded / 64px collapsed |

---

## 4. Unhappy Path Handling

### 4.1 AI Hallucination Risks

| Risk | Mitigation | UI Pattern |
|---|---|---|
| Incompatible livestock/plants | Run AI output through deterministic compatibility rules engine. Display warnings prominently. | ⚠️ Warning badge with explanation on tap |
| Wrong plant requirements | Require tank specs (size, lighting, CO₂) upfront before generating any plan. | Progressive disclosure: mandatory fields marked |
| Fabricated product names | Ground all outputs against curated knowledge base of verified species, plants, products. | Confidence scores next to each recommendation |

### 4.2 Image Recognition Failures

| Risk | Mitigation | UI Pattern |
|---|---|---|
| Misidentification | Show confidence scores. When <80%, present top-3 candidates for user confirmation. Never auto-add. | 🟢>85% auto, 🟡70-85% confirm, 🔴<70% explicit add |
| Unidentifiable images | Graceful fallback: "I couldn't identify this — can you describe what you see?" → Q&A mode. | Friendly error illustration + text input |
| Regional species gaps | Train on global datasets with regional tagging. Prioritize SEA/Vietnam species coverage. | — |

**Confidence Score UI Patterns (see [08 Error States](docs/ux-solution/08-error-states.md)):**
- 🟢 **Green (>85%):** "High confidence" — auto-included, user can remove
- 🟡 **Yellow (70–85%):** "Moderate confidence — please confirm" — requires tap to include
- 🔴 **Red (<70%):** "Low confidence" — shown as suggestion only, requires explicit add

### 4.3 User Input Inconsistencies

| Risk | Mitigation | UI Pattern |
|---|---|---|
| Tank too small for stocking | Hard bioload constraints. Refuse plans exceeding safe levels with educational explanation. | Red alert card with "why this matters" expandable |
| Conflicting inputs (e.g., no CO₂ + carpet plants) | Flag conflicts explicitly. Offer alternatives (easy carpet plants for low-tech). | 🟡 Caution chip with alternative suggestions |
| Incomplete inputs | Progressive disclosure. Tank size/type mandatory. Everything else optional but marked as quality-improving. | "Complete your profile for better results" nudges |

### 4.4 Offline & Persistence

| Risk | Mitigation | UI Pattern |
|---|---|---|
| Offline use | Core planning with bundled local knowledge base. AI features require connectivity. | Persistent "Offline" banner (see [08 Error States](docs/ux-solution/08-error-states.md)) |
| AI unavailable offline | Cache last generated plans. Queue AI requests for when connection returns. | "Queued — will process when online" badge |
| Plan loss (mid-session) | Auto-save every 30 seconds to local storage + cloud sync. | "Last saved 12s ago" indicator |

**Empty/Error UI Patterns (see [06 Empty States](docs/ux-solution/06-empty-states.md) and [08 Error States](docs/ux-solution/08-error-states.md)):**
- **Offline banner:** Persistent top banner "You're offline — saved plans are available. AI features paused." with cloud-off icon
- **Empty plans:** Watercolor illustration + "Your first aquarium awaits 🌊" + "Create Plan" CTA
- **Error state:** "Something went wrong" card with retry button. Never show raw error messages.

### 4.5 Paludarium-Specific Risks

| Risk | Mitigation | UI Pattern |
|---|---|---|
| Humidity control overlooked | Add paludarium mandatory fields: target humidity%, ventilation type. | Dedicated paludarium settings section |
| Escape-prone fauna | Flag all semi-aquatic species with "requires sealed lid" warning. | ⚠️ Warning badge on species cards |
| Water/land ratio mismatches | Make water/land split required input. Filter species by ratio compatibility. | Ratio slider + compatible species filter |
| Compatibility warning banners | Distinct paludarium warnings (land section temp vs water temp conflicts). | 🟡 Caution cards with cross-section conflict details |

### 4.6 Legal & Ethical

| Risk | Mitigation |
|---|---|
| Invasive species suggestions | Geofence by user location. Integrate CITES appendices + local wildlife regulations. |
| CITES-listed species in defaults | Tag all CITES Appendix I/II species. Display legal warnings. Exclude from defaults. |
| Livestock liability | Mandatory disclaimer: "Educational guidance, not a guarantee." Require explicit acknowledgement. Recommend understocking <85% capacity. |
| Regional legality variations | Region-specific knowledge base updates (e.g., certain snails banned in EU, specific fish banned in Australia). |

---

## Appendix A: Figma File Structure (Target)

Based on the PRD specifications (see [BPL-148 §3.4](mention://issue/ca83a738-a1b4-4e22-ab85-d90dafce218a)):

```
📁 AquaPlan Design System
├── 📁 Foundations
│   ├── 🎨 Colors (Light & Dark tokens)
│   ├── 🔤 Typography (Fraunces + Inter scales)
│   ├── 📐 Spacing & Grid (4px base)
│   ├── 🔲 Icons (Lucide library)
│   └── 🎬 Motion (duration/easing tokens)
├── 📁 Components
│   ├── Buttons (Primary, Secondary, Ghost, Icon)
│   ├── Cards (PlanCard, MaterialCard, TankTypeCard)
│   ├── Inputs (Text, Select, Slider, Chip)
│   ├── Navigation (BottomBar, Sidebar, TabBar)
│   ├── Badges (ConfidenceBadge, StatusBadge)
│   ├── Dialogs (Confirm, Alert, AI Generation)
│   └── Empty States (No Plans, Offline, Error)
├── 📁 Screens
│   ├── Onboarding (Welcome → Tank Type → Size → Materials → Goals → Generation)
│   ├── Home Dashboard
│   ├── Plan Detail (with all 4 tab variants)
│   ├── Image → Plan (Capture → Analysis → Results)
│   └── Q&A Chat (Empty, Active, History)
└── 📁 Prototypes
    ├── First-time user flow
    ├── Image-to-plan flow
    └── Q&A interaction flow
```

**Layout Grids:**
- Mobile: 4-column, 16px margin, 16px gutter
- Tablet: 8-column, 24px margin, 24px gutter
- Desktop: 12-column, auto margin (max 960px content), 24px gutter

---

## Appendix B: Squad Attribution

| Section | Source Agent | Status |
|---|---|---|
| 1. Business Context | [@Competitor-Analyst](mention://agent/94330e9f-38f7-45f8-9e33-95f408e7a01e) | ✅ Complete (PRD vFinal) |
| 2. Global Style Guide | [@UX-Architect](mention://agent/cb65a0f4-201a-4376-a4d1-5d5f069cdcd6) | ✅ Complete (PRD vFinal) |
| 3. UX/UI Flow | [@UX-Architect](mention://agent/cb65a0f4-201a-4376-a4d1-5d5f069cdcd6) + Modular Docs | ✅ Complete (PRD + BPL-150 expanded wireframes) |
| 4. Unhappy Path Handling | [@Competitor-Analyst](mention://agent/94330e9f-38f7-45f8-9e33-95f408e7a01e) + [@UX-Architect](mention://agent/cb65a0f4-201a-4376-a4d1-5d5f069cdcd6) | ✅ Complete (PRD vFinal) |
| Final Compilation | [@Doc-Housekeeper](mention://agent/e1864713-9443-4288-9443-33d2a999e89f) | ✅ Complete (this document) |

---

## Appendix C: Data Sources

- AqAdvisor (aqadvisor.com) — web-only stocking calculator
- Tropica (tropica.com) — plant guides
- Aquarium Co-Op (aquariumcoop.com) — blog + ecommerce
- Buce Plant (buceplant.com) — ecommerce
- Practical Fishkeeping (practicalfishkeeping.co.uk) — membership model
- GitHub API — searched `aquarium+app` (363 repos), `paludarium` (41 repos), `aquarium+compatibility` (0 results)
- Google Play Store — Aquarium AI, AquaLens, Aquabuildr
- GitHub — Danio, cd-caio/aquarium-builder, AquaBuilder, Comparium
- Verified Market Research — aquarium hardware market sizing ($12.63B → $19.2B)
