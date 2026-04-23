---
id: SAAS-TEN-001
status: active
owner: architecture
last_reviewed: 2026-04-23
tags: [saas, multi-tenant]
source_refs: [arquitecto-moderno/parte-iii-ingenieria-saas-y-multi-tenancy/capitulo-10-modelos-de-aislamiento-de-datos]
---

# Tenancy Models

## Contexto

Elegir mal el modelo de aislamiento es una de las decisiones mas caras de revertir.

## Regla

- Pool (`shared tables + tenant_id`) para early scale con disciplina fuerte.
- Schema-per-tenant para aislamiento intermedio.
- Database-per-tenant para enterprise con compliance alto.
- Estrategia recomendada: hibrida por segmento de tenant.

## Cuando aplica / no aplica

- Aplica siempre que exista multi-tenancy.
- No aplica a single-tenant temporal de laboratorio.

## Trade-offs

- Pool: menor costo, mayor riesgo de leakage.
- Silo: mayor seguridad, mayor costo operativo.

## Checklist de verificacion

- [ ] Hay criterio explicito de segmentacion por tenant tier.
- [ ] Hay plan de evolucion de topologia.
- [ ] Se definio postura de aislamiento por tipo de cliente.
