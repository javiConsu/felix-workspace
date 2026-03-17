# HEARTBEAT.md - Scheduled Checks

Things to check periodically (rotate through these, 2-4 times per day).
Track check state in `memory/heartbeat-state.json`.

## Morning Check (9:00 CET)
- [ ] Check email for urgent messages
- [ ] Review calendar for today's events
- [ ] Check Stripe dashboard for overnight revenue/issues
- [ ] Verify all production sites are up (run site-health skill)
- [ ] Review yesterday's daily notes for pending tasks

## Midday Check (13:00 CET)
- [ ] Check social media mentions (X, LinkedIn)
- [ ] Review any open GitHub issues/PRs
- [ ] Check deployment status on Vercel/Railway
- [ ] Run revenue-metrics skill for daily snapshot

## Afternoon Check (17:00 CET)
- [ ] Check email again
- [ ] Review progress on active tasks
- [ ] Update daily notes with day's activity
- [ ] Prepare summary for Javi if anything notable happened

## Weekly (Monday Morning)
- [ ] Weekly revenue report (Stripe metrics)
- [ ] Review and clean up MEMORY.md
- [ ] Check for dependency updates on active projects
- [ ] Review and archive old daily notes (>30 days)

## Rules
- Don't check the same thing twice within 30 minutes
- Skip checks if Javi is actively chatting (focus on conversation)
- If something is down or broken, alert immediately - don't wait for next scheduled check
- Log all checks to `memory/heartbeat-state.json`
