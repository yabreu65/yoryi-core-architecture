---
id: FE-ARCH-BOUND-001
status: active
owner: frontend-architecture
last_reviewed: 2026-04-23
tags: [frontend, architecture, boundaries]
source_refs: [operational-original]
---

# Frontend Boundaries

## Contexto

Sin limites claros en frontend, la UI termina mezclando logica de dominio, integracion y estado global, haciendo el sistema dificil de evolucionar.

## Regla

- Separar capas de `presentation`, `application`, `infrastructure` y `shared`.
- La capa de presentacion no hace llamadas HTTP directas ni accede a storage sensible.
- Las decisiones de dominio viven en casos de uso/adapters, no en componentes UI.
- El BFF/API contract es la frontera externa oficial del frontend.

## Cuando aplica / no aplica

- Aplica a aplicaciones frontend enterprise con multiples features y equipos.
- No aplica a prototipos throwaway de baja vida util.

## Trade-offs

- Mas estructura inicial y convenciones estrictas.
- Menor acoplamiento entre vistas, mejor testabilidad y mayor velocidad de cambio sostenida.

## Checklist de verificacion

- [ ] Componentes UI sin side effects de infraestructura.
- [ ] Casos de uso frontend separados de la vista.
- [ ] Contratos de integracion tipados y versionados.
- [ ] Modulos por feature sin dependencias circulares.
- [ ] Reglas de carpeta respetadas por PR.

## Errores comunes

- Componentes "smart" que concentran rendering, reglas de negocio y networking.
- Helpers globales que violan ownership de modulo.
- Compartir estado mutable entre features sin frontera.

## Referencias

- `domains/backend/nestjs/module-boundaries.md`
- `checks/architecture/module-review-checklist.md`
- `checks/delivery/pr-architecture-checklist.md`
