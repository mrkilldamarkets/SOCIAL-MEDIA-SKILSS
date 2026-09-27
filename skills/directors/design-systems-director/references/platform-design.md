# Platform Design — Instagram, Website, Presentations & Iconography

## Instagram Design System

**Feed aesthetic:** Magazine / Luxury brand / Investment firm / Operator journal

**Grid strategy:** The feed is a portfolio. Every 9 posts viewed together should tell a coherent visual story.

**Post aspect ratios:**
- Square: 1080×1080px (1:1)
- Portrait: 1080×1350px (4:5) — performs better algorithmically
- Story/Reel cover: 1080×1920px (9:16)

**Post template specifications:**

```
SINGLE IMAGE POST:
  Background:   Deep black or midnight blue — no white backgrounds
  Text overlay: If used, maximum 6 words. Level 02 type or above. Never body text on image.
  Safe zone:    Keep critical content 150px from edges (accounting for UI overlays)
  Branding:     Subtle — a small wordmark or no explicit branding on most posts

QUOTE/TEXT POST:
  Background:   Black or navy gradient. Never flat color alone — add subtle texture or vignette.
  Quote text:   Cormorant Garamond or Inter. Large. Centered or left-aligned.
  Attribution:  Small, uppercase, tracked, gold
  Layout:       Maximum 40 words of text. If more is needed — it's a carousel.
```

---

## Carousel Design Framework

**10-slide structure (standard):**

```
SLIDE 01 — HOOK
  Visual: Strongest image or high-contrast abstract
  Text: 5–8 words maximum. The promise. The curiosity gap.
  Layout: Full-bleed visual with text overlay
  Purpose: Stop the scroll. Create the open loop.

SLIDE 02 — PROBLEM / REALITY
  Visual: Can be simpler — focus is on the statement
  Text: The situation the audience is in right now. Their pain in their language.
  Layout: Text-dominant, clean

SLIDE 03 — ROOT CAUSE / WHY IT HAPPENS
  Visual: Minimal — a diagram or abstract if helpful
  Text: The insight they don't have yet. Why the problem exists.
  Layout: Text-dominant with possible visual element

SLIDE 04 — FRAMEWORK / OVERVIEW
  Visual: A visual diagram, simple model, or framework graphic
  Text: Name the framework. 1–2 sentences on what it is.
  Layout: Diagram-forward

SLIDES 05–07 — STEPS / EDUCATION
  Visual: Step number prominent, content-supporting visual
  Text: One clear step per slide. Specific, actionable, not generic.
  Layout: Step number (large, gold) + content

SLIDE 08 — COMMON MISTAKES
  Visual: Can use contrast (red accent for mistake indicators)
  Text: 3 mistakes. Brief. Specific.
  Layout: List format acceptable here — numbered or bulleted

SLIDE 09 — SUMMARY
  Visual: Clean recap — can use mini-version of slide 04 framework
  Text: The distilled lesson. One powerful sentence.
  Layout: Text-forward, premium

SLIDE 10 — CTA
  Visual: Minimal — focus on the action
  Text: One action. No more. "DM me [word]" / "Follow for more" / "Join the community"
  Layout: Clean, direct, no desperation
```

**Carousel design specs:**
- All slides use ecosystem palette
- Consistent typography scale across all 10 slides
- Progress indicator subtle but visible (dots or slide number)
- Swipe-right cue on slide 1 (arrow or "swipe for more" in small text)
- Branding: same placement on every slide (top-left wordmark or bottom-right)

---

## Website Component Library

**Hero sections:**
- Full-viewport height minimum
- Background: Deep black or cinematic gradient
- Headline: Level 01 type, centered or left-aligned
- Subheadline: Level 03 type, rgba(255,255,255,0.70)
- CTA: Primary gold button — one only
- Visual: 3D render, particle system, or high-quality image — never stock photo

**Feature sections (3-column grid):**
- 3 glass cards, evenly spaced
- Icon top (line art, gold)
- Title: Level 02
- Description: Level 03
- Optional: metric or highlight in gold

**Testimonial sections:**
- Dark background
- Quote: large, italic, Cormorant Garamond
- Attribution: photo (if available) + name + title
- Never: crowded, too many testimonials at once, obvious fake feel

**Pricing sections:**
- Cards per tier
- Featured tier: gold border, slightly elevated
- Price: very large, prominent
- Feature list: checkmarks in gold
- CTA: per-card

**Footer:**
- Dark background (#050505 or #08111F)
- Minimal — logo, navigation, social links, legal
- No content overload — the footer communicates restraint

---

## Presentation Design System

**Deck aesthetic:** Private equity / Family office / Institutional capital / Luxury strategy consulting

**Slide dimensions:** 16:9 widescreen standard (1920×1080 or 1280×720)

**Layout rules:**
- Maximum 40 words per slide in normal content slides (not counting data)
- One idea per slide — not two, not three
- Data visualized, not just listed
- Generous margins: minimum 80px on all sides

**Slide background variants:**
1. Full dark: #050505 or #08111F — primary for most slides
2. Dark gradient: left-to-right from #08111F to #102A43 — for variety on key slides
3. Blue marlin deep: #071A35 — for Blue Marlin-specific decks

**Data visualization:**
- Charts: dark background, gold primary line/bar, no chart junk
- Tables: minimal borders, alternating row shading (rgba white, 2%)
- Metrics highlighted: large number in gold, label in small uppercase

---

## Iconography System

**Style:** Minimal / Consistent / Elegant / Functional / Professional

**Specifications:**
- Line weight: 1.5px at standard size
- Style: Outline (not filled) — more sophisticated at small sizes
- Color: rgba(255,255,255,0.70) default / #D4AF37 for active/highlighted states
- Size: 24px standard UI / 32–48px for featured icons
- Grid: 24×24px safe zone for all icons

**Preferred icon libraries:** Lucide / Heroicons / Feather (all share a clean line aesthetic)

**Never:** Emoji as icons in professional interfaces / Filled solid icons (too heavy) /
Inconsistent styles mixed within one design / Icon overuse (every element does not need an icon)

