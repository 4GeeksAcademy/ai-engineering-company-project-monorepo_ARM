# Progress — Brasaland · Tablero de control del proyecto

> Fuente única: `CONTEXT.md` (Briefing de empresa · 4Geeks Academy · AI Engineering Track).
> Última actualización: 2026-10-26.

---

## Resumen ejecutivo

Brasaland es rentable y tiene clientes fieles en Colombia y Florida, pero opera con herramientas pensadas para un único local. El equipo interno **Brasaland Digital** (impulsado por la CEO Mariana Restrepo) debe construir la plataforma digital desde casi cero. **Hito actual completado:** la infraestructura base de agentes y la estructura del monorepo. **En curso:** definir arquitectura/stack y los primeros agentes concretos. **Siguiente fase:** empezar a construir las interfaces (`uis/`) y los servicios (`services/`) de la empresa.

---

## 1. ✅ Completado — Infraestructura base de agentes (hito actual)

| # | Entregable | Dónde | Detalle |
|---|-----------|-------|---------|
| 1 | Empresa asignada y cargada | `CONTEXT.md` | Briefing completo de **Brasaland** (14 locales, 2 países, ~115 empleados, ~6M USD/año). |
| 2 | Selección documentada | `company-choice.md` | Decisión de trabajar con Brasaland y retos/áreas prioritarias (RRHH, Operaciones, Marketing/CRM, API central). Idea inicial de agente: **"Tu asesor de Brasa"** (fidelización y pedidos). |
| 3 | Memory-bank inicializado | `memory-bank/` | `projectbrief.md`, `techContext.md` y este `progress.md` creados a partir de CONTEXT.md. |
| 4 | Directrices de operación para agentes de IA | `AGENTS.md` | Lectura obligatoria de contexto, flujo pre-commit de 4 pasos y zonas protegidas. |
| 5 | Estructura del monorepo | raíz | Carpetas top-level con README por capa: `uis/`, `services/`, `data/`, `agents/`, `skills/`, `mcps/`, `workflows/`, `packages/`, `shared/`, `docs/`, `infra/`, `scripts/`, `internal/`. |
| 6 | Plantilla base de agente | `agents/_template/` | Estructura estándar: `agent.py`, `tests/` y README (es/en) para crear agentes consistentes. |
| 7 | Catálogo base de skills | `skills/` | `_template/` (SKILL.md + ejemplos/recursos/scripts), `data-analysis/` (script `pandas_clean.py` + `common_metrics.md`), `research/` (ejemplos y templates), `code-review/` (esqueleto). |
| 8 | Tipos compartidos | `packages/shared/` | Paquete privado `@repo/shared-types` con base (`Id`, `BaseEntity`) listo para extender con tipos de dominio. |
| 9 | Esqueleto de datos | `data/` | Carpetas `raw/`, `pipelines/`, `process/`, `eval/` definidas (sin contenido todavía). |

---

## 2. 🚧 En curso

- [ ] **Definir arquitectura y stack tecnológico** de la plataforma (no declarados en el briefing) — decisión del CTO Nicolás Park y el equipo de Tecnología.
- [ ] **Definir el primer agente concreto** de Brasaland. Candidatos documentados en `company-choice.md`:
  - *"Tu asesor de Brasa"* (Marketing/Experiencia digital): recomienda platos según preferencias, historial de pedidos y puntos "Brasa Points".
  - Agente de RRHH (gestión de disponibilidad/ausencias) y/o agente de pedidos/operaciones (histórico centralizado de pedidos e inventario).
- [ ] **Completar plantillas en blanco:** `agents/_template/agent.py`, `skills/_template/SKILL.md` y el contenido de `skills/code-review/` (hoy solo esqueleto).
- [ ] **Diseñar el esquema de datos de dominio** en `@repo/shared-types` (Location, Menu, Sale, Customer, Supplier) como base de API y agentes.

---

## 3. 🔜 Próximos pasos lógicos — hacia interfaces (`uis/`) y servicios (`services/`)

> Orden de construcción propuesto para la siguiente fase, empezando por lo fundacional.

1. **API central FastAPI** en `services/api/` con routers por dominio (locales, menús, ventas, clientes, proveedores). Es la base de la que dependen dashboards, UIs y agentes. *(Recomendación del README del repo: un único backend central, sin microservicios prematuros.)*
2. **Pipeline de datos y telemetría** (`data/pipelines/`) que alimente los dashboards de operaciones, marketing y finanzas; captura de datos desde los 14 locales (COP y USD).
3. **Interfaz de operaciones** (`uis/backoffice/` o `uis/website/`): primer dashboard de ventas en tiempo real por local — primer vertical completo para demostrar valor rápido. *(Decisiones de moneda: COP y USD.)*
4. **Sistemas de dominio del backlog por área** (ver tabla siguiente), priorizados por solapamiento de datos (menús/ventas → marketing; ventas/stock → compras).
5. **UI de clientes** (app de fidelización/pedidos "Brasa Points" digital) y **asistente ejecutivo de IA** (dashboard de la CEO en lenguaje natural) una vez exista API y datos.
6. **Decidir idioma base** (es/en) de la plataforma de formación y planificar multiidioma.
7. **Documentar decisiones técnicas** (ADRs en `docs/`) y mantener este tablero actualizado tras cada hito.

---

## 📋 Backlog por área (requisitos de `CONTEXT.md` — pendientes)

> Todo esto es trabajo por construir; nada de la operación actual de Brasaland está todavía digitalizado.

**Pila fundacional (Tecnología / CTO):**
- [ ] API central (locales, menús, ventas, clientes, proveedores).
- [ ] Telemetría en tiempo real desde cada local.
- [ ] Pipeline de datos (operaciones, marketing, finanzas).

**Operaciones (Felipe Guerrero):**
- [ ] Dashboard de ventas en tiempo real por local (COP y USD).
- [ ] Sistema inteligente de pedidos de ingredientes (ventas históricas + stock actual).
- [ ] Alertas automáticas de local sin ventas en horario de apertura.

**Compras y Proveedores (Lucía Fernández):**
- [ ] Plataforma de gestión de proveedores (historial de precios y alertas).
- [ ] Visibilidad consolidada de compras a nivel de cadena.

**Marketing y Experiencia Digital (Camila Ospina):**
- [ ] App digital de fidelización y pedidos.
- [ ] CRM de clientes (historial y preferencias).
- [ ] Motor de personalización basado en comportamiento.

**Personas y Cultura (Ashley Turner):**
- [ ] Portal interno de RRHH (vacaciones y ausencias).
- [ ] Flujo automatizado de onboarding.
- [ ] Dashboard de KPIs de RRHH segmentado por país (rotación, absentismo, cobertura de vacantes).

**Formación y Calidad (Jake Morrison):**
- [ ] Plataforma de formación con catálogo de recetas buscable.
- [ ] Itinerario de incorporación estructurado.
- [ ] Distribución simultánea de actualizaciones de recetas a los 14 locales.
- [ ] Soporte multiidioma (es/en) — recomendado, empezando por un idioma base.

**Dirección Ejecutiva (Mariana Restrepo):**
- [ ] Dashboard ejecutivo con ventas totales de la cadena (USD y COP).
- [ ] Asistente de IA consultable en lenguaje natural.
- [ ] Informe semanal automatizado (lunes a las 7:00).

---

## ⚠️ Deuda técnica y riesgos conocidos

- Puntos de venta distintos por país sin integración: requieren estrategia de captura de datos en cada local.
- Datos históricos dispersos en hojas de cálculo y documentos no estructurados (limpieza/consolidación pendientes).
- Dos legislaciones laborales (RRHH) y dos mercados culturales (marketing) complican la estandarización.
- Equipo de Tecnología pequeño: el alcance (7 áreas, 2 países) debe dimensionarse de forma iterativa.
- Plantillas de agentes aún con archivos vacíos; el catálogo de agentes reales está por construir.