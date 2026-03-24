---
name: linkedin-content
description: >
  Generate LinkedIn content strategy and posts for Javi. Creates monthly
  content plans, drafts posts from market signals, and suggests strategic
  comments on prospect posts. ALWAYS requires Javi's approval before posting.
---

# LinkedIn Content Skill

Turn market intelligence into LinkedIn content that attracts the right ICP — without Javi having to think about what to post.

## When to Run
- **Monthly plan:** First Monday of each month during the Weekly Heartbeat.
- **Signal-triggered post:** During Morning Heartbeat when a relevant market signal is detected.
- **On demand:** "genera un post sobre [topic]".

## Content Strategy Framework

### Post Types (in order of engagement for B2B sales)
1. **Contrarian take:** Challenge a common belief in the ICP's world.
2. **Case study / result:** Specific outcome with numbers (anonymized if needed).
3. **Signal-based post:** "He visto que [market trend] — esto es lo que significa para [ICP]".
4. **Framework / process:** A simple 3-step framework that solves a pain point.
5. **Behind the scenes:** What's actually happening in sales teams right now.

### Monthly Content Plan (12 posts)
Generate one plan per month. Each post includes:
- Type (from the list above)
- Hook (first line — the most important part)
- Body outline (3-5 bullet points or a short story arc)
- CTA (what should the reader do or think)
- Best day/time to post (Tue-Thu, 9:00 or 13:00 CET)

### Signal-Based Posts
When the Signal Scanner detects a relevant market trend, generate a post draft:

```
Señal detectada: [X empresas del sector industrial están contratando SDRs masivamente]

Post sugerido:
---
Hook: "Las empresas industriales están contratando SDRs como si no hubiera mañana. Hay un problema."

[Body: 3-4 short paragraphs explaining the insight]

CTA: "¿Tu equipo de ventas está preparado para escalar? Cuéntame en comentarios."
---
```

### Strategic Comments on Prospect Posts
During the Midday Heartbeat, scan for recent posts from Decision Makers in the TAM:
1. Query Apify LinkedIn Posts Scraper for the top 10 prospects.
2. For each relevant post, draft a comment that adds value without selling.
3. Present to Javi for approval before posting.

**Comment formula:** Agree with the core point + add a specific insight or data point + end with a question.

## Approval Flow
- **NEVER post without explicit approval from Javi.**
- Present all drafts with a [Publicar] / [Editar] / [Descartar] choice.
- Save approved posts to `memory/content/[YYYY-MM-DD]-[slug].md`.

## Output Format for Monthly Plan

```markdown
# Plan de Contenido LinkedIn — [Month Year]

## Semana 1
**Post 1 (Martes [date], 9:00):** Contrarian take
- Hook: "[First line]"
- Idea: [2-3 sentence summary]

## Semana 2
**Post 2 (Miércoles [date], 13:00):** Case study
...
```
