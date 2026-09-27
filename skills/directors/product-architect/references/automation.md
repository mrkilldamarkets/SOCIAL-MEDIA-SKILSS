# Automation Architecture & AI Integration

## Automation Philosophy

Default question before any manual process: **Can this be automated?**

If it happens more than once and follows a pattern — it should be automated.
Manual work is a liability. Automation is an asset.

---

## What Gets Automated (Priority Order)

| Category | Examples |
|---|---|
| Reporting | Weekly P&L reports, MAM performance summaries, community growth stats |
| Lead Routing | Form submission → CRM → email sequence → Telegram notification |
| Onboarding | Purchase → account creation → welcome sequence → resource delivery |
| Notifications | Trade alerts, community milestones, client check-in reminders |
| Data Collection | Trading journal entries, check-in form processing, analytics aggregation |
| Customer Workflows | Copy trading subscription management, course access grants |
| Scheduling | Content publishing queues, weekly review reminders, check-in triggers |
| Internal Processes | Invoice generation, performance reviews, brand metric dashboards |
| Follow Ups | Abandoned cart sequences, trial expiry alerts, re-engagement flows |

---

## Automation Stack

**Primary orchestration:** N8N (self-hosted or cloud)
- Best for: Complex multi-step workflows, custom API calls, trading system integrations
- Use when: Logic is non-trivial or requires custom code nodes

**Secondary:** Make (Integromat)
- Best for: SaaS integrations, visual workflow builders, simpler automation
- Use when: Speed of build matters and the workflow is straightforward

**Tertiary:** Zapier
- Best for: Quick connections between popular SaaS tools
- Use when: No custom logic required and tools have native Zapier support

**Rule:** Never use multiple automation tools for the same workflow. Pick one and own it.

---

## N8N Workflow Architecture

### Naming Convention
```
[Brand]_[Trigger]_[Action]
Examples:
  4xProphet_PurchaseWebhook_OnboardUser
  HTBB_WeeklyTrigger_SendProgressReport
  BlueMarlin_FormSubmission_RouteToInvestorCRM
  LegacyByDarling_CheckinForm_ProcessAndNotifyCoach
```

### Standard Workflow Structure
```
TRIGGER NODE
  ↓
VALIDATION / FILTER
  ↓
DATA TRANSFORMATION
  ↓
[PARALLEL BRANCHES if needed]
  ├── CRM Update
  ├── Email Trigger
  ├── Notification
  └── Analytics Event
  ↓
ERROR HANDLER
  ↓
SUCCESS LOG
```

### Error Handling (Non-Negotiable)
Every workflow must have:
- Error catch node
- Notification to operator on failure (Telegram or email)
- Failed record logged to Supabase for manual review
- Retry logic for transient failures (API timeouts, webhook misses)

---

## AI Integration Philosophy

AI reduces friction, increases speed, improves decision-making, and automates repetitive work.

AI does not replace: trust / leadership / strategy / relationships.

### Where AI Gets Integrated

**Research desk:** Automated market summary generation, news aggregation, sentiment analysis
**Content pipeline:** Hook generation, caption drafts, script outlines from raw ideas
**Client systems:** Automated check-in analysis, progress summaries, coaching note generation
**Internal operations:** Weekly performance report generation, meeting summaries, SOP drafts
**Lead qualification:** Application pre-screening, inquiry routing, FAQ automation

### AI Integration Stack

| Tool | Use Case |
|---|---|
| Claude (Anthropic API) | Research reports, content drafts, analysis, document generation |
| OpenAI API | Fallback / specific use cases requiring GPT behavior |
| MCP Systems | Tool-calling, workflow orchestration with AI decision nodes |
| N8N AI nodes | Inline AI processing within automation flows |

### Claude API Integration Pattern (Standard)

```javascript
const response = await fetch("https://api.anthropic.com/v1/messages", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({
    model: "claude-sonnet-4-20250514",
    max_tokens: 1000,
    system: "[Role and task context here]",
    messages: [{ role: "user", content: "[Dynamic prompt with data]" }]
  })
});
```

**When building AI-powered products:**
- Always define system prompt at the architecture stage — not during build
- User-facing AI responses must be reviewed before going live
- Never expose API keys in frontend code — route through Supabase edge functions or server actions
- Rate limit AI calls — log usage per user per day
- Cache deterministic outputs (e.g., daily market summaries) — do not regenerate unnecessarily

---

## Supabase Automation Triggers

Use Supabase database webhooks and edge functions for:

- New user signup → trigger onboarding N8N flow
- Payment confirmed → grant product access + trigger welcome sequence
- Check-in form submitted → notify coach + log to dashboard
- Trade journal entry created → update performance metrics
- New investor application → route to Blue Marlin CRM + notify JorDache

**Edge function naming:**
```
on-new-user
on-purchase-confirmed
on-checkin-submitted
on-application-received
```

---

## Automation Documentation Standard

Every workflow must be documented:

```
Workflow Name:      [Following naming convention]
Brand:              [Which entity]
Trigger:            [What starts it — webhook / schedule / database event]
Steps:              [Numbered sequence]
Integrations:       [All tools touched]
Error Handling:     [What happens on failure]
Frequency:          [Real-time / hourly / daily / weekly]
Owner:              [Who maintains this]
Last Updated:       [Date]
```

