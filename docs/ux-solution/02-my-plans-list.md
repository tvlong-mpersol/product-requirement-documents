---
title: "AquaPlan UX — 02 My Plans List"
status: final
last_updated: 2026-05-31
related_prd: "BPL-148"
source_issue: "BPL-150"
related_screens:
  - my-plans-list
---

## 2. My Plans List

### Interaction Flow

1. **Entry:** Push from Dashboard "My Plans" tab. 250ms page transition.
2. **Search bar:** Tap → keyboard slides up, list filters in real-time as user types (300ms debounce). Clear button (✕) appears after first character.
3. **Filter chips:** Tap chip → toggles filter, 300ms ripple. "All" is default. Selected chip gets reef-500 background, white text. Multiple chips can be active (OR logic). Chip scrolls horizontally, fades at edges for overflow hint.
4. **Plan cards:** Show thumbnail, title, compatibility score badge, tank size, last modified. Tap card → pushes Plan Detail.
5. **Swipe actions:** Swipe left on card reveals 3 actions:
   - **Share** (bubble icon, seagrass bg) — tap → share sheet (native OS share)
   - **Duplicate** (copy icon, shallows bg) — tap → instant duplicate with "(Copy)" suffix, 400ms card enter at top of list
   - **Delete** (trash icon, coral bg) — tap → confirmation dialog
6. **Long-press:** Context menu with same 3 actions (no swipe needed). Medium haptic.
7. **Sort toggle:** "Sort by" dropdown in header: Recently Modified (default), Compatibility (high→low), Name (A→Z), Date Created.
8. **Empty state →** see Section 6.
9. **Pull-to-refresh:** 80px threshold, refreshes list from cloud, light haptic on release.

---

### Mobile (375px)

```
┌─────────────────────────────────────┐
│  ← Dashboard    My Plans     🔍    │  ← Nav bar 56px
│                          [Sort ⏷]  │     🔍 toggles search bar
├─────────────────────────────────────┤
│  ┌────────────────────────────────┐ │
│  │ 🔍  Search plans...       [✕] │ │  ← Search bar 48px H, 12px pad
│  └────────────────────────────────┘ │     radius-sm (4px), border
│                                     │     ✕ appears when text entered
│  ┌────────────────────────────────┐ │
│  │ [● All] [Aquarium] [Palud] [Ri]│→│  ← Filter chips, h-scroll
│  └────────────────────────────────┘ │     Inter 500 14px, radius-full
│                                     │     selected: bg-reef, text-white
│  ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ │     unselected: bg-surface, border
│                                     │
│  ┌────────────────────────────────┐ │  ← Plan card, 16px pad, radius-md
│  │ ┌──────┐                       │ │
│  │ │      │  My 20G Planted       │ │  ← Inter 600 16px title
│  │ │ Thumb│  🟢 92% Compatible    │ │  ← Confidence badge (--text-xs)
│  │ │ 80×80│  20 gal · Freshwater  │ │  ← Inter 400 14px meta
│  │ │      │  Modified 2 days ago  │ │  ← Inter 400 12px, text-secondary
│  │ └──────┘                       │ │
│  │                          [ › ] │ │  ← Chevron, tap → detail
│  │  ← Swipe left for actions →   │ │  ← Hint on first visit only
│  └────────────────────────────────┘ │
│                                     │
│  ┌────────────────────────────────┐ │
│  │ ┌──────┐                       │ │
│  │ │      │  10G Betta Haven      │ │
│  │ │ Thumb│  🟢 98% Compatible    │ │
│  │ │ 80×80│  10 gal · Freshwater  │ │
│  │ │      │  Modified 5 days ago  │ │
│  │ └──────┘                       │ │
│  │                          [ › ] │ │
│  └────────────────────────────────┘ │
│                                     │
│  ┌────────────────────────────────┐ │
│  │ ┌──────┐                       │ │
│  │ │      │  55G Paludarium       │ │
│  │ │ Thumb│  🟡 76% Compatible    │ │  ← 🟡 = needs attention
│  │ │ 80×80│  55 gal · Paludarium  │ │
│  │ │      │  Modified 1 week ago  │ │
│  │ └──────┘                       │ │
│  │                          [ › ] │ │
│  └────────────────────────────────┘ │
│                                     │
│  ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ │
│                                     │
│  ┌─ Swipe-Action States ──────────┐│
│  │ (plan card swiped left -80px)  ││
│  │                                 ││
│  │ ┌──────────────────────────────┤│  ← Card shifted left
│  │ │ Thumb│  My 20G Planted      ▐││
│  │ │ 80×80│  🟢 92% · 2d ago    ▐││
│  │ └──────────────────────────────┤│
│  │  [🔄 Share] [📋 Dup] [🗑 Del]  ││  ← 3 action buttons, each 64px
│  │    bubble    shallows  coral    ││     icon + 10px label below
│  └─────────────────────────────────┘│     Inter 400 10px
│                                     │
├─────────────────────────────────────┤
│  🏠    📋●   ➕    💬    ⚙️         │  ← Bottom Nav, Plans active
└─────────────────────────────────────┘
```

---
