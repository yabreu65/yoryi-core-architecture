# ADR-0003 JurisManager Secure Retrieval and Isolation

## Metadata

- ADR ID: ADR-0003
- Date: 2026-04-23
- Status: accepted
- Owners: juris-techlead
- Scope: product
- Related docs:
  - `products/jurismanager/context.md`
  - `domains/backend/security/identity-tenant-context.md`
  - `domains/ai/rag/multi-tenant-rag.md`

## Context

JurisManager maneja informacion legal sensible y requiere postura conservadora de seguridad multi-tenant y AI retrieval.

## Decision

Adoptar aislamiento reforzado para tenants sensibles y retrieval con pre-filtering obligatorio + trazabilidad completa de fuentes en toda respuesta AI.

## Alternatives considered

1. Pool vectorial con metadata filtering como default.
2. Namespace/silo por tenant sensible + fallback pool para no sensibles (decision elegida).
3. Sin features AI en produccion.

## Trade-offs

- Beneficios: menor riesgo de fuga semantica y mayor auditabilidad.
- Costos: incremento de costo por almacenamiento y operaciones vectoriales.
- Riesgos: complejidad de governance de perfiles sensibles.

## Consequences

Cada pipeline AI debe registrar tenant scope, ids de chunks y evidencia de permisos efectivos.

## Rollout plan

1. Definir clasificacion de tenants por sensibilidad.
2. Activar pre-filtering hard mandatory en retrieval.
3. Habilitar dashboards de leakage evals por tenant tier.

## Expiration / review trigger

Revisar en 3 meses o despues del primer release AI-native en produccion.
