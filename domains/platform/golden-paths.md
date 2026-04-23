---
id: PLAT-GP-001
status: active
owner: platform
last_reviewed: 2026-04-23
tags: [platform, golden-paths, idp]
source_refs: [arquitecto-moderno/parte-vii-operacion-enterprise-y-ai-runtime/capitulo-23-platform-engineering-y-golden-paths]
---

# Golden Paths

## Contexto

Sin camino pavimentado, cada equipo inventa su pipeline y baja la consistencia global.

## Regla

Golden path minimo incluye:

- plantilla de servicio,
- CI/CD con gates,
- observabilidad por defecto,
- seguridad base automatizada,
- ownership explicito.

## Checklist de verificacion

- [ ] Existe template versionado.
- [ ] Scorecard impacta promotion a produccion.
- [ ] Excepciones tienen owner y fecha de expiracion.
