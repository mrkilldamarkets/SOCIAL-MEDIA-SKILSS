---
name: ig-daily-unfollow-sweep
description: Daily: unfollow Instagram accounts that don't follow @jordachedarling back (respecting keep-list and 3-day grace).
---

Daily Instagram unfollow sweep for @jordachedarling.

1. Read ~/.claude/scheduled-tasks/instagram-data/PLAYBOOK.md and follow it (pacing, stop conditions, browser method).
2. Read state.json. If now < cooldown_until or another task is running (<30 min), report one line and exit. Else set running = {"task":"ig-daily-unfollow-sweep","at":<now>}.
3. The user has given FULL permission to unfollow anyone who does not follow @jordachedarling back (he watches creators from a burner account). Do not ask for approval.
4. Collect the lists @jordachedarling FOLLOWS and his FOLLOWERS by opening the Following/Followers dialogs on https://www.instagram.com/jordachedarling/ and scrolling slowly (3–5 s between scrolls). If the dialog stops loading, work with what loaded and note it.
5. Non-followers = following − followers. Exclude: handles in keep-list.txt (includes the 75 Da Nang collab targets), and accounts in engagement-log.md's Follow tracker followed less than 3 full days ago.
6. Unfollow up to 40 (daily cap; check state.json counters[today].unfollows), 5–10 s between each. On any stop condition (429, "Try again later", restriction, checkpoint): stop, set cooldown_until = now+24h with reason.
7. Append each to unfollow-log.csv as `YYYY-MM-DD,handle,no follow-back`; update the Follow tracker rows in engagement-log.md; update counters.
8. Clear running. Report: following/followers before and after, unfollowed list, how many non-followers remain.