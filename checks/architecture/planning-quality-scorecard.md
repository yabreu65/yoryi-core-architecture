# Planning Quality Scorecard

Scorecard para medir calidad de planificacion y reduccion de alucinaciones en OpenCode/agentes.

## Objetivo

Evaluar si un plan es confiable, trazable y accionable antes de implementar.

## Rubrica (0-2 por criterio)

1. **Context coverage**
   - 0: no consulta doctrina minima
   - 1: consulta parcial
   - 2: consulta completa (knowledge-map + constitution + dominio + checks)

2. **Evidence traceability**
   - 0: sin citas de paths
   - 1: citas incompletas
   - 2: cada decision relevante cita path concreto

3. **Anti-hallucination discipline**
   - 0: inventa artefactos/detalles
   - 1: supuestos no marcados
   - 2: todo supuesto marcado como GAP y sin fabricacion

4. **Decision quality**
   - 0: sin trade-offs
   - 1: trade-offs superficiales
   - 2: opciones y trade-offs claros

5. **Governance compliance**
   - 0: ignora ADR/checklists
   - 1: aplica parcialmente
   - 2: aplica checklists y define necesidad ADR

6. **Execution readiness**
   - 0: plan vago
   - 1: tareas incompletas
   - 2: pasos claros, riesgos y mitigaciones accionables

## Scoring

- Max score: 12
- 10-12: production-ready planning
- 7-9: usable with fixes
- <=6: no-go, replan required

## Gate rule

Ningun plan pasa a implementacion si:

- Score total < 10, o
- `Anti-hallucination discipline` < 2, o
- `Evidence traceability` < 2.
