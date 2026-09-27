# Member Journey — Onboarding, Retention & Outcomes

## Onboarding Flow (Tier 01 — 4x Prophet Access)

### Day 0 — Purchase Confirmed
- Payment confirmed → Supabase record created → automation triggered
- Discord access granted (role: "4x Prophet Member")
- Telegram community access link delivered
- Welcome email sent (automated):
  - Community rules
  - Discord navigation guide
  - Module 01 start link
  - Prop firm discount codes
  - 1-on-1 onboarding call booking link

### Day 1 — Orientation
- Staff welcome post in #introduce-yourself (triggered by new member join)
- Onboarding checklist DM:
  - [ ] Complete #introduce-yourself post
  - [ ] Watch orientation video
  - [ ] Start Module 01
  - [ ] Book 1-on-1 onboarding call

### Day 3 — First Check-In
- Automated DM: "How are you settling in? Any questions about getting started?"
- If no activity detected in Discord → gentle re-engagement trigger

### Day 7 — Onboarding Call
- 1-on-1 call with staff (Noah or JorDache)
- Agenda: Goals / Current level assessment / Recommended starting module / Expectations set
- Notes logged to member CRM record

### Day 14 — Two-Week Review
- Automated check-in: module progress, first questions, community engagement
- If no course activity → "What's getting in the way?" message — human response required

---

## Onboarding Flow (Tier 02 — Operator Mentorship)

### Application Stage
- Application submitted → reviewed by JorDache within 48 hours
- Accepted: discovery call booked → call completed → contract sent → payment processed
- Declined: respectful, direct response — no door fully closed if trajectory improves

### Day 0 — Contract & Payment
- Contract signed → payment confirmed → onboarding questionnaire sent
- Questionnaire covers: trading history / goals / current challenges / physique baseline / habits

### Day 1 — Onboarding Call (JorDache)
- 60-minute deep-dive session
- Establish: 90-day transformation targets / current level assessment / weekly rhythm / first assignments

### Week 1 — Foundation
- First trade review session scheduled
- Habit baseline established
- Physique baseline photos submitted (if physique coaching included)
- Weekly check-in cadence confirmed

### Ongoing — Weekly Rhythm
- Weekly trade submission for review (template required)
- Weekly habit/physique check-in (Friday)
- 1-on-1 call: bi-weekly minimum, weekly if needed
- Performance accountability: if commitments not met → addressed directly, not ignored

---

## Progression Tracking System

Every member has a progression record in Supabase:

```
Member ID
Tier (Access / Mentorship)
Join Date
Current Phase (01–04)
Modules Completed
Journal Streak (current + best)
Prop Firm Status (no challenge / in challenge / funded / paying out)
Withdrawal Count
Discord Activity Score
Last Check-In Date
Retention Risk Flag (auto-set if inactive 14+ days)
Notes (staff observations)
```

---

## Retention System

### Engagement Tiers

**Active:** Discord activity in last 7 days + course progress in last 14 days → healthy
**At Risk:** No Discord activity 14+ days OR no course progress 21+ days → flag for re-engagement
**Churning:** No activity 30 days → direct outreach, offer support call
**Gone Dark:** No response to outreach → cancellation likely imminent

### Re-Engagement Sequence (At Risk)

- Day 14 inactive: Automated DM — "We noticed you haven't been in the community lately. Is everything alright? What's getting in the way?"
- Day 21 inactive: Personal message from Noah or staff — not automated
- Day 30 inactive: JorDache personal message for Operator Mentorship / staff call for Access tier

### Cancellation Protocol

- 3 days post-cancellation: exit interview (automated survey)
- Survey captures: reason for leaving / what could have been better / likelihood to return / willingness to refer
- All responses logged — reviewed monthly for curriculum and experience improvements

---

## Success Metrics Dashboard

Track weekly:

| Metric | Target |
|---|---|
| New members | [Monthly goal] |
| Churn rate | <5% monthly |
| Active members (7-day) | >60% of total |
| Course completion (Module 01) | >80% of all members |
| Journal streak (30+ days) | Growing month over month |
| Prop firm challenges active | Growing month over month |
| Funded traders (total) | Tracked as a brand metric |
| Withdrawals (total) | Tracked as a brand metric |
| NPS / satisfaction | Surveyed quarterly |

---

## Referral Program

**Trigger:** Member achieves Phase 03 or above (Funded Trader status)

**Mechanics:**
- Unique referral code issued
- Referral converts → referring member earns 1 month free or credit toward annual plan
- Top referrers recognized monthly in community

**Positioning:** "You got funded. Help someone else get there." — referral should feel like a natural next step, not a sales ask.

