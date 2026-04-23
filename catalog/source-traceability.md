# Source Traceability

Mapeo explicito desde `arquitecto-moderno` hacia conocimiento operacional.

## Mapping table

| Source chapter | Operational docs |
| --- | --- |
| Cap 10 modelos de aislamiento | `domains/saas/tenancy-models.md`, `domains/backend/postgres/multi-tenancy-data-isolation.md` |
| Cap 11 identidad y contexto tenant | `domains/backend/security/identity-tenant-context.md` |
| Cap 12 seguridad y auditoria | `checks/architecture/service-readiness-scorecard.md` |
| Cap 16 multi-tenant RAG | `domains/ai/rag/multi-tenant-rag.md` |
| Cap 23 platform engineering | `domains/platform/golden-paths.md` |
| Apendice ADR template | `templates/adr-template.md` |

## Rules

- Cada doc operativo nuevo debe incluir `source_refs` si proviene del libro.
- Si un doc es netamente nuevo, marcar `source_refs: [operational-original]`.
- No editar contenido editorial del repo fuente desde este repositorio.
