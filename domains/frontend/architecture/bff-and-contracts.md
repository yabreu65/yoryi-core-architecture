---
id: FE-ARCH-BFF-001
status: active
owner: frontend-architecture
last_reviewed: 2026-04-23
tags: [frontend, bff, contracts]
source_refs: [operational-original]
---

# BFF and Contracts

## Contexto

Cuando frontend consume APIs sin frontera de contrato estable, cada cambio backend rompe flujos de UI y dispara retrabajo entre equipos.

## Regla

- Definir BFF como frontera de adaptacion para necesidades de UI.
- Contratos frontend-BFF deben estar tipados, versionados y con estrategia de deprecacion.
- El frontend no conoce detalles internos de microservicios o modulos backend.
- Errores de contrato se tratan como incidentes de integracion, no bugs de vista.

## Cuando aplica / no aplica

- Aplica a productos con mas de una experiencia cliente/canal.
- No aplica a MVP simple con backend monolitico y un unico consumidor temporal.

## Trade-offs

- Capa BFF agrega costo de mantenimiento.
- Reduce acoplamiento y acelera evolucion paralela de frontend y backend.

## Checklist de verificacion

- [ ] Contratos de request/response tipados y versionados.
- [ ] Politica de deprecacion y compatibilidad definida.
- [ ] BFF mapea errores de backend a errores de UX consistentes.
- [ ] Cambios breaking tienen migration plan.
- [ ] Observabilidad por endpoint BFF (latencia/error rate).

## Errores comunes

- Dejar al frontend consumir endpoints internos no estables.
- Romper contrato sin versionar para "acelerar".
- Duplicar logica de composicion de datos en cada pantalla.

## Referencias

- `domains/backend/nestjs/api-versioning.md`
- `checks/delivery/release-gates.md`
