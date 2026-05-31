---
title: "AquaPlan UX — 01 Home Dashboard"
status: final
last_updated: 2026-05-31
related_prd: "BPL-148"
source_issue: "BPL-150"
related_screens:
  - home-dashboard
---

## 1. Home Dashboard

### Interaction Flow

1. **Entry:** App launches → 250ms `ease-in-out` page transition. Dashboard slides in from right.
2. **Greeting:** "Good morning, [Name]" with time-of-day aware greeting (morning/afternoon/evening). Avatar tap → Settings/Profile.
3. **Quick Start cards:** Each card has 300ms `ease-out` ripple on tap.
   - **New Plan** → pushes Onboarding Wizard (Step 1: Welcome)
   - **Image → Plan** → pushes Camera capture screen
   - **Ask AI** → pushes Q&A Chat with contextual greeting
4. **Recent Plans carousel:** Horizontal swipe on cards. Tap card → pushes Plan Detail. Long-press card → context menu (Duplicate, Share, Delete). Carousel enters with 400ms staggered `ease-out` (card enter token).
5. **Daily Tip card:** Tap → expands inline to show full tip with "Learn more" link → pushes relevant Q&A topic. Swipe left → next tip. Pull-to-refresh on dashboard fetches new tip.
6. **Quick Stats row:** Tap "Active Plans" → pushes filtered My Plans list. Tap "Livestock" → pushes filtered by livestock category.
7. **Haptic feedback:** Light haptic on Quick Start card taps, medium on long-press context menu.
8. **Gestures:** Pull-to-refresh (entire dashboard) — 80px threshold, bounces at 120px max drag. Smooth `ease-out` snap back.
9. **Desktop keyboard shortcuts:**
   - `Ctrl+N` — New Plan
   - `Ctrl+I` — Image → Plan
   - `Ctrl+K` — Q&A Chat (opens with input focused)
   - `Ctrl+1-4` — Navigate top tabs (if present)
   - `/` — Focus search (My Plans view)

---

### Mobile (375px)

```
┌─────────────────────────────────────┐  ← Viewport 375×812
│                                     │
│  🔔 AquaPlan                    🧑‍💼 │  ← App bar, 56px H
│                                     │     🔔 notifications, 🧑‍💼 avatar 32px
├─────────────────────────────────────┤
│                                     │
│  Good morning,                      │  ← Fraunces 2xl (31px/40px)
│  Alex 🌊                           │     text-primary, mt-8
│                                     │
│  ┌ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ┐  │
│  │  Quick Start          [See All]│  │  ← Row: text-sm label + link
│  │                                │  │
│  │ ┌──────────┐┌──────────┐┌────┐│  │  ← 3 cards in horizontal scroll
│  │ │  🪣       ││  📸       ││ 💬 ││  │     each 140×120px
│  │ │           ││           ││    ││  │
│  │ │ New Plan  ││ Image→Plan││Ask ││  │  ← Inter 500 14px title
│  │ │           ││           ││ AI ││  │     Lucide icons 24px
│  │ │ 3 steps   ││  Instant  ││Any ││  │  ← Inter 400 12px subtitle
│  │ │           ││           ││ ?  ││  │
│  │ └──────────┘└──────────┘└────┘│  │     bg-shallows(light)/deep(dark)
│  └ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ┘  │     radius-md (8px), shadow-sm
│                                     │
│  ┌ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ┐  │
│  │  Recent Plans          [All ›]│  │  ← Row label
│  │                                │  │
│  │ ┌──────────────────────┐  ┌──┐ │  │  ← Horizontal scroll cards
│  │ │  ┌────────────────┐  │  │  │ │  │     each 260×160px
│  │ │  │    [Preview]   │  │  │  │ │  │     radius-md, 1px border
│  │ │  │                │  │  │  │ │  │
│  │ │  └────────────────┘  │  │  │ │  │
│  │ │  My 20G Planted      │  │  │ │  │  ← Inter 600 16px
│  │ │  🟢 92% · 2d ago     │  │  │ │  │  ← Confidence badge + meta
│  │ └──────────────────────┘  └──┘ │  │
│  └ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ┘  │
│                                     │
│  ┌─────────────────────────────────┐│
│  │  💡 Daily Tip                   ││  ← Card, full width
│  │                                 ││     bg-surface, radius-md
│  │  When introducing new fish,     ││     border-l: 3px solid coral
│  │  acclimate them slowly — float  ││
│  │  the bag for 15 min, then add   ││  ← Inter 400 14px/20px
│  │  tank water gradually.          ││
│  │                                 ││
│  │  [Learn more about acclimation] ││  ← reef-500 text-link 14px
│  └─────────────────────────────────┘│
│                                     │
│  ┌─ Quick Stats ───────────────────┐│
│  │                                 ││
│  │   ┌──────────┐  ┌──────────┐   ││  ← 2 stat cards side by side
│  │   │    3     │  │    24    │   ││     each fills 1/2 width - 8px gap
│  │   │  Active  │  │  Total   │   ││
│  │   │  Plans   │  │ Livestock│   ││  ← Number: Fraunces 2xl (31px)
│  │   │          │  │          │   ││     Label: Inter 400 12px
│  │   │ 2 🟢 · 1 🟡│  │ 🐠18 🌿6 │   ││     bg-deep, text-surface
│  │   └──────────┘  └──────────┘   ││     radius-md
│  └─────────────────────────────────┘│
│                                     │
│                                     │  ← scroll space
├─────────────────────────────────────┤
│  🏠    📋    ➕    💬    ⚙️         │  ← Bottom Nav, 64px H
│ Home  Plans  New   Chat  Settings   │     Inter 400 11px labels
└─────────────────────────────────────┘     5 items, active: reef-500
                                              inactive: text-secondary
```

---

### Tablet (768px)

```
┌──────────────────────────────────────────────────────────────┐  768×1024
│  🏠 AquaPlan                                  🔔      🧑‍💼   │  Top Nav 56px
├──────────────────────────────────────────────────────────────┤
│                                                              │
│  ┌─────────────────────────┐                                │
│  │ Sidebar (280px)         │  Main Content (488px)          │
│  │                         │                                │
│  │ ┌─────────────────────┐ │  Good morning, Alex 🌊         │
│  │ │ 🧑‍💼 Alex Chen       │ │                                │
│  │ │ alex@email.com      │ │  ┌ ─ ─ Quick Start ─ ─ ─ ─ ┐  │
│  │ └─────────────────────┘ │  │ ┌─────────┐┌───────────┐ │  │
│  │                         │  │ │ 🪣       ││ 📸         │ │  │  2-col grid
│  │ ─── Main ───────────── │  │ │ New Plan ││Image→Plan  │ │  │  each 228×120
│  │ 🏠 Dashboard     [●]   │  │ └─────────┘└───────────┘ │  │
│  │ 📋 My Plans             │  │ ┌─────────┐              │  │
│  │ 💬 Q&A Chat             │  │ │ 💬      │              │  │
│  │                         │  │ │ Ask AI  │              │  │
│  │ ─── Quick ──────────── │  │ └─────────┘              │  │
│  │ ➕ New Plan             │  └ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ┘  │
│  │ 📸 Image → Plan         │                                │
│  │                         │  ┌ ─ ─ Recent Plans ─ ─ ─ ─ ┐  │
│  │ ────────────────────── │  │ ┌─────────────────────┐    │  │
│  │ ⚙️ Settings             │  │ │  [Preview]          │    │  │
│  │                         │  │ │  My 20G 🟢 92%     │    │  │
│  │                         │  │ └─────────────────────┘    │  │
│  │ (Active: reef bg,       │  │ ┌─────────────────────┐    │  │
│  │  white text)            │  │ │  [Preview]          │    │  │
│  │                         │  │ │  10G Betta 🟢 98%   │    │  │
│  └─────────────────────────┘  │ └─────────────────────┘    │  │
│                                └ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ┘  │
│                                ┌ ─ ─ Daily Tip ─ ─ ─ ─ ─ ┐  │
│                                │ 💡 Acclimate new fish... │  │
│                                └ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ┘  │
│                                ┌ ─ ─ Quick Stats ─ ─ ─ ─ ┐  │
│                                │   3 Active    24 Total   │  │
│                                │   Plans       Livestock  │  │
│                                └ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ┘  │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

---

### Desktop (1024px+)

```
┌──────────────────────────────────────────────────────────────────────────────┐  1440×900
│                                                                              │
│ ┌──────────┐ ┌─────────────────────────────────────────────────────────────┐ │
│ │ Sidebar  │ │                    Main Content (max 960px)                  │ │
│ │          │ │                                                             │ │
│ │  🏠 Aqua │ │  Good morning, Alex 🌊                        🔔      🧑‍💼   │ │
│ │  ─────── │ │                                                             │ │
│ │  [🐠]    │ │  ┌─────────────────────────────────────────────────────────┐│ │
│ │          │ │  │  Quick Start                                             ││ │
│ │  [🏠] ●  │ │  │                                                         ││ │
│ │  [📋]    │ │  │  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ││ │
│ │  [💬]    │ │  │  │    🪣        │  │     📸       │  │     💬       │  ││ │
│ │          │ │  │  │              │  │              │  │              │  ││ │
│ │  ─────── │ │  │  │  New Plan    │  │ Image → Plan │  │   Ask AI     │  ││ │
│ │  [➕]    │ │  │  │              │  │              │  │              │  ││ │
│ │  [📸]    │ │  │  │ 3-step       │  │ Snap &       │  │ Instant      │  ││ │
│ │          │ │  │  │ wizard       │  │ identify     │  │ answers      │  ││ │
│ │  ─────── │ │  │  └──────────────┘  └──────────────┘  └──────────────┘  ││ │
│ │  [⚙️]    │ │  │                                                         ││ │
│ │          │ │  └─────────────────────────────────────────────────────────┘│ │
│ │          │ │                                                             │ │
│ │ Collapse │ │  ┌──────────────────────────────────┐ ┌───────────────────┐ │ │
│ │   → [<]  │ │  │  Recent Plans                    │ │  Daily Tip        │ │ │
│ │          │ │  │                                  │ │                   │ │ │
│ │ 64px or  │ │  │  ┌──────────┐ ┌──────────┐     │ │  💡 Acclimate    │ │ │
│ │ 320px    │ │  │  │[Preview] │ │[Preview] │ →   │ │  new fish        │ │ │
│ │          │ │  │  │          │ │          │     │ │  slowly...       │ │ │
│ │ Footer:  │ │  │  │20G      │ │10G Betta │     │ │                   │ │ │
│ │ v1.0.0   │ │  │  │🟢 92%   │ │🟢 98%    │     │ │  [Learn more]   │ │ │
│ │          │ │  │  └──────────┘ └──────────┘     │ └───────────────────┘ │ │
│ └──────────┘ │  └──────────────────────────────────┘                     │ │
│              │                                                             │ │
│              │  ┌──────────────────────────────────┐ ┌───────────────────┐ │ │
│              │  │  Quick Stats                     │ │  Activity         │ │ │
│              │  │                                  │ │                   │ │ │
│              │  │   ┌────────┐ ┌────────┐         │ │  • Plan "20G     │ │ │
│              │  │   │   3    │ │   24   │         │ │    Planted"       │ │ │
│              │  │   │ Active │ │ Total  │         │ │    created 2d ago │ │ │
│              │  │   │ Plans  │ │Lvstock │         │ │                   │ │ │
│              │  │   └────────┘ └────────┘         │ │  • Water change  │ │ │
│              │  │                                  │ │    due in 3 days │ │ │
│              │  └──────────────────────────────────┘ └───────────────────┘ │ │
│              │                                                             │ │
│              │  12-column grid: Quick Start = 12col, Recent Plans = 8col, │ │
│              │  Daily Tip = 4col, Stats = 6col, Activity = 6col           │ │
│              └─────────────────────────────────────────────────────────────┘ │
└──────────────────────────────────────────────────────────────────────────────┘
```

**Desktop 12-col grid breakdown (960px max, 24px gutter):**
```
┌────┬────┬────┬────┬────┬────┬────┬────┬────┬────┬────┬────┐
│ 1  │ 2  │ 3  │ 4  │ 5  │ 6  │ 7  │ 8  │ 9  │ 10 │ 11 │ 12 │
├────┴────┴────┴────┴────┴────┴────┴────┴────┴────┴────┴────┤  Quick Start (all 3 cards)
├─────────────────────┬──────────────────────────────────────┤
│  Recent Plans (8col)│  Daily Tip (4col)                    │
├─────────────────────┴──────────────────────────────────────┤
│  Quick Stats (6col)  │  Activity Feed (6col)               │
└────────────────────────────────────────────────────────────┘
Each col = 58px + 24px gutter. Full width: 12×58 + 11×24 = 696 + 264 = 960px
```

---
