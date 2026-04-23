---
id: FE-QUAL-OBS-001
status: active
owner: frontend-platform
last_reviewed: 2026-04-23
tags: [frontend, observability, quality]
source_refs: [operational-original]
---

# Frontend Observability

## Contexto

Sin observabilidad de frontend, los equipos ven solo errores backend y pierden visibilidad de latencia percibida, fallos de UX y degradaciones por navegador/dispositivo.

## Regla

- Instrumentar RUM (Real User Monitoring) para performance y errores en cliente.
- Correlacionar eventos frontend con `trace_id` de backend cuando exista request.
- Capturar eventos clave de negocio por flujo critico (no solo telemetria tecnica).
- Incluir `tenant_id` y contexto de usuario de forma segura y anonimizada cuando aplique.

## Cuando aplica / no aplica

- Aplica a aplicaciones web en produccion con impacto de negocio.
- No aplica a demos internas sin usuarios reales.

## Trade-offs

- Mayor volumen de eventos y costo de observabilidad.
- Mejor deteccion temprana de degradaciones UX y menor MTTR.

## Metricas minimas

- Web vitals: LCP, INP, CLS.
- Error rate de cliente por version/release.
- Tiempo de carga de pantallas criticas.
- Exito/fallo de interacciones clave de negocio.
- Latencia percibida por tenant tier o segmento.

## Alertas recomendadas

- Error burst por release (frontend error rate spike).
- Degradacion de LCP/INP sobre umbral.
- Caida de conversion en flujos core.
- Incremento de fallos de integracion BFF.

## Checklist de verificacion

- [ ] RUM habilitado en ambiente productivo.
- [ ] Correlacion frontend-backend con trace id.
- [ ] Dashboard por flujo critico y tenant segment.
- [ ] Alertas accionables definidas con ownership.
- [ ] Politica de privacidad de telemetria validada.

## Errores comunes

- Medir solo page views y no journeys de negocio.
- No versionar eventos, rompiendo series historicas.
- Mezclar datos sensibles en logs de frontend.

## Referencias

- `domains/frontend/architecture/bff-and-contracts.md`
- `checks/delivery/release-gates.md`
- `checks/architecture/service-readiness-scorecard.md`
