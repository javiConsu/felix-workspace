---
name: competitor-intel
description: >
  Monitor and analyze competitors. Tracks their messaging, pricing,
  advertising, and customer reviews. Updates COMPETITORS.md and generates
  battlecards. Run weekly during the Weekly Heartbeat.
---

# Competitor Intel Skill

Know what competitors are doing before clients ask about them.

## When to Run
- Every Monday during the Weekly Heartbeat (Ad Intelligence Monitor).
- On demand: "analiza a [competitor]" or "actualiza las battlecards".
- Triggered when a prospect mentions a competitor during a sales call.

## Execution Protocol

### Phase 1 — Advertising Intelligence (Free, no auth required)
For each competitor in `COMPETITORS.md`:
1. Query Apify Meta Ad Library Scraper for active Facebook/Instagram ads.
2. Query Apify LinkedIn Ads Scraper for active LinkedIn ads.
3. Note: ads running for 14+ days are likely converting — these are the messages that work.

Analyze:
- What pain points are they addressing?
- What proof points are they using (numbers, logos, testimonials)?
- What audiences are they targeting (inferred from ad copy)?
- What angles are they NOT covering? (This is the opportunity.)

### Phase 2 — Review Mining (G2 / Capterra)
1. Query Apify G2 Reviews Scraper for the latest 20 reviews.
2. Categorize reviews: What do customers LOVE? What do they HATE?
3. The "hates" are the battlecard ammunition.

### Phase 3 — Website & Messaging Analysis
1. Scrape the competitor's website (homepage, pricing, features).
2. Detect any messaging changes since the last scan.
3. Note new features, pricing changes, or new ICP targeting.

### Phase 4 — Battlecard Update
Update `COMPETITORS.md` and generate/refresh individual battlecard files in `memory/battlecards/[competitor].md`:

```markdown
# Battlecard: [Competitor Name] — Updated [Date]

## En una frase
[What they do and who they target]

## Sus puntos fuertes (lo que dicen los clientes que aman)
- [Point 1]
- [Point 2]

## Sus puntos débiles (lo que dicen los clientes que odian)
- [Weakness 1] → Nuestra ventaja: [How we win here]
- [Weakness 2] → Nuestra ventaja: [How we win here]

## Sus mensajes actuales (ads activos)
- "[Ad headline 1]" — Lleva activo X días
- "[Ad headline 2]" — Ángulo: [pain point addressed]

## Ángulos que NO están cubriendo (nuestra oportunidad)
- [Gap 1]
- [Gap 2]

## Cómo ganarles en una conversación de ventas
1. [Tactic 1]
2. [Tactic 2]
3. [Tactic 3]
```
