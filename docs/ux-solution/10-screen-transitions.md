---
title: "AquaPlan UX — 10 Screen Transitions"
status: final
last_updated: 2026-05-31
related_prd: "BPL-148"
source_issue: "BPL-150"
related_screens:
  - navigation
---

## Appendix: Screen Transition Map

```
┌──────────────────────────────────────────────────────────────────────┐
│                                                                      │
│  ┌───────────┐    tap card     ┌───────────────┐                     │
│  │  Home      │──────────────→ │  Plan Detail   │                    │
│  │  Dashboard │                │  (with tabs)   │                    │
│  └─────┬─────┘                └───────┬───────┘                     │
│        │                              │                              │
│        │ tap "New Plan"                │ tap "Ask AI about this plan" │
│        ↓                              ↓                              │
│  ┌───────────┐    complete     ┌───────────────┐                     │
│  │ Onboarding │──────────────→ │  Q&A Chat      │                    │
│  │ Wizard     │                │  (contextual)  │                    │
│  └───────────┘                └───────────────┘                     │
│        │                              │                              │
│        │ tap "Image → Plan"            │ tap suggested question       │
│        ↓                              ↓                              │
│  ┌───────────┐    analyze      ┌───────────────┐                     │
│  │ Camera     │──────────────→ │  Results +     │                    │
│  │ Capture    │                │  Generate Plan │                    │
│  └───────────┘                └───────────────┘                     │
│                                      │                              │
│  All transitions: 250ms ease-in-out  │ "Generate full plan"          │
│                                      ↓                              │
│                                ┌───────────────┐                     │
│                                │  Plan Detail   │                    │
│                                │  (newly created)│                   │
│                                └───────────────┘                     │
│                                                                      │
│  Modal overlays (confirmations, share sheets):                       │
│    300ms ease-out, slide up from bottom (mobile)                    │
│    300ms ease-out, scale + fade (desktop)                            │
│    Backdrop: abyss at 40% opacity                                    │
│    Dismiss: swipe down (mobile), tap backdrop, Escape key           │
│                                                                      │
└──────────────────────────────────────────────────────────────────────┘
```

---

*UX solution compiled by UX-Architect against PRD [BPL-148](mention://issue/ca83a738-a1b4-4e22-ab85-d90dafce218a) (2026-05-30). All measurements use 4px grid, Ocean Depth Palette tokens, Major Third type scale, and defined motion tokens. Ready for Figma implementation.*
