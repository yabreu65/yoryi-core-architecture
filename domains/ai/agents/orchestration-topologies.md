---
id: AI-AG-ORCH-001
status: active
owner: ai-architecture
last_reviewed: 2026-04-23
tags: [ai, agents, orchestration]
source_refs: [arquitecto-moderno/parte-v-arquitectura-orientada-a-ia/capitulo-17-orquestacion-de-agentes-de-ia]
---

# Agent Orchestration Topologies

## Contexto

No toda tarea requiere multi-agent. Elegir topologia incorrecta eleva costo y complejidad sin mejorar resultado.

## Regla

- Single-agent para tareas lineales y contexto acotado.
- Supervisor + workers para tareas paralelizables por dominio.
- Event-driven orchestration para procesos largos y asincronos.

## Cuando aplica / no aplica

- Aplica a sistemas AI-native con herramientas y decisiones compuestas.
- No aplica a endpoints sin necesidad de razonamiento multi-paso.

## Trade-offs

- Orquestacion distribuida mejora escalado.
- Aumenta complejidad de observabilidad, retry y seguridad de herramientas.

## Checklist de verificacion

- [ ] Topologia elegida se justifica por tipo de tarea.
- [ ] Existe control de timeout y retry por agente.
- [ ] Existe trazabilidad de decisiones y llamadas a tools.
- [ ] Existe fallback deterministico si el agente falla.

## Referencias

- `domains/ai/agents/tool-contracts.md`
- `patterns/ai-native/retrieval-firewall.md`
