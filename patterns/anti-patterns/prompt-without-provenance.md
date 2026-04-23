# Anti-pattern: Prompt Without Provenance

## Smell

Respuesta AI sin referencias de fuentes recuperadas.

## Impact

Sin trazabilidad no hay auditoria ni debugging confiable.

## Guardrail

Toda respuesta debe incluir ids de documentos/chunks y tenant scope.
