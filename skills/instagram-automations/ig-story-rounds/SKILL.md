---
name: ig-story-rounds
description: View & like stories of ~25 niche creators per round, 4 rounds a day, within daily caps.
---

Instagram story round for @jordachedarling.

1. Read ~/.claude/scheduled-tasks/instagram-data/PLAYBOOK.md and follow it exactly (limits, pacing, stop conditions, browser method).
2. Read state.json in that folder. If now < cooldown_until, or "running" was set by another task within the last 30 minutes, write a one-line report and exit. Otherwise set running = {"task":"ig-story-rounds","at":<now>} and save.
3. Build today's target list from story-targets.txt (niche creators). Skip accounts whose stories were liked in the last 2 days (track in state.json → "story_seen": {handle: date}). Also check the home story tray for niche creators (trading, fitness, transformation, entrepreneurship) and include them; ignore personal friends/family accounts.
4. For up to 25 accounts (and within the daily cap of 100 story accounts in state.json counters[today].stories): open https://www.instagram.com/stories/HANDLE/ ; if there is no active story, skip; otherwise click "View story", like each frame (heart), press ArrowRight to the next frame, up to 5 frames per account. Wait 4–8 s between accounts. Record story_seen and increment counters[today].stories.
5. If any stop condition from the playbook appears (429 / "Try again later" / restriction / checkpoint), stop, set cooldown_until = now+24h with reason, and report.
6. Clear "running" in state.json. Report: accounts with active stories, frames liked, skipped, today's running total.