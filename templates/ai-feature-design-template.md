# AI Feature Design Template

## Metadata

- Feature ID:
- Product:
- Owner:
- Fecha:
- Estado: draft | approved | released

## Problema y objetivo

- Problema de negocio:
- Outcome esperado:
- KPI de exito:

## Alcance funcional

- In scope:
- Out of scope:
- Segmento de tenants:

## Arquitectura AI

- Tipo: prompt-only | RAG | agentic
- Modelo(s):
- Tools integradas:
- Topologia de orquestacion:

## Seguridad y gobernanza

- Tenant isolation strategy:
- Autorizacion pre-retrieval:
- Guardrails de entrada/salida:
- Riesgo de leakage y mitigacion:

## Datos y evaluacion

- Fuentes de datos:
- Politica de retencion:
- Baseline de evals: `templates/ai-evals-baseline-template.md`
- Umbrales de gate:

## Operaciones

- Observabilidad (logs/traces/metrics):
- Cost governance y quotas:
- Plan de incident response:

## Rollout

- Estrategia: canary | gradual | full
- Kill switch:
- Rollback plan:

## Decision record

- ADR requerida: si | no
- ADR ID:
- Fecha de re-evaluacion:
