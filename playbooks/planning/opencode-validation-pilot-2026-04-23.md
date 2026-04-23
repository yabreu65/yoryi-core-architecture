# OpenCode Validation Pilot - 2026-04-23

## Scope

Piloto inicial para validar el flujo real de planificacion con doctrina consolidada de Sprint 1 + Sprint 2.

## Limitaciones

- No es un benchmark estadistico completo.
- Usa evidencia existente de casos reales y simulaciones ya documentadas.
- Sirve como punto de partida para la corrida formal del runbook.

## Casos evaluados

1. `playbooks/planning/s1-08-opencode-simulation-report.md`
2. `playbooks/planning/s2-09-validation-report-2-real-cases.md` (BuildingOS)
3. `playbooks/planning/s2-09-validation-report-2-real-cases.md` (JurisManager)

## Score por caso (rubrica planning-quality-scorecard)

| Caso | Context | Evidence | Anti-hallucination | Decision | Governance | Execution | Total |
| --- | --- | --- | --- | --- | --- | --- | --- |
| S1-08 JurisManager simulation | 2 | 2 | 2 | 2 | 2 | 2 | 12 |
| S2-09 BuildingOS validation | 2 | 2 | 2 | 1 | 2 | 2 | 11 |
| S2-09 JurisManager validation | 2 | 2 | 2 | 2 | 2 | 2 | 12 |

Promedio piloto: 11.67/12

## Hallucination control signals

- Claims sin evidencia de path: 0 detectados en los casos evaluados.
- Artefactos fabricados: 0 detectados.
- Gaps explicitos declarados: si, cuando correspondio en S1-08.

## Resultado del piloto

- Estado: pass (pilot)
- Riesgo residual: falta corrida formal baseline vs guided vs stress.

## Recomendaciones inmediatas

1. Ejecutar corrida formal con `playbooks/planning/opencode-validation-runbook.md` (5 baseline + 5 guided + 5 stress).
2. Publicar reporte formal con `templates/planning-validation-report-template.md`.
3. Mantener gate de score >= 10 en planes previos a implementacion.
