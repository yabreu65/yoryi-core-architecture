# Sprint 2 Executable

Duracion sugerida: 10 dias habiles.

## Objetivo del sprint

Completar la capa operativa faltante para frontend, operaciones y governance de arquitectura review, dejando el repo listo para adopcion multi-equipo.

## Definition of done del sprint

- Doctrina frontend activa en arquitectura y calidad.
- Playbooks operativos de incidentes y migraciones publicados.
- Templates de review arquitectonica y AI feature design listos para uso.
- Ownership por dominio definido en governance.
- Simulacion con 2 casos reales (BuildingOS + JurisManager) cerrada con hallazgos.

## Backlog ejecutable

| ID | Tarea | Tipo | Owner sugerido | Estimacion | Dependencias | Entregable |
| --- | --- | --- | --- | --- | --- | --- |
| S2-01 | Publicar frontend boundaries y state strategy | doc-core | frontend-arch | 1d | - | `domains/frontend/architecture/frontend-boundaries.md`, `domains/frontend/architecture/state-strategy.md` |
| S2-02 | Publicar BFF/contracts y testing frontend | doc-core | frontend-arch | 1d | S2-01 | `domains/frontend/architecture/bff-and-contracts.md`, `domains/frontend/quality/testing-strategy.md` |
| S2-03 | Publicar observabilidad frontend | doc-core | frontend-platform | 0.5d | S2-02 | `domains/frontend/quality/observability-frontend.md` |
| S2-04 | Crear playbook incident response | operations | sre | 0.5d | - | `playbooks/operations/incident-response-flow.md` |
| S2-05 | Crear playbook migration rollout | operations | backend-platform | 0.5d | - | `playbooks/operations/migration-rollout-flow.md` |
| S2-06 | Crear playbook tenant isolation upgrade | operations | saas-arch | 0.5d | S2-05 | `playbooks/operations/tenant-isolation-upgrade-flow.md` |
| S2-07 | Publicar templates de architecture review y AI feature design | governance | principal-arch | 0.5d | S2-01,S2-02,S2-03 | `templates/architecture-review-template.md`, `templates/ai-feature-design-template.md` |
| S2-08 | Definir ownership model por dominio | governance | principal-arch | 0.5d | S2-07 | `governance/ownership-model.md` |
| S2-09 | Ejecutar validacion con 2 casos reales | validation | architecture | 1d | S2-04..S2-08 | reporte en `playbooks/planning/` |
| S2-10 | Cerrar gaps y release v0.3.0 | release | architecture | 0.5d | S2-09 | `CHANGELOG.md` actualizado |

## Secuencia recomendada

1. S2-01, S2-04 y S2-05 en paralelo.
2. S2-02 y S2-06.
3. S2-03 y S2-07.
4. S2-08.
5. S2-09.
6. S2-10.

## Riesgos y mitigacion

- Riesgo: frontend doctrine genérica y poco accionable. Mitigacion: incluir checks verificables por PR.
- Riesgo: playbooks sin adopcion operativa. Mitigacion: simulacros obligatorios por producto.
- Riesgo: ownership ambiguo. Mitigacion: RACI simple y owner unico por dominio.

## KPIs del sprint

- % de docs frontend y operations publicados.
- Tiempo de resolution en simulacro de incidente.
- % de PRs con checklist de arquitectura completo.
- Cantidad de gaps detectados en validaciones reales.
