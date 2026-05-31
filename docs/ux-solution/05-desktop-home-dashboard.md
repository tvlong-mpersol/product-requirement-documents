---
title: "AquaPlan UX — 05 Desktop Home Dashboard"
status: final
last_updated: 2026-05-31
related_prd: "BPL-148"
source_issue: "BPL-150"
related_screens:
  - home-dashboard
---

## 5. Desktop Layout (1024px+) — Home Dashboard

*(Already covered in Section 1 — Desktop. This section adds the collapsed icon rail state and keyboard navigation details.)*

### Sidebar States

**Expanded (320px):**
```
┌───────────────────────────────┐
│                               │
│  🐠  AquaPlan                 │  ← Fraunces 700 20px logo
│  ───────────────────────────  │
│                               │
│  ┌─ Main ───────────────────┐ │
│  │ 🏠  Dashboard        [●] │ │  ← 48px H rows, 16px pad
│  │ 📋  My Plans              │ │     Inter 500 16px
│  │ 💬  Q&A Chat              │ │     Active: reef bg, white text
│  │                           │ │     radius-md on active row
│  │ ── Quick Actions ─────── │ │
│  │ ➕  New Plan              │ │
│  │ 📸  Image → Plan          │ │
│  │                           │ │
│  │ ──────────────────────── │ │
│  │ ⚙️  Settings              │ │
│  │ ❓  Help & Support        │ │
│  └───────────────────────────┘ │
│                               │
│                               │
│  ┌──────────────────────────┐ │
│  │ 3 Active Plans           │ │  ← Mini stats in sidebar footer
│  │ 🟢 2 compatible          │ │     bg-deep, radius-md
│  │ 🟡 1 needs attention     │ │     Inter 400 12px
│  └──────────────────────────┘ │
│                               │
│  v1.0.0                 [<]  │  ← Collapse button, 32×32px
└───────────────────────────────┘
```

**Collapsed — Icon Rail (64px):**
```
┌──────┐
│      │
│  🐠  │  ← Logo icon only
│ ──── │
│      │
│  🏠  │  ← Active: reef bg pill
│  📋  │
│  💬  │
│      │
│ ──── │
│  ➕  │
│  📸  │
│      │
│ ──── │
│  ⚙️  │
│      │
│      │
│  [>] │  ← Expand button
│      │
└──────┘
Each icon: 24px Lucide, 40px touch target (centered in 64px rail)
Tooltip on hover (200ms delay): shows label to right of icon
```

### Keyboard Navigation (Full Desktop Map)

| Shortcut | Context | Action |
|---|---|---|
| `Ctrl+N` | Global | New Plan |
| `Ctrl+I` | Global | Image → Plan |
| `Ctrl+K` | Global | Ask AI (Q&A Chat) |
| `Ctrl+,` | Global | Settings |
| `Ctrl+1` | Global | Home Dashboard |
| `Ctrl+2` | Global | My Plans |
| `Ctrl+3` | Global | Q&A Chat |
| `Ctrl+B` | Global | Toggle sidebar |
| `/` | My Plans | Focus search |
| `↑/↓` | My Plans | Navigate plan list |
| `Enter` | My Plans | Open selected plan |
| `Ctrl+D` | Plan Detail | Duplicate plan |
| `Ctrl+Shift+D` | Plan Detail | Delete plan (with confirm) |
| `Ctrl+S` | Plan Detail | Share plan |
| `1-4` | Plan Detail | Switch tabs (Mat/Steps/Sched/Notes) |
| `Escape` | Any modal | Close modal/dialog |
| `?` | Global | Show keyboard shortcuts overlay |

---
