# OpenCode Validation Runbook

Runbook para validar en contexto real si la doctrina reduce alucinaciones y mejora planificacion.

## Preguntas que responde

1. El plan cita evidencia real del repo o inventa contexto?
2. El plan identifica gaps de conocimiento de forma explicita?
3. El plan mejora calidad y ejecutabilidad frente a baseline previo?

## Protocolo

### Fase 1 - Baseline

1. Seleccionar 5 prompts reales de planificacion sin contexto guiado.
2. Ejecutar OpenCode y guardar salidas en `reports/baseline/`.
3. Puntuar con `checks/architecture/planning-quality-scorecard.md`.

### Fase 2 - Guided doctrine

1. Repetir los mismos 5 prompts usando flujo obligatorio (`knowledge-map`, `constitution`, dominio, checks).
2. Guardar salidas en `reports/guided/`.
3. Puntuar nuevamente con el mismo scorecard.

### Fase 3 - Stress prompts

1. Ejecutar 5 prompts ambiguos o incompletos.
2. Verificar si el agente marca `GAP` en lugar de inventar.
3. Puntuar disciplina anti-hallucination.

## Metricas

- Planning quality score promedio (baseline vs guided).
- Tasa de claims sin evidencia (`no-path claims`).
- Tasa de fabricacion de artefactos.
- Tiempo medio para plan utilizable.
- % planes con score >= 10.

## Criterio de exito

- +25% de mejora en score promedio guided vs baseline.
- <= 5% de claims sin evidencia.
- 0 casos de artefactos fabricados en planes aprobados.

## Output esperado

- Reporte final usando `templates/planning-validation-report-template.md`.
- Lista de gaps para hardening doctrinal.
- Acciones para siguiente iteracion de governance.
