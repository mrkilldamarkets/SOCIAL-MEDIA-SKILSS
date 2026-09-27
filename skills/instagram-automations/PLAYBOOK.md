# @jordachedarling Instagram Operating Playbook

Every scheduled Instagram task reads this file first and follows it exactly.
Data folder: ~/.claude/scheduled-tasks/instagram-data/

## 1. Brand & voice
TRAIN • TRADE • TRANSFORM. JorDache lives in Da Nang, Vietnam and trains at Evolve Gym (@evolvegym.vn, his friend's gym; never mine its followers/tags).
Comments: confident, direct, human, specific to the post, occasionally funny. No "great post", no emoji chains, no links, no "DM me", no self-promo, no fake personal experiences, nothing negative. Vary length and wording.

## 2. Daily schedule (local time)
| Time | Task id | What it does |
|---|---|---|
| 08:30 | ig-daily-unfollow-sweep | Unfollow non-followers (respects keep-list + 3-day grace) |
| 11:00 | ig-story-rounds | Story round 1 (25 accounts) |
| 12:30 | ig-collab-outreach | Da Nang collab round A (approved rows only) |
| 14:00 | ig-story-rounds | Story round 2 |
| 15:30 | ig-niche-comments | Niche comment round (approved rows only) |
| 17:00 | ig-story-rounds | Story round 3 |
| 18:30 | ig-collab-outreach | Da Nang collab round B |
| 20:00 | ig-story-rounds | Story round 4 |
| 21:00 | ig-evening-prep | Draft tomorrow's comments for approval + daily report |
| Sun 20:00 | ig-weekly-unfollow-sheet | Weekly Google Sheet tab of unfollows |

## 3. Daily limits (hard caps, tracked in state.json → counters[today])
| Action | Cap/day | Per round |
|---|---|---|
| Comments (all types) | 40 | 10 |
| Post likes | 150 | 40 |
| Follows | 25 | 10 |
| Unfollows | 40 | 40 |
| Story accounts viewed/liked | 100 | 25 |
| Profile/post page loads | ~400 | ~80 |
Before each action check the counter; stop the round when a cap is reached. Increment counters as you go (write state.json after every few actions).

## 4. Pacing
- Wait 4–8 seconds between actions (vary it). Wait 20–40 s between accounts in comment/collab rounds.
- Never run scripted API calls (/api/v1/..., topsearch, web_profile_info, friendships). Browse pages normally.
- Only one Instagram task runs at a time; if another is mid-run (state.json "running" set within last 30 min), exit.

## 5. Stop conditions → cooldown
If you see ANY of: HTTP 429 page, "Try again later", "We restrict certain activity", action-blocked dialog, login checkpoint →
stop immediately, set state.json "cooldown_until" = now + 24h and "cooldown_reason", and report. Every task checks cooldown_until first and exits if now < cooldown_until.
Never enter passwords or solve checkpoints — report to JorDache.

## 6. Approval rule
Comments are only posted if they appear in approval-queue.md with status `approved` (JorDache approves drafts in chat). Likes, story likes, follows and unfollows need no approval.

## 7. Browser method (Claude in Chrome) — what works
- Load tools via ToolSearch in one call: tabs_context_mcp, tabs_create_mcp, navigate, computer, find, javascript_tool, browser_batch, get_page_text.
- Like a post (on /p/CODE/): `svg[aria-label="Like"]` with height 24 → click its closest `div[role=button],button`. If aria-label is "Unlike" it's already liked.
- Follow on a post page: first `main div[role=button]/button` whose text is exactly "Follow".
- Comment: `ta=document.querySelector('textarea'); ta.focus(); ta.select(); document.execCommand('insertText', false, TEXT)`; wait 1 s; re-query and click the `div[role=button]` whose text is "Post"; wait 3 s; verify textarea is empty. Keyboard typing and Enter do NOT work reliably.
- Stories: open https://www.instagram.com/stories/USERNAME/ ; if a "View story" button exists click it, then click the heart (Like) in the story footer; for multiple frames press ArrowRight and like each; if URL redirects to the profile there is no active story → skip.
- Verify comments afterwards at https://www.instagram.com/your_activity/interactions/comments/ .

## 8. Files
- state.json — cooldown + counters + running flag
- approval-queue.md — comment drafts (pending/approved/posted/skipped)
- danang-collab-candidates.md — 75 collab targets
- collab-day1-queue.md — approved-but-unposted day-1 collab comments (treat as approved)
- story-targets.txt — accounts for story rounds (rotate; don't repeat an account within 2 days)
- engagement-log.md — log of every comment/follow; append to it
- keep-list.txt, unfollow-log.csv — unfollow sweep
- daily-report-YYYY-MM-DD.md — written by evening prep
