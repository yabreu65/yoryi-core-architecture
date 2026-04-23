---
id: AI-RT-COST-001
status: active
owner: ai-platform
last_reviewed: 2026-04-23
tags: [ai, runtime, quotas, cost]
source_refs: [operational-original]
---

# Quotas and Cost Governance

## Contexto

Sin limites de consumo, un tenant o feature puede romper margen y estabilidad de la plataforma.

## Regla

- Definir cuotas por tenant, plan y tipo de workload AI.
- Aplicar budget guardrails por request, dia y mes.
- Rechazar o degradar graciosamente cuando se supera cuota.

## Cuando aplica / no aplica

- Aplica a cualquier producto con costos variables por tokens, retrieval o tools externos.
- No aplica a entornos de prueba aislados.

## Trade-offs

- Limites estrictos pueden afectar experiencia premium si no se disena bien el plan.
- Evitan eventos de costo descontrolado y protegen sostenibilidad financiera.

## Checklist de verificacion

- [ ] Cuotas definidas por plan y tenant tier.
- [ ] Presupuesto y alertas de costo por producto.
- [ ] Politica de throttling/degradacion documentada.
- [ ] Reporte de consumo visible para operaciones y producto.

## Referencias

- `domains/saas/tenancy-models.md`
- `domains/platform/golden-paths.md`
