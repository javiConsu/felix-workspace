---
name: pipeline-review
description: >
  Analyze the HubSpot pipeline to detect stalled deals, churn risks,
  and expansion opportunities. Generates a prioritized action plan.
  Run every Monday during the Weekly Heartbeat.
---

# Pipeline Review Skill

Analyze the full pipeline and surface what needs attention — before Javi has to ask.

## When to Run
- Every Monday during the Weekly Heartbeat.
- On demand: "revisa el pipeline" or "¿cómo está el pipeline?".

## Execution Protocol

### Phase 1 — Data Pull (HubSpot)
1. Pull all open deals from HubSpot via MCP.
2. Pull all contacts with activity in the last 30 days.
3. Pull all leads created in the last 7 days.

### Phase 2 — Deal Health Analysis

For each open deal, calculate a health score:

| Condition | Score Impact |
| :--- | :--- |
| Last activity < 7 days ago | +3 |
| Last activity 7-14 days ago | 0 |
| Last activity 14-30 days ago | -2 |
| No activity in 30+ days | -5 (STALLED) |
| Next step defined | +2 |
| No next step defined | -2 |
| Close date in the past | -3 (OVERDUE) |
| Multiple contacts engaged | +2 |
| Only one contact engaged | -1 |

### Phase 3 — Churn Risk Detection
For existing customers (closed-won deals):
1. Check email activity in Gmail — no reply in 14+ days = risk.
2. Check HubSpot for support tickets or negative feedback.
3. Flag any account with a health score below 3.

### Phase 4 — Expansion Signals
For existing customers:
1. Cross-reference with Signal Scanner data — is the account growing?
2. Check if they have other ICPs that could benefit from the product.
3. Flag expansion opportunities with a suggested upsell message.

### Phase 5 — Action Plan Generation
Generate a prioritized action list:

```markdown
# Pipeline Review — [Date]

## 🚨 Acción inmediata (deals en riesgo)
1. **[Deal Name]** — Sin actividad en 21 días. Último contacto: [name].
   → Acción: Email de reactivación generado → [link to draft]

## ⚠️ Atención esta semana
2. **[Deal Name]** — Fecha de cierre vencida hace 5 días.
   → Acción: Actualizar fecha o mover a perdido.

## 💚 En buen estado
- [Deal 1], [Deal 2], [Deal 3] — Sin acción requerida.

## 🌱 Oportunidades de expansión
- **[Customer Name]** — Han contratado 5 personas nuevas en ventas.
  → Acción: Proponer upsell al plan Pro. Mensaje generado → [link to draft]

## 📊 Resumen
- Deals activos: [X] | Valor total: [€Y]
- Deals en riesgo: [Z] | Valor en riesgo: [€W]
- Nuevos leads esta semana: [N]
```
