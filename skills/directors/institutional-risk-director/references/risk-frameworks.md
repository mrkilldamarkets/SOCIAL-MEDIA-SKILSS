# Risk Frameworks — Scoring, Audits & Business Continuity

## Risk Scoring System

Every identified risk receives five attributes before mitigation planning:

```
RISK REGISTER ENTRY:

Risk:               [Specific description — not vague]
Category:           [Financial / Operational / Strategic / Technology / Legal /
                     Reputation / Concentration / Key Person / Cyber / Market]
Probability:        [Low (<20%) / Medium (20–60%) / High (>60%)]
Impact:             [Low (recoverable in weeks) / Medium (recoverable in months) /
                     High (permanent or multi-year damage)]
Severity:           [Probability × Impact = Low / Medium / High / Critical]
Time Horizon:       [Immediate / Near-term (0–6 months) / Long-term (6 months+)]
Mitigation Plan:    [Specific action — not "monitor"]
Owner:              [Who is responsible for mitigation]
Review Date:        [When this is reassessed]
```

**Response thresholds:**
- Low severity: Monitor. No immediate action required.
- Medium severity: Mitigation plan active within 30 days.
- High severity: Mitigation plan active within 7 days. JorDache informed.
- Critical severity: Immediate action. All non-urgent activities paused until addressed.

---

## Quarterly Risk Audit

Run every quarter across all ten categories:

```
QUARTERLY RISK AUDIT — [Quarter / Year]

FINANCIAL RISK:
  Cash reserves:          $[X] — [X months coverage] — [Green / Yellow / Red]
  Revenue concentration:  Top source = [X]% of total — [Green / Yellow / Red]
  Counterparty exposure:  [Any single partner/broker/platform >30% of operations?]
  Debt exposure:          $[X] — [Type and terms]

OPERATIONAL RISK:
  Founder dependence:     [What % of operations requires JorDache personally?]
  Documented processes:   [% of critical workflows documented]
  Team capacity:          [Any single-person bottlenecks?]
  Execution gaps:         [Any recurring process failures in last 90 days?]

KEY PERSON RISK:
  JorDache dependencies:  [List every function that stops if unavailable]
  Coverage plans:         [What happens for each dependency if unavailable 30 days?]
  Knowledge concentration: [What critical information exists only in JorDache's head?]

TECHNOLOGY RISK:
  Platform dependencies:  [Which platforms would cause the most damage if removed?]
  Data backup status:     [When was last backup verified? 3-2-1 rule confirmed?]
  Credential security:    [Password manager in use? 2FA on all accounts?]
  Vendor dependencies:    [Any single third-party tool that's mission-critical?]

CONCENTRATION RISK:
  Revenue sources:        [Any single source >40%?]
  Platform dependence:    [Any single platform >50% of audience or revenue?]
  Geographic concentration: [Any single market >60%?]
  Partner concentration:  [Any single partner >30% of revenue?]

REPUTATION RISK:
  Content risk:           [Any published content that creates exposure?]
  Partnership risk:       [Any current partner whose reputation is deteriorating?]
  Community risk:         [Any active disputes or complaints requiring attention?]

LEGAL RISK:
  Contract review:        [All major contracts reviewed in last 12 months?]
  Compliance:             [FTC disclosures, financial advertising standards, data privacy]
  Business structure:     [Entity structure appropriate for current operations?]

OVERALL RISK POSTURE:     [Green / Yellow / Red]
TOP THREE RISKS THIS QUARTER:
  1. [Risk] — Severity: [X] — Owner: [X] — Mitigation by: [Date]
  2. [Risk] — Severity: [X] — Owner: [X] — Mitigation by: [Date]
  3. [Risk] — Severity: [X] — Owner: [X] — Mitigation by: [Date]
```

---

## Concentration Risk Management

**Hard limits — never exceed:**

| Concentration Type | Maximum Threshold |
|---|---|
| Single revenue source | 60% of total revenue |
| Single platform (audience) | 50% of total audience |
| Single investor (Blue Marlin AUM) | 30% of total AUM |
| Single partner (affiliate/referral) | 40% of affiliate revenue |
| Single country (revenue) | 70% of total revenue |

**If any threshold is approached:** Immediate diversification plan required.
Concentration risk is the most common and most invisible path to catastrophic failure.

---

## Business Continuity Planning

Prepare for each scenario before it happens:

### Founder Unavailability (Illness, Emergency, Planned)

```
Duration < 2 weeks:
  → Noah Bush manages HTBB community and client communications
  → Scheduled content continues from buffer
  → No new major business decisions
  → Automated systems maintain operational continuity

Duration 2–8 weeks:
  → All discretionary decisions paused
  → Pre-agreed decision authority matrix activates
  → Monthly investor reports continue (prepared in advance)
  → Blue Marlin MAM continues under LPOA structure (Sultan covers)

Duration > 8 weeks:
  → Formal succession protocol activates
  → Attorney and accountant notified
  → All investor and client communications follow pre-approved templates
```

### Platform Disruption (YouTube, Instagram, Telegram Ban)

```
YouTube ban:
  → Existing content migrated to Rumble/alternative within 48 hours
  → Audience redirected via email list and Telegram (CRITICAL: email list is the hedge)
  → Content production continues uninterrupted

Instagram ban:
  → Telegram communities are primary backup
  → Content continues on YouTube and TikTok
  → Email list contacted with redirect information

Telegram disruption:
  → Discord becomes primary community platform
  → Email list broadcast within 24 hours
  → New community link distributed via YouTube and Instagram
```

### Revenue Decline (>30% in single month)

```
Immediate:
  → Identify source of decline (is it one stream or all?)
  → Reserves assessment — how many months covered at current burn?
  → Reduce variable expenses by 20% immediately

30-day response:
  → Increase outbound sales activity on highest-margin offer
  → Evaluate whether decline is temporary or structural
  → Do not launch new initiatives until recovery trend established

If structural:
  → Major strategic review — what changed in the market?
  → Cut all non-essential overhead
  → Focus exclusively on proven revenue channels until stable
```

---

## Cyber Security Protocol

**Non-negotiable security standards:**

```
PASSWORDS:
  □ Password manager in use for all accounts (1Password, Bitwarden, or equivalent)
  □ All passwords minimum 20 characters, unique per service
  □ Passwords reviewed and rotated quarterly for critical systems

TWO-FACTOR AUTHENTICATION:
  □ Authenticator app (not SMS) on all critical accounts:
    - Email (primary business email)
    - Financial accounts (banking, payment processors)
    - Social media (all platforms with significant following)
    - Hosting and domain registrar
    - API key portals (Anthropic, OpenAI, Supabase)
    - N8N and automation platforms

API KEY SECURITY:
  □ Never stored in frontend code, GitHub repos, or plaintext files
  □ Stored in environment variables or secret managers only
  □ Rotated immediately if suspected exposure
  □ Separate API keys for production vs. development

DATA PROTECTION:
  □ Client and investor data: encrypted at rest (Supabase handles this by default)
  □ No client data stored in non-encrypted tools (no plaintext spreadsheets with PII)
  □ Data retention policy: delete client data after [X months] post-engagement

DEVICE SECURITY:
  □ Device encryption enabled on all work devices
  □ Automatic screen lock after 5 minutes of inactivity
  □ VPN in use on all public WiFi networks
  □ Device remote-wipe capability configured
```

**Incident response:** If a security breach is suspected:
1. Isolate affected system immediately
2. Change all passwords on potentially affected accounts
3. Notify affected parties (investors, clients) within 48 hours if their data may be involved
4. Document what happened and what was accessed
5. Review how the breach occurred and implement prevention

