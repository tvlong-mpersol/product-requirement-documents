---
title: "AquaPlan UX — 06 Empty States"
status: final
last_updated: 2026-05-31
related_prd: "BPL-148"
source_issue: "BPL-150"
related_screens:
  - empty-states
  - home-dashboard
  - my-plans-list
  - plan-detail
---

## 6. Empty States

All empty states use watercolor-inspired botanical illustrations with subtle animated SVG elements (floating bubbles, swaying plants). Consistency: centered layout, Fraunces heading, Inter body, single clear CTA.

### 6.1 Home Dashboard — "Welcome to AquaPlan"

```
┌─────────────────────────────────────┐
│  🏠 AquaPlan                   🧑‍💼 │  ← Nav bar 56px
├─────────────────────────────────────┤
│                                     │
│                                     │
│            ┌───────────┐            │
│            │  🐠  🌿  🦐 │            │  ← Watercolor illustration
│            │  ~ ≈ ~  ≈ ~ │            │     200×200px, centered
│            │   ≈ ~ ≈ ~   │            │     animated bubble SVG
│            └───────────┘            │
│                                     │
│       Welcome to AquaPlan           │  ← Fraunces 2xl (31px), abyss
│                                     │
│    Your AI-powered aquarium         │  ← Inter base (16px), secondary
│    planner. Let's build your        │     max-width 280px, centered
│    dream tank together.             │
│                                     │
│                                     │
│  ┌────────────────────────────────┐ │
│  │    🪣  Create Your First Plan  │ │  ← Primary CTA, 48px H
│  └────────────────────────────────┘ │     reef-500 bg, white text
│                                     │     radius-md, full width-32px
│                                     │
│    Or try:  📸 Photo → Plan        │  ← Secondary text link
│              💬 Ask AquaPlan AI    │     Inter 500 14px, reef-500
│                                     │
│                                     │
└─────────────────────────────────────┘
```

### 6.2 My Plans — "Your first aquarium awaits 🌊"

```
┌─────────────────────────────────────┐
│  ← Dashboard    My Plans           │
├─────────────────────────────────────┤
│                                     │
│  ┌────────────────────────────────┐ │
│  │ 🔍  Search plans...            │ │  ← Search still available
│  └────────────────────────────────┘ │     (user might not know
│  [All] [Aquarium] [Palud] [Ripar]  │      they have no plans yet)
│                                     │
│                                     │
│            ┌───────────┐            │
│            │    🏺      │            │  ← Watercolor empty aquarium
│            │  ~ ≈ ~ ≈ ~ │            │     with small plant sprout
│            │   ≈ ~ ≈ ~  │            │     160×160px
│            └───────────┘            │
│                                     │
│     Your first aquarium awaits 🌊   │  ← Fraunces xl (25px), abyss
│                                     │
│     Plans you create will appear    │  ← Inter base (16px), secondary
│     here. Each plan guides you      │
│     from setup to thriving tank.    │
│                                     │
│  ┌────────────────────────────────┐ │
│  │    🪣  Create Your First Plan  │ │  ← Primary CTA
│  └────────────────────────────────┘ │
│                                     │
│  💡 Try snapping a photo of an     │  ← Tip with camera icon
│     aquarium you love!             │
│                                     │
└─────────────────────────────────────┘
```

### 6.3 Q&A Chat — "Ask me anything about aquariums"

```
┌─────────────────────────────────────┐
│  ← Back      AquaPlan AI          │
├─────────────────────────────────────┤
│                                     │
│                                     │
│            ┌───────────┐            │
│            │    🤖      │            │  ← AI assistant illustration
│            │  💬 ≈ 💬   │            │     bubble-500 colored
│            │   ≈ 💬 ≈   │            │     120×120px
│            └───────────┘            │
│                                     │
│    Ask me anything about            │  ← Fraunces xl (25px), abyss
│    aquariums                        │
│                                     │
│    I can help with stocking,        │  ← Inter base (16px), secondary
│    plants, water chemistry,         │     max-width 300px
│    troubleshooting, and more.       │
│                                     │
│  ┌─ Suggested Questions ──────────┐ │
│  │                                │ │
│  │  ┌──────────────────────────┐  │ │
│  │  │ 💬  Best fish for a 10G  │  │ │  ← Tap → sends message
│  │  └──────────────────────────┘  │ │     Inter 500 14px
│  │  ┌──────────────────────────┐  │ │     bg-surface, radius-full
│  │  │ 💬  How to cycle a tank  │  │ │     300ms ripple on tap
│  │  └──────────────────────────┘  │ │     Horizontal scroll
│  │  ┌──────────────────────────┐  │ │
│  │  │ 💬  Low light plants?    │  │ │
│  │  └──────────────────────────┘  │ │
│  │  ┌──────────────────────────┐  │ │
│  │  │ 💬  Why is water cloudy? │  │ │
│  │  └──────────────────────────┘  │ │
│  │  ┌──────────────────────────┐  │ │
│  │  │ 💬  Shrimp-safe fertilizer│  │ │
│  │  └──────────────────────────┘  │ │
│  └────────────────────────────────┘ │
│                                     │
│  ┌────────────────────────────────┐ │
│  │  Type your question...     ↗️  │ │  ← Input bar always visible
│  └────────────────────────────────┘ │     48px H, radius-sm
└─────────────────────────────────────┘
```

### 6.4 Search Empty — "No plans found"

```
┌─────────────────────────────────────┐
│  ← Dashboard    My Plans           │
├─────────────────────────────────────┤
│  ┌────────────────────────────────┐ │
│  │ 🔍  "reef tank"            [✕] │ │  ← Active search with query
│  └────────────────────────────────┘ │
│  [All] [Aquarium] [Paludarium] [Ri] │
│                                     │
│                                     │
│            ┌───────────┐            │
│            │    🔍      │            │  ← Search illustration
│            │  ≈  🐟  ≈  │            │     fish swimming away from
│            │   ≈   ≈    │            │     magnifying glass
│            └───────────┘            │
│                                     │
│         No plans found              │  ← Fraunces xl (25px), abyss
│                                     │
│     We couldn't find any plans      │  ← Inter base (16px), secondary
│     matching "reef tank".           │
│     Try a different search term     │
│     or adjust your filters.         │
│                                     │
│  ┌────────────────────────────────┐ │
│  │         Clear Filters          │ │  ← Secondary button, outlined
│  └────────────────────────────────┘ │
│                                     │
│  💡 Tip: Plans are searchable by   │  ← Helpful hint at bottom
│     name, tank type, and livestock │
└─────────────────────────────────────┘
```

---
