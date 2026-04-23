---
id: AI-AG-TOOLS-001
status: active
owner: ai-platform
last_reviewed: 2026-04-23
tags: [ai, agents, tools, contracts]
source_refs: [arquitecto-moderno/parte-v-arquitectura-orientada-a-ia/capitulo-18-frameworks-de-orquestacion]
---

# Tool Contracts

## Contexto

Los agentes no deben improvisar invocaciones de tools: cada tool es un contrato con pre/postcondiciones.

## Regla

- Toda tool define input schema, output schema, errores esperados y politicas de seguridad.
- Tool calls que mutan estado deben ser idempotentes o tener clave de deduplicacion.
- Tool sin contrato versionado no se habilita en produccion.

## Cuando aplica / no aplica

- Aplica a MCP tools, integraciones externas y acciones con side effects.
- No aplica a funciones internas puras sin exposicion a agentes.

## Trade-offs

- Contratos estrictos agregan trabajo de diseño.
- Reducen fallas ambiguas y facilitan pruebas automatizadas de agentes.

## Checklist de verificacion

- [ ] Schema de entrada y salida versionado.
- [ ] Reglas de autorizacion por tenant/rol definidas.
- [ ] Errores de negocio y sistema documentados.
- [ ] Existe suite de tests de contrato de tool.

## Referencias

- `checks/delivery/release-gates.md`
- `domains/backend/security/identity-tenant-context.md`
