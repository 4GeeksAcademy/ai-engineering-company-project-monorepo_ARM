# Regla: Ubicación del código de producto (frontend / backend)

> Directriz de gobernanza del monorepo · Complementa `AGENTS.md` y `memory-bank/techContext.md`.
> **Aplica a:** todo el desarrollo de producto (interfaces y servicios) del repo.

## Propósito

Garantizar que el código de producto de la empresa vive **siempre** en las carpetas estándar de la plantilla del monorepo, de modo que cualquier agente o persona sepa dónde colocar (y dónde buscar) cada pieza sin crear árboles paralelos.

## Regla

| Ruta | Qué va aquí cuando se cree |
|------|----------------------------|
| `uis/` | Todos los proyectos frontend de la empresa (interfaces de usuario). |
| `uis/website` | Web corporativa de cara al público (entrada en `/`); marca y copy alineados con `CONTEXT.md`. |
| `uis/backoffice` | App interna de la empresa (layout propio, separado de la web pública; vista de entrada en `/`). |
| `services/` | APIs y servicios backend. La API central de Brasaland se desarrolla aquí como `services/api/` (FastAPI). |

## Criterios de decisión (regla rápida)

- Si tiene **interfaz visual** → `uis/`.
- Si **expone una API** o **corre en segundo plano** → `services/`.
- Si **mueve o transforma datos** → `data/`.
- Si el trabajo lo hace un **modelo de IA** → `agents/` (+ `skills/` o `mcps/`).

## Prohibiciones

- **NO** crear un segundo árbol de frontend o de API en otra ubicación del repo (raíz, `packages/`, `shared/`, etc.) para código de producto.
- **NO** mezclar frontend y backend en la misma carpeta de producto: las UIs viven en `uis/`, los servicios en `services/`.

---

## Checklist rápido antes de commit

- [ ] ¿El frontend está bajo `uis/` (en `website` o `backoffice` según su público)?
- [ ] ¿La API/servicio está bajo `services/` (un subcarpeta por servicio)?
- [ ] ¿No hay código de producto duplicado en otra ruta del repo?
- [ ] ¿La web pública se alinea con `CONTEXT.md` (marca y copy) y el backoffice tiene layout propio?