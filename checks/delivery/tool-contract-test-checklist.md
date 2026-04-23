# Tool Contract Test Checklist

Checklist de validacion para tools expuestas a agentes (MCP o equivalentes).

## Contract correctness

- [ ] Input schema validado y versionado.
- [ ] Output schema validado y versionado.
- [ ] Errores esperados documentados (negocio y sistema).
- [ ] Semantica de codigos de error consistente.

## Security and tenant boundaries

- [ ] Tenant context requerido y validado.
- [ ] RBAC/ABAC aplicado antes de ejecutar side effects.
- [ ] Requests no autorizados fallan de forma segura.
- [ ] No se exponen datos sensibles en mensajes de error.

## Reliability

- [ ] Idempotencia definida para operaciones mutables.
- [ ] Retry policy definida (incluye backoff y max attempts).
- [ ] Timeouts configurados por tipo de tool.
- [ ] Manejo de dependencia externa degradado y observable.

## Observability

- [ ] Logs con `tenant_id`, `trace_id`, `tool_name`, `version`.
- [ ] Metricas de latencia, error rate y throughput.
- [ ] Trazas con inicio/fin y causas de fallo.

## Release readiness

- [ ] Test suite automatizada en CI.
- [ ] Cobertura de paths feliz + errores criticos.
- [ ] Evidencia de pruebas anexada al PR.
- [ ] Gate de release aprobado.
