# Investor Journey — Pipeline, Calls & Onboarding

## Full Investor Journey Map

```
Discovery        →  Investor encounters Blue Marlin via content, referral, or outreach
Research         →  Investor reviews website, materials, social proof
Inquiry          →  Investor makes contact or submits application
Qualification    →  Discovery call — assess fit, goals, risk tolerance, capital readiness
Presentation     →  Strategy overview, fee structure, process walkthrough
Q&A              →  All questions answered without pressure
Broker Setup     →  Investor opens BlackBull Markets account (or confirms existing)
KYC              →  Identity verification completed through broker
Funding          →  Capital deposited to broker account
LPOA / MAM Link  →  Limited Power of Attorney signed, account linked to Blue Marlin MAM
Allocation       →  Capital deployed to selected strategy
Reporting        →  Monthly reports delivered on schedule
Retention        →  Ongoing relationship maintenance, quarterly reviews
```

**Philosophy at each stage:** Never push the investor to the next stage — create the conditions for them to pull themselves forward.

---

## Discovery Call Structure

Duration: 30–45 minutes. No pitch until Section 4. The first half is entirely about the investor.

### Section 1 — Introduction (5 min)
Brief, warm, professional.
"Tell me a little about yourself and what brought you here."
Listen more than speak. Take notes.

### Section 2 — Investor Goals (10 min)
- What are you trying to achieve with this capital?
- What's your investment timeline?
- What does success look like for you in 12 months? 3 years?
- What experience do you have with managed accounts or alternative investments?

### Section 3 — Risk Tolerance (5 min)
- How do you respond to drawdowns? (Be specific — "if you saw -15% on paper, what would you do?")
- Is this speculative capital or core capital?
- What is your current liquidity position?

**Gate check:** If the investor cannot tolerate drawdowns, is using core savings, or expects guaranteed returns — disqualify gracefully. Do not proceed to Section 4.

### Section 4 — Strategy Overview (10 min)
Now present. Lead with process, not performance.
- What Blue Marlin Securities is and how it operates
- The strategies available (Oracle / Heist V7 / Discretionary)
- How MAM/LPOA works — the investor controls their own broker account
- How performance is measured and reported

### Section 5 — Fee Structure (5 min)
Transparent. Direct. No apology for the fees.
- Algo strategies: 30% performance fee + 5% management fee
- Manual/discretionary: 50% performance fee
- No upfront charges. Fees only on growth.

### Section 6 — Questions (5–10 min)
"What questions do you have?"
Answer everything factually. Do not over-explain. Do not pressure.
If you don't know the answer — say so and follow up within 24 hours.

### Section 7 — Next Steps
If the investor is qualified and interested:
- Confirm broker setup timeline
- Send follow-up email with materials within 2 hours
- Set clear next touchpoint (never leave a call without a defined next step)

---

## Qualification Framework

### Green Light (Proceed)
- Minimum $7,500 available as speculative/investment capital
- Understands and accepts drawdown possibility
- Investment timeline of 6 months minimum
- Has read materials or willing to review before committing
- No expectation of guaranteed returns
- Can complete KYC without complications

### Yellow Flag (Proceed with caution — educate more)
- Capital is savings but investor understands the risk
- Has had bad experiences with managed accounts before (address directly)
- Wants to start below minimum (discuss exceptions case by case with JorDache)
- Uncertain about timeline (help them define it)

### Red Flag (Disqualify gracefully)
- Expects guaranteed returns or specific monthly income
- Capital is rent money, emergency fund, or borrowed
- Wants to withdraw within 30–60 days
- Has litigation history with financial service providers
- Displays emotional volatility about money or markets

**Disqualification script:** "Based on what you've shared, I want to be honest with you — this may not be the right fit right now. [Reason]. This isn't a door closing permanently, but I'd rather you be in a position where you're fully comfortable with the risk profile before we move forward."

---

## CRM Pipeline Architecture

Every investor tracked through these fields in Supabase:

```
Investor ID
Full Name
Contact (email + phone + preferred method)
Source (referral / content / outreach / event)
Stage (Discovery / Research / Qualified / Broker Setup / KYC / Funded / Active / Inactive / Lost)
Stage Date (date of last stage change)
Capital Indicated ($)
Capital Allocated ($)
Strategy (Oracle / Heist V7 / Discretionary / Multiple)
Broker Account Status (Not started / In progress / Live)
KYC Status (Pending / Submitted / Approved)
Discovery Call Date
Notes (running relationship notes — not just status)
Last Contact Date
Next Action (with due date)
Referral Source (if referred — who referred them)
Retention Risk Flag
```

**Notes rule:** Every interaction gets a note within 24 hours. The notes field is the relationship memory — treat it as a professional journal, not a status log.

---

## Onboarding Sequence (Post-Qualification)

### Day 0 — Post-Call
- Follow-up email sent within 2 hours (see communication-assets.md for template)
- Investor Information Memorandum attached
- Broker setup instructions included
- CRM updated with call notes and next step

### Day 3 — Broker Check-In
- "Have you had a chance to start the broker setup? Any questions I can answer?"
- If they've started: confirm progress, offer to assist with any friction points
- If they haven't: no pressure — "Whenever you're ready, I'm here."

### Day 7 — KYC Follow-Up
- Confirm KYC document submission status
- If stuck: offer to walk them through it
- Provide direct broker contact if needed

### Day 14 — Funding Follow-Up
- If broker live but not funded: "Is there anything holding you back that I can help clarify?"
- If still undecided: offer a second call, not pressure

### Funded Day 1 — Allocation Confirmation
- Confirmation email: capital received, strategy allocated, reporting schedule confirmed
- Welcome to Blue Marlin message (warm but institutional)
- First monthly report date communicated

### Month 1 — First Report
- Monthly report delivered on time, no exceptions
- Personal note from JorDache or Sultan on the first report
- Check-in call offered (not mandatory — investor-led)

