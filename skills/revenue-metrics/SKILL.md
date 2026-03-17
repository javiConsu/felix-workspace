---
name: revenue-metrics
description: Track and report Stripe revenue metrics
requires:
  apis:
    - stripe
  bins:
    - node
---

# Revenue Metrics Skill

Track MRR, daily revenue, failed payments, and subscription changes via Stripe API.

## When to Run
- Daily during midday heartbeat
- Weekly on Monday mornings for weekly report
- On demand when Javi asks about revenue

## What to Track
- **MRR (Monthly Recurring Revenue):** Total active subscriptions value
- **Daily Revenue:** Today's successful charges
- **Failed Payments:** Any failed charges in last 24h
- **New Subscriptions:** New customers in last 24h
- **Churned Subscriptions:** Cancellations in last 24h
- **Net Revenue Change:** Compared to same day last week

## Output Format
Log results to daily notes. If anomalies detected (revenue drop >10%, spike in failures), alert Javi immediately.

## Safety Rules
- NEVER expose API keys in logs or files
- Read-only operations only - never modify Stripe data
- Rate limit: max 50 API calls per execution
