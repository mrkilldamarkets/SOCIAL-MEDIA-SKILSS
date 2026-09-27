---
name: ig-weekly-unfollow-sheet
description: Every Sunday: add a Google Sheet tab listing everyone unfollowed that week.
---

Weekly Instagram unfollow report for @jordachedarling.

1. Read ~/.claude/scheduled-tasks/instagram-data/unfollow-log.csv (columns: date,account,reason). Select rows from the last 7 days (Monday through today).
2. Load the `anthropic-skills:google-workspace` skill before touching Google files, then use the Google Drive connector.
3. Find the Google Sheet named "Instagram Unfollow Log" in the user's Drive. If it doesn't exist, create it. Store its file ID in ~/.claude/scheduled-tasks/instagram-data/sheet-id.txt for future runs (read that file first if it exists).
4. Add a NEW tab named "Week of YYYY-MM-DD" (the Monday of this week) with columns: Date | Account | Profile link (https://www.instagram.com/<handle>/) | Reason. One row per unfollow. Add a total count at the bottom. If there were zero unfollows, still create the tab with a single row saying "No unfollows this week".
5. Do not share the sheet with anyone. Report the sheet link and the count.