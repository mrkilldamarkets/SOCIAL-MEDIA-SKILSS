# Workflow Design Framework

## Automation Design Protocol (7 Steps)

Never skip steps. A skipped step creates a broken workflow.

```
Step 1 — Define Outcome
  What does success look like? One sentence.
  "When X happens, Y occurs automatically, and Z is notified."

Step 2 — Map Current Workflow
  Document exactly what happens manually today.
  Who does what. In what order. How long it takes. Where it breaks.

Step 3 — Identify Bottlenecks
  Where does the process slow down?
  Where do errors occur?
  What requires human judgment (and must stay manual)?
  What is purely mechanical (and must be automated)?

Step 4 — Design the System
  Map the automated flow before touching any tool.
  Use the standard structure below.
  Confirm integrations exist before committing to a platform.

Step 5 — Build the Automation
  Build in the preferred platform for the complexity level.
  Test with real data in staging before going live.
  Document every node's purpose as you build.

Step 6 — Monitor Performance
  Set up error notifications on Day 1.
  Log every run outcome (success / failure / partial).
  Review the first 10 runs manually before trusting fully.

Step 7 — Optimize
  After 30 days of live operation: audit for failures, bottlenecks, and redundancies.
  Upgrade manual decision nodes to AI nodes where viable.
  Move the workflow up the automation hierarchy where possible.
```

---

## Standard Workflow Structure

```
[TRIGGER]
  ↓
[FILTER / VALIDATION]
  — Does this trigger meet the criteria to proceed?
  — If no: log and exit. If yes: continue.
  ↓
[DATA TRANSFORMATION]
  — Clean, format, enrich the incoming data
  ↓
[PARALLEL BRANCHES — if applicable]
  ├── [CRM / Database Update]
  ├── [Email / Notification Trigger]
  ├── [Third-party Integration]
  └── [Analytics / Logging Event]
  ↓
[ERROR HANDLER]
  — Catch failures
  — Log to Supabase error table
  — Notify operator via Telegram
  — Retry logic where applicable
  ↓
[SUCCESS LOG]
  — Record run timestamp, trigger source, outcome
```

---

## N8N Architecture Standards

### Naming Convention
```
[Brand]_[Trigger]_[Action]
Examples:
  4xProphet_NewPurchase_OnboardMember
  BlueMarlin_InvestorApplication_RouteToCRM
  HTBB_WeeklySchedule_GenerateProgressReport
  LegacyByDarling_CheckinSubmission_ProcessAndAlert
  4xHeist_TradeClose_UpdateJournalAndStats
```

### Node Documentation Rule
Every node must have a descriptive name — not N8N's default.
Bad:  "HTTP Request 3"
Good: "POST to Supabase — Create User Record"

### Credential Management
- All API keys stored as N8N credentials — never hardcoded in nodes
- Rotate credentials quarterly
- Separate credential sets for staging vs. production workflows
- Document which credentials each workflow uses

### Error Notification Template (Telegram)
```
⚠️ WORKFLOW FAILURE
Workflow:   [Name]
Time:       [Timestamp]
Node:       [Failed node name]
Error:      [Error message]
Data:       [Trigger payload summary]
Action:     Check N8N → [workflow link]
```

---

## Workflow Documentation Template

Every live workflow must have a documentation entry:

```
WORKFLOW NAME:        [Following naming convention]
BRAND:                [Which entity]
STATUS:               Active / Paused / Deprecated
TRIGGER:              [Webhook / Schedule / Database event / Manual]
FREQUENCY:            [Real-time / Hourly / Daily / Weekly]
PURPOSE:              [One sentence — what problem this solves]
STEPS:                [Numbered sequence with tool at each step]
INTEGRATIONS:         [All platforms touched]
AI NODES:             [Yes / No — describe if yes]
ERROR HANDLING:       [Where failures go]
NOTIFICATIONS:        [Who gets alerted and how]
DEPENDENCIES:         [Other workflows or systems this relies on]
OWNER:                [JorDache / or delegated role]
LAST TESTED:          [Date]
LAST UPDATED:         [Date]
KNOWN ISSUES:         [Any open problems]
```

---

## Reporting System Standard

Every workflow at Level 5+ must generate operational data:

**Minimum logging per run:**
- Run ID
- Trigger source
- Timestamp (start + end)
- Outcome (success / failure / partial)
- Records processed
- Error message (if applicable)

**Weekly automation report** (auto-generated, sent to JorDache every Monday):
- Total runs across all workflows
- Success rate by workflow
- Hours saved (estimated based on manual process time)
- Top failures with resolution status
- Any workflows needing attention

---

## Platform Selection Guide

| Scenario | Use |
|---|---|
| Complex multi-step with custom logic or AI | N8N |
| SaaS-to-SaaS with visual builder needed | Make |
| Quick connection, popular tools, no custom logic | Zapier |
| Database-triggered automation | Supabase Edge Functions + N8N webhook |
| AI decision node inside a workflow | N8N AI nodes + Claude API |
| Scheduled report generation | N8N cron trigger |

**Rule:** One platform per workflow. Never split a single workflow across tools.

