# Sprint 1 Executable

Duracion sugerida: 10 dias habiles.

## Objetivo del sprint

Dejar `yoryi-core-architecture` en estado usable por OpenCode y equipos para planificacion y reviews de arquitectura.

## Definition of done del sprint

- Doctrina minima publicada y enlazada desde `catalog/knowledge-map.md`.
- Checks de delivery activos y aplicables.
- ADRs iniciales aprobadas para portfolio y productos iniciales.
- Flujo de planificacion con OpenCode usable sin bloqueos.

## Backlog ejecutable

| ID | Tarea | Tipo | Owner sugerido | Estimacion | Dependencias | Entregable |
| --- | --- | --- | --- | --- | --- | --- |
| S1-01 | Completar doctrine NestJS (4 docs) | doc-core | backend-arch | 1.5d | - | `domains/backend/nestjs/*.md` |
| S1-02 | Completar doctrine AI Agents y Runtime (4 docs) | doc-core | ai-arch | 1.5d | - | `domains/ai/agents/*.md`, `domains/ai/runtime/*.md` |
| S1-03 | Crear checks de delivery | governance | platform | 0.5d | S1-01,S1-02 | `checks/delivery/*.md` |
| S1-04 | Actualizar catalogos e indices | governance | architecture | 0.5d | S1-01,S1-02,S1-03 | `catalog/*.md` |
| S1-05 | Definir ADR inicial portfolio | decision | principal-arch | 0.5d | S1-04 | `products/_blueprint/local-adrs/ADR-0001-*.md` |
| S1-06 | Definir ADR inicial BuildingOS | decision | buildingos-techlead | 0.5d | S1-05 | `products/buildingos/local-adrs/ADR-0002-*.md` |
| S1-07 | Definir ADR inicial JurisManager | decision | juris-techlead | 0.5d | S1-05 | `products/jurismanager/local-adrs/ADR-0003-*.md` |
| S1-08 | Simulacion de plan OpenCode con caso real | validation | architecture | 1d | S1-01..S1-07 | reporte en `playbooks/planning/` |
| S1-09 | Gap list y fixes de quick wins | hardening | architecture | 1d | S1-08 | backlog S2 draft |
| S1-10 | Cierre sprint y release v0.2.0 | release | architecture | 0.5d | S1-09 | `CHANGELOG.md` actualizado |

## Secuencia recomendada

1. S1-01 + S1-02 en paralelo.
2. S1-03 + S1-04 en paralelo corto.
3. S1-05, luego S1-06 y S1-07.
4. S1-08 y S1-09.
5. S1-10.

## Riesgos y mitigacion

- Riesgo: docs largos y ambiguos. Mitigacion: regla de un problema por archivo.
- Riesgo: ADRs sin adopcion. Mitigacion: gate en `checks/delivery/release-gates.md`.
- Riesgo: deriva con repo editorial. Mitigacion: actualizar `catalog/source-traceability.md` por cada extraccion.

## KPIs del sprint

- % de tareas del backlog completadas.
- % de docs con metadata completa.
- Tiempo medio de planificacion OpenCode con contexto completo.
- Cantidad de gaps detectados en simulacion.
