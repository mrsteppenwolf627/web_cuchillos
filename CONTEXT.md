# CONTEXT · Web de cuchillos

Contexto estable del proyecto. Las decisiones con fecha y motivo están en `DECISIONS.md`; el plan y su estado, en `FASES.md`; el registro de riesgos con mitigaciones, en `docs/PROCESO.md` (apartado 6).

Última actualización: 2026-11-08 (cierre de la Fase 0)

## Visión
Web de cuchillos para generar ingresos pasivos: catálogo/directorio con una ficha de producto por cuchillo y un blog (técnicas, afilado, información). Máximo SEO técnico y on-page en cada ficha, posicionamiento SEO/GEO y navegación muy cuidada.

## Estado actual
- Fase 0 (estructura del proyecto): HECHA el 2026-11-08, con R-09 abierto y asumido.
- Fase 1 y siguientes: sin definir; se definen una a una en el chat de planificación.
- No hay todavía aplicación, dominio ni contenido.

## Alcance
- Dentro: catálogo de fichas clasificadas (tipo, uso, otros criterios por definir en Fase 1), blog, monetización por afiliación y vías complementarias.
- Mercado: España, castellano. Expansión solo según resultados.
- Crecimiento por oleadas: núcleo reducido de categorías y cuchillos, luego ampliación.
- Pendiente de definir: taxonomía del catálogo y fases posteriores a la 0.

## Stack e infraestructura
- Next.js + Supabase + Vercel Hobby. Desarrollo ejecutado con Claude Code.
- Node 24 (`.nvmrc`), npm (pnpm y yarn no se usan).
- Repositorio: GitHub `mrsteppenwolf627/web_cuchillos`, PÚBLICO (D-009), rama `main`. Secret scanning y push protection activos (D-011).
- Vercel: proyecto `web_cuchillos` (plan Hobby) conectado a `main`; despliegue sin aplicación todavía.
- Supabase: proyecto `web_cuchillos` (plan Free, eu-central-1).
- Dominio, Search Console, analítica y programas de afiliación: sin crear (ver `docs/ACCESOS.md`).

## Estrategia SEO
Cola larga + SEO programático sobre todo el catálogo (D-020). Hubs de categoría y de tipo en versión mínima, producidos después de las primeras fichas y rankings. Control de calidad: cada página programática exige unicidad mínima; las que no la cumplan no se indexan (R-11).

## Monetización
Varias vías a la vez. Principal: afiliación desde las fichas. El resto, como complemento. Los enlaces de afiliación llevan siempre aviso de afiliación visible.

## Restricciones
- Tiempo: 8-10 h/semana.
- Inversión inicial: solo dominio; el resto con free tiers.
- Hito orientativo: primeros ingresos en ~3 meses. El posicionamiento es de largo plazo.
- Repositorio público: nada de secretos, datos con licencia dudosa ni borradores sensibles.
- Supabase Free: en la organización hay otro proyecto activo (`kakebo-ahorro`) además de `web_cuchillos`. Si el límite del plan es de 2 proyectos activos (a verificar en la documentación vigente), no se puede activar un tercero sin pausar uno.

## Contenido y datos
- Contenido generado con IA bajo supervisión y criterio del autor.
- Fichas y artículos: originales y diferenciados, nunca copia de descripciones de fabricante, apoyados en datos verificables. Si un dato no es verificable, se indica.
- Datos: se acepta scraping de fuentes públicas/legales. Al ser el repo público, los datos de origen con licencia dudosa no se versionan (`data/raw/` y `data/dumps/` ignorados por git).

## Supuestos
- La afiliación desde fichas puede producir ingresos en ~3 meses (orientativo, sin validar).
- Los free tiers de Vercel Hobby y Supabase bastan para el volumen inicial.
- Vercel Hobby es utilizable para este proyecto (D-012): asumido por el autor; términos de uso comercial y precio del plan Pro sin comprobar.

## Riesgos conocidos
Resumen; detalle y mitigaciones en `docs/PROCESO.md`.
- R-01 Vercel Hobby y uso comercial (asumido, D-012).
- R-02 Pausa de Supabase free por inactividad (gestionado por el autor).
- R-03 Sin copia de la base de datos fuera de GitHub (abierto).
- R-04 Penalización de buscadores por contenido masivo generado con IA (abierto).
- R-05 Competencia alta en afiliación de producto (asumido).
- R-06 Fuga de secretos o datos por repositorio público (mitigado con D-011).
- R-07 Scraping de fuentes con licencia o términos problemáticos (abierto).
- R-08 El hito de ingresos a ~3 meses puede no cumplirse (asumido).
- R-09 Supabase con 2FA de un único autenticador y sin códigos de recuperación (asumido, respaldo pendiente).
