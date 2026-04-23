---
id: BE-PG-MT-001
status: active
owner: backend-platform
last_reviewed: 2026-04-23
tags: [backend, postgres, multi-tenant, rls]
source_refs: [arquitecto-moderno/parte-iii-ingenieria-saas-y-multi-tenancy/capitulo-10-modelos-de-aislamiento-de-datos]
---

# Multi-tenancy Data Isolation

## Contexto

La app puede fallar; la base no debe permitir acceso cruzado.

## Regla

- `tenant_id` obligatorio en toda tabla tenant-scoped.
- Postgres RLS obligatorio para datos sensibles compartidos.
- Query path sin tenant context es bloqueo automatico.

## Trade-offs

- RLS aumenta complejidad de testing y migraciones.
- RLS reduce blast radius ante bug de filtrado en app.

## Checklist de verificacion

- [ ] Todas las tablas tenant-scoped tienen `tenant_id`.
- [ ] Politicas RLS definidas y testeadas.
- [ ] Existen pruebas de no acceso cross-tenant.
- [ ] Logs incluyen `tenant_id` para auditoria.
