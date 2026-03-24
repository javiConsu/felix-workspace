---
name: signal-scanner
description: >
  Detect buying intent signals from the TAM (Total Addressable Market).
  Scans for funding rounds, job postings, leadership changes, news, and
  active advertising. Use during the Morning Heartbeat or on demand.
---

# Signal Scanner Skill

Detect when companies in the TAM are ready to buy — before the competition does.

## When to Run
- Daily during the Morning Heartbeat (8:00 CET).
- On demand when Javi asks to scan a specific company or sector.

## Signal Sources (in order of cost)

| Source | Signal Type | Cost | Tool |
| :--- | :--- | :--- | :--- |
| NewsData.io | Funding, expansion, leadership news | Free (200 req/day) | REST API |
| Apollo API | Headcount growth, tech stack change, funding | Included in Apollo plan | MCP |
| Apify: Google News | Press mentions | Very low (~$0.001/company) | Apify |
| Apify: LinkedIn Job Search | Active hiring (intent signal) | ~$0.05/company | Apify |
| Meta Ad Library | Active advertising (expansion signal) | Free | Apify |

## Execution Protocol

### Phase 1 — Free Signals (always run)
1. Pull the list of TAM companies from `ICP-*.md` or HubSpot.
2. For each company, query NewsData.io for news in the last 7 days.
3. Query Apollo for headcount changes and funding events.
4. Score each signal using the scoring matrix below.

### Phase 2 — Paid Signals (run if Apify token available)
1. For companies with a score >= 5 from Phase 1, run Apify LinkedIn Job Search.
2. Check Meta Ad Library for active ads.
3. Update scores.

### Signal Scoring Matrix

| Signal | Score |
| :--- | :--- |
| Funding round announced | +5 |
| Headcount growth >10% in 3 months | +4 |
| Hiring for commercial/sales roles | +4 |
| Active advertising (new campaigns) | +3 |
| Leadership change (new CEO/CRO/VP Sales) | +3 |
| Expansion news (new office, new market) | +3 |
| Tech stack change (new CRM, new sales tool) | +2 |
| Company news mention | +1 |

### Phase 3 — Outreach Generation
For companies with a final score >= 6:
1. Check HubSpot — if already in pipeline, skip.
2. Find the Decision Maker via Apollo (`apollo_search_people`).
3. Generate a personalized outreach message that references the specific signal detected.
4. Add to the Daily Proposal for Javi's review and approval before launching.

## Output Format
Log results to `memory/YYYY-MM-DD.md`. Format:

```
## Signal Scanner Results — [DATE]
### High Priority (score >= 6)
- **[Company Name]** (Score: 8) — Señal: Ronda de financiación de 2M€ + 3 ofertas de SDR activas.
  → Contacto sugerido: [Name, Title]
  → Outreach generado: [draft saved to /drafts/outreach-[company].md]

### Medium Priority (score 3-5)
- [Company Name] (Score: 4) — Señal: Crecimiento de headcount del 15%.
```
