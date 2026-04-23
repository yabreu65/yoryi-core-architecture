---
id: AI-RAG-MT-001
status: active
owner: ai-architecture
last_reviewed: 2026-04-23
tags: [ai, rag, multi-tenant]
source_refs: [arquitecto-moderno/parte-v-arquitectura-orientada-a-ia/capitulo-16-multi-tenant-rag]
---

# Multi-tenant RAG

## Contexto

El peor incidente en RAG B2B es responder con datos correctos del tenant equivocado.

## Regla

- Pre-filtering obligatorio por `tenant_id` y permisos efectivos.
- Post-filtering solo como defensa secundaria.
- Toda respuesta debe poder trazar fuentes y chunks recuperados.

## Trade-offs

- Namespaces/silos: mas aislamiento, mas costo.
- Pool con metadata filters: menor costo, mayor riesgo si falla governance.

## Checklist de verificacion

- [ ] Filtro tenant y permisos aplicado antes del retrieval.
- [ ] Registro de chunks/documentos recuperados.
- [ ] Evals de leakage por tenant.
- [ ] Guardrails de salida para datos sensibles.
