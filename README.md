# yoryi-core-architecture

Sistema operativo arquitectonico reusable para SaaS multi-tenant, sistemas AI-native y flujos de planificacion con OpenCode.

## Proposito

- Convertir conocimiento pedagogico (`arquitecto-moderno`) en conocimiento operacional, modular y consultable por IA.
- Estandarizar decisiones de arquitectura para BuildingOS, JurisManager y futuros SaaS.
- Funcionar como constitucion arquitectonica, no como libro ni sitio editorial.

## Audiencias

- Arquitectura: decisiones, trade-offs, ADRs.
- Equipos de producto: checklists y golden paths.
- OpenCode y agentes IA: reglas de planificacion y enforcement.

## Como consumir este repo

1. Leer `catalog/knowledge-map.md`.
2. Leer `constitution/architecture-principles.md` y `constitution/decision-policy.md`.
3. Entrar al dominio relevante en `domains/`.
4. Validar con `checks/`.
5. Si hay excepcion, registrar ADR en `templates/adr-template.md`.

## Regla base

No se planifica ni implementa sin contexto arquitectonico minimo.

## Relacion con arquitecto-moderno

- `arquitecto-moderno` sigue siendo fuente editorial.
- Este repo es fuente operacional.
- Trazabilidad de origen en `catalog/source-traceability.md`.
