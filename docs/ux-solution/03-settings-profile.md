---
title: "AquaPlan UX — 03 Settings Profile"
status: final
last_updated: 2026-05-31
related_prd: "BPL-148"
source_issue: "BPL-150"
related_screens:
  - settings-profile
---

## 3. Settings / Profile

### Interaction Flow

1. **Entry:** Push from Bottom Nav ⚙️ or avatar tap. 250ms page transition.
2. **Profile section:** Tap row → pushes Profile Edit screen (name, email, avatar upload). Avatar uses 300ms ripple.
3. **Account section:** "Change Password" → pushes password form. "Linked Accounts" → OAuth management.
4. **Notifications:** Toggle switches. 300ms `ease-out` animation on toggle. Light haptic on toggle. Sub-settings reveal inline when master toggle is ON (push-down animation 250ms).
5. **Display:** Radio group for Light/Dark/System. Instant preview — toggling shows the change immediately behind a 200ms crossfade. System follows OS preference.
6. **AI Preferences:** Model dropdown (GPT-4o, Claude, Gemini, Local). Confidence threshold slider (50-100%). "Show confidence scores" toggle (default ON — "Transparent > Magical" principle).
7. **About:** Version number, build info. Tap version 3× → easter egg (bubble animation). Links to: Privacy Policy, Terms of Service, Licenses (pushes webview).
8. **Sign Out:** Red text. Tap → confirmation dialog: "Sign out? Your plans are saved to your account." [Cancel] [Sign Out]. Destructive action requires two taps.
9. **Haptics:** Light on toggles, medium on sign-out confirmation.

---

### Mobile (375px)

```
┌─────────────────────────────────────┐
│  ← Back          Settings          │  ← Nav bar 56px
├─────────────────────────────────────┤
│                                     │
│  ┌────────────────────────────────┐ │
│  │  ┌────┐                        │ │  ← Profile section
│  │  │    │  Alex Chen             │ │     Avatar 56×56, radius-full
│  │  │ 🧑‍💼 │  alex.chen@email.com  │ │     Fraunces 600 20px name
│  │  └────┘                        │ │     Inter 400 14px email
│  │                          [ › ] │ │     Tap → Edit Profile
│  └────────────────────────────────┘ │     bg-surface, radius-md
│                                     │
│  ─── Account ──────────────────────│  ← Section header, Inter 500 12px
│                                     │     uppercase, text-secondary,
│  ┌────────────────────────────────┐ │     letter-spacing 0.5px, mt-8
│  │  🔑  Change Password     [ › ] │ │
│  ├────────────────────────────────┤ │  ← Grouped rows, 48px H each
│  │  🔗  Linked Accounts     [ › ] │ │     Inter 400 16px, Lucide 20px
│  ├────────────────────────────────┤ │     Inside: bg-white (light)
│  │  🗑   Delete Account      [ › ] │ │     Separator: 1px border
│  └────────────────────────────────┘ │     Entire group: radius-md
│                                     │
│  ─── Notifications ────────────────│
│                                     │
│  ┌────────────────────────────────┐ │
│  │  🔔  Push Notifications  [●──]│ │  ← Toggle (●── = ON, ──○ = OFF)
│  ├────────────────────────────────┤ │     reef-500 active track
│  │  📧  Email Digest        [●──]│ │     48px H, Inter 400 16px
│  ├────────────────────────────────┤ │
│  │     ┌─ Sub-options (when ON) ─┤ │  ← Revealed inline, pushed down
│  │     │ ⏰  Weekly summary [●──]│ │     bg-deep (slightly inset)
│  │     │ 💡  Tips & tricks  [──○]│ │     Inter 400 14px
│  │     └─────────────────────────┤ │
│  ├────────────────────────────────┤ │
│  │  📢  Product Updates     [──○]│ │
│  └────────────────────────────────┘ │
│                                     │
│  ─── Display ──────────────────────│
│                                     │
│  ┌────────────────────────────────┐ │
│  │  ☀️  Light              [ ○ ] │ │  ← Radio group
│  ├────────────────────────────────┤ │     ○ = unselected, ● = selected
│  │  🌙  Dark               [ ● ] │ │     48px H each
│  ├────────────────────────────────┤ │
│  │  📱  System Default     [ ○ ] │ │  ← Follows OS preference
│  └────────────────────────────────┘ │
│                                     │
│  ─── AI Preferences ───────────────│
│                                     │
│  ┌────────────────────────────────┐ │
│  │  🧠  AI Model                  │ │
│  │      GPT-4o              [ ⏷ ]│ │  ← Dropdown selector
│  ├────────────────────────────────┤ │     48px H, chevron indicator
│  │  🎯  Confidence Threshold      │ │
│  │      ───●────────────── 75%   │ │  ← Slider 48px H, reef track
│  ├────────────────────────────────┤ │     dot handle 20px, sand fill
│  │  🫧  Show Confidence     [●──]│ │  ← Toggle (default ON)
│  └────────────────────────────────┘ │
│                                     │
│  ─── About ────────────────────────│
│                                     │
│  ┌────────────────────────────────┐ │
│  │  ℹ️   Version           1.0.0 │ │
│  ├────────────────────────────────┤ │
│  │  📄  Privacy Policy     [ › ] │ │
│  ├────────────────────────────────┤ │
│  │  📜  Terms of Service   [ › ] │ │
│  ├────────────────────────────────┤ │
│  │  📚  Open Source Licenses[ › ]│ │
│  └────────────────────────────────┘ │
│                                     │
│  ┌────────────────────────────────┐ │
│  │         Sign Out               │ │  ← coral-500 (red) text
│  └────────────────────────────────┘ │     Centered, Inter 500 16px
│                                     │     48px H, radius-md
│                                     │     bg-surface, border-coral
├─────────────────────────────────────┤
│  🏠    📋    ➕    💬    ⚙️●        │  ← Bottom Nav, Settings active
└─────────────────────────────────────┘
```

---
