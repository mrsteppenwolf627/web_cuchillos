# CONTEXT · Web de cuchillos

Contexto estable del proyecto. Las decisiones con fecha y motivo están en `DECISIONS.md`; el plan y su estado, en `FASES.md`.

## Visión
Web de cuchillos para generar ingresos pasivos: catálogo/directorio con una ficha de producto por cuchillo y un blog (técnicas, afilado, información). Máximo SEO técnico y on-page en cada ficha, posicionamiento SEO/GEO y navegación muy cuidada.

## Alcance
- Dentro: catálogo de fichas clasificadas (tipo, uso, otros criterios por definir en Fase 1), blog, monetización por afiliación y vías complementarias.
- Mercado: España, castellano. Expansión solo según resultados.
- Crecimiento por oleadas: núcleo reducido de categorías y cuchillos, luego ampliación.
- Fuera de alcance en Fase 0: código de producto, dominio, contenido.
- Pendiente de definir: taxonomía del catálogo (Fase 1) y fases posteriores a la 0 (chat de planificación).

## Stack
Next.js + Supabase + Vercel Hobby. Desarrollo ejecutado con Claude Code. Gestor de paquetes: npm. Node 24 (`.nvmrc`).

## Monetización
Varias vías a la vez. Principal: afiliación desde las fichas. El resto, como complemento. Los enlaces de afiliación llevan siempre aviso de afiliación visible.

## Restricciones
- Tiempo: 8-10 h/semana.
- Inversión inicial: solo dominio; el resto con free tiers.
- Hito orientativo: primeros ingresos en ~3 meses. El posicionamiento es de largo plazo.
- Repositorio público: nada de secretos, datos con licencia dudosa ni borradores sensibles.

## Contenido y datos
- Contenido generado con IA bajo supervisión y criterio del autor.
- Fichas y artículos: originales y diferenciados, nunca copia de descripciones de fabricante, apoyados en datos verificables. Si un dato no es verificable, se indica.
- Datos: se acepta scraping de fuentes públicas/legales. Al ser el repo público, los datos de origen con licencia dudosa no se versionan.

## Supuestos
- La afiliación desde fichas puede producir ingresos en ~3 meses (orientativo, sin validar).
- Los free tiers de Vercel Hobby y Supabase bastan para el volumen inicial.

## Riesgos conocidos
1. Vercel Hobby: sus términos limitan el uso comercial; una web con afiliación podría quedar fuera de plan.
2. Supabase free se pausa por inactividad (gestionado por el autor).
3. Copia de la base de datos fuera de GitHub: pendiente de resolver.
4. Penalización de buscadores por contenido masivo generado con IA.
5. Competencia alta en afiliación de producto.
6. Repositorio público: cualquier fuga es visible; mitigado con secret scanning y push protection activados.
