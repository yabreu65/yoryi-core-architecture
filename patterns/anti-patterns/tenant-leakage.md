# Anti-pattern: Tenant Leakage

## Smell

Datos de un tenant pueden ser visibles por otro por falla de filtros o permisos.

## Why it happens

- Falta de RLS.
- Tenant context debil.
- Retrieval IA sin pre-filtering.

## Guardrail

Aplicar aislamiento en app + DB + retrieval.
