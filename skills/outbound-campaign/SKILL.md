---
name: outbound-campaign
description: >
  Orchestrate a full multi-channel outbound campaign from lead list to
  active sequences. Handles Apollo prospecting, channel selection (email
  via Instantly or LinkedIn via Walead), and sequence generation.
  ALWAYS requires Javi's approval before launching.
---

# Outbound Campaign Skill

Build and launch a complete outbound campaign. The agent does all the research and setup — Javi approves before anything is sent.

## When to Run
- On demand: "lanza una campaña para [ICP] en [sector/país]".
- Triggered by Signal Scanner when high-priority signals are detected.

## Execution Protocol

### Phase 1 — Lead Discovery (Apollo)
1. Read the target ICP from `ICP-*.md` or from Javi's request.
2. Query `apollo_search_companies` with the ICP parameters (sector, size, country, tech stack).
3. For each company, query `apollo_search_people` to find the Decision Maker.
4. Enrich the top 20-30 leads with `apollo_bulk_enrich_people`.
5. Cross-check HubSpot — remove any leads already in the pipeline.

### Phase 2 — Channel Selection (per lead)
For each lead, select the optimal outreach channel:

| Condition | Channel |
| :--- | :--- |
| Active on LinkedIn (posts in last 30 days, 500+ connections) | LinkedIn via Walead |
| Verified email available, low LinkedIn activity | Email via Instantly |
| Both available | LinkedIn first, email as fallback |

### Phase 3 — Sequence Generation
For each lead, generate a personalized sequence using the signal detected and the ICP context from `ICP-*.md`:

**Email sequence (3 steps):**
- Email 1 (Day 1): Personalized hook referencing the specific signal.
- Email 2 (Day 4): Value-add (case study, insight, or relevant data).
- Email 3 (Day 9): Soft breakup with a direct question.

**LinkedIn sequence (2 steps):**
- Connection request with a personalized note (max 300 chars).
- Follow-up message after connection (Day 2).

### Phase 4 — Approval Gate (MANDATORY)
Before launching, present the full campaign plan to Javi:

```
## Campaña lista para lanzar: [Campaign Name]

Leads: [X] contactos en [Y] empresas
Canal: [Z email / W LinkedIn]
Señal de activación: [Signal that triggered this]

Muestra de los primeros 3 leads:
1. [Name, Title, Company] — Email 1: "[First line of email]"
2. [Name, Title, Company] — LinkedIn: "[Connection note]"
3. ...

¿Lanzamos? [SÍ / Editar / Cancelar]
```

### Phase 5 — Launch & Monitor
After Javi approves:
1. Create campaign in Instantly (email leads) via REST API.
2. Add LinkedIn leads to Walead campaign via MCP.
3. Log campaign details to `memory/campaigns/[YYYY-MM-DD]-[name].md`.
4. Monitor replies during Midday Heartbeat.

## Reply Handling
When a reply is received (via webhook from Instantly or Walead):
1. Classify the reply: Positive / Needs Info / Not Interested / Out of Office / Wrong Person.
2. For Positive and Needs Info: draft a response and present to Javi for approval.
3. For Not Interested: mark as lost in HubSpot, add to 90-day nurture sequence.
4. For Out of Office: reschedule follow-up for when they return.
5. Log all replies and classifications to `memory/campaigns/[campaign-name]-replies.md`.
