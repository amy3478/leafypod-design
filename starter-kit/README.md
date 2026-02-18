# LeafyPod Design Prototype — Starter Kit

> Everything an AI coding agent needs to build interactive prototypes for LeafyPod.
> Drop this folder into any AI session (Claude, ChatGPT, Cursor, Copilot) as context.

---

## What's Inside

| File | Purpose | When to use |
|------|---------|-------------|
| `design-system.md` | Visual specs — colors, typography, radius, spacing, components | Every prototype session |
| `prototype-base.html` | Reusable HTML shell — phone frame, nav system, transitions | Starting a new prototype |
| `example-screen.html` | One complete screen extracted from the onboarding prototype | Show the AI "build like this" |
| `content-spec-template.md` | Blank template for specifying screen content | Planning a new flow |
| `visual-audit-template.md` | Blank template for competitive design analysis | Starting visual exploration |

---

## Quick Start

### 1. Plan your flow
Copy `content-spec-template.md`, fill in every screen's content (headlines, body, CTAs, states).

### 2. Build the prototype
Give your AI agent this prompt:

```
I'm building an interactive mobile prototype. Here's my context:

- Design system: [paste or attach design-system.md]
- Prototype base: [paste or attach prototype-base.html]  
- Example screen pattern: [paste or attach example-screen.html]
- Content spec: [paste your filled-out content spec]

Build all screens into a single HTML file following the base template patterns.
Wire the navigation between screens. Add smooth transitions.
Output should work on desktop (phone frame) and mobile (fullscreen).
```

### 3. Test & iterate
- **Desktop:** Open the HTML file in a browser — phone frame with shadow
- **Mobile:** Host it (GitHub Pages, Vercel, or `npx serve`) and open the URL on your phone
- **Home screen:** Add to home screen on iOS/Android for native app feel

---

## Design System Summary

**Brand:** LeafyPod — AI-powered plant care platform
**Philosophy:** Content-first, photography-forward. The plant is the star, the UI is the frame.

| Token | Value |
|-------|-------|
| Primary green | `#2D5A3D` |
| AI gradient | `linear-gradient(135deg, #82F4B1, #30C67C)` |
| Background | `#FFFFFF` (white canvas) |
| Text | `#000000` / `rgba(0,0,0,0.6)` |
| Border | `#E5E5EA` |
| Font | Outfit + SF Pro fallback |
| Button radius | `16px` |
| Card radius | `20px` |
| Pill radius | `999px` |

Full specs in `design-system.md`.

---

## Tips for AI Agents

- **One screen = one `<div class="screen">`** with an id. Navigation is handled by `navigate('screen-id')` and `goBack()`.
- **Dark screens** (green bg, camera) need white status bar. Add screen id to `darkScreens` array in JS.
- **Auto-advance screens** (loading/analyzing): use `setTimeout(() => navigate('next'), 2500)` triggered when screen becomes active.
- **Scrollable screens**: add content inside the screen div — overflow-y is auto.
- **Sticky bottom buttons**: use `position:absolute; bottom:0` with gradient fade background.
- **New paths**: set `currentPath` variable in JS, then branch in advance functions.

---

## Hosting

**GitHub Pages (free, easiest):**
```bash
git init && git add . && git commit -m "init"
gh repo create my-prototype --public --source=. --push
gh api repos/USERNAME/my-prototype/pages -X POST -f "source[branch]=main" -f "source[path]=/"
# Live at: USERNAME.github.io/my-prototype/prototype.html
```

**Quick local server (for phone testing on same WiFi):**
```bash
npx serve .
# Open the IP:port URL on your phone
```
