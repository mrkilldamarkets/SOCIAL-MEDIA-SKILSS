# Product Development Framework

## Pre-Build Discovery Protocol

Before writing a single line of code or opening Lovable, answer all seven:

```
Problem:          What specific problem exists?
Who:              Who experiences it — and how often?
Cost of Problem:  What does it cost them in time, money, or friction?
Simplest Fix:     What is the minimum viable solution?
Scalability:      Can this serve 10x users without breaking?
Automation:       What parts can be automated?
Asset Potential:  Can this become a revenue-generating or leverage-multiplying asset?
```

If the problem is unclear — do not build. Clarify first.

---

## Product Development Stages

### Stage 1 — Architecture
Define before touching code.

```
Product Name:         [Name]
Brand:                [Which 4x Heist entity this lives under]
Core Function:        [One sentence — what it does]
Target User:          [Specific persona]
User Journey:         [Entry point → core action → outcome]
Key Features:         [Maximum 5 for MVP]
Non-Features:         [What this explicitly does NOT do]
Revenue Connection:   [How this connects to or generates revenue]
```

### Stage 2 — Database Design

Design schema before building UI. Rules:
- Every table has a clear single responsibility
- Naming: snake_case, descriptive, no abbreviations
- Foreign keys defined from the start
- Created_at / updated_at on every table
- Soft deletes preferred over hard deletes for user data
- RLS (Row Level Security) enabled on all Supabase tables by default

**Schema documentation format:**
```
Table: [table_name]
Purpose: [what this stores]
Columns:
  - id: uuid (PK, auto-generated)
  - [column]: [type] — [purpose]
  - created_at: timestamptz
  - updated_at: timestamptz
Relationships:
  - [relationship description]
RLS: [policy summary]
```

### Stage 3 — User Flow Architecture

Map every user flow before building:
```
Flow Name:    [e.g., New Member Onboarding]
Trigger:      [What starts this flow]
Steps:        [Numbered sequence of actions + system responses]
Exit Points:  [Where users can leave or divert]
Success:      [What the completed flow looks like]
Edge Cases:   [What can go wrong]
```

### Stage 4 — Build Order

Always build in this sequence:
1. Database schema
2. Authentication
3. Core data operations (CRUD)
4. API layer / server actions
5. Core UI components
6. Page assembly
7. Automation connections
8. Testing
9. Performance optimization
10. Deployment

### Stage 5 — Documentation

Every shipped product includes:
- Architecture overview (system diagram or written)
- Database schema with all tables documented
- User flows mapped
- Automation triggers and actions documented
- API endpoints documented
- Known limitations or future expansion notes
- Operational runbook (who does what when something breaks)

---

## Lovable Build Brief Format

When producing a Lovable brief:

```
PROJECT NAME:     [Name]
BRAND:            [Which entity]
PURPOSE:          [One paragraph — problem + solution]

TECH STACK:
  Frontend: Next.js + TypeScript
  Backend: Supabase
  Auth: Supabase Auth
  Hosting: Vercel

PAGES / ROUTES:
  / — [Description]
  /dashboard — [Description]
  [etc.]

DATABASE TABLES:
  [Full schema per Stage 2 format]

KEY FEATURES:
  1. [Feature + user-facing description]
  2. [etc.]

USER FLOWS:
  [Per Stage 3 format]

DESIGN DIRECTION:
  Style: [Cinematic / Institutional / etc.]
  Colors: #0A0A0A background / #C9A84C gold / #E8E8E8 white
  Font: Inter
  Components: Glass cards / Floating panels / Dark theme
  References: [Specific visual references]

AUTOMATION:
  [Any N8N / Make / Zapier flows required]

MVP SCOPE:
  In: [What is built in Phase 1]
  Out: [What is explicitly deferred]

SUCCESS METRIC:
  [Single measurable outcome for MVP]
```

---

## UI Component Standards

### Cards
- Background: rgba(255,255,255,0.03)
- Border: 1px solid rgba(255,255,255,0.08)
- Blur: backdrop-filter: blur(12px)
- Radius: 2px (brand standard) or 8–12px (premium feel, context-dependent)
- Shadow: 0 8px 32px rgba(0,0,0,0.4)

### Buttons (Primary)
- Background: #C9A84C
- Text: #0A0A0A
- Hover: brightness(1.1) + subtle lift
- Never: Rounded pill buttons on institutional products

### Data Tables
- Dark background
- Subtle row alternation (rgba white, 2–3% opacity)
- No heavy borders
- Sortable headers with minimal indicators
- Pagination over infinite scroll for data-dense tables

### Forms
- Floating label style
- Dark input backgrounds
- Gold focus ring (1px, #C9A84C)
- Inline validation — no modal errors

