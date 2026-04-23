# ADR-0002 BuildingOS Tenancy Profile

## Metadata

- ADR ID: ADR-0002
- Date: 2026-04-23
- Status: accepted
- Owners: buildingos-techlead
- Scope: product
- Related docs:
  - `products/buildingos/context.md`
  - `domains/saas/tenancy-models.md`
  - `domains/backend/postgres/multi-tenancy-data-isolation.md`

## Context

BuildingOS combina tenants de mid-market y cuentas enterprise con necesidades de aislamiento diferentes.

## Decision

Adoptar modelo hibrido: pool + RLS por default para mid-market, con ruta de promocion a schema/db dedicados para enterprise regulado.

## Alternatives considered

1. Pool-only.
2. Database-per-tenant para todos.
3. Hibrido por segmento (decision elegida).

## Trade-offs

- Beneficios: balance entre costo y seguridad por segmento.
- Costos: mayor complejidad de operaciones y migracion por tenant.
- Riesgos: sobrecarga operativa si no hay automation de lifecycle.

## Consequences

Se requiere tenant catalog con tier y estrategia de aislamiento declarada por tenant.

## Rollout plan

1. Mantener pool + RLS como baseline.
2. Definir criterios de promocion a tier aislado.
3. Automatizar migracion de tenants premium.

## Expiration / review trigger

Revisar en 4 meses o al superar 50 tenants enterprise activos.
