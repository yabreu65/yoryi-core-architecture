# Anti-pattern: Shared DB Without RLS

## Smell

Se usa shared tables con `tenant_id` pero sin politicas RLS.

## Impact

Un bug de query puede exponer datos cross-tenant.

## Guardrail

RLS obligatorio para tablas tenant-scoped sensibles.
