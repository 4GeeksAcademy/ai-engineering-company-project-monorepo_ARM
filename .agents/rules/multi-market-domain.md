# Regla: Multi-mercado, divisas y datos de dominio (Brasaland)

> Directriz de gobernanza del monorepo · Complementa `AGENTS.md`.
> **Aplica a:** todo el código, agentes, servicios, UIs y documentación del repo.

## Propósito

Brasaland opera en **dos países**, **dos monedas (COP y USD)** y **dos idiomas (es/en)**. Cualquier feature, agente, servicio o interfaz que se desarrolle debe respetar estas restricciones para no romper la consistencia de la marca y del dominio.

## 1. Divisas explícitas (COP / USD)

- Toda representación de dinero **DEBE** especificar su moneda: `COP` o `USD`. Nunca almacenes, muestres ni devuelvas por API una cantidad sin moneda.
- Utiliza un tipo estructurado (p. ej. `{ amount, currency }`) o tipos de dominio en `@repo/shared-types` en lugar de `float`/`number` a secas.
- Los dashboards o agregados a nivel de cadena **DEBEN** poder expresarse en ambas monedas y documentar el tipo de cambio aplicado (y su fecha).

## 2. Idioma y mercado

- Contenido dirigido a clientes de Colombia → **español**.
- Contenido dirigido a clientes de Florida (EE. UU.) → **inglés**.
- Contenido interno (READMEs, memoria) puede ser monolingüe, pero debe marcarse el idioma y ser consistente dentro de un mismo artefacto (no mezclar es/en en un mismo documento).
- Los datos que dependan de mercado (impuestos, legislación laboral, formato de fecha/dirección) deben parametrizarse por país, nunca hardcodearse.

## 3. Datos de dominio: no inventar

- Cualquier cifra del negocio (ventas, número de locales, empleados, proveedores, precios, métricas) **DEBE** proceder de `CONTEXT.md` o de una fuente documentada en el repo.
- Queda **prohibido inventar** estadísticas de la empresa en código, prompts, respuestas de agentes o documentación.
- Si se necesita un valor de ejemplo, márcalo explícitamente como `SAMPLE`/`EJEMPLO` y preferiblemente en `data/` o fixtures, nunca como dato real.

## 4. Consistencia de marca

- La propuesta de valor (mismo sabor, servicio cálido, cocina rápida) no debe degradarse al digitalizar.
- Los textos y flujos de cara al cliente deben mantener el tono cálido y consistente de la marca en ambos mercados.

---

## Checklist rápido antes de commit

- [ ] ¿Cada importe tiene moneda explícita (COP/USD)?
- [ ] ¿El contenido tiene el idioma correcto para su mercado?
- [ ] ¿Los datos citados provienen de `CONTEXT.md` o fuente documentada (sin inventos)?
- [ ] ¿La lógica dependiente de país está parametrizada, no hardcodeada?