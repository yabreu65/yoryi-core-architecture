# Sprint 1 + Sprint 2 Consolidation

Documento de estabilizacion antes de abrir Sprint 3.

## Objetivo

- Estabilizar doctrina base.
- Completar docs criticos.
- Validar flujo real con OpenCode.
- Medir reduccion de alucinaciones y mejora de planificacion.

## Estado actual

- Doctrina core: disponible.
- Playbooks operativos: disponibles.
- Templates governance: disponibles.
- Validacion inicial por casos reales: disponible.

## Checklist de consolidacion

### 1) Doctrina base estable

- [ ] Freeze temporal de cambios estructurales (solo fixes).
- [ ] Revisar consistencia entre `AGENTS.md`, `knowledge-map` y `checks`.
- [ ] Confirmar ownership por dominio vigente.

### 2) Docs criticos completos

- [ ] Ningun doc critico sin owner o metadata minima.
- [ ] Todas las fronteras clave cubiertas (tenant, contracts, AI safety, operations).
- [ ] Indices (`catalog/*`) sincronizados.

### 3) Validacion real con OpenCode

- [ ] Ejecutar `playbooks/planning/opencode-validation-runbook.md`.
- [ ] Guardar evidencias baseline/guided/stress.
- [ ] Generar reporte con `templates/planning-validation-report-template.md`.

### 4) Metricas de calidad

- [ ] Aplicar `checks/architecture/planning-quality-scorecard.md` a todos los casos.
- [ ] Confirmar umbrales de exito.
- [ ] Definir backlog de mejoras doctrinales.

## Gate para abrir Sprint 3

Sprint 3 solo se abre si:

1. Validacion completa publicada.
2. Score promedio >= 10 en planes guiados.
3. Tasa de claims sin evidencia <= 5%.
4. Cero fabricacion de artefactos en planes aprobados.
