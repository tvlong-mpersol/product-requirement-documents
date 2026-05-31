---
title: "AquaPlan UX — 11 Design Decisions"
status: final
last_updated: 2026-05-31
related_prd: "BPL-148"
source_issue: "BPL-150"
related_screens:

---

## 9. Design Decision Rationale

### Why Bottom Nav (Mobile) over Hamburger Menu
Competitor research showed hobbyists make 3-5 quick checks per day (morning feeding, evening viewing, weekend maintenance). Bottom navigation provides one-thumb access to all core actions — matching the mobile-first behavior observed in AquaLens (freemium, most feature-complete tracker). Hamburger menus hide discoverability; our 5-tab layout surfaces Home, Plans, Create (+), AI Chat, and Settings with zero cognitive load.

### Why Horizontal Scroll for Recent Plans
Based on AqAdvisor's shareable URL pattern, users often have 2-3 active plans and 5-10 archived plans. A horizontal carousel surfaces the 3 most recent without overwhelming the dashboard, while "See All" provides the full list view. This matches Buce Plant's visual-first approach — thumbnail images sell the dream before the data.

### Why Accordion Materials (Not Flat List)
Plan Detail must show 20-40 items across 4 categories. Accordions prevent overwhelming scroll while keeping all sections accessible with one tap. The PRD's compatibility algorithm (AqAdvisor-style) benefits from grouped display — seeing all livestock together helps users spot the one ⚠️ warning in context.

### Why Staggered Card-Enter Animation
The 100ms stagger per card gives a "flowing water" feel that reinforces the Zen of Water design philosophy. It also guides the eye naturally from top to bottom, matching the reading pattern for stocking lists (most important — livestock — appears first).

### Why 64px Collapsed Sidebar (Desktop)
320px full sidebar is generous for discovery, but power users with established plans need maximum canvas. The 64px icon rail collapses to recognizable Lucide icons with tooltips on hover — matching VS Code's proven pattern. Keyboard shortcut ⌘\ toggles it instantly.

---

*End of Expanded UX Solution — ready for Figma implementation.*
