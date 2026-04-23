---
id: CONST-PRINC-001
status: active
owner: architecture
last_reviewed: 2026-04-23
tags: [constitution, principles]
source_refs: [arquitecto-moderno/cheatsheet-decisiones-arquitectura]
---

# Architecture Principles

## Contexto

Estos principios gobiernan todas las decisiones del portfolio.

## Reglas

1. Tenant safety first: sin aislamiento verificable no hay release.
2. Contracts over coupling: interfaces explicitas antes de integracion.
3. Evolutionary architecture: preferir caminos que permitan migracion gradual.
4. Operational by design: observabilidad, seguridad y costos desde el inicio.
5. AI with boundaries: retrieval, agentes y tools con autorizacion y trazabilidad.

## Trade-offs

- Estandarizacion reduce autonomia local, pero reduce incidentes repetidos.
- Rigor documental agrega friccion inicial, pero acelera escalado organizacional.

## Checklist de verificacion

- [ ] La decision respeta tenant safety.
- [ ] Existe contrato claro entre modulos.
- [ ] Existe plan de evolucion sin big-bang rewrite.
- [ ] Incluye controles operativos minimos.
- [ ] Si involucra IA, incluye guardrails y evals.
