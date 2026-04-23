# Tenant Isolation Upgrade Flow

Playbook para migrar tenants entre niveles de aislamiento (pool -> schema -> database) con riesgo controlado.

## Objetivo

Permitir upgrades de aislamiento por compliance, performance o contrato enterprise sin downtime critico.

## Criterios de elegibilidad

- Requerimiento regulatorio/documental del cliente.
- Saturacion de performance en modelo actual.
- Riesgo de seguridad por densidad compartida.

## Fase 1: Planificacion

1. Registrar motivo y alcance del upgrade por tenant.
2. Confirmar topologia destino y prerequisitos de infraestructura.
3. Definir ventana de migracion y plan de comunicacion.
4. Preparar plan de rollback al modelo origen.

## Fase 2: Preparacion tecnica

1. Provisionar destino (schema o DB dedicada).
2. Sincronizar schema/migraciones y politicas de seguridad.
3. Validar tenant context y routing rules.
4. Preparar verificacion de integridad de datos.

## Fase 3: Migracion controlada

1. Congelar escrituras no criticas del tenant.
2. Ejecutar copia/sync incremental de datos.
3. Ejecutar checks de consistencia y conteo.
4. Switch de routing a destino.

## Fase 4: Validacion y estabilizacion

1. Validar operaciones core del tenant en destino.
2. Monitorear latencia/error rate por tenant.
3. Confirmar no acceso cross-tenant post-migracion.
4. Cerrar ventana y confirmar exito con stakeholders.

## Checklist minima

- [ ] Backup y rollback probados.
- [ ] Routing por tenant validado en canary.
- [ ] Consistency checks aprobados.
- [ ] Security checks post-cutover en verde.
- [ ] Evidencia de cierre registrada.
