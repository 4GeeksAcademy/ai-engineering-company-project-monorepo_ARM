---
name: memory-bank-update
description: Mantener `memory-bank/progress.md` como tablero de control del proyecto
  tras completar una feature, tarea o hito. Usar SIEMPRE después de hacer cambios
  en el repo y antes del commit (paso 3 del flujo de AGENTS.md).
---

# Memory bank update

## Objetivo

Mantener `memory-bank/progress.md` como fuente única y **siempre actualizada** del estado del proyecto, reflejando cada feature, tarea o hito completado **antes de cada commit**, de modo que las secciones "✅ Completado / 🚧 En curso / 🔜 Próximos pasos" describan con veracidad el estado real en todo momento.

## Cuándo usar
- Tras completar una feature o tarea de "En curso" o del backlog.
- Antes de cada commit que toque código, docs o gobernanza del repo.
- Al cerrar o mover ítems entre "Completado / En curso / Próximos pasos".

## Inputs

- **Cambios a registrar:** `diff` o lista de features/archivos/commits del trabajo completado.
- **Tablero actual:** ruta `memory-bank/progress.md` con su estado presente.
- **Regla de dominio aplicable:** `.agents/rules/multi-market-domain.md` (checklist COP/USD, es/en, sin datos inventados).
- **Contexto de empresa:** `CONTEXT.md` (referencia para validar que ninguna cifra del negocio se inventa o contradice).

## Procedimiento

1. **Lee** el `memory-bank/progress.md` actual y el diff de lo completado.
2. **Mueve** el ítem culminado a la sección "✅ Completado" (añade fila en la tabla).
3. **Reordena** "🚧 En curso" y "🔜 Próximos pasos" según el nuevo estado.
4. **Actualiza** el resumen ejecutivo y la fecha de "Última actualización".
5. **Verifica** el checklist de la regla multi-mercado (`.agents/rules/multi-market-domain.md`).

## Criterios de aceptación verificables

- [ ] `memory-bank/progress.md` existe y su título es `# Progress — Brasaland · Tablero de control del proyecto`.
- [ ] Todo lo completado en el diff aparece en "✅ Completado" con la columna `Dónde` apuntando a una ruta real del repo.
- [ ] Nada completado permanece marcado como pendiente en "🚧 En curso" o en el backlog.
- [ ] La fecha de "Última actualización" es la de hoy y el resumen ejecutivo refleja el estado tras el cambio.
- [ ] Ninguna cifra del negocio del tablero contradice `CONTEXT.md` (regla multi-mercado: COP/USD, es/en, sin inventos).
- [ ] El fichero es Markdown válido y el `git diff` del fichero contiene solo los bloques esperados.