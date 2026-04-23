# Planning Validation Report

## Metadata

- Fecha: 2026-04-23
- Owner: architecture
- Version doctrina: 0.3.0
- Scope (productos/casos): BuildingOS, JurisManager

## Setup

- Numero de prompts baseline: 5
- Numero de prompts guided: 5
- Numero de stress prompts: 5
- Herramienta/agente: OpenCode (flujo doctrinal del repo)

## Results summary

- Score promedio baseline: 6.8/12
- Score promedio guided: 10.8/12
- Mejora porcentual: 58.8%
- Claims sin evidencia (%): baseline 31%, guided 4%, stress 6%
- Casos con fabricacion de artefactos: baseline 3/5, guided 0/5, stress 0/5

## Detailed findings

### Strengths

- Flujo guiado aumenta trazabilidad de decisiones por path.
- Checklists y ADR gate mejoran disciplina de governance.
- En prompts ambiguos, se incrementa uso de `GAP` en lugar de inventar.

### Gaps detected

- En stress prompts sigue habiendo 6% de claims sin path.
- Falta automatizar scoring para evitar evaluacion manual.
- Falta consolidar evidencia de corrida periodica (cadencia mensual).

### Hallucination patterns

- Baseline: tendencia a proponer artefactos no presentes en repositorio.
- Guided: baja fuerte de fabricacion por reglas de evidencia y anti-hallucination gate.
- Stress: mejora robusta, pero requiere reforzar evidencias en respuestas rapidas.

## Recommendations

1. Hacer obligatorio el `planning-quality-scorecard` para toda propuesta previa a implementacion.
2. Agregar check automatico de citas de path en flujo de planning.
3. Ejecutar la corrida baseline/guided/stress en cada release mayor de doctrina.

## Decision

- Estado: pass
- Siguiente accion: mantener consolidacion Sprint 1+2 y abrir Sprint 3 solo con cadencia de validacion definida.
- ADR requerida: no

## Evidence links

- `reports/prompt-set-2026-04-23.md`
- `reports/baseline/results-2026-04-23.md`
- `reports/guided/results-2026-04-23.md`
- `reports/stress/results-2026-04-23.md`
