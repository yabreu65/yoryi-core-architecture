# Roadmap Phases

Tracking oficial de implementacion del sistema doctrinal multi-SaaS con OpenCode.

## Estado global actual

- Fase activa: **Fase 1 - Integracion simple**
- Fases pendientes: **Fase 2, Fase 3, Fase 4**
- Regla de control: no iniciar nueva fase sin cumplir criterio de salida de la fase actual.

## Resumen por fase

| Fase | Nombre | Estado | Aprobado | Siguiente paso |
| --- | --- | --- | --- | --- |
| Fase 1 | Integracion simple | in-progress | yes | Cerrar checklist de Fase 1 y congelar baseline |
| Fase 2 | Reusable architecture layer | pending | no | Iniciar solo cuando Fase 1 este en `done` |
| Fase 3 | MCP + semantic retrieval | pending | no | Iniciar solo cuando Fase 2 este en `done` |
| Fase 4 | Multi-agent runtime | pending | no | Iniciar solo cuando Fase 3 este en `done` |

---

## Fase 1 - Integracion simple

- **Estado**: `in-progress`
- **Aprobado**: `yes`

### Objetivo

Conectar todos los SaaS a un unico core doctrinal sin duplicacion documental.

### Alcance

- Core unico en ruta fija.
- AGENTS global + AGENTS local por producto.
- Referencias explicitas en `opencode.json` hacia core, overlay y current-state.
- Flujo minimo anti-alucinacion en planning.

### Entregables esperados

- Ruta canonica del core definida y comunicada.
- Contrato de consumo del core por cada SaaS.
- Plantillas base para `current-state` y `core-overlay`.
- Reglas de evidencia (`path -> regla`) activas en planificacion.
- Validacion inicial baseline/guided/stress publicada.

### Criterio para pasar a la siguiente fase

1. Todos los SaaS activos consumen el mismo core sin copias locales.
2. `AGENTS.md` local de cada SaaS exige consulta doctrinal previa.
3. `opencode.json` local referencia explicita al core y contexto local.
4. Metricas de validacion dentro de umbral:
   - score guiado >= 10
   - claims sin evidencia <= 5%
   - 0 artefactos fabricados en planes aprobados

---

## Fase 2 - Reusable architecture layer

- **Estado**: `pending`
- **Aprobado**: `no`

### Objetivo

Estandarizar la capa reusable por producto (overlays/current-state) para escalar sin divergencia.

### Alcance

- Contrato formal de overlays.
- Contrato formal de current-state.
- Indices y trazabilidad consistentes entre core y productos.

### Entregables esperados

- `overlay-contract` v1 aplicado en todos los SaaS.
- `current-state` template v1 aplicado en todos los SaaS.
- Reporte de divergencia doctrinal por producto.

### Criterio para pasar a la siguiente fase

1. 100% de productos con overlay/current-state en formato estandar.
2. 0 duplicacion de doctrina global en repos de producto.
3. Auditoria doctrinal sin bloqueantes criticos.

---

## Fase 3 - MCP + semantic retrieval

- **Estado**: `pending`
- **Aprobado**: `no`

### Objetivo

Mejorar recuperacion semantica y precision contextual para planificacion/review de agentes.

### Alcance

- Indice semantico de core + overlays + current-state.
- Politica de retrieval con trazabilidad obligatoria.
- Validacion comparativa contra flujo sin retrieval semantico.

### Entregables esperados

- Pipeline MCP de retrieval documentado.
- Politica de citas por evidencia obligatoria.
- Reporte de mejora de precision y reduccion de alucinaciones.

### Criterio para pasar a la siguiente fase

1. Retrieval semantico estable en al menos 2 SaaS.
2. Mejora medible de calidad de planning >= 15% vs fase previa.
3. Sin degradacion de governance ni trazabilidad.

---

## Fase 4 - Multi-agent runtime

- **Estado**: `pending`
- **Aprobado**: `no`

### Objetivo

Operar flujos agentic especializados (planning/review/compliance) con gates de calidad.

### Alcance

- Roles de agentes por capacidad.
- Orquestacion con quality gates.
- Observabilidad de decisiones y trazabilidad end-to-end.

### Entregables esperados

- Topologia multi-agent formalizada.
- Gates automaticos de compliance doctrinal.
- Runbooks operativos de incidentes de agentes.

### Criterio para cierre de roadmap

1. Runtime multi-agent en produccion controlada.
2. Cumplimiento sostenido de quality gates.
3. Postmortems y mejoras continuas institucionalizadas.

---

## Politica de control de fase

- Solo una fase puede estar `in-progress` a la vez.
- Si una fase esta `in-progress`, las siguientes deben permanecer `pending`.
- Cambio de estado requiere:
  - evidencia documental,
  - validacion contra criterios,
  - aprobacion de arquitectura.

## Proxima decision esperada

Cuando Fase 1 cumpla su criterio de salida:

- marcar Fase 1 como `done`
- marcar Fase 2 como `in-progress`
- crear milestone e issues especificos de Fase 2
