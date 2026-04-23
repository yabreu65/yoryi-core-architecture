---
id: BE-NEST-HEX-001
status: active
owner: backend-architecture
last_reviewed: 2026-04-23
tags: [nestjs, clean-architecture, hexagonal]
source_refs: [arquitecto-moderno/parte-ii-arquitectura-base-y-diseno-de-codigo/capitulo-07-clean-architecture-y-arquitectura-hexagonal]
---

# Clean Hexagonal

## Contexto

La arquitectura se rompe cuando el dominio depende de frameworks, ORMs y transportes.

## Regla

- Dominio y casos de uso no dependen de NestJS ni Prisma.
- Adaptadores implementan puertos del dominio.
- Controllers y handlers solo orquestan entrada/salida.

## Cuando aplica / no aplica

- Aplica a modulos core de negocio.
- No aplica a scripts de migracion o tooling de infraestructura.

## Trade-offs

- Mas capas implican mas codigo estructural.
- Se gana testabilidad, independencia de framework y evolucion de infraestructura.

## Checklist de verificacion

- [ ] Casos de uso no importan clases de framework.
- [ ] Puertos de salida definidos en dominio o aplicacion.
- [ ] Infraestructura implementa adapters concretos.
- [ ] Tests unitarios del dominio corren sin DB.

## Referencias

- `checks/architecture/module-review-checklist.md`
