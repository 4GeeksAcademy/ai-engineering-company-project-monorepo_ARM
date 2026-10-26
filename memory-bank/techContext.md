# Tech Context — Brasaland

> Fuente única de información: `CONTEXT.md` (Briefing de empresa · 4Geeks Academy · AI Engineering Track).
> Última actualización: 2026-10-26.

## Stack tecnológico base (tal como está hoy)

El stack actual de Brasaland es mínimo y está fragmentado. No hay plataforma digital consolidada:

- **Web:** web estática (de 2019), sin pedidos online. Valoración de la app en la App Store: 2,8.
- **App móvil:** app desactualizada (obsoleta).
- **Puntos de venta (POS):** un terminal diferente en cada país, sin integración entre ellos.
- **Gestión de datos:** una colección de hojas de cálculo (Excel) que llevan años haciendo el trabajo de sistemas de gestión reales.
- **Procesos operativos:** pedidos de materia prima por WhatsApp o teléfono; informes de turno en papel o Excel enviados semanalmente a RRHH; negociación de proveedores por email y Excel; RRHH por email y Excel; materiales de formación en un Google Drive compartido.
- **Fidelización:** tarjetas físicas de sellos ("Brasa Points") sin generación de datos.
- **Conocimientos técnicos internos:** sin API interna, sin datos consolidados, sin telemetría, sin pipeline de datos.

## Decisiones arquitectónicas

### Decisión estratégica de negocio
- Mariana ha creado un equipo interno llamado **Brasaland Digital** cuyo mandato es construir las herramientas, los sistemas y las automatizaciones que permitan a Brasaland operar como una empresa moderna.
- El CTO **Nicolás Park** tiene el mandato de construir la **plataforma digital de Brasaland desde casi cero**.

### Componentes que el briefing ordena construir (por requerimiento funcional)
1. **API central de Brasaland** — dominio: locales, menús, ventas, clientes y proveedores. Es la base sobre la que se articulan el resto de sistemas.
2. **Telemetría en tiempo real** desde cada uno de los 14 locales.
3. **Pipeline de datos** que alimente los dashboards de operaciones, marketing y finanzas.
4. **Dashboards**: operativo de ventas por local en tiempo real (COP y USD), dashboard ejecutivo de la cadena (ventas totales en USD y COP), dashboard de KPIs de RRHH segmentado por país.
5. **Sistemas de dominio**: gestión de proveedores con historial de precios y alertas; CRM de clientes con historial/preferencias; motor de personalización; portal de RRHH; plataforma de formación con catálogo de recetas y distribución de actualizaciones; informe semanal automatizado.
6. **Asistente de IA** consultable en lenguaje natural (dashboard ejecutivo).

### Requisitos funcionales transversales que condicionan la arquitectura
- **Tiempo real:** visibilidad de ventas en tiempo real por local; alertas automáticas cuando un local no registra ventas en horario de apertura.
- **Multi-divisa:** operar en COP y USD; dashboards en ambas monedas.
- **Multi-idioma:** español e inglés (soporte multiidioma recomendado para la plataforma de formación, empezando por un idioma base).
- **Inteligencia de negocio / ML:** predicción de demanda de ingredientes basada en ventas históricas y stock actual; personalización de menú; agentes de soporte multilingüe; telemetría de ventas en tiempo real.

## Restricciones

- **Partida de cero:** no hay API interna, ni datos consolidados, ni telemetría, ni pipeline previo que reutilizar; la plataforma debe construirse desde casi cero.
- **Heterogeneidad heredada:** POS distintos por país sin integración, hojas de cálculo como "sistemas" y procesos manuales (WhatsApp, papel, email, Excel, Google Drive) que deben ser sustituidos o integrados.
- **Dos mercados, dos legislaciones:** cumplimiento operativo en Colombia y Florida (impacta sobre todo a RRHH) — los sistemas deben segmentar por país.
- **Dos monedas:** operaciones cotizadas en COP y USD; las cifras consolidadas deben poder expresarse en ambas.
- **Dos idiomas:** español (mercado principal, Colombia) e inglés (Florida); contenido de marca y formación en ambos.
- **Cultura de marca:** el alma del negocio (sabor consistente, servicio cálido, cocina rápida) no debe sacrificarse al digitalizar; los sistemas deben preservar la consistencia de la experiencia.
- **Escala limitada pero real:** 14 locales en 2 países, ~115 empleados, ~20 proveedores, ~6M USD/año — la arquitectura debe ser adecuada a esta escala (no sobredimensionada), pero preparada para crecer.
- **Equipo pequeño:** el equipo de Tecnología es pequeño; cualquier solución debe ser mantenible con recursos limitados.
- **Restricción de fuente documental:** este documento se basa exclusivamente en `CONTEXT.md`; no hay decisiones técnicas concretas de stack (lenguajes, frameworks, infraestructura) declaradas en el briefing salvo las descritas como estado actual.