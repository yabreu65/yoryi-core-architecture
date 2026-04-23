---
id: FE-ARCH-STATE-001
status: active
owner: frontend-architecture
last_reviewed: 2026-04-23
tags: [frontend, state-management, strategy]
source_refs: [operational-original]
---

# State Strategy

## Contexto

Una estrategia de estado ambigua produce bugs de sincronizacion, duplicacion de datos y degradacion de performance en UI complejas.

## Regla

- Diferenciar explicitamente: `server state`, `client state`, `ephemeral UI state`.
- `Server state` se resuelve con cache invalidable y politicas de stale/revalidation.
- `Client state` global solo para datos realmente compartidos por multiples features.
- `UI state` local debe quedarse cerca del componente y no escalarse sin criterio.

## Cuando aplica / no aplica

- Aplica a frontend con integraciones API, workflows y permisos por tenant.
- No aplica a pantallas estaticas sin interaccion relevante.

## Trade-offs

- Mas disciplina de clasificacion de estado.
- Menos race conditions, menor re-render innecesario y mejor debugging.

## Decision heuristics

1. Si el dato viene del backend y requiere refresh -> server state.
2. Si el dato coordina features separadas -> client state global.
3. Si el dato vive solo en una vista/flujo -> local UI state.

## Checklist de verificacion

- [ ] Cada store/context declara ownership y lifecycle.
- [ ] No hay duplicacion de la misma fuente en stores distintos.
- [ ] Invalidation/refetch definidos por evento de negocio.
- [ ] Estado sensible scoped por tenant y permisos.
- [ ] Tests cubren transiciones de estado criticas.

## Errores comunes

- Usar estado global para todo por comodidad.
- Copiar datos de server state a client state sin necesidad.
- Ignorar tenant context en caches compartidas.

## Referencias

- `domains/backend/security/identity-tenant-context.md`
- `checks/architecture/module-review-checklist.md`
- `checks/delivery/release-gates.md`
