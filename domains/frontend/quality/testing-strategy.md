---
id: FE-QUAL-TEST-001
status: active
owner: frontend-quality
last_reviewed: 2026-04-23
tags: [frontend, testing, quality]
source_refs: [operational-original]
---

# Frontend Testing Strategy

## Contexto

Sin estrategia de testing por capas, los equipos dependen de QA manual y bugs de regresion llegan tarde a produccion.

## Regla

- Separar testing en 4 niveles: unit, component, contract, e2e critical paths.
- Priorizar contract tests para integracion frontend-BFF.
- E2E solo para journeys de negocio criticos, no para toda la UI.
- Tests deben incluir escenarios multi-tenant y permisos.

## Cuando aplica / no aplica

- Aplica a todas las aplicaciones frontend con release continuo.
- No aplica a spikes descartables sin ruta a produccion.

## Trade-offs

- Mayor inversion inicial en automatizacion.
- Menor costo de regresion y mas confianza de release.

## Testing matrix minima

- Unit tests: hooks, utilidades, reducers, mappers.
- Component tests: rendering/interaction de componentes de negocio.
- Contract tests: schemas y compatibilidad con BFF.
- E2E: login, tenant context, flujos de alto valor.

## Checklist de verificacion

- [ ] Cada feature declara cobertura minima por nivel.
- [ ] Contract tests corren en CI para PRs.
- [ ] E2E cubre flujos criticos por tenant tier.
- [ ] Fixtures no incluyen datos sensibles reales.
- [ ] Falla de tests de contrato bloquea release.

## Errores comunes

- Exceso de E2E inestables y lentos como unica defensa.
- Falta de contract tests pese a cambios frecuentes de API.
- Cobertura alta pero sin escenarios de negocio reales.

## Referencias

- `domains/frontend/architecture/bff-and-contracts.md`
- `checks/delivery/pr-architecture-checklist.md`
- `checks/delivery/release-gates.md`
