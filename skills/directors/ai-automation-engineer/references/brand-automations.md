# Brand-Specific Automation Requirements

## 4x Prophet

### Content Automation
- Hook + caption drafts from raw idea inputs
- Carousel slide copy generation
- Video concept briefs from pillar + topic combinations
- Content calendar population (weekly, auto-populated from idea bank)
- Cross-platform repurposing (long-form → short-form → caption → hook)
- Performance reporting: view rate, follower growth, DM volume by week

### Lead Generation Automation
- Lead capture form → CRM entry → tagged by source (YouTube / Instagram / TikTok / Telegram)
- Lead scoring: engagement level + intent signals
- DM trigger words: OPERATOR → Mentorship sequence | HEIST → MAM/copy trading sequence
- Follow-up sequences: 3-touch email + Telegram message within 48 hours of lead capture
- Abandoned inquiry: if discovery call not booked within 72 hours → re-engagement trigger

### Client Onboarding Automation
- Purchase confirmed → Telegram access granted → Discord access granted → welcome email sent
- Operator Mentorship application received → reviewed → accepted/declined → onboarding sequence
- Copy trading subscriber → followed → confirmation message → first week check-in at Day 7
- Prop firm affiliate: click tracked → code applied → commission logged

### Affiliate Tracking
- Prop firm click → UTM captured → stored in Supabase
- Monthly affiliate commission report auto-generated
- Active affiliate codes: 4XPROPHET (forex/XAUUSD), 4xprophet (futures)

---

## Blue Marlin Securities

### Investor Relations Automation
- Application received → CRM entry created → JorDache notified via Telegram
- Application qualified → discovery call booking link triggered → calendar event created
- Discovery call completed → follow-up email + document checklist sent automatically
- KYC document submitted → status updated in CRM → next step triggered
- Investment confirmed → investor portal access granted → welcome package delivered

### Reporting Automation
- Monthly MAM performance report → generated from BlackBull data → formatted to Blue Marlin standard → delivered to investor
- Quarterly capital summary → compiled → reviewed → distributed
- AUM tracker: updated on every capital event (deposit / withdrawal / new investor)

### Communication Automation
- Investor communication schedule: minimum monthly touch even without news
- Market event triggers: significant XAUUSD move → contextual investor update drafted for review
- Birthday / anniversary triggers → relationship maintenance touchpoints

---

## HowToBeBullish (HTBB)

### Member Onboarding
- Payment confirmed → Discord role assigned → welcome DM sent → resource library link delivered
- Onboarding sequence: Day 1 (welcome) / Day 3 (community guide) / Day 7 (first check-in) / Day 14 (progress prompt)
- Referral tracking: referral code issued at signup → tracked → commission or credit applied

### Challenge & Progress Tracking
- Trading challenge submission → logged to Supabase → progress dashboard updated
- Milestone achieved → Discord announcement auto-posted → congratulations DM sent
- Funded trader milestone (prop firm pass) → Discord recognition → case study request triggered

### Community Automation
- Weekly report: member growth / active members / challenge completions / milestone awards
- Churn risk detection: member inactive 14+ days → re-engagement sequence triggered
- Discord engagement report: weekly summary of most active threads, top contributors

### Retention Automation
- Subscription renewal reminder: 7 days before → 3 days before → day of
- Churn interview: 3 days after cancellation → automated survey → response logged

---

## Legacy By Darling

### Client Onboarding
- Application received → intake questionnaire triggered → responses logged to Supabase
- Accepted → contract sent → payment link → portal access granted → first session booked
- Day 1 onboarding sequence: welcome email / portal walkthrough video / first check-in scheduled

### Weekly Check-In Automation
- Check-in form reminder: every Sunday evening to all active clients
- Form submitted → response parsed → coach summary generated (AI-assisted) → JorDache notified
- Missed check-in → follow-up reminder at 24 hours → escalation at 48 hours

### Progress Tracking
- Weekly weight/measurement submission → logged → trend calculated → dashboard updated
- Progress photo submitted → stored in Supabase Storage → comparison view updated
- Milestone hit → celebration message sent → case study request triggered

### Retention
- Transformation report: generated at 30 / 60 / 90 days → delivered to client
- End of contract: renewal offer triggered 2 weeks before end date → if no response → exit interview

---

## MrKillDaMarkets

### Content Pipeline
- Raw idea captured (voice note / text) → transcribed → formatted into content brief → added to content calendar
- YouTube video published → short-form clips brief auto-generated → Telegram and X post drafted
- Content performance report: weekly — views / watch time / subscriber change / top performers

### Community Management
- New Telegram follower → welcome message → pinned resources delivered
- Keyword triggers in DMs: "mentorship" / "funded" / "signals" → appropriate response + routing
- Inactive Telegram member (30 days no interaction) → re-engagement message

### Lead Routing
- YouTube comment with intent signal → flagged for manual response or automated DM
- Link clicks tracked by UTM → routed to correct funnel → lead captured

---

## Cross-Brand Automations

### Unified CRM Pipeline
- Every lead across all brands → single Supabase CRM table with brand tag
- Lead source tracked: platform + campaign + content piece
- Pipeline stages: Lead → Qualified → Discovery → Proposal → Closed / Lost
- Lost reason logged for every closed-lost lead → reviewed monthly

### Weekly Operator Report (Every Monday, 7am)
Auto-generated summary delivered to JorDache via Telegram:
```
📊 WEEKLY OPERATOR REPORT — [Date]

REVENUE
  4x Prophet:      $[X]
  Blue Marlin:     $[X]
  HTBB:            $[X]
  Legacy:          $[X]
  Total:           $[X]

NEW LEADS:         [X] across all brands
CONVERSIONS:       [X] total
AUTOMATION RUNS:   [X] total / [X]% success rate
HOURS SAVED:       ~[X] hours

ALERTS:
  [Any failed workflows / urgent items]
```

