# ADR-0001 Portfolio Tenancy and AI Governance Baseline

## Metadata

- ADR ID: ADR-0001
- Date: 2026-04-23
- Status: accepted
- Owners: principal-architecture
- Scope: portfolio
- Related docs:
  - `constitution/architecture-principles.md`
  - `domains/saas/tenancy-models.md`
  - `domains/ai/rag/multi-tenant-rag.md`

## Context

El portfolio necesita una postura comun para aislamiento multi-tenant y seguridad AI para evitar decisiones contradictorias entre productos.

## Decision

Se adopta baseline portfolio: estrategia hibrida de tenancy por segmento y AI retrieval con pre-filtering obligatorio por tenant y permisos efectivos.

## Alternatives considered

1. Pool-only para todos los tenants.
2. Silo-only para todos los tenants.
3. Estrategia hibrida segmentada (decision elegida).

## Trade-offs

- Beneficios: consistencia transversal, menor riesgo de leakage, mejor control de costos.
- Costos: mayor complejidad operativa de routing y gobernanza.
- Riesgos: mala segmentacion inicial de tenants.

## Consequences

Todos los productos deben declarar su perfil de aislamiento y su politica de retrieval autorizado.

## Rollout plan

1. Publicar baseline en core.
2. Crear ADR por producto alineado al baseline.
3. Aplicar gates de release para tenant safety y AI quality.

## Expiration / review trigger

Revisar en 6 meses o antes si hay incidente cross-tenant severo.
