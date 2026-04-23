# AI Leakage Incident Response

Runbook operativo para incidente de potencial fuga de informacion entre tenants en capacidades AI.

## Triggers

- Alerta automatica de leakage eval.
- Reporte de cliente sobre respuesta con datos ajenos.
- Deteccion interna por QA/SRE/Seguridad.

## Severity model

- Sev-1: evidencia confirmada de fuga cross-tenant en produccion.
- Sev-2: alta probabilidad de fuga sin confirmacion completa.
- Sev-3: anomalia aislada sin impacto confirmado.

## Respuesta inmediata (0-30 min)

1. Activar incident channel y owner.
2. Congelar feature AI afectada (kill-switch o degrade mode).
3. Bloquear tools o retrieval route sospechoso.
4. Preservar evidencias (logs, traces, prompts, retrieval ids).

## Contencion (30-120 min)

1. Identificar tenant(s) potencialmente afectados.
2. Revocar cache/contextos AI contaminados.
3. Aplicar hotfix de filtros tenant y permisos.
4. Ejecutar smoke eval de leakage posterior al fix.

## Erradicacion y recuperacion

1. Correr suite completa de leakage evals.
2. Validar gates de release AI antes de reactivar.
3. Rehabilitar feature en rollout gradual.
4. Monitorear 24h con alertas reforzadas.

## Comunicacion

- Stakeholders internos: arquitectura, seguridad, producto, soporte.
- Cliente(s) afectados: mensaje claro con timeline y mitigaciones.
- Registro formal en issue postmortem.

## Post-incident actions

- Crear ADR/actualizacion de policy si hubo brecha de diseño.
- Agregar test de regresion obligatorio.
- Actualizar baselines de evals y checklist de release.

## Evidencia minima

- `incident_id`
- `tenant_id` potencialmente afectados
- hash de version desplegada
- consultas/prompts implicados
- accion de contencion aplicada
- timestamp de recuperacion
