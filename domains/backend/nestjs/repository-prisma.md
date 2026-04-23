---
id: BE-NEST-PRISMA-001
status: active
owner: backend-platform
last_reviewed: 2026-04-23
tags: [nestjs, prisma, repository]
source_refs: [arquitecto-moderno/parte-ii-arquitectura-base-y-diseno-de-codigo/capitulo-08-el-patron-repository-en-nestjs]
---

# Repository with Prisma

## Contexto

Usar Prisma directo en servicios de aplicacion acopla dominio a detalles de persistencia.

## Regla

- Prisma Client vive en capa infraestructura.
- Repositorios implementan interfaces de puertos del dominio.
- El dominio nunca manipula modelos Prisma.

## Cuando aplica / no aplica

- Aplica a casos de uso con persistencia relacional.
- No aplica a lecturas ad-hoc de reporting fuera del core.

## Trade-offs

- Duplica mapeo entre entidades y modelos.
- Evita propagacion de deuda ORM a dominio.

## Checklist de verificacion

- [ ] Interface de repositorio definida antes de adapter Prisma.
- [ ] No se filtran tipos Prisma al dominio.
- [ ] Queries incluyen tenant scope cuando aplica.
- [ ] Test de repositorio cubre errores de constraints y not found.

## Referencias

- `domains/backend/postgres/multi-tenancy-data-isolation.md`
