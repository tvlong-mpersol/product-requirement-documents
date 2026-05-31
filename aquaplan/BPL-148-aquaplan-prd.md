# AquaPlan — Product Requirements Document (PRD)
**Issue:** [BPL-148](mention://issue/ca83a738-a1b4-4e22-ab85-d90dafce218a)  
**Status:** Final | **Date:** 2026-05-30  
**Product:** Cross-platform AI-assisted aquarium & paludarium planner app (Web, Mobile, iPad)

---

## 1. Business Context

### 1.1 Market Opportunity

The aquarium hardware market is valued at **$12.63B (2023) → $19.2B by 2031** (CAGR 6.17%). Household segment holds 66.18% share ($8.36B, 2024). Asia-Pacific leads with 34.37% market share. 14.7M US households own pet fish. Up to 90% of marine aquarium fish are wild-caught — a growing sustainability concern.

### 1.2 Competitor Landscape

**7 Key Players (Web/Content):**

| Competitor | Type | Strengths | Gaps |
|---|---|---|---|
| **AqAdvisor** (aqadvisor.com) | Free stocking calculator | Compatibility algorithm, shareable URLs | No AI, no image recognition, no paludarium, no mobile |
| **Tropica** (tropica.com) | Plant authority | Easy/Medium/Advanced difficulty symbols | Content-only, no planning tools, no AI |
| **Aquarium Co-Op** (aquariumcoop.com) | Content + ecommerce | YouTube community, strong SEO | No app, no planning tool, no AI |
| **Buce Plant** (buceplant.com) | Ecommerce | High-quality plant photos, strong community | Pure ecommerce, zero planning features |
| **2Hr Aquarist** (2hraquarist.com) | Blog | Science-based aquascaping guides | Blog only, no tools, intermediate+ audience |
| **Practical Fishkeeping** | Magazine | Expert Q&A, gear reviews | Paywall (£5.99/mo), no tools |
| **Borneo IoT** (GitHub ★74) | Open-source hardware | LED PWM controller (Flutter) | Hardware-only, zero planning/AI |

**Direct App Competitors (Google Play/GitHub):**

| Competitor | Type | Strengths | Gaps |
|---|---|---|---|
| **Aquarium AI** | AI chatbot + fish ID | Harmony Score™, BYO AI keys | Requires user's own API key |
| **AquaLens** | Water test + fish ID | Freemium, most feature-complete tracker | No beginner education, no paludarium |
| **Aquabuildr** | Stocking builder | Pre-built tanks, compatibility algorithm | No AI features |
| **Danio** (GitHub, unreleased) | Flutter edu app | 72 lessons, gamification, GPT-4o | Unreleased, freshwater-only |
| **cd-caio/aquarium-builder** | 3D tank builder | Three.js, paludarium support | Single-file hobby project, Portuguese-only, no AI |

**GitHub Landscape:** 363 aquarium app repos — all <10 stars except Borneo IoT. Zero paludarium apps commercially. **No production-ready AI aquarium planner exists.**

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
- `--color-abyss`: #0B1E36 (darkest — nav bars, footers, deep backgrounds)
- `--color-deep`: #1A3A5C (card backgrounds, secondary surfaces)
- `--color-reef`: #2563EB (primary actions, links, active states)
- `--color-shallows`: #60A5FA (hover states, secondary accents)
- `--color-surface`: #E8F4FD (light backgrounds, inputs)

**Living Element Accents:**
- `--color-coral`: #F97316 (warnings, compatibility alerts, destructive actions)
- `--color-seagrass`: #22C55E (success, safe/compatible indicators, confirmed steps)
- `--color-sand`: #FCD34D (caution, medium confidence, "needs attention")
- `--color-bubble`: #A78BFA (AI features, generation states, chat bubbles)

**Light / Dark Mode Semantic Tokens:**

| Token | Light | Dark |
|---|---|---|
| `--bg-primary` | #FFFFFF | #0B1E36 |
| `--bg-secondary` | #E8F4FD | #1A3A5C |
| `--text-primary` | #0B1E36 | #F8FAFC |
| `--text-secondary` | #475569 | #94A3B8 |
| `--border` | #CBD5E1 | #334155 |

### 2.3 Typography

**Font Stack:**
- **Headings:** Fraunces (serif, warmth + authority) — weights 400 (regular), 600 (semibold), 700 (bold)
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
- Home: `layout-dashboard`
- My Plans: `clipboard-list`
- New Plan: `plus-circle`
- Q&A Chat: `message-circle`
- Settings: `settings`
- Tank: `waves`
- Plant: `sprout`
- Fish: `fish`
- AI: `sparkles`
- Camera/Capture: `camera`
- Warning: `alert-triangle`
- Success/Check: `check-circle`

### 2.5 Spacing Scale

4px base unit: `--space-1: 4px` | `--space-2: 8px` | `--space-3: 12px` | `--space-4: 16px` | `--space-5: 20px` | `--space-6: 24px` | `--space-8: 32px` | `--space-10: 40px` | `--space-12: 48px` | `--space-16: 64px`

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
| `--shadow-sm` | 0 1px 2px rgba(11,30,54,0.05) | Cards (light mode) |
| `--shadow-md` | 0 4px 6px rgba(11,30,54,0.07) | Elevated cards, dropdowns |
| `--shadow-lg` | 0 10px 15px rgba(11,30,54,0.1) | Modals, sheets |
| `--shadow-glow` | 0 0 20px rgba(167,139,250,0.4) | AI generation pulse |

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

#### Journey 1: Onboarding — Create First Plan (Mobile, 375px)

```
┌──────────────────────────────────┐
│         ⬆️  AquaPlan             │  ← App bar, Fraunces logo
├──────────────────────────────────┤
│                                  │
│     ┌────────────────────┐       │
│     │   🐠  🌿  🦐      │       │  ← Hero illustration
│     │                    │       │     (animated SVG)
│     │  Build Your Dream  │       │
│     │  Aquarium          │       │  ← Fraunces 3xl, abyss
│     │                    │       │
│     │  AI-powered plans  │       │  ← Inter base, secondary
│     │  for beginners     │       │
│     └────────────────────┘       │
│                                  │
│  ┌────────────────────────────┐  │
│  │  🪣  Aquarium              │  │  ← Tank type card
│  │  Traditional underwater     │  │     (reef bg, radius-lg)
│  └────────────────────────────┘  │
│  ┌────────────────────────────┐  │
│  │  🌴  Paludarium            │  │
│  │  Half water, half land     │  │
│  └────────────────────────────┘  │
│  ┌────────────────────────────┐  │
│  │  🏞️  Riparium              │  │
│  │  Riverside / stream edge   │  │
│  └────────────────────────────┘  │
│                                  │
│  [Or describe your own idea...]  │  ← Text link, secondary
│                                  │
│  ┌────────────────────────────┐  │
│  │     Continue →             │  │  ← Primary CTA, reef-500
│  └────────────────────────────┘  │     (disabled until selection)
└──────────────────────────────────┘
```

→ Tank Size screen: Slider (5–150 gal) + dimension inputs (L×W×H)  
→ Materials screen: I already have... (multi-select chips: Tank, Filter, Heater, Lights, Substrate, Hardscape, Plants, Livestock)  
→ Goals screen: Checkbox options (Low-maintenance, Shrimp-safe, Breeding, Show tank, Budget-friendly)  
→ **Generation screen:** AI progress ripple animation, "Crafting your plan..." with rotating tips  
→ **Plan Detail screen** (see Journey 2)

#### Journey 2: Plan Detail (Mobile, 375px)

```
┌──────────────────────────────────┐
│  ← Plans    My 20G Planted  ⋯   │  ← Nav bar
├──────────────────────────────────┤
│  ┌────────────────────────────┐  │
│  │  [Reference Image]         │  │  ← Hero image, 200px height
│  │   AI-generated aquarium    │  │     rounded-lg
│  └────────────────────────────┘  │
│                                  │
│  ┌────────────────────────────┐  │
│  │  🟢 92% Compatibility      │  │  ← Overall score badge
│  └────────────────────────────┘  │
│                                  │
│  [Materials] [Steps] [Sched] [📝]│  ← Tab bar, 4 tabs
│  ───────────────────────────     │
│                                  │
│  ┌──────────────────────────┐    │
│  │ 🐠  Livestock (6)    ▼   │    │  ← Accordion sections
│  │  ├ Neon Tetra ×10  ✓     │    │     ✓ = compatible
│  │  ├ Corydoras ×6    ✓     │    │
│  │  ├ Betta splendens ⚠️    │    │     ⚠️ = warning (tap for details)
│  │  └ Amano Shrimp ×5 ✓    │    │
│  └──────────────────────────┘    │
│  ┌──────────────────────────┐    │
│  │ 🌿  Plants (4)       ▼   │    │
│  │  ├ Anubias nana    ✓     │    │
│  │  └ Java fern       ✓     │    │
│  └──────────────────────────┘    │
│  ┌──────────────────────────┐    │
│  │ 🪨  Hardscape (3)    ▼   │    │
│  │  └ Dragon stone  ×2      │    │
│  └──────────────────────────┘    │
│  ┌──────────────────────────┐    │
│  │ ⚙️  Equipment (5)    ▼   │    │
│  │  └ Fluval 207 filter     │    │
│  └──────────────────────────┘    │
│                                  │
│  ┌────────────────────────────┐  │
│  │  💬  Ask AI about this     │  │  ← Floating action
│  │      plan                  │  │
│  └────────────────────────────┘  │
└──────────────────────────────────┘
```

#### Journey 3: Image → Plan (Mobile, 375px)

```
┌──────────────────────────────────┐
│  Cancel     Identify Tank    📸  │
├──────────────────────────────────┤
│                                  │
│  ┌────────────────────────────┐  │
│  │                            │  │
│  │     [Camera Viewfinder]    │  │  ← Live camera or photo picker
│  │                            │  │
│  │   ┌──────────────┐         │  │
│  │   │ Focus frame  │         │  │  ← Animated corner brackets
│  │   └──────────────┘         │  │
│  │                            │  │
│  └────────────────────────────┘  │
│                                  │
│  ┌────────────────────────────┐  │
│  │  💡 Tips:                  │  │
│  │  • Photograph whole tank   │  │
│  │  • Good lighting helps     │  │
│  │  • Get close to plants     │  │
│  └────────────────────────────┘  │
│                                  │
│  ┌────────────────────────────┐  │
│  │        📸  Capture         │  │  ← Large capture button
│  └────────────────────────────┘  │
│                                  │
│  ┌────────────────────────────┐  │
│  │  🖼️  Choose from Gallery   │  │
│  └────────────────────────────┘  │
└──────────────────────────────────┘
```

→ **AI Analysis screen:** Scan overlay with progress bar. Animated "analyzing" grid overlay on image. Results appear one-by-one with staggered reveals.  
→ **Results screen:** Material cards with confidence badges (🟢 >85%, 🟡 70-85%, 🔴 <70%). "Add to plan" toggle per item. "Generate full plan" CTA.

#### Journey 4: Q&A Chat (Mobile, 375px)

```
┌──────────────────────────────────┐
│  ← Back      AquaPlan AI    ⋯   │
├──────────────────────────────────┤
│                                  │
│  ┌────────────────────────────┐  │
│  │ 💬  How often should I     │  │  ← Suggested question chips
│  │     feed neon tetras?      │  │     (horizontal scroll)
│  ├────────────────────────────┤  │
│  │ 💬  Best plants for low    │  │
│  │     light tanks?           │  │
│  ├────────────────────────────┤  │
│  │ 💬  Why is my water cloudy?│  │
│  └────────────────────────────┘  │
│                                  │
│  ┌──────────────────────────────┐│
│  │                         ┌──┐ ││
│  │ You: Is my 10G okay      │🟢│ ││  ← User message (right-aligned)
│  │ for a betta + shrimp?   └──┘ ││     with confidence if auto-detected
│  └──────────────────────────────┘│
│                                  │
│  ┌──────────────────────────────┐│
│  │┌──┐                          ││
│  ││🤖│ Great question! A 10     ││  ← Bot response (left-aligned)
│  │└──┘ gallon is **perfect**    ││     Markdown rendered
│  │ for a betta. Here's what     ││
│  │ to consider with shrimp:     ││
│  │                              ││
│  │ **Compatibility:**           ││
│  │ • Amano shrimp ✓ (too big   ││
│  │   for betta to eat)         ││
│  │ • Cherry shrimp ⚠️ (betta   ││
│  │   may hunt them)            ││
│  │                              ││
│  │ **Recommended stocking:**    ││
│  │ • 1× Betta splendens        ││
│  │ • 5× Amano shrimp           ││
│  │ • 2× Nerite snails          ││
│  │                              ││
│  │ Was this helpful? 👍 👎      ││  ← Feedback row
│  └──────────────────────────────┘│
│                                  │
│  ┌────────────────────────────┐  │
│  │  Type your question...  ↗️  │  │  ← Input bar with send
│  └────────────────────────────┘  │
└──────────────────────────────────┘
```

### 3.3 Responsive Layouts

**Mobile (375px — 767px):** Single-column, bottom nav bar (5 tabs), stacked content, full-width cards. Hamburger menu overflow for secondary actions.

**Tablet (768px — 1023px):** Two-column master-detail. Left: persistent sidebar/plan list (280px). Right: content area. Top nav replaces bottom. Split-pane for plan detail (image left, content right).

**Desktop (1024px+):** Full sidebar (320px, collapsible to 64px icon rail). Max content width 960px centered. Keyboard shortcuts. Multi-pane for complex views (plan detail shows materials + reference image side-by-side).

### 3.4 Figma Design Specifications

**File Structure:**
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

**Key Component Measurements:**
- Primary Button: 48px height, 16px horizontal padding, 8px radius, Inter 500 16px
- Card: 16px padding, 8px radius, 1px border (#CBD5E1), shadow-sm
- Tab: 48px height, Inter 500 14px, 2px active indicator (reef-500)
- Input: 48px height, 12px horizontal padding, 4px radius, 1px border
- Bottom Nav: 64px height, 5 items max, Inter 400 11px labels
- Sidebar: 320px expanded, 64px collapsed (icon rail)

---

## 4. Unhappy Path Handling

### 4.1 AI Hallucination Risks

| Risk | Mitigation |
|---|---|
| Incompatible livestock/plants | Run AI output through deterministic compatibility rules engine. Display warnings prominently. |
| Wrong plant requirements | Require tank specs (size, lighting, CO₂) upfront before generating any plan. |
| Fabricated product names | Ground all outputs against curated knowledge base of verified species, plants, products. |

### 4.2 Image Recognition Failures

| Risk | Mitigation |
|---|---|
| Misidentification | Show confidence scores. When <80%, present top-3 candidates for user confirmation. Never auto-add. |
| Unidentifiable images | Graceful fallback: "I couldn't identify this — can you describe what you see?" → Q&A mode. |
| Regional species gaps | Train on global datasets with regional tagging. Prioritize SEA/Vietnam species coverage. |

**Confidence Score UI Patterns:**
- 🟢 **Green (>85%):** "High confidence" — auto-included, user can remove
- 🟡 **Yellow (70–85%):** "Moderate confidence — please confirm" — requires tap to include
- 🔴 **Red (<70%):** "Low confidence" — shown as suggestion only, requires explicit add

### 4.3 User Input Inconsistencies

| Risk | Mitigation |
|---|---|
| Tank too small for stocking | Hard bioload constraints. Refuse plans exceeding safe levels with educational explanation. |
| Conflicting inputs (e.g., no CO₂ + carpet plants) | Flag conflicts explicitly. Offer alternatives (easy carpet plants for low-tech). |
| Incomplete inputs | Progressive disclosure. Tank size/type mandatory. Everything else optional but marked as quality-improving. |

### 4.4 Offline & Persistence

| Risk | Mitigation |
|---|---|
| Offline use | Core planning with bundled local knowledge base. AI features require connectivity. |
| AI unavailable offline | Cache last generated plans. Queue AI requests for when connection returns. |
| Plan loss (mid-session) | Auto-save every 30 seconds to local storage + cloud sync. |

**Offline/Empty/Error States:**
- **Offline banner:** Persistent top banner "You're offline — saved plans are available. AI features paused." with cloud-off icon
- **Empty plans:** Watercolor illustration + "Your first aquarium awaits 🌊" + "Create Plan" CTA
- **Error state:** "Something went wrong" card with retry button. Never show raw error messages.

### 4.5 Paludarium-Specific Risks

| Risk | Mitigation |
|---|---|
| Humidity control overlooked | Add paludarium mandatory fields: target humidity%, ventilation type. |
| Escape-prone fauna | Flag all semi-aquatic species with "requires sealed lid" warning. |
| Water/land ratio mismatches | Make water/land split required input. Filter species by ratio compatibility. |
| Compatibility warning banners | Distinct paludarium warnings (land section temp vs water temp conflicts). |

### 4.6 Legal & Ethical

| Risk | Mitigation |
|---|---|
| Invasive species suggestions | Geofence by user location. Integrate CITES appendices + local wildlife regulations. |
| CITES-listed species in defaults | Tag all CITES Appendix I/II species. Display legal warnings. Exclude from defaults. |
| Livestock liability | Mandatory disclaimer: "Educational guidance, not a guarantee." Require explicit acknowledgement. Recommend understocking <85% capacity. |
| Regional legality variations | Region-specific knowledge base updates (e.g., certain snails banned in EU, specific fish banned in Australia). |

---

## Appendix A: Squad Attribution

| Section | Responsible Agent | Status |
|---|---|---|
| 1. Business Context | [@Competitor-Analyst](mention://agent/94330e9f-38f7-45f8-9e33-95f408e7a01e) | ✅ Complete |
| 2. Global Style Guide | [@UX-Architect](mention://agent/cb65a0f4-201a-4376-a4d1-5d5f069cdcd6) | ✅ Complete |
| 3. UX/UI Flow | [@UX-Architect](mention://agent/cb65a0f4-201a-4376-a4d1-5d5f069cdcd6) | ✅ Complete |
| 4. Unhappy Path Handling | [@Competitor-Analyst](mention://agent/94330e9f-38f7-45f8-9e33-95f408e7a01e) + [@UX-Architect](mention://agent/cb65a0f4-201a-4376-a4d1-5d5f069cdcd6) | ✅ Complete |
| Final Compilation | [@Research-Orchestrator](mention://agent/eb91dca7-07e8-4129-8b29-e74223b33d9a) | ✅ Complete |

## Appendix B: Data Sources

- AqAdvisor (aqadvisor.com) — direct page fetch, web-only stocking calculator
- Tropica (tropica.com) — direct page fetch, plant guides
- Aquarium Co-Op (aquariumcoop.com) — direct page fetch, blog + ecommerce
- Buce Plant (buceplant.com) — direct page fetch, ecommerce
- Practical Fishkeeping (practicalfishkeeping.co.uk) — direct page fetch, membership model
- GitHub API — searched `aquarium+app` (363 repos), `paludarium` (41 repos), `aquarium+compatibility` (0 results)
- Google Play Store — Aquarium AI, AquaLens, Aquabuildr
- GitHub — Danio, cd-caio/aquarium-builder, AquaBuilder, Comparium
- Verified Market Research — aquarium hardware market sizing ($12.63B → $19.2B)
