---
title: "AquaPlan UX — 07 Loading Processing States"
status: final
last_updated: 2026-05-31
related_prd: "BPL-148"
source_issue: "BPL-150"
related_screens:
  - loading-states
  - ai-generation
  - image-analysis
---

## 7. Loading & Processing States

### 7.1 AI Generation — "Crafting your plan..."

```
┌─────────────────────────────────────┐
│  ← Back      Create Plan           │
├─────────────────────────────────────┤
│                                     │
│                                     │
│          ┌───────────────┐          │
│          │               │          │  ← Central card, 280×320px
│          │    ╭──────╮   │          │     bg-deep (light: surface)
│          │    │  🧠  │   │          │     radius-lg, shadow-glow
│          │    │  ✨  │   │          │
│          │    ╰──────╯   │          │  ← AI pulse animation (2000ms)
│          │               │          │     bubble-500 glow expanding
│          │  Crafting your │          │     and contracting
│          │  plan...       │          │
│          │               │          │  ← Fraunces lg (20px), abyss
│          │  ┌───────────┐ │          │
│          │  │ ████████░░│ │          │  ← Progress bar, 200px wide
│          │  │  65%       │ │          │     reef-500 fill, 8px H
│          │  └───────────┘ │          │     radius-full
│          │               │          │
│          │  💡 Did you    │          │  ← Rotating tips (every 4s,
│          │  know?         │          │     crossfade 500ms)
│          │  A 20% water   │          │     Inter 400 14px, italic
│          │  change weekly │          │     text-secondary
│          │  keeps fish    │          │
│          │  healthy.      │          │
│          │               │          │
│          │  [Cancel]      │          │  ← Text button, secondary
│          └───────────────┘          │
│                                     │
│                                     │
│  ─ ─ ─ Step indicators ─ ─ ─ ─ ─ ─ │
│  ● Tank type  ● Size  ● Materials  │  ← Completed steps
│  ● Goals  ◐ Generating  ○ Complete │  ← Current (pulsing), pending
│                                     │
│  ┌─ Material Preview (staggered) ──┐│
│  │                                 ││  ← Results appear below card
│  │ 🐠  Neon Tetra ×10     🟢 94%  ││     staggered 400ms card enter
│  │ 🌿  Anubias nana       🟢 97%  ││     each row: 48px H
│  │ 🪨  Dragon stone              ││     confidence badge right
│  │ ⚙️  Fluval 207 filter         ││
│  └─────────────────────────────────┘│
└─────────────────────────────────────┘
```

### 7.2 Image Analysis — Scan Overlay

```
┌─────────────────────────────────────┐
│  Cancel      Analyzing...          │
├─────────────────────────────────────┤
│                                     │
│  ┌────────────────────────────────┐ │
│  │                                │ │
│  │     [Captured Image]           │ │  ← Full-width image, 300px H
│  │                                │ │     radius-lg
│  │  ┌──┐┌──┐┌──┐┌──┐┌──┐┌──┐   │ │
│  │  │  ││  ││  ││  ││  ││  │   │ │  ← Animated scan grid overlay
│  │  ├──┤├──┤├──┤├──┤├──┤├──┤   │ │     6×4 grid lines, reef-500
│  │  │  ││  ││  ││  ││  ││  │   │ │     20% opacity
│  │  ├──┤├──┤├──┤├──┤├──┤├──┤   │ │     Scanning top→bottom 2s loop
│  │  │  ││  ││🔍││  ││  ││  │   │ │     🔍 = active scan cell
│  │  ├──┤├──┤├──┤├──┤├──┤├──┤   │ │
│  │  │  ││  ││  ││  ││  ││  │   │ │
│  │  └──┘└──┘└──┘└──┘└──┘└──┘   │ │
│  │                                │ │
│  └────────────────────────────────┘ │
│                                     │
│  Identifying organisms...           │  ← Inter 500 14px, centered
│                                     │
│  ┌─ Staggered Results ────────────┐│
│  │                                 ││  ← Results reveal one by one
│  │ ✓  Plant identified   🟢 94%   ││     each 400ms apart
│  │ ✓  Fish detected      🟢 89%   ││     card enter animation
│  │ ◐  Analyzing...                 ││
│  │ ○  Hardscape                    ││
│  └─────────────────────────────────┘│
│                                     │
│  ┌────────────────────────────────┐ │
│  │    [View Results] (disabled)   │ │  ← Enables when all complete
│  └────────────────────────────────┘ │
└─────────────────────────────────────┘
```

### 7.3 List Loading — Skeleton Cards

```
┌─────────────────────────────────────┐
│  ← Dashboard    My Plans           │
├─────────────────────────────────────┤
│  ┌────────────────────────────────┐ │
│  │ ░░░░░░░░░░░░░░░░░░░░░░░░░░░░ │ │  ← Skeleton search bar
│  └────────────────────────────────┘ │     48px H, bg-deep + shimmer
│                                     │
│  [░░░░░] [░░░░░░░░] [░░░░░░░]      │  ← Skeleton chips
│                                     │
│  ┌────────────────────────────────┐ │
│  │ ┌────────┐  ░░░░░░░░░░░░░░░░  │ │  ← Skeleton card 1
│  │ │        │  ░░░░░░░░░░         │ │     80×80 thumbnail placeholder
│  │ │  ░░░░  │  ░░░░░░░░░░░░░░    │ │     Title (2 lines), meta (1)
│  │ │  ░░░░  │                     │ │     16px pad, radius-md
│  │ └────────┘                     │ │
│  └────────────────────────────────┘ │
│                                     │
│  ┌────────────────────────────────┐ │  ← Skeleton card 2
│  │ ┌────────┐  ░░░░░░░░░░░░░░░░  │ │
│  │ │        │  ░░░░░░░░░░         │ │
│  │ │  ░░░░  │  ░░░░░░░░░░░░░░    │ │
│  │ │  ░░░░  │                     │ │
│  │ └────────┘                     │ │
│  └────────────────────────────────┘ │
│                                     │
│  ┌────────────────────────────────┐ │  ← Skeleton card 3
│  │ ┌────────┐  ░░░░░░░░░░░░░░░░  │ │
│  │ │        │  ░░░░░░░░░░         │ │     Shimmer animation:
│  │ │  ░░░░  │  ░░░░░░░░░░░░░░    │ │     linear gradient sweeps
│  │ │  ░░░░  │                     │ │     left→right, 1500ms loop
│  │ └────────┘                     │ │     bg: deep→surface→deep
│  └────────────────────────────────┘ │
│                                     │
│  (3-4 skeleton cards total —        │
│   enough to fill viewport)          │
└─────────────────────────────────────┘
```

---
