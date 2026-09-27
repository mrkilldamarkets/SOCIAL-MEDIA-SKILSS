---
name: ig-collab-outreach
description: Post approved comments, 5 likes and a follow for ~5 Da Nang collab targets per round.
---

Da Nang collab outreach round for @jordachedarling.

Goal: build relationships with the 75 Da Nang/Vietnam creators in danang-collab-candidates.md so JorDache can invite them to train/film at Evolve Gym or do trading content.

1. Read ~/.claude/scheduled-tasks/instagram-data/PLAYBOOK.md and follow it exactly.
2. Read state.json. If now < cooldown_until or another task is running (set <30 min ago), report one line and exit. Else set running.
3. Work queue, in order:
   a. collab-day1-queue.md → rows under "Approved, not yet posted" (already approved by JorDache). Mark each row posted as you go.
   b. then rows in approval-queue.md with type=collab and status=approved.
   Take up to 5 accounts this round (max 10 comments), staying under the daily caps in state.json counters[today] (comments 40, likes 150, follows 25).
4. For each account: open each approved post → like it → post the exact approved comment using the playbook's insertText + "Post" method → verify. Then like the listed extra posts (5 likes total per account) and follow the account if not already following. Wait 20–40 s between accounts.
5. Never post a comment that isn't approved. Never post the same comment twice (check the post's comments / your_activity first if a previous attempt is uncertain).
6. Append each comment/follow to engagement-log.md; update counters; mark rows posted.
7. On any stop condition: stop, set cooldown_until = now+24h with reason, report.
8. Clear running. Report: accounts done, comments posted (quote them), likes, follows, remaining approved queue.