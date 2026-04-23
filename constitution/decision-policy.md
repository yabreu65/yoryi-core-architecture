---
id: CONST-DEC-001
status: active
owner: architecture
last_reviewed: 2026-04-23
tags: [constitution, governance, decisions]
source_refs: [arquitecto-moderno/apendice-adr-template]
---

# Decision Policy

## Decision classes

- D1: local implementation (sin impacto transversal).
- D2: product architecture (impacto por producto).
- D3: platform/portfolio (impacto multi-SaaS).

## ADR policy

ADR obligatorio cuando:

- cambia topologia multi-tenant,
- cambia contrato de integracion entre dominios,
- cambia postura de seguridad,
- cambia estrategia de orquestacion AI,
- introduce excepcion a principios globales.

## SLA de decision

- D1: <= 2 dias.
- D2: <= 5 dias.
- D3: <= 10 dias y review de arquitectura.
