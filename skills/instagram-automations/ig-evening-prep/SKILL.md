---
name: ig-evening-prep
description: Draft tomorrow's collab + niche comments for approval and write the daily report.
---

Evening prep & daily report for @jordachedarling's Instagram.

1. Read ~/.claude/scheduled-tasks/instagram-data/PLAYBOOK.md and follow it (voice, limits, pacing, stop conditions). This task only READS Instagram (no likes/comments/follows) — keep page loads under ~80 and skip browsing entirely if now < cooldown_until (then only write the report from the files).
2. Daily report → write daily-report-YYYY-MM-DD.md: today's counters from state.json, comments posted (from engagement-log.md), follows/unfollows, any cooldowns, and which collab targets have now been engaged (x/75).
3. Draft tomorrow's comments into approval-queue.md with status `pending`:
   a. Collab: the next 10 un-engaged accounts from danang-collab-candidates.md (skip anyone already in engagement-log.md or collab-day1-queue.md). For each, open their profile, pick their 2 most recent real posts (skip ads, giveaways, bare tags, sensitive/political/tragedy posts), read the caption (translate Vietnamese/Russian), and draft 1 specific comment per post in JorDache's voice. List 3 extra post codes to like. type=collab.
   b. Niche: find 10 fresh (≤7 days) posts from trading / fitness / transformation creators (not already commented on) via hashtags or the home feed and draft 1 comment each. type=niche, follow=yes/no.
4. Finish with a message to JorDache: the daily report summary + the full list of pending drafts (account, one-line post summary, comment) and ask him to reply "approve" or give edits. When he approves in chat, rows get switched to `approved` for tomorrow's rounds.