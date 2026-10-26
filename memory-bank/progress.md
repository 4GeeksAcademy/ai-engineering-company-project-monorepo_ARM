# Progress — Brasaland

> Fuente única de información: `CONTEXT.md` (Briefing de empresa · 4Geeks Academy · AI Engineering Track).
> Última actualización: 2026-10-26.

## Estado actual del desarrollo (basado en el briefing)

**Resumen ejecutivo:** Brasaland es rentable y tiene una base de clientes fiel en los dos mercados (Colombia y Florida), pero opera con herramientas diseñadas para un único restaurante local. El equipo interno **Brasaland Digital** (impulsado por la CEO Mariana Restrepo) acaba de ser creado con el mandato de construir la plataforma digital desde casi cero. El proyecto está en **fase 0 / inicio**: no existe todavía API, ni datos consolidados, ni telemetría, ni dashboards. Todo lo descrito a continuación son **requerimientos pendientes de construir**, no funcionalidades ya entregadas.

### Lo que ya existe (estado actual del sistema, NO proyectos completados)
- 14 restaurantes operando en 2 países con POS distintos sin integración.
- Web estática (2019) sin pedidos online; app obsoleta (2,8 en App Store).
- Fidelización "Brasa Points" en tarjetas físicas de sellos (≈60% de clientes no las usan; no generan datos).
- Procesos manuales: pedidos por WhatsApp/teléfono, informes en papel/Excel, RRHH y proveedores por email/Excel, formación en Google Drive sin estructura.
- Equipo interno Brasaland Digital creado; CTO Nicolás Park con mandato de construir la plataforma.

### Lo que el briefing ordena construir (backlog de trabajo — nada entregado aún)

**Pila fundacional (Tecnología / CTO):**
- [ ] API central de Brasaland (locales, menús, ventas, clientes, proveedores).
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
- [ ] Informe semanal automatizado (generado y enviado cada lunes a las 7:00).

## Problemas detectados que motivan el trabajo (por qué hacemos esto)
- Sin visibilidad en tiempo real de lo que ocurre en cada local; decisiones basadas en llamadas, PDFs semanales de los martes e intuición.
- Exceso de stock en unos locales y roturas en otros (pedidos sin datos de inventario).
- Sin conocimiento del cliente (marketing a ciegas) y fidelización sin datos.
- Competidores (incluidas cadenas más nuevas y pequeñas) ganando terreno con pedidos digitales, marketing data-driven y dashboards operativos.

## Siguientes pasos (próximas acciones recomendadas)
1. **Definir la arquitectura de la plataforma** y el stack tecnológico (no declarados en el briefing) — decisión de Nicolás Park y el equipo de Tecnología.
2. **Diseñar y construir la API central de Brasaland** como primer bloque fundacional (dominios: locales, menús, ventas, clientes, proveedores), ya que el resto de sistemas dependen de ella.
3. **Establecer el pipeline de datos y la telemetría** para alimentar los dashboards (es requisito transversal de operaciones, marketing y finanzas).
4. **Priorizar un primer vertical completo** (candidato natural: dashboard de ventas en tiempo real para Operaciones) para demostrar valor rápido a la cadena.
5. **Elegir el orden de los sistemas de dominio** según prioridad de negocio, considerando el solapamiento de datos (menús/ventas alimentan a marketing; ventas/stock alimentan a compras).
6. **Decidir el idioma base** de la plataforma de formación (español o inglés) y planificar el multiidioma.
7. **Documentar decisiones técnicas** a medida que se tomen para mantener actualizado este memory-bank (proyecto en fase inicial: estos ficheros se encuentran en construcción).

## Deuda técnica / riesgos conocidos
- Puntos de venta distintos por país sin integración: requieren estrategia de captura de datos en cada local.
- Datos históricos dispersos en hojas de cálculo y documentos no estructurados (limpieza y consolidación pendientes).
- Dos legislaciones laborales (RRHH) y dos mercados culturales (marketing) complican la estandarización.
- Equipo de Tecnología pequeño: el alcance (7 áreas, 2 países) debe dimensionarse de forma iterativa.