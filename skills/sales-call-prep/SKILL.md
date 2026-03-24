---
name: sales-call-prep
description: >
  Generate a comprehensive pre-call briefing for any sales meeting.
  Researches the company, the contact, and the competitive landscape.
  Use 30 minutes before any external meeting detected in Google Calendar.
---

# Sales Call Prep Skill

Generate a complete briefing before any sales meeting so Javi walks in knowing more than the prospect expects.

## When to Run
- Automatically during the Morning Heartbeat when a meeting with an external contact is detected in Google Calendar.
- On demand: "prepárame la reunión con [name/company]".

## Execution Protocol (3 Parallel Subagents)

### Subagent A — Company Deep Dive
1. Scrape the company's website (value proposition, products, pricing, team).
2. Query Apollo for company data (size, sector, tech stack, headcount trend).
3. Search NewsData.io for recent news (last 30 days).
4. Check Apify LinkedIn Job Search for active hiring signals.
5. Check Meta Ad Library for active campaigns.

### Subagent B — Contact Profile
1. Query Apollo to enrich the contact (role, seniority, LinkedIn URL, history).
2. Scrape their LinkedIn profile for recent posts and activity.
3. Identify their likely pain points based on their role and the company's situation.
4. Infer their decision-making style (analytical, relational, results-driven).

### Subagent C — Competitive Context
1. Read `COMPETITORS.md` to identify which competitors are relevant to this prospect.
2. Check if the prospect uses any competitor tools (via Apollo tech stack data).
3. Prepare 2-3 competitive differentiators relevant to this specific meeting.

## Output Format

The briefing is saved to `memory/briefings/[YYYY-MM-DD]-[company].md` and surfaced in the Daily Proposal.

```markdown
# Briefing: [Meeting Title] — [Date] [Time]

## La empresa en 60 segundos
[2-3 sentences: what they do, size, recent news]

## El contacto
- **Nombre:** [Name]
- **Cargo:** [Title]
- **Tiempo en el cargo:** [X months/years]
- **Estilo probable:** [Analytical / Relational / Results-driven]
- **Publicó recientemente:** "[recent LinkedIn post quote]"

## Por qué ahora (señales detectadas)
- [Signal 1: e.g., "Están contratando 3 SDRs — tienen presupuesto y mandato de crecimiento"]
- [Signal 2: e.g., "Acaban de lanzar una nueva línea de producto — necesitan pipeline rápido"]

## Posibles objeciones y cómo rebatirlas
| Objeción | Respuesta |
| :--- | :--- |
| "Ya tenemos una solución" | [Response based on COMPETITORS.md] |
| "No es el momento" | [Response based on signals detected] |

## Talk Track sugerido
**Apertura:** [Personalized opening referencing a specific signal or post]
**Pregunta de diagnóstico:** [Key question to uncover their main pain]
**Propuesta de valor:** [1-2 sentences tailored to their situation]
**Siguiente paso:** [Specific CTA]
```
