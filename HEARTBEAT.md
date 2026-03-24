# HEARTBEAT.md - Scheduled Checks & GTM Operations

Things to check periodically (rotate through these, 2-4 times per day).
Track check state in `memory/heartbeat-state.json`.

## Morning Check (8:00 CET) - The "Morning Brief"
- [ ] **Calendar & Email:** Review today's meetings and urgent unread emails.
- [ ] **Pipeline Health:** Check HubSpot for deals without activity in 7+ days or new inbound leads.
- [ ] **Signal Scanner:** Run Apify/NewsData/Apollo to detect signals in the TAM (funding, job postings, news).
- [ ] **Consolidate:** Generate the "Propuesta Diaria" (Daily Proposal) for Javi with max 5 actionable items (Urgente, Hoy, Oportunidad, Pipeline).
- [ ] **System Health:** Verify all production sites and Stripe webhooks are up.

## Midday Check (13:00 CET) - The "Execution Phase"
- [ ] **Outbound Campaigns:** Check Instantly/HeyReach for campaign performance and new replies.
- [ ] **Reply Triage:** Categorize incoming replies (Positive, Negative, Info) and draft responses for Javi's approval.
- [ ] **Social Media:** Check LinkedIn/X mentions and engagement. Suggest strategic comments on prospect's posts.
- [ ] **GitHub/Dev:** Review any open GitHub issues/PRs or deployment statuses.

## Afternoon Check (17:00 CET) - The "Wrap-up"
- [ ] **Email/Inbox:** Final check of emails and LinkedIn messages.
- [ ] **Task Progress:** Review progress on active tasks and follow-ups.
- [ ] **Memory Consolidation:** Update `memory/YYYY-MM-DD.md` with the day's activity. Extract durable facts to `MEMORY.md` or `ICP-*.md`.
- [ ] **Summary:** Prepare a brief summary for Javi if anything notable happened.

## Weekly (Monday Morning) - The "Strategy Review"
- [ ] **Revenue Report:** Stripe metrics (MRR, churn, new subs).
- [ ] **Competitor Scan:** Run Ad Intelligence Monitor to check competitors' active ads.
- [ ] **Content Plan:** Draft the LinkedIn content plan for the week based on market signals.
- [ ] **Memory Cleanup:** Review and archive old daily notes (>30 days).

## Rules
- Don't check the same thing twice within 30 minutes.
- Skip checks if Javi is actively chatting (focus on conversation).
- If something is down or broken (Stripe, Vercel), alert immediately - don't wait for next scheduled check.
- Log all checks to `memory/heartbeat-state.json`.
