# AI Evals Baseline Template

Template minimo para definir baseline de calidad y seguridad antes de release de una capacidad AI.

## Metadata

- Feature:
- Product:
- Owner:
- Fecha:
- Modelo(s):
- Version de prompt/system:
- Version de retrieval index:

## Scope funcional

- Caso de uso principal:
- Casos de uso fuera de scope:
- Perfil de tenant objetivo:

## Dataset de evaluacion

- Total de casos:
- Casos por tenant tier:
- Casos sensibles (PII/legal/finance):
- Fuente de ground-truth:

## Metricas obligatorias

- Exactitud de respuesta (quality score):
- Leakage rate cross-tenant:
- Rechazo correcto en consultas no autorizadas:
- Tasa de alucinacion:
- Latencia P50/P95:
- Costo por request:

## Umbrales de gate

- Leakage rate: `<= 0.1%` (o mas estricto por producto)
- Rechazo correcto no autorizado: `>= 99%`
- Quality score minimo: definir por dominio
- Latencia P95 maxima: definir por SLA
- Costo maximo por request: definir por plan

## Suites de prueba

- [ ] Normal queries
- [ ] Unauthorized queries
- [ ] Prompt injection attempts
- [ ] Retrieval poisoning attempts
- [ ] Empty retrieval scenarios

## Resultado

- Estado: pass | fail | conditional
- Riesgos residuales:
- Mitigaciones acordadas:
- Fecha de re-evaluacion:

## Evidencia

- Dashboards:
- Reporte de evals:
- Issue/ADR relacionados:
