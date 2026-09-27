# Component Library — Specs, Typography & Motion

## Typography System

**Philosophy:** Authority / Sophistication / Confidence / Clarity

### Typeface Recommendations

| Use Case | Typeface | Alternative |
|---|---|---|
| Hero / Display | Cormorant Garamond (serif, editorial luxury) | Playfair Display |
| UI / Body | Inter (clean, institutional, modern) | DM Sans |
| Code / Monospace | JetBrains Mono | Fira Code |
| Captions / Labels | Inter, uppercase, tracked wide | DM Sans |

**Rule:** Maximum two typefaces per context. Never mix more than serif + sans in one design.

### Typography Hierarchy

```
Level 01 — Hero Headlines
  Size: 64–120px (web) / 48–72px (mobile)
  Weight: 300–400 (light to regular — let scale do the work)
  Tracking: 0 to -0.02em (slight tightening at large sizes)
  Usage: Hero sections, major impact moments

Level 02 — Section Titles
  Size: 36–48px
  Weight: 400–500
  Usage: Section headers, feature titles

Level 03 — Supporting Copy / Body
  Size: 16–20px
  Weight: 400
  Line height: 1.6–1.8 (generous for readability)
  Usage: Paragraphs, descriptions, narrative text

Level 04 — Micro Text / Labels
  Size: 11–13px
  Weight: 500–600
  Transform: UPPERCASE
  Tracking: 0.08–0.12em (wider tracking at small sizes)
  Usage: Category labels, metric labels, captions, metadata
```

---

## Spacing System

**Base unit:** 4px

**Scale:** 4 / 8 / 12 / 16 / 24 / 32 / 48 / 64 / 96 / 128px

**Doctrine:** Never overcrowd. Whitespace communicates value. Premium brands leave room to breathe.

**Section padding (website):**
- Mobile: 24px horizontal / 48px vertical
- Tablet: 48px horizontal / 64px vertical
- Desktop: 80–120px horizontal / 96–128px vertical

---

## Glass Card System

The primary UI component across all ecosystem products.

```css
/* Standard Glass Card */
background: rgba(255, 255, 255, 0.04);
border: 1px solid rgba(255, 255, 255, 0.08);
backdrop-filter: blur(12px);
-webkit-backdrop-filter: blur(12px);
border-radius: 12px;
box-shadow: 0 8px 32px rgba(0, 0, 0, 0.40),
            0 2px 8px rgba(0, 0, 0, 0.20);

/* Hover state */
transform: translateY(-4px);
box-shadow: 0 16px 48px rgba(0, 0, 0, 0.50),
            0 4px 12px rgba(0, 0, 0, 0.25);
border-color: rgba(212, 175, 55, 0.20); /* Gold accent on hover */
transition: all 200ms cubic-bezier(0.16, 1, 0.3, 1);

/* Premium variant (featured cards) */
background: rgba(255, 255, 255, 0.06);
border: 1px solid rgba(212, 175, 55, 0.15);
```

**Card content layout:**
- Icon or category label: Level 04 type, uppercase, gold
- Card title: Level 02 type
- Description: Level 03 type, rgba(255,255,255,0.70)
- Metric or data point (if applicable): Level 01 size, gold
- Never: cramped content, more than one primary CTA, competing visual hierarchies

---

## Button System

```css
/* Primary Button */
background: #D4AF37;
color: #050505;
padding: 14px 28px;
border-radius: 2px; /* Brand standard — minimal radius */
font-weight: 600;
font-size: 14px;
letter-spacing: 0.04em;
text-transform: uppercase;
transition: all 180ms ease;

/* Hover */
background: #F4D35E;
transform: translateY(-1px);
box-shadow: 0 4px 16px rgba(212, 175, 55, 0.30);

/* Secondary Button (Ghost) */
background: transparent;
border: 1px solid rgba(212, 175, 55, 0.50);
color: #D4AF37;

/* Never use: pill buttons (too casual), pure rounded corners (too startup-like) */
```

---

## Form System

```css
/* Input field */
background: rgba(255, 255, 255, 0.03);
border: 1px solid rgba(255, 255, 255, 0.10);
border-radius: 4px;
padding: 14px 16px;
color: #FFFFFF;
font-size: 16px;
transition: border-color 150ms ease;

/* Focus state */
border-color: #D4AF37;
outline: none;
box-shadow: 0 0 0 3px rgba(212, 175, 55, 0.10);

/* Label (floating or static above input) */
font-size: 12px;
text-transform: uppercase;
letter-spacing: 0.08em;
color: rgba(255, 255, 255, 0.50);
```

---

## Motion System

**Entrance animations (elements entering the viewport):**
```css
/* Standard reveal */
from: opacity: 0; transform: translateY(16px);
to: opacity: 1; transform: translateY(0);
duration: 500–700ms;
easing: cubic-bezier(0.16, 1, 0.3, 1);  /* Ease out — fast in, slow settle */

/* Stagger delay for sequential reveals */
Each element: +80–120ms delay from previous
```

**Hover interactions:**
```css
/* Lift */
transform: translateY(-4px);
duration: 200ms;
easing: ease;

/* Scale (use sparingly) */
transform: scale(1.02);
duration: 200ms;
```

**Forbidden motion:**
- Bouncing or spring animations (too playful)
- Spin or rotation on primary UI elements
- Flash effects or strobe-like transitions
- Fast-cut video editing for institutional content
- Motion that continues while the user is not interacting (except for ambient particles)

**Ambient particle systems:**
- Density: sparse (never more than 50 particles per viewport)
- Speed: near imperceptible drift
- Color: rgba(212, 175, 55, 0.15) for gold particles / rgba(255,255,255,0.08) for white
- Size: 1–3px

---

## Dashboard / Data Display System

**Philosophy:** Mission Control, not admin panel.

```
Data hierarchy in dashboards:
  Primary metric:    Large (40–56px), gold, center or top of card
  Secondary metric:  Medium (24–32px), white
  Label:            Small (12px), uppercase, tracked, rgba(255,255,255,0.50)
  Change indicator:  +X% (green: #4ADE80) / -X% (red: #F87171)

Table design:
  Background: transparent / alternating rgba(255,255,255,0.02)
  Header: uppercase, Level 04 type, gold
  Row borders: 1px solid rgba(255,255,255,0.05)
  No heavy borders — let whitespace separate rows
  Sortable columns: subtle sort indicator only
```

