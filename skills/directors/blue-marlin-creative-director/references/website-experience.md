# Blue Marlin Securities — Website Experience Architecture

## Core Philosophy

The website should feel like a documentary. Not a website.
Users experience a story. They do not read information.

Every scroll is a descent. Every section is a revelation.
The user is not browsing — they are being shown something they weren't supposed to see.

---

## Technical Systems (Every Page)

All pages deploy: Scrollytelling / Layered depth / 3D motion / Cinematic transitions /
Parallax systems / Particle effects / Glass panels / Dynamic lighting /
Premium typography / Micro interactions

**Performance rule:** Visual richness must never compromise load speed.
Cinematic = precise and optimized. Not heavy and slow.

---

## Homepage — Full Narrative Architecture

### SECTION 01 — The Abyss

**Experience:** User enters darkness. A deep ocean environment. Tiny particles moving imperceptibly.
Subtle ambient motion throughout. A distant Blue Marlin silhouette appears — far away, barely visible.
No sales copy. No headlines. Only emotion.

**Objective:** Atmospheric entry. Trust before information. Set the world.

**Technical:** Full-viewport canvas. Particle field. Ambient audio optional (muted by default).
Marlin silhouette rendered in subtle light refraction. No text until scroll begins.

---

### SECTION 02 — The Emergence

**Experience:** The Marlin becomes more visible. Camera slowly approaches — the user is descending.
Institutional typography fades in from zero opacity, letter by letter or word by word.

```
Blue Marlin Securities
Capital. Intelligence. Sovereignty.
```

**Objective:** Identity reveal. Brand positioning statement. Emotional lock-in.

**Technical:** 3D camera movement or parallax depth illusion. Typography entrance: fade + subtle upward drift.
Timing: unhurried. 2–4 second entrance per element.

---

### SECTION 03 — The Descent

**Experience:** Camera continues moving deeper. Information emerges from darkness.
Glass panels surface one by one, each introducing a core capability:

- Research
- Capital
- Markets
- Technology
- Intelligence

**Objective:** Capability establishment. Institutional credibility. No selling — only presenting.

**Technical:** Glass card stagger reveals synced to scroll position. Each card has: icon (minimal line art
or 3D glyph), single word headline, one sentence maximum. Hover: card lifts, subtle gold edge glow.

---

### SECTION 04 — The Core

**Experience:** The Marlin fractures — breaks apart into particles. Particles transform: they become data
streams, network nodes, capital flow visualizations, research system maps, digital infrastructure.

**Objective:** Philosophy made visual. The Marlin is not just a fish — it is the system.

**Technical:** Particle dissolution animation. Post-fracture: particles reform into abstract network graph
or data architecture. Cinematic timing. Not rushed. This is the climax of the homepage story.

---

### SECTION 05 — The Future

**Experience:** User reaches final section. A digital institutional ecosystem appears — everything
connected, everything operating, everything intentional. The full Blue Marlin Securities platform visible
as living infrastructure. Ends with a single understated CTA.

**Objective:** Vision close. Aspiration. The invitation.

**CTA copy options:**
- "Request Access"
- "Begin the Conversation"
- "Enter"

Never: "Sign Up Free" / "Get Started" / "Learn More"

---

## Interior Page Architecture

### About / Philosophy Page
Lead with the brand philosophy: **"The Ocean Rewards Precision."**
Tell the story of the Marlin — intelligence, patience, precision, execution.
Connect philosophy to firm. No team photos. No "we believe in" corporate copy.

### Capital / Investment Page
Institutional in structure. Glass panel layout. Minimal prose. Data-first.
Feels like a fund factsheet — but cinematic. Metrics emerge on scroll.

### Research Page
Publication-style layout. Financial Times meets Bloomberg Terminal.
Dark background. Gold accents on category labels. Articles surface on scroll.

### Contact Page
Single panel. No form overload. One email. One sentence.
"Private inquiries only." Understated exclusivity.

---

## Motion Design Standards

**Entrance:** Fade + upward drift (12–20px travel). Duration: 400–800ms. Ease: cubic-bezier(0.16, 1, 0.3, 1)

**Hover states:** Lift (translateY -4px) + subtle shadow expansion. Duration: 200ms.

**Scroll-synced animations:** Tied to scroll progress, not time. Use Intersection Observer or GSAP ScrollTrigger.

**Camera/parallax:** Depth layers move at different scroll rates — foreground faster, background slower.

**Particle systems:** 60fps minimum. Sparse density. Drift speed: near-imperceptible.

**Forbidden motion:** Bouncing / Spinning / Fast cuts / Strobe effects / Aggressive transitions

