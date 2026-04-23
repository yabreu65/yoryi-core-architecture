# AGENTS.md

Protocolo obligatorio para OpenCode, agentes IA y copilots que usen este repositorio.

## Mission

Aplicar la constitucion arquitectonica antes de proponer planes, cambios o revisiones.

## Mandatory planning flow

1. Cargar `catalog/knowledge-map.md`.
2. Cargar `constitution/architecture-principles.md`.
3. Cargar `constitution/decision-policy.md`.
4. Cargar docs del dominio afectado en `domains/`.
5. Ejecutar checklist aplicable en `checks/`.

Si falta contexto, crear gap explicito antes de planificar.

## Hard rules

- No plan without context.
- No decision without traceability.
- No exception without ADR.
- No permanent exception without expiration date.
- No AI retrieval without tenant authorization boundary.
- No unsupported claim: every relevant architectural claim must cite at least one repo path.
- No fabricated artifacts: never invent files, services, contracts, metrics, or decisions not present in repo evidence.
- If context is missing, mark it as explicit gap before proposing implementation details.

## Violation detection

Una propuesta viola arquitectura si ocurre uno o mas casos:

- Ignora `tenant_id` o aislamiento de datos por tenant.
- Introduce acoplamiento entre modulos sin contrato.
- Salta quality gates de seguridad/observabilidad.
- Define agentes sin guardrails, evals ni trazabilidad.

## Required output format for plans

Todo plan debe incluir:

- Context docs consultados.
- Evidencia por decision (`path -> regla usada`).
- Decisiones candidatas con trade-offs.
- Checklist aplicado.
- Riesgos y mitigaciones.
- ADR requerido o justificacion de no requerir ADR.

## Anti-hallucination protocol

Para reducir alucinaciones en planificacion:

1. Verificar contexto minimo (`knowledge-map`, `constitution`, dominio, `checks`).
2. Citar rutas concretas para reglas y constraints usadas.
3. Marcar explicitamente lo desconocido como `GAP`.
4. Evitar detalles de implementacion no respaldados por docs existentes.
5. Cerrar con score de calidad usando `checks/architecture/planning-quality-scorecard.md`.

## Multi-SaaS mode

- Global defaults: `constitution/`, `domains/`, `patterns/`, `checks/`, `templates/`.
- Product overrides: `products/<product>/local-overrides.md`.
- Si hay conflicto, gana la constitucion global salvo ADR aprobado.
