# Brand-Specific System Requirements

## 4x Heist Investments (Parent)

**Role:** Holding company hub and primary investor-facing platform

**Core systems to build:**
- Investor portal (MAM/PAMM reporting, AUM tracking, performance dashboard)
- Internal command dashboard (cross-brand analytics, revenue tracking, operations)
- LP/investor onboarding flow

**Design language:** Most institutional of all brands. Closest to Blue Marlin in tone.
Dark. Gold. Cinematic. No retail aesthetics.

**Key integrations:** BlackBull Markets data, Supabase, automated performance reporting

---

## Blue Marlin Securities

**Role:** Premium institutional capital brand — private capital, research, asset management

**Core systems to build:**
- Website (full cinematic scrollytelling experience — see blue-marlin-creative-director skill)
- Investor portal (private, application-gated)
- Research publication platform
- MAM reporting dashboard
- Client onboarding system

**Design language:** Deep ocean blue (#071A35), gold (#D4AF37), cinematic 3D, glassmorphism.
Closest references: private banking platforms, luxury family office sites.

**Non-negotiables:**
- Never feels retail
- No public-facing pricing
- Application-only access
- Every touchpoint reinforces institutional trust

---

## 4x Prophet

**Role:** Trading education and community — copy trading, signals, courses, mentorship

**Core systems to build:**
- Member portal (course access, community links, resource library)
- Copy trading dashboard (follower stats, performance, subscription management)
- Funnel system (lead capture → email → offer → checkout)
- Signals delivery system (Telegram integration or native)
- Affiliate tracking (prop firm codes: 4XPROPHET / 4xprophet)

**Design language:** Slightly more accessible than Blue Marlin — still dark, premium, gold.
Can use more motion and dynamic elements. Operator energy, not guru energy.

**Pricing to support:**
- Copy trading: $267/month
- Operator Mentorship: $5,000/month (application-only)
- Courses: variable

---

## HowToBeBullish (HTBB)

**Role:** Group mentorship platform — co-run with Noah Bush

**Core systems to build:**
- Member portal (course content, resources, community access)
- Challenge tracker (trading challenges, habit tracking)
- Progress dashboard (member performance, milestones)
- Discord integration layer
- Membership management (pricing: $177/month → $1,497/year)

**Design language:** Accessible premium. Dark but approachable. Educational feel without being generic.
Slightly warmer than the institutional brands.

---

## Legacy By Darling

**Role:** Fitness and lifestyle coaching brand — physique transformation, performance

**Core systems to build:**
- Client portal (program access, check-in system, progress photos)
- Habit dashboard (daily tracking, streaks, compliance)
- Nutrition system (meal plans, macro tracking integration)
- Check-in automation (weekly client submissions → coach review)
- Transformation analytics (progress over time, body composition trends)
- Coaching offer: $2,000/month, 3-month minimum

**Design language:** Premium fitness aesthetic — dark, clean, performance-focused.
Not supplement brand. Not Instagram fitness. Serious transformation infrastructure.

---

## MrKillDaMarkets

**Role:** Personal trading media brand — content, audience, community

**Core systems to build:**
- Link-in-bio / hub page (routes to all platforms and offers)
- Telegram community management tools
- Content scheduling integration
- YouTube analytics dashboard (custom — not just YouTube Studio)
- Lead capture for email list

**Design language:** Most media-forward of all brands. Still dark and premium but more
personality-driven. Can use more bold typography and contrast.

---

## Cross-Brand Infrastructure

These systems serve the entire ecosystem:

**CRM / Contact Management**
- Unified contact database across all brands
- Lead source tracking
- Conversion pipeline per brand
- Supabase backend

**Email Infrastructure**
- Transactional: automated sequences, onboarding, receipts
- Marketing: newsletters, launch sequences, community updates
- Segmented by brand — single sender infrastructure

**Analytics Layer**
- Revenue by brand
- Traffic by source and brand
- Conversion rates by funnel
- Community growth metrics
- Content performance (YouTube, Instagram, TikTok)

**Automation Stack**
- N8N as primary orchestration layer
- Triggers: form submissions, purchases, community actions, trading events
- Outputs: notifications, CRM updates, email sequences, Telegram messages

