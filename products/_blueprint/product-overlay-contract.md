# Product Overlay Contract

Define como un producto consume el core global sin duplicar doctrina.

## Archivos requeridos por producto

- `context.md`
- `local-overrides.md`
- `local-adrs/`

## Reglas

- No copiar principios globales.
- Solo declarar deltas o constraints locales.
- Toda excepcion local requiere ADR local.
- Toda excepcion local debe incluir fecha de expiracion.
