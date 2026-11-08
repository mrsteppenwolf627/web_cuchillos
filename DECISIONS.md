# DECISIONS · Registro de decisiones

Formato: ID · fecha · decisión · motivo. Las decisiones D-001 a D-008 estaban tomadas en planificación antes de F0.2 y se cargan aquí con fecha de registro; cuando el motivo no quedó documentado, se indica. Una decisión nueva se añade al final; una revocada no se borra: se marca como sustituida.

| ID | Fecha | Decisión | Motivo |
|---|---|---|---|
| D-001 | 2026-11-08 (registro) | Proyecto = catálogo/directorio de cuchillos (fichas de producto) + blog. Taxonomía del catálogo se define en la Fase 1. | Modelo de ingresos pasivos por afiliación desde fichas, con SEO/GEO. |
| D-002 | 2026-11-08 (registro) | Mercado: España, castellano. Expansión solo según resultados. | Foco inicial; motivo detallado no registrado. |
| D-003 | 2026-11-08 (registro) | Crecimiento por oleadas: núcleo reducido de categorías y cuchillos, luego ampliación. | Limitar alcance inicial y validar antes de ampliar (recursos de 8-10 h/semana). |
| D-004 | 2026-11-08 (registro) | Monetización: varias vías a la vez; principal = afiliación desde fichas. Hito orientativo: primeros ingresos en ~3 meses. | Objetivo de ingresos pasivos; el hito es orientativo, no un compromiso. |
| D-005 | 2026-11-08 (registro) | Stack: Next.js + Supabase + Vercel Hobby; desarrollo con Claude Code. | Inversión inicial limitada a dominio, resto en free tiers. |
| D-006 | 2026-11-08 (registro) | Contenido generado con IA bajo supervisión y criterio del autor. | Capacidad de producción con 8-10 h/semana. Riesgo asociado: penalización por contenido masivo por IA. |
| D-007 | 2026-11-08 (registro) | Datos: se acepta scraping de fuentes públicas/legales. | Motivo detallado no registrado. |
| D-008 | 2026-11-08 (registro) | Método: 1 chat = 1 tarea, con chat de planificación aparte. Toda tarea termina con actualización de FASES.md, commit y push. | Evitar hilos largos y mantener FASES.md como fuente de verdad. |
| D-009 | 2026-11-08 | Repositorio PÚBLICO en GitHub (antes: privado). Sustituye la decisión inicial de repo privado. | Orden expresa del autor: facilita el trabajo; secret scanning no existe en repos privados del plan actual. Consecuencia: todo lo subido es visible. |
| D-010 | 2026-11-08 | Node 24 fijado en `.nvmrc`; gestor de paquetes: npm (pnpm/yarn no instalados). | Node 24 coincide con el instalado en el equipo del autor (v24.12.0). |
| D-011 | 2026-11-08 | Secret scanning y push protection activados en GitHub. | Mitigar el riesgo de fuga de secretos en repo público. |
| D-012 | 2026-11-08 | Se asume el riesgo R-01 (Vercel Hobby y uso comercial): se mantiene Hobby y, si hace falta, el autor pasará al plan Pro (20 USD según el autor, sin verificar). | Orden expresa del autor; evita coste inicial. Los términos de uso comercial siguen sin comprobarse. |
| D-013 | 2026-11-08 | Categorías base del catálogo: cuchillos de cocina, navajas, outdoor, caza, EDC y japoneses, más piedras de afilar y accesorios. Ampliación por oleadas. | Decisión del autor; visión de catálogo amplio con crecimiento progresivo. |
| D-014 | 2026-11-08 | Primera oleada: solo cuchillos de cocina. | Decisión del autor; acotar alcance inicial (8-10 h/semana). |
| D-015 | 2026-11-08 | Criterios de clasificación: tipo, uso, acero, origen, precio, marca y nivel de usuario. | Decisión del autor. Qué criterios son categorías indexables y cuáles filtros se define en F1.4. |
| D-016 | 2026-11-08 | Las fichas de la oleada 1 salen de los 10 cuchillos de cocina más populares encontrados online, con KW research y matrices de KW. Datos solo de elaboración propia en el repo público. | Decisión del autor; ancla el catálogo en demanda real. Riesgos: R-07, R-04. |
| D-017 | 2026-11-08 | Ficha = técnica objetiva + reseña con veredicto/puntuación; habrá rankings y comparativas. Sin afirmar pruebas no realizadas. | Decisión del autor (ambas). La transparencia sobre la base de cada reseña la fija esta fase por falta de colección propia. |
| D-018 | 2026-11-08 | Herramientas solo gratuitas + Claude in Chrome. Dominio .com preferido, sin elegir ni comprar hasta tener una web mínima. Afiliación (cuentas y programas) aplazada a fases posteriores. | Decisión del autor; coste inicial limitado a dominio, que se retrasa. |
| D-019 | 2026-11-08 | En F1.2 se lee Amazon.es (rankings de más vendidos) a mano y de forma puntual con Claude in Chrome, asumiendo el riesgo R-10. En el repo solo se guardan posiciones, recuentos de reseñas y bandas de precio. | El autor indicó en el chat que se usara Claude in Chrome tras exponerle que las condiciones vigentes de Amazon.es (versión 2025-11-28) limitan el uso a fines no comerciales y prohíben compilar listas de productos y precios. Sin asesoramiento jurídico. Alternativa descartada: excluir Amazon.es y revisar la ponderación del método. |

