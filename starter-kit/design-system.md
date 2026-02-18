# LeafyPod 2.0 Design System

> Content-first, photo-forward, semantically colored
> Last updated: Feb 16, 2026

---

## Philosophy

**The plant is the star. The UI is the frame.**

Pure white backgrounds let plant photography command attention. Color is reserved for meaning — health states, AI interactions, calls-to-action. Nothing competes with the user's content.

---

## Color System

### Content-First Neutrals (90% of UI)

| Role | Light Mode | Dark Mode | Usage |
|------|------------|-----------|-------|
| **Background** | `#FFFFFF` Pure White | `#000000` Pure Black | Full canvas |
| **Surface** | `#F5F5F7` iOS Gray 6 | `#1C1C1E` iOS Gray 5 | Elevated sections |
| **Card** | `#FFFFFF` White | `#2C2C2E` iOS Gray 4 | Content containers |
| **Border Subtle** | `#E5E5EA` iOS Gray 5 | `#38383A` iOS Gray 3 | Card borders |
| **Border Strong** | `#C7C7CC` iOS Gray 4 | `#48484A` iOS Gray 2 | Focus states |

### Text Hierarchy

| Role | Light Mode | Dark Mode | Usage |
|------|------------|-----------|-------|
| **Primary** | `#000000` Black | `#FFFFFF` White | Headlines, plant names |
| **Secondary** | `#3C3C43` @60% | `#EBEBF5` @60% | Body text, descriptions |
| **Tertiary** | `#3C3C43` @30% | `#EBEBF5` @30% | Metadata, timestamps |
| **Quaternary** | `#3C3C43` @15% | `#EBEBF5` @15% | Disabled, placeholders |

### Semantic Accents (10% of UI)

Use sparingly. Every accent color has a job.

#### Primary Green — Growth & Life
```
Primary:  #2D5A3D  (Rich forest — stronger than #3A5A40)
Light:    #4A7A5A  (Moss — hover states)
Dark:     #1F4530  (Deep forest — dark mode variant)
Tint:     #E8F2EB  (Pale mint — badges, backgrounds)
```
**Used for:** Primary CTAs, healthy plants, success, "Add Plant" FAB

#### Warm Amber — Attention & Care
```
Primary:  #D4A373  (Warm sand)
Tint:     #FDF6ED  (Pale cream — backgrounds)
```
**Used for:** Care tasks due soon, gentle reminders, secondary CTAs

#### Cool Teal — AI & Intelligence
```
Primary:  #4A9B94  (Ocean teal — refined from earlier)
Tint:     #E8F3F2  (Pale ice)
```
**Used for:** AI FAB, AI-generated content, smart suggestions

#### Warm Coral — Problems & Urgency
```
Primary:  #C97B63  (Terracotta — gentler than harsh red)
Tint:     #FDF0EC  (Pale peach)
```
**Used for:** Unhealthy plants, errors, critical alerts

---

## Radius System

Friendly without being bubbly. Bumped up from earlier iterations.

| Component | Radius | Rationale |
|-----------|--------|-----------|
| **Tags / Chips** | `999px` (full) | Most friendly, browsable |
| **Buttons** | `16px` | **Changed from 12px** — more approachable |
| **Plant Cards** | `20px` | **Changed from 16px** — premium feel |
| **Feature Cards** | `24px` | Elevated content |
| **Bottom Sheets** | `28px` (top) | iOS standard, friendly |
| **AI FAB** | `32px` or full | Rounded square or squircle |
| **Inputs / Search** | `16px` | Matches buttons |
| **Avatars** | `50%` (circle) | Universal |

### Shape Philosophy

- Pure white cards with **1px subtle border** (`#E5E5EA` @ light, `#38383A` @ dark)
- **No drop shadows** — rely on border and spacing
- Generous internal padding: **20px** for cards, **16px** for compact

---

## Typography

**Outfit** for brand personality + **SF Pro** for system/data

### Display Scale

| Style | Size | Weight | Line Height | Use |
|-------|------|--------|-------------|-----|
| **Display L** | 48pt | Bold (700) | 52pt | AI greeting, hero |
| **Display M** | 40pt | Bold (700) | 44pt | Achievements |
| **Display S** | 34pt | Semibold (600) | 40pt | Screen titles |

### Heading Scale

| Style | Size | Weight | Use |
|-------|------|--------|-----|
| **H1** | 28pt | Semibold (600) | Plant names, main headers |
| **H2** | 22pt | Semibold (600) | Section headers |
| **H3** | 20pt | Medium (500) | Card titles, modal sections |

### Body Scale

| Style | Size | Weight | Use |
|-------|------|--------|-----|
| **Body Large** | 17pt | Regular (400) | AI briefing, primary reading |
| **Body Large Em** | 17pt | Semibold (600) | Emphasized content |
| **Body** | 16pt | Regular (400) | Standard text |
| **Body Em** | 16pt | Medium (500) | Important details |
| **Caption** | 13pt | Regular (400) | Metadata, timestamps |
| **Caption Em** | 13pt | Medium (500) | Emphasized metadata |
| **Overline** | 11pt | Medium (500) | Labels, all-caps tags |

### Special Treatments

- **Sensor numbers**: SF Pro with `font-variant-numeric: tabular-nums` — perfect alignment
- **Plant names**: Outfit Semibold, 28pt — the most important text on screen
- **AI briefing**: Outfit Regular 17pt, generous line height (1.5) — conversational

---

## Components

### Plant Card

```
┌─────────────────────────────────────┐  ← 20px radius
│  ┌──────────┐                       │
│  │          │  Monstera Deliciosa   │  ← 28pt semibold
│  │  [photo] │  ╭──────────╮         │  ← 12pt badge
│  │          │  │ Healthy  │         │     #E8F2EB bg
│  └──────────┘  ╰──────────╯         │     #2D5A3D text
│              Water in 2 days        │  ← 14pt secondary
└─────────────────────────────────────┘
```

- **Size**: Full width minus 32px margins, 160px height
- **Photo**: 100×136px, 12px radius left side
- **Padding**: 12px all sides
- **Border**: 1px `#E5E5EA`
- **Background**: White

### Status Badge

| State | Background | Text | Usage |
|-------|------------|------|-------|
| **Thriving** | `#E8F2EB` | `#2D5A3D` | Exceptional growth |
| **Healthy** | `#E8F2EB` | `#4A7A5A` | Normal, good |
| **Attention** | `#FDF6ED` | `#D4A373` | Care due soon |
| **Unhealthy** | `#FDF0EC` | `#C97B63` | Problem identified |
| **Critical** | `#C97B63` | `#FFFFFF` | Urgent — filled, not pill |

- **Pill**: 14px radius (full on 28px height)
- **Padding**: 6px 12px
- **Font**: 12pt Medium

### Button Primary

```
┌────────────────┐  ← 16px radius
│  Identify Plant│  ← 17pt semibold, white
└────────────────┘
```

- **Height**: 52px
- **Padding**: 0 24px
- **Background**: `#2D5A3D`
- **Pressed**: `#1F4530` (dark variant)
- **Disabled**: `#3C3C43` @15% bg, `@30%` text

### AI FAB

```
┌──────────┐
│    ✨    │  ← 32px radius (rounded square)
└──────────┘
```

- **Size**: 64×64px
- **Background**: `#4A9B94` (teal — AI is intelligent, not just growth)
- **Shadow**: Subtle elevation — 0 4px 12px rgba(0,0,0,0.15)
- **Icon**: 28pt white sparkle

### Bottom Sheet

```
╭────────────────────────────────╮  ← 28px top radius
│ ━━━━━━                         │     drag handle
│                                │
│     [content]                  │
│                                │
╰────────────────────────────────╯
```

- **Top radius**: 28px
- **Bottom radius**: 0 (grounded)
- **Drag handle**: 36×5px, 30% opacity pill
- **Backdrop**: Black 40% + 20px blur

---

## Semantic Health States

### Colorblind-Accessible System

| State | Color | Lightness | Icon |
|-------|-------|-----------|------|
| **Thriving** | `#2D5A3D` Green | 25% (darkest) | ✨ Sparkle |
| **Healthy** | `#4A7A5A` Light green | 38% | ✓ Check |
| **Attention** | `#D4A373` Amber | 66% | ⚠ Triangle |
| **Unhealthy** | `#C97B63` Coral | 59% | ● Circle |
| **Critical** | `#8B4540` Deep rust | 40% | ✕ X |

**Accessibility strategy:**
- Value differences (lightness) visible in grayscale
- Icon shapes provide non-color differentiation
- Text labels always accompany color

---

## Spacing System

Base unit: **8px**. All spacing is multiples.

| Token | Value | Use |
|-------|-------|-----|
| `xs` | 4px | Inline gaps, icon-to-text |
| `sm` | 8px | Within-component spacing |
| `md` | 16px | Between related elements |
| `lg` | 24px | Between cards, section gaps |
| `xl` | 32px | Major section separation |
| `2xl` | 48px | Screen edge padding |

### Layout Patterns

- **Screen margins**: 16px (iOS standard)
- **Between cards**: 16px
- **Card internal**: 12-20px based on density
- **Section headers to content**: 16px
- **Major sections**: 32px

---

## Dark Mode

### Principles

1. **Pure black backgrounds** — Photos look stunning, OLED saves power
2. **Elevated surfaces** get slightly lighter
3. **Accents stay warm** — Greens, ambers, teals work on dark
4. **Text inverts** — White primary, 60% gray secondary

### Photo Treatment

Plant photos on pure black:
- Greens appear more vibrant
- Creates "gallery" exhibition feel
- User content becomes the light source

### Border Adjustments

Dark mode borders need slight opacity increase:
- Light: 1px at 6% black
- Dark: 1px at 8% white (more visible on black)

---

## Usage Rules

### DO ✅

- Use **white backgrounds** as default
- Let **plant photos** provide visual interest
- Reserve **green** for "life/growth/CTAs"
- Use **amber** for gentle attention
- Use **teal** for AI interactions
- Use **coral** sparingly for problems
- Keep **90% of UI** in neutrals
- Use **Outfit** for brand moments (greetings, plant names)
- Use **SF Pro** for data and system text
- Use **tabular figures** for sensor readings
- Apply **generous radius** (16px+ for interactive elements)

### DON'T ❌

- Don't use green for "Cancel" or "Back" buttons
- Don't put colored backgrounds behind photos
- Don't use harsh primary red — use warm coral
- Don't use corporate blue for AI — use teal
- Don't use drop shadows — rely on borders and spacing
- Don't use sharp corners (0px radius) — everything is rounded

---

## Accessibility

### Contrast Ratios (WCAG 2.1 AA)

| Combination | Ratio | Pass |
|-------------|-------|------|
| Black text on white | 21:1 | ✅ AAA |
| `#2D5A3D` on white | 7.5:1 | ✅ AAA |
| `#4A9B94` on white | 4.8:1 | ✅ AA |
| White text on `#2D5A3D` | 7.5:1 | ✅ AAA |
| 60% gray on white | 7:1 | ✅ AA |

### Color Blindness Support

- **Avoid red/green pairs** — use green/amber/coral
- **Value differentiation** — health states differ in lightness
- **Icon + color** — always pair badges with distinct shapes

---

## Quick Reference

### Color Palette
```
Background:    #FFFFFF / #000000
Surface:       #F5F5F7 / #1C1C1E
Text Primary:  #000000 / #FFFFFF
Text Secondary: 60% gray
Border:        #E5E5EA / #38383A

Accent Green:  #2D5A3D
Accent Teal:   #4A9B94
Accent Amber:  #D4A373
Accent Coral:  #C97B63
```

### Radius Scale
```
Tags:     999px (full)
Buttons:  16px
Cards:    20px
Features: 24px
Sheets:   28px (top)
FAB:      32px
```

### Typography Scale
```
Display:  48-34pt
H1:       28pt semibold
H2:       22pt semibold
Body:     16-17pt regular
Caption:  13pt
```

---

**Version:** 2.0
**Last updated:** Feb 16, 2026
**Next review:** After first round of Figma prototypes