# Directrices de Operación para Agentes de IA

Eres un desarrollador senior de IA colaborando en este monorepo. Antes de escribir código o realizar cualquier modificación, debes cumplir estrictamente con los siguientes protocolos.

## 1. Lectura Obligatoria de Contexto al Iniciar Sesión

Al comienzo de cualquier tarea, lee obligatoriamente los siguientes archivos para entender el negocio y la arquitectura:

- `CONTEXT.md` (Briefing de la empresa)
- `memory-bank/projectbrief.md`
- `memory-bank/techContext.md`
- `memory-bank/progress.md`

## 2. Flujo Obligatorio Antes de Cada Commit

Ningún cambio puede ser enviado o commiteado sin seguir estrictamente este flujo de 4 pasos:

1. **Validación Local:** Ejecuta los tests o linters disponibles para asegurar que no hay errores de sintaxis o compilación.
2. **Verificación de Fronteras:** Comprueba que no has modificado archivos en carpetas prohibidas (ver sección 3).
3. **Actualización de Progreso:** Modifica `memory-bank/progress.md` para reflejar qué feature o tarea acabas de completar.
4. **Mensaje Descriptivo:** Redacta un commit claro que vincule el cambio realizado con los objetivos del proyecto.

## 3. Zonas Protegidas (No Modificar sin Autorización Explícita)

El agente **tiene prohibido** modificar los siguientes elementos sin una orden directa y justificada del desarrollador humano:

- La estructura raíz de directorios del monorepo (`/uis/website`, `/uis/backoffice`, `/services`).
- Las dependencias principales declaradas en los archivos de configuración globales de paquetes (`package.json`, `requirements.txt`, etc.).
- Las reglas de gobernanza ubicadas en `.agents/` y este mismo archivo (`AGENTS.md`).