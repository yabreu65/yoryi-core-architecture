# Release Gates

Gates minimos antes de promover cambios a produccion.

## Gate 1 - Architecture compliance

- Checklist de PR completo.
- Sin violaciones criticas de constitucion.

## Gate 2 - Security and tenant safety

- Validacion de tenant context y autorizacion.
- Tests de no acceso cross-tenant en verde.

## Gate 3 - Observability and operations

- Logs, metricas y trazas activos.
- Alertas y runbook disponibles.

## Gate 4 - AI quality (si aplica)

- Evals de leakage y calidad por encima de umbral.
- Guardrails de output activos.

## Gate 5 - Change governance

- ADR aprobado cuando corresponde.
- Excepciones con owner y fecha de expiracion.
