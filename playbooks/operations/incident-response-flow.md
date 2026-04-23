# Incident Response Flow

Playbook base para incidentes operativos de plataforma y producto.

## Scope

- Incidentes de disponibilidad
- Incidentes de degradacion severa
- Incidentes de seguridad
- Incidentes de integracion critica

## Fase 1: Deteccion y triage (0-15 min)

1. Confirmar alerta y reproducibilidad.
2. Asignar incident commander (IC).
3. Clasificar severidad (Sev-1/2/3).
4. Abrir canal de incidente y registrar timeline.

## Fase 2: Contencion (15-60 min)

1. Activar mitigacion inmediata (rollback, feature flag, rate limit).
2. Aislar sistema o feature afectada.
3. Preservar evidencia tecnica (logs, traces, metrics, deploy hash).
4. Comunicar estado interno cada 15 minutos para Sev-1.

## Fase 3: Recuperacion (1-4 h)

1. Implementar fix temporal o definitivo.
2. Validar salud tecnica (SLO, error rate, latencia, colas).
3. Restaurar trafico gradualmente.
4. Confirmar salida de incidente con stakeholders.

## Fase 4: Post-incident (24-72 h)

1. Generar postmortem sin culpables.
2. Identificar causa raiz y factores contribuyentes.
3. Definir acciones correctivas con owner y fecha.
4. Actualizar playbooks/checklists/ADRs si aplica.

## Roles minimos

- Incident commander: coordina decisiones.
- Scribe: mantiene timeline y evidencia.
- Tech lead de dominio: ejecuta mitigaciones.
- Comunicacion: actualiza stakeholders/clientes.

## Evidencia obligatoria

- `incident_id`
- severidad y alcance
- servicios/tenants impactados
- tiempo de deteccion y recuperacion
- causa raiz preliminar/final
- acciones preventivas
