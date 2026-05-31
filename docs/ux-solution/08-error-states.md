---
title: "AquaPlan UX — 08 Error States"
status: final
last_updated: 2026-05-31
related_prd: "BPL-148"
source_issue: "BPL-150"
related_screens:
  - error-states
---

## 8. Error States

### 8.1 Network Error — Banner + Retry

```
┌─────────────────────────────────────┐
│  ┌────────────────────────────────┐ │
│  │ 🔌  You're offline             │ │  ← Persistent top banner
│  │     Saved plans are available. │ │     44px H, sand-500 bg
│  │     AI features paused.        │ │     Inter 400 13px
│  │                         [✕]   │ │     Dismissible (swipe up or ✕)
│  └────────────────────────────────┘ │
├─────────────────────────────────────┤
│  🏠 AquaPlan                   🧑‍💼 │  ← Nav bar (normal app chrome)
├─────────────────────────────────────┤
│                                     │
│  (Dashboard content — recent plans  │
│   still visible from local cache)   │
│                                     │
│  ┌────────────────────────────────┐ │
│  │ ⚠️  Could not refresh           │ │  ← Inline error card
│  │                                 │ │     bg-surface, border-coral
│  │     Pull down to retry, or      │ │     coral-500 left border 3px
│  │     check your connection.      │ │
│  │                                 │ │
│  │        [Retry Now]             │ │  ← Secondary button
│  └────────────────────────────────┘ │     outlined coral
│                                     │
│  ┌────────────────────────────────┐ │
│  │  Quick Start                   │ │  ← Quick Start still works
│  │  (New Plan works offline)      │ │     offline-capable
│  │  [New Plan] [Ask AI (offline)] │ │     AI: shows cached knowledge
│  └────────────────────────────────┘ │
└─────────────────────────────────────┘
```

### 8.2 AI Unavailable — Fallback Card

```
┌─────────────────────────────────────┐
│  ← Back      AquaPlan AI          │
├─────────────────────────────────────┤
│                                     │
│  ┌────────────────────────────────┐ │
│  │                                 │ │
│  │          ┌──────────┐           │ │
│  │          │   😴     │           │ │  ← Friendly illustration
│  │          │  💤 ≈ 💤  │           │ │     AI taking a nap
│  │          └──────────┘           │ │
│  │                                 │ │
│  │    AI is taking a break         │ │  ← Fraunces xl (25px), abyss
│  │                                 │ │
│  │    Our AI assistant is          │ │  ← Inter base (16px), secondary
│  │    temporarily unavailable.     │ │
│  │    You can still:               │ │
│  │                                 │ │
│  │  ┌───────────────────────────┐ │ │
│  │  │ 📋  Browse your saved plans│ │ │  ← Offline mode options
│  │  └───────────────────────────┘ │ │     Each 48px H
│  │  ┌───────────────────────────┐ │ │     bg-surface, radius-md
│  │  │ 📖  Read aquarium guides  │ │ │     tap → bundled knowledge base
│  │  └───────────────────────────┘ │ │
│  │  ┌───────────────────────────┐ │ │
│  │  │ 📸  Identify a photo      │ │ │  ← On-device ML fallback
│  │  │     (basic mode)          │ │ │
│  │  └───────────────────────────┘ │ │
│  │                                 │ │
│  │        [Notify Me When Back]   │ │  ← Primary CTA
│  └────────────────────────────────┘ │
│                                     │
└─────────────────────────────────────┘
```

### 8.3 Image Unrecognized — Q&A Redirect

```
┌─────────────────────────────────────┐
│  Cancel       Results              │
├─────────────────────────────────────┤
│                                     │
│  ┌────────────────────────────────┐ │
│  │                                │ │
│  │     [Uploaded Image]           │ │  ← Dimmed at 60% opacity
│  │                                │ │
│  │  ┌──────────────────────────┐  │ │
│  │  │  😕                      │  │ │
│  │  │  I couldn't identify     │  │ │  ← Overlay card on image
│  │  │  this image.             │  │ │     bg-abyss 80% opacity
│  │  │                          │  │ │     radius-lg
│  │  │  Can you describe what   │  │ │
│  │  │  you see?                │  │ │  ← Fraunces lg (20px), white
│  │  └──────────────────────────┘  │ │
│  │                                │ │
│  └────────────────────────────────┘ │
│                                     │
│  ┌────────────────────────────────┐ │
│  │  💬  Tell us what's in the     │ │  ← Redirect to Q&A
│  │      photo and we'll help      │ │     tap → Q&A with context
│  │      you build the plan.       │ │     (image attached to chat)
│  │                          [→]  │ │
│  └────────────────────────────────┘ │
│                                     │
│  ┌────────────────────────────────┐ │
│  │  📸  Try Another Photo         │ │  ← Secondary action
│  └────────────────────────────────┘ │
│                                     │
│  ┌────────────────────────────────┐ │
│  │  🪣  Create Plan Manually      │ │  ← Bypass to onboarding wizard
│  └────────────────────────────────┘ │
└─────────────────────────────────────┘
```

---
