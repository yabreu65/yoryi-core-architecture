---
id: BE-SEC-TCTX-001
status: active
owner: security
last_reviewed: 2026-04-23
tags: [backend, security, tenant-context]
source_refs: [arquitecto-moderno/parte-iii-ingenieria-saas-y-multi-tenancy/capitulo-11-identidad-y-contexto-del-tenant]
---

# Identity and Tenant Context

## Contexto

Sin tenant context confiable, no existe seguridad multi-tenant real.

## Regla

- Resolver tenant context en borde (gateway/BFF/API layer).
- Propagar tenant context como contrato explicito, no inferido.
- Validar RBAC/ABAC antes de acceso a datos y herramientas IA.

## Errores comunes

- Resolver tenant por header no firmado.
- Mezclar autenticacion con autorizacion de tenant.
- Omitir tenant context en jobs asincronos.

## Checklist de verificacion

- [ ] Tenant context firmado y validado.
- [ ] Contrato de propagacion definido.
- [ ] Background jobs preservan tenant context.
