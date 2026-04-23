---
id: BE-NEST-MOD-001
status: active
owner: backend-architecture
last_reviewed: 2026-04-23
tags: [nestjs, modularity, boundaries]
source_refs: [arquitecto-moderno/parte-ii-arquitectura-base-y-diseno-de-codigo/capitulo-06-del-monolito-al-monolito-modular]
---

# Module Boundaries

## Contexto

Un monolito modular solo funciona si los limites de modulo son verificables y no negociables.

## Regla

- Cada modulo expone una API interna explicita (commands, queries, events).
- Ningun modulo consume repositorios o entidades internas de otro modulo.
- Integraciones entre modulos se hacen por contratos, no por imports directos de implementacion.

## Cuando aplica / no aplica

- Aplica a todo servicio NestJS de negocio.
- No aplica a librerias puras sin dominio.

## Trade-offs

- Limites estrictos agregan friccion inicial.
- Reducen deuda de acoplamiento y facilitan extraccion futura a servicio separado.

## Checklist de verificacion

- [ ] Existe un folder de public API por modulo.
- [ ] No hay imports cruzados de internals entre modulos.
- [ ] Eventos inter-modulo estan versionados.
- [ ] Los tests de contrato cubren casos de consumo cruzado.

## Referencias

- `checks/architecture/module-review-checklist.md`
- `patterns/architectural/modular-monolith.md`
