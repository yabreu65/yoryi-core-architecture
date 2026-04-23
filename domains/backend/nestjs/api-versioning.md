---
id: BE-NEST-API-VER-001
status: active
owner: backend-architecture
last_reviewed: 2026-04-23
tags: [nestjs, api, versioning]
source_refs: [arquitecto-moderno/parte-ii-arquitectura-base-y-diseno-de-codigo/capitulo-09-estrategias-de-versionado-de-apis]
---

# API Versioning

## Contexto

Sin estrategia de versionado, cada cambio rompe clientes y reduce velocidad de evolucion.

## Regla

- Toda API publica debe tener estrategia explicita de version.
- Cambios breaking solo por version mayor o endpoint nuevo.
- Deprecaciones requieren ventana de convivencia y fecha de retiro.

## Cuando aplica / no aplica

- Aplica a API externas y contratos entre front/back.
- No aplica a interfaces internas no compartidas.

## Trade-offs

- Mantener versiones en paralelo aumenta costo de mantenimiento.
- Elimina migraciones forzadas y reduce riesgo de outage por cambios de contrato.

## Checklist de verificacion

- [ ] Se documento estrategia (URL/header/media type).
- [ ] Hay plan de deprecacion y comunicacion.
- [ ] Contratos versionados tienen tests de compatibilidad.
- [ ] Observabilidad separa trafico por version.

## Referencias

- `checks/delivery/release-gates.md`
