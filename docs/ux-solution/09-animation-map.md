---
title: "AquaPlan UX — 09 Animation Map"
status: final
last_updated: 2026-05-31
related_prd: "BPL-148"
source_issue: "BPL-150"
related_screens:
  - animation-tokens
---

## 9. Interaction Animation Map

### Complete Motion Token Reference

```
┌─────────────────────────────────────────────────────────────┐
│  ANIMATION           │ DURATION │ EASING      │ TRIGGER     │
├─────────────────────────────────────────────────────────────┤
│  Ripple tap           │ 300ms    │ ease-out    │ All buttons,│
│                       │          │             │ chips, cards│
├─────────────────────────────────────────────────────────────┤
│  Card enter (stagger) │ 400ms    │ ease-out    │ List load,  │
│                       │          │             │ search      │
│                       │          │             │ results     │
├─────────────────────────────────────────────────────────────┤
│  Page transition      │ 250ms    │ ease-in-out │ Nav pushes  │
├─────────────────────────────────────────────────────────────┤
│  AI pulse             │ 2000ms   │ ease-in-out │ Generation  │
│                       │          │ (loop)      │ state       │
├─────────────────────────────────────────────────────────────┤
│  Bubble float         │ 3000ms   │ linear      │ Ambient     │
│                       │          │ (loop)      │ background  │
├─────────────────────────────────────────────────────────────┤
│  Confidence reveal    │ 500ms    │ ease-out    │ Score       │
│                       │          │             │ percentages │
├─────────────────────────────────────────────────────────────┤
│  Skeleton shimmer     │ 1500ms   │ linear      │ List        │
│                       │          │ (loop)      │ loading     │
├─────────────────────────────────────────────────────────────┤
│  Accordion expand     │ 300ms    │ ease-out    │ Tab/content │
│                       │          │             │ expand      │
├─────────────────────────────────────────────────────────────┤
│  Toggle switch        │ 300ms    │ ease-out    │ Settings    │
│                       │          │             │ toggles     │
├─────────────────────────────────────────────────────────────┤
│  Crossfade            │ 200ms    │ ease-in-out │ Tab switch, │
│                       │          │             │ theme change│
├─────────────────────────────────────────────────────────────┤
│  Modal/sheet enter    │ 300ms    │ ease-out    │ Dialogs,    │
│                       │          │             │ bottom      │
│                       │          │             │ sheets      │
├─────────────────────────────────────────────────────────────┤
│  Swipe snap           │ 250ms    │ ease-out    │ Swipe       │
│                       │          │             │ actions     │
├─────────────────────────────────────────────────────────────┤
│  Badge counter pop    │ 400ms    │ ease-out    │ New         │
│                       │          │ (spring)    │ notification│
├─────────────────────────────────────────────────────────────┤
│  Tip rotation         │ 500ms    │ ease-in-out │ AI gen tips │
│                       │          │ (crossfade) │ cycling     │
└─────────────────────────────────────────────────────────────┘
```

### Haptic Feedback Map

```
┌──────────────────────────────────────────────────────┐
│  INTERACTION              │ HAPTIC     │ PLATFORM    │
├──────────────────────────────────────────────────────┤
│  Button tap (primary)      │ Light      │ iOS/Android │
│  Card tap                  │ None       │ —           │
│  Long-press (context menu) │ Medium     │ iOS/Android │
│  Swipe action reveal       │ Light      │ iOS/Android │
│  Pull-to-refresh threshold │ Light      │ iOS/Android │
│  Toggle switch             │ Light      │ iOS/Android │
│  Delete confirmation       │ Medium     │ iOS/Android │
│  Error banner appear       │ Heavy      │ iOS/Android │
│  AI generation complete    │ Success    │ iOS/Android │
│  Compatibility warning     │ Warning    │ iOS/Android │
└──────────────────────────────────────────────────────┘
```

---
