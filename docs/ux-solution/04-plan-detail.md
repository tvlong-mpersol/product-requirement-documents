---
title: "AquaPlan UX — 04 Plan Detail"
status: final
last_updated: 2026-05-31
related_prd: "BPL-148"
source_issue: "BPL-150"
related_screens:
  - plan-detail
---

## 4. Tablet Layout (768px) — Plan Detail (Master-Detail)

### Interaction Flow

1. **Entry:** From My Plans tap or Dashboard Recent Plans tap. 250ms page transition.
2. **Left panel (Master, 280px):** Scrollable plan list. Current selection highlighted with reef-500 left border (3px) and slight bg-shallows. Tap any plan → instant selection, right panel updates with 250ms crossfade.
3. **Right panel (Detail, 488px):** Shows selected plan: hero image, compatibility badge, 4 tabs (Materials, Steps, Schedule, Notes), accordion content. Independent scroll from left panel.
4. **Tab switching:** Tap tab → 200ms content crossfade. Active tab: reef-500 2px bottom indicator.
5. **Accordion expand/collapse:** Tap header → 300ms height transition. Only one accordion open at a time (optional "expand all" in overflow menu). Chevron rotates 180°.
6. **"Ask AI" FAB:** 56×56px, bubble-500 bg, always visible in bottom-right of right panel. Tap → opens Q&A in split-view sidebar or pushes full Q&A.
7. **Drag handle:** Vertical divider at 280px is draggable (260-340px range). Shows grip cursor on hover.
8. **Keyboard shortcuts (Desktop/Tablet with keyboard):**
   - `Ctrl+[` — Focus left panel (plan list)
   - `Ctrl+]` — Focus right panel (detail)
   - `1-4` — Switch tabs when detail is focused
   - `↑/↓` — Navigate plan list
   - `Enter` — Select highlighted plan

---

### Tablet (768px)

```
┌──────────────────────────────────────────────────────────────────────────┐  768×1024
│  ← Back    AquaPlan Plans                                         ⚙️     │  Top Nav 56px
├──────────────────────────────────────────────────────────────────────────┤
│                                                                          │
│  ┌─────────────────────┐  ┌─────────────────────────────────────────────┐│
│  │ Master (280px)      │  │  Detail (488px)                             ││
│  │                     │  │                                             ││
│  │ ┌─────────────────┐ │  │  ┌─────────────────────────────────────────┐││
│  │ │ 🔍 Search...    │ │  │  │  [Reference Image — AI generated]       │││
│  │ └─────────────────┘ │  │  │                                  200px  │││
│  │                     │  │  └─────────────────────────────────────────┘││
│  │ [All][Aquar][Palud] │  │                                             ││
│  │                     │  │  ┌────────────────┐                         ││
│  │ ──────────────────  │  │  │ 🟢 92% Compat  │  ← Confidence badge     ││
│  │                     │  │  └────────────────┘                         ││
│  │ ┌─────────────────┐ │  │                                             ││
│  │ │ ┃ ┌──────┐      │ │  │  ┌─────────────────────────────────────────┐││
│  │ │ ┃ │ Thumb│ 20G  │ │  │  │ [Materials] [Steps] [Sched] [Notes]    │││
│  │ │ ┃ │ 64×64│ 🟢   │ │  │  │  ────────                              │││
│  │ │ ┃ └──────┘ 92%  │ │  │  └─────────────────────────────────────────┘││
│  │ └─────────────────┘ │  │                                             ││
│  │    ← selected       │  │  ┌─────────────────────────────────────────┐││
│  │                     │  │  │ 🐠  Livestock (6)                   [▼] │││
│  │ ┌─────────────────┐ │  │  ├─────────────────────────────────────────┤││
│  │ │   ┌──────┐      │ │  │  │  Neon Tetra ×10                ✓ 🟢   │││
│  │ │   │ Thumb│ 10G  │ │  │  │  Corydoras ×6                  ✓ 🟢   │││
│  │ │   │ 64×64│ 🟢   │ │  │  │  Betta splendens               ⚠️ 🟡   │││
│  │ │   └──────┘ 98%  │ │  │  │  Amano Shrimp ×5               ✓ 🟢   │││
│  │ └─────────────────┘ │  │  │  Nerite Snail ×2               ✓ 🟢   │││
│  │                     │  │  │  Otocinclus ×3                 ✓ 🟢   │││
│  │ ┌─────────────────┐ │  │  └─────────────────────────────────────────┘││
│  │ │   ┌──────┐      │ │  │                                             ││
│  │ │   │ Thumb│ 55G  │ │  │  ┌─────────────────────────────────────────┐││
│  │ │   │ 64×64│ 🟡   │ │  │  │ 🌿  Plants (4)                    [▶]  │││
│  │ │   └──────┘ 76%  │ │  │  └─────────────────────────────────────────┘││
│  │ └─────────────────┘ │  │                                             ││
│  │                     │  │  ┌─────────────────────────────────────────┐││
│  │ ┌─────────────────┐ │  │  │ 🪨  Hardscape (3)                 [▶]  │││
│  │ │   ┌──────┐      │ │  │  └─────────────────────────────────────────┘││
│  │ │   │ Thumb│ Nano │ │  │                                             ││
│  │ │   │ 64×64│ 🟢   │ │  │  ┌─────────────────────────────────────────┐││
│  │ │   └──────┘ 88%  │ │  │  │ ⚙️  Equipment (5)                 [▶]  │││
│  │ └─────────────────┘ │  │  └─────────────────────────────────────────┘││
│  │                     │  │                                             ││
│  │   ...more plans...  │  │                                     ┌─────┐ ││
│  │                     │  │                                     │ 💬  │ ││
│  │                     │  │                                     │ Ask │ ││
│  │                     │  │                                     │ AI  │ ││
│  │                     │  │                                     └─────┘ ││
│  └─────────────────────┘  └─────────────────────────────────────────────┘│
│       ▌← draggable divider (260-340px range)                              │
└──────────────────────────────────────────────────────────────────────────┘
```

---
