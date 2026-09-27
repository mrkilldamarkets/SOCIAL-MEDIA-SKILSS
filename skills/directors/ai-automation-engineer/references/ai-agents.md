# AI Agent Architecture

## Agent Philosophy

Agents function like departments. Not tools. Not chatbots.

A properly built agent has: a defined role / a scope boundary / access to the right data /
the ability to take action / a reporting mechanism / an escalation path.

The goal is a bench of agents that collectively run operations — freeing human attention for
strategy, relationships, and high-judgment decisions.

---

## Agent Department Map

| Agent | Function | Priority |
|---|---|---|
| COO Agent | Strategic planning, weekly priorities, decision support | High |
| Content Agent | Hook generation, caption drafts, content calendar management | High |
| Research Agent | Market analysis, XAUUSD intelligence, daily briefings | High |
| Sales Agent | Lead qualification, follow-up sequences, pipeline updates | High |
| Support Agent | Client FAQs, community moderation, ticket routing | Medium |
| Investor Relations Agent | Investor communications, application processing, reporting | Medium |
| Operations Agent | SOP generation, process documentation, task coordination | Medium |
| Automation Agent | Workflow audit, error detection, optimization recommendations | Medium |

---

## Agent Architecture Standard

Every agent is defined by six components:

```
AGENT NAME:         [Department-style name]
ROLE:               [One sentence — what this agent does]
SCOPE:              [What it handles / what it escalates]
DATA ACCESS:        [What context/data it needs to function]
ACTIONS:            [What it can do autonomously]
ESCALATION:         [What requires human approval before acting]
OUTPUT FORMAT:      [How it delivers results — message / report / draft / decision]
```

---

## Claude API Agent Pattern

### Single-Turn Agent (Research / Content / Analysis)

```javascript
const response = await fetch("https://api.anthropic.com/v1/messages", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({
    model: "claude-sonnet-4-20250514",
    max_tokens: 1000,
    system: `You are the [Agent Name] for 4x Heist Investments.
[Full role description and constraints.]
Always respond in the following format: [Format spec]`,
    messages: [
      { role: "user", content: `[Dynamic prompt with injected data]` }
    ]
  })
});
```

### Multi-Turn Agent (Sales / Support / Operations)

Maintain conversation history across turns:

```javascript
const messages = [
  ...conversationHistory,
  { role: "user", content: newUserMessage }
];

const response = await fetch("https://api.anthropic.com/v1/messages", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({
    model: "claude-sonnet-4-20250514",
    max_tokens: 1000,
    system: agentSystemPrompt,
    messages: messages
  })
});

// Append assistant response to history
conversationHistory.push(
  { role: "user", content: newUserMessage },
  { role: "assistant", content: response.content[0].text }
);
```

### Agent with Tool Use (Actions-Capable Agent)

For agents that need to read from or write to Supabase, send Telegram messages, or update CRM:

```javascript
body: JSON.stringify({
  model: "claude-sonnet-4-20250514",
  max_tokens: 1000,
  system: agentSystemPrompt,
  tools: [
    {
      name: "update_crm_lead",
      description: "Update a lead record in the CRM with new status or notes",
      input_schema: {
        type: "object",
        properties: {
          lead_id: { type: "string" },
          status: { type: "string", enum: ["qualified", "discovery", "proposal", "closed_won", "closed_lost"] },
          notes: { type: "string" }
        },
        required: ["lead_id", "status"]
      }
    }
  ],
  messages: messages
})
```

---

## Content Agent — Full Specification

**Role:** Generate high-quality content assets from raw inputs across all 4x Heist brands.

**Inputs accepted:**
- Raw idea (1-3 sentences)
- Topic + platform + pillar
- Existing content to repurpose
- Market insight to convert to educational content

**Outputs delivered:**
- 5 hook variations (curiosity / pain / contrarian / proof / desire angles)
- Full caption (hook → problem → insight → solution → lesson → CTA)
- Carousel 10-slide structure with copy per slide
- Reel script with timestamps
- Suggested visual direction

**System prompt core directive:**
```
You are the Content Agent for 4x Heist Investments.
You create media assets for the Sovereign Operator brand — not social media posts.
Every output positions Jor-Dache Darling as an Operator, Builder, Trader, and Founder.
Never use motivational language, guru framing, or retail trading energy.
Output format: [specified per request type]
```

---

## Research Agent — Full Specification

**Role:** Generate daily XAUUSD intelligence briefings and trade analysis.

**Trigger:** Daily at 6:00am (before London session) — N8N cron → Claude API → formatted report → delivered to Telegram

**Inputs injected into prompt:**
- Previous session close price
- Overnight high/low
- DXY and US10Y levels
- Upcoming economic events (fetched via economic calendar API)
- Previous day's bias and whether it played out

**Output:** Structured daily brief following the `daily-analysis.md` format from trading-research-analyst skill

**Escalation rule:** Research Agent drafts — JorDache approves before Blue Marlin distribution.
Internal 4x Prophet use may go direct after 30 days of quality validation.

---

## Sales Agent — Full Specification

**Role:** Qualify inbound leads, manage follow-up sequences, and update pipeline.

**Trigger:** New lead captured (form / DM trigger word / YouTube comment flag)

**Qualification logic:**
```
High intent signals:    Specific question about offer / price / application / timeline
Medium intent signals:  Engagement with content / following for 30+ days / repeat DM
Low intent signals:     Generic comment / one-time interaction / no profile context
```

**Autonomous actions:**
- Send qualification message sequence (Days 1 / 3 / 7)
- Update lead status in CRM
- Log all interactions to contact record

**Escalation to JorDache:**
- Lead requests discovery call → calendar link delivered + JorDache notified
- Lead indicates high budget or institutional inquiry → immediate notification
- Lead shows distress or complaint → immediate escalation, no automated response

---

## Agent Deployment Checklist

Before any agent goes live:

- [ ] System prompt written and tested with 20+ sample inputs
- [ ] Edge cases identified and handled (ambiguous inputs, out-of-scope requests)
- [ ] Escalation paths defined and tested
- [ ] Output format validated against brand standards
- [ ] Error logging in place
- [ ] Rate limiting configured (per-user and global)
- [ ] Human review process defined for first 30 days
- [ ] Performance metric defined (what does "working" look like?)

