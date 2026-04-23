# S1-08 OpenCode Simulation Report

Fecha: 2026-04-23
Estado: completed
Owner: architecture

## Caso real simulado

Implementar un asistente AI de busqueda documental en JurisManager para responder preguntas sobre expedientes por tenant.

## Context docs consultados

- `catalog/knowledge-map.md`
- `constitution/architecture-principles.md`
- `constitution/decision-policy.md`
- `domains/saas/tenancy-models.md`
- `domains/backend/security/identity-tenant-context.md`
- `domains/ai/rag/multi-tenant-rag.md`
- `domains/ai/agents/tool-contracts.md`
- `domains/ai/runtime/ai-ops-observability.md`
- `checks/architecture/module-review-checklist.md`
- `checks/delivery/release-gates.md`

## Objetivo tecnico

Habilitar respuestas AI sobre documentos legales de un tenant sin fuga cross-tenant, con trazabilidad y gating de calidad para release.

## Decisiones candidatas y trade-offs

1. **Aislamiento de retrieval**
   - Opcion A: pool vectorial con metadata filters.
   - Opcion B: namespace/silo por tenant sensible + pool para no sensibles.
   - Decision recomendada: Opcion B por perfil de riesgo JurisManager.
   - Trade-off: mas costo operativo a cambio de menor riesgo de leakage.

2. **Topologia de agentes**
   - Opcion A: single-agent con tool de retrieval.
   - Opcion B: supervisor + retrieval-worker + policy-worker.
   - Decision recomendada: Opcion A para primer release controlado.
   - Trade-off: menor complejidad inicial, menor paralelismo funcional.

3. **Contratos de tools**
   - Opcion A: tool inputs flexibles sin schema fuerte.
   - Opcion B: schema versionado + errores tipados + autorizacion por tenant/rol.
   - Decision recomendada: Opcion B (obligatoria por doctrina).
   - Trade-off: mayor esfuerzo upfront, menos fallas ambiguas en runtime.

## Plan propuesto por OpenCode (simulado)

1. Resolver tenant context firmado en API layer.
2. Calcular permisos efectivos del actor (RBAC/ABAC).
3. Ejecutar retrieval con pre-filter por `tenant_id` y `doc_id` permitido.
4. Construir prompt con chunks trazables y sources auditables.
5. Aplicar guardrails de salida para datos sensibles.
6. Emitir telemetria AI runtime (tokens, latencia, retrieval hit/miss, leak score).
7. Correr evals de leakage y quality antes de release.

## Checklist aplicado

### Constitution checklist

- [x] Tenant safety respetado en diseño.
- [x] Contratos explicitos entre modulos y tools.
- [x] Camino evolutivo sin big-bang rewrite.
- [x] Controles operativos minimos incluidos.
- [x] IA con guardrails y evals.

### Module review checklist

- [x] Limites de modulo claros.
- [x] Contratos de entrada/salida definidos.
- [x] Sin acoplamiento circular en el diseño propuesto.
- [x] Manejo de errores explicito.
- [x] Seguridad y tenant context considerados.
- [x] Observabilidad minima incluida.
- [ ] Tests de contrato definidos (gap).

### Release gates

- [x] Gate 1 architecture compliance.
- [x] Gate 2 tenant safety (diseño listo, falta evidencia de tests).
- [x] Gate 3 observability (definida, falta dashboard implementado).
- [x] Gate 4 AI quality (evals definidas, falta baseline cuantitativo).
- [x] Gate 5 governance (ADR-0003 existente).

## Riesgos y mitigaciones

- Riesgo: leakage por error de filtros en retrieval.
  - Mitigacion: pre-filtering hard mandatory + evals de leakage por tenant.
- Riesgo: tool calls no idempotentes en workflows de larga duracion.
  - Mitigacion: contract tests + dedup key por invocacion.
- Riesgo: release sin evidencia de calidad AI.
  - Mitigacion: gate de release con umbral minimo de evals.

## Violaciones detectadas en simulacion

No se detectaron violaciones criticas de constitucion.

Se detectaron gaps operativos (no bloqueantes de diseño, si bloqueantes de release):

1. Falta template de baseline de evals AI por caso de uso.
2. Falta guia de contract testing para MCP tools.
3. Falta runbook especifico de incidente AI leakage.

## Output final de S1-08

- Simulacion completada con caso real JurisManager.
- Plan cumple doctrina global y ADR de producto.
- Se genera backlog de quick wins para S1-09.

## Quick wins propuestos para S1-09

1. Crear `templates/ai-evals-baseline-template.md`.
2. Crear `checks/delivery/tool-contract-test-checklist.md`.
3. Crear `playbooks/operations/ai-leakage-incident-response.md`.
