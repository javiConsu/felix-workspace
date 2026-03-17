---
name: site-health
description: Monitor website uptime and health
requires:
  bins:
    - curl
---

# Site Health Skill

Check that all production websites and APIs are responding correctly.

## Sites to Monitor
(Add URLs as projects are set up)
- TBD - Add production URLs here

## Checks
- HTTP status code (expect 200)
- Response time (alert if >3 seconds)
- SSL certificate validity (alert if expiring within 14 days)
- Key page elements loading correctly

## When to Run
- Morning heartbeat (daily)
- After any deployment
- On demand

## Alert Conditions
- Any site returning non-200 status
- Response time >3 seconds
- SSL expiring within 14 days
- Site content missing expected elements

## Response Protocol
1. Log issue to daily notes
2. Retry after 2 minutes to confirm it's not transient
3. If still down, alert Javi immediately via Telegram
4. If Vercel/Railway site, check deployment logs
5. Document resolution in daily notes
