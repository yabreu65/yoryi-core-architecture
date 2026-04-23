---
id: AI-RT-OBS-001
status: active
owner: ai-platform
last_reviewed: 2026-04-23
tags: [ai, runtime, observability]
source_refs: [arquitecto-moderno/parte-vii-operacion-enterprise-y-ai-runtime/capitulo-24-evaluacion-continua-y-operacion-de-ia]
---

# AI Ops Observability

## Contexto

Sin observabilidad AI-centric no podes explicar costo, calidad ni fallas de agentes en produccion.

## Regla

- Trazar cada ejecucion con `tenant_id`, `trace_id`, modelo, tokens, latencia y tool calls.
- Separar metricas de calidad (evals) de metricas de performance.
- Alertar por degradacion de precision, no solo por errores tecnicos.

## Cuando aplica / no aplica

- Aplica a todo flujo LLM, RAG y agentes.
- No aplica a prototipos locales sin trafico real.

## Trade-offs

- Mayor volumen de telemetria y costo de almacenamiento.
- Facilita auditoria, tuning y deteccion temprana de regresiones.

## Checklist de verificacion

- [ ] Structured logs incluyen metadata AI minima.
- [ ] Dashboards separan costo, latencia y calidad.
- [ ] Existe trazabilidad de prompt, retrieval y output.
- [ ] Evals periodicas con umbrales de gate definidos.

## Referencias

- `checks/architecture/service-readiness-scorecard.md`
- `checks/delivery/release-gates.md`
