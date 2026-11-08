# FASES.md · Web de cuchillos (catálogo + blog)

> Documento maestro del proyecto ("la biblia"). Se actualiza al cerrar cada tarea.
> Método: 1 chat = 1 tarea. El chat de planificación es independiente.
> REGLA OBLIGATORIA: toda tarea termina con actualización de este archivo, commit y push a GitHub.

Última actualización: 2026-11-08 (F1.1 y F1.2 hechas; Fase 1 en curso, 2 de 7 tareas; R-09 y R-10 abiertos)

## Estado global

| Fase | Nombre | Estado |
|---|---|---|
| 0 | Estructura del proyecto | HECHO 2026-11-08 (F0.1, F0.2 y F0.3 hechas; R-09 abierto, asumido) |
| 1 | Estrategia y fundamentos | EN CURSO (F1.1 y F1.2 hechas 2026-11-08; 2 de 7) |
| 2+ | Por definir (una a una, en el chat de planificación) | — |

---

# FASE 0 · Estructura del proyecto
Estado: HECHO (2026-11-08) · Duración estimada: 3-4 h · Chats: 3

## Objetivo
Dejar operativo el marco de trabajo: repositorio privado sincronizado, documentación base,
proceso chat=tarea y entorno local verificado. Sin código de producto, sin dominio, sin contenido.

## Decisiones congeladas (contexto para todos los chats)
- Proyecto: web de cuchillos = catálogo/directorio de cuchillos (fichas de producto) + blog.
- Taxonomía del catálogo (tipo, uso, otros criterios): se define en la Fase 1.
- Mercado: España, castellano. Expansión según resultados.
- Crecimiento por oleadas: núcleo reducido de categorías/cuchillos, luego ampliación.
- Monetización: varias vías a la vez; principal = afiliación desde fichas; resto como complemento.
- Hito: primeros ingresos en ~3 meses (orientativo). Posicionamiento = largo plazo.
- Stack: Next.js + Supabase + Vercel Hobby. Desarrollo con Claude Code.
- Contenido: generado con IA, con supervisión y criterio del autor.
- Datos: se acepta scraping de fuentes públicas/legales.
- Recursos: 8-10 h/semana; inversión inicial solo dominio; resto free tiers.
- Método: 1 chat = 1 tarea. Chat de planificación aparte.
- REGLA OBLIGATORIA: toda tarea termina con actualización de FASES.md, commit y push a GitHub.
- Riesgos asumidos/conocidos: Vercel Hobby (términos de uso comercial), pausa de Supabase free
  (gestionada por el autor), copia de la BD fuera de GitHub (pendiente), contenido masivo por IA.

## F0.1 · Repositorio y entorno local
Estado: HECHO (2026-11-08)
Progreso 2026-11-08:
- [x] Paso 2: git init, rama main.
- [x] Paso 3: .gitignore.
- [x] Paso 4: .env.example vacío.
- [x] Paso 5: .nvmrc = 24. Basado en el Node que reporta la app de escritorio de Claude (v24.22.0), que no es necesariamente el Node instalado en el sistema del autor: confirmar con `node -v`.
- [x] Paso 6: repo https://github.com/mrsteppenwolf627/web_cuchillos creado, remoto origin añadido, historial subido a main. CAMBIO DE DECISIÓN 2026-11-08: el repo pasó de PRIVADO a PÚBLICO por orden expresa del autor (facilita el trabajo; secret scanning no existe en repos privados del plan actual). Consecuencia: todo lo que se suba es visible; nada de secretos, datos con licencia dudosa ni borradores sensibles.
- [x] Paso 1: verificado en el equipo Windows del autor el 2026-11-08: git 2.52.0.windows.1; gh 2.103.3 (instalado manualmente en C:\Program Files\GitHub CLI\, autenticado en github.com como mrsteppenwolf627, protocolo https); Node v24.12.0 (coincide con .nvmrc = 24); npm 11.8.0; pnpm/yarn no instalados (se usa npm); remoto origin, `git status` limpio y sincronizado con origin/main, user.name y user.email configurados.
- [x] Paso 7: Secret Protection (secret scanning alerts) y Push protection activados el 2026-11-08 en Settings > Advanced Security; verificado en la interfaz (Push protection = On).
Entradas: carpeta local "web cuchillos", cuenta GitHub, Claude Code abierto.
Pasos:
1. Verificar herramientas: git, GitHub CLI (gh) autenticado, Node (LTS) y gestor de paquetes.
2. git init en la carpeta; rama principal = main.
3. Crear .gitignore (node_modules, .env*, .next, builds, datos pesados, archivos del sistema).
4. Crear .env.example vacío de valores.
5. Fijar versión de Node (.nvmrc).
6. Crear repo PRIVADO en GitHub, añadir remoto, primer commit y push.
7. Activar en GitHub: secret scanning y push protection.
Salida: repo privado sincronizado con primer commit en main.
Cierre: git status limpio, push verificado en GitHub, FASES.md actualizado.

## F0.2 · Documentación base
Estado: HECHO (2026-11-08)
Progreso 2026-11-08:
- [x] Paso 1: README.md.
- [x] Paso 2: CONTEXT.md.
- [x] Paso 3: FASES.md (existente; actualizado).
- [x] Paso 4: DECISIONS.md (D-001 a D-011; D-009 registra el cambio de repo privado a público).
- [x] Paso 5: CLAUDE.md.
- [x] Paso 6: docs/, content/, data/, src/ con .gitkeep.
- Revisión cruzada: README, CONTEXT, DECISIONS y CLAUDE.md coherentes entre sí y con FASES.md (repo público, Node 24, npm, stack, regla de cierre). Nota: los pasos históricos de F0.1 siguen diciendo "PRIVADO"; superados por D-009.
Entradas: bloque "Decisiones congeladas".
Pasos:
1. README.md (qué es, cómo arrancar en local).
2. CONTEXT.md (visión, alcance, decisiones, stack, restricciones, supuestos, riesgos).
3. FASES.md (esta biblia: fases, tareas, estado, criterios de cierre).
4. DECISIONS.md (registro de decisiones con fecha y motivo; cargar las ya tomadas).
5. CLAUDE.md (reglas para Claude Code: convenciones, commit+push obligatorio al cerrar
   tarea, no ejecutar acciones destructivas sin confirmar, no ampliar alcance).
6. Estructura mínima de carpetas: docs/, content/, data/, src/ (vacías con .gitkeep).
Salida: documentos coherentes entre sí en la raíz del repo.
Cierre: revisión cruzada de coherencia, commit, push.

## F0.3 · Proceso de trabajo y accesos
Estado: HECHO (2026-11-08), con R-09 abierto
Progreso 2026-11-08:
- [x] Paso 1: plantilla de tarea en docs/PROCESO.md (apartado 1).
- [x] Paso 2: definición de "hecho" (apartado 2) y convención de nombres de chat (apartado 4).
- [x] Paso 3: convención de commits (apartado 5).
- [x] Paso 4: inventario creado en docs/ACCESOS.md. Verificados GitHub, Vercel (proyecto web_cuchillos, Hobby) y Supabase (proyecto web_cuchillos, Free, eu-central-1). 2FA confirmado por el autor el 2026-11-08 en GitHub y Vercel (códigos de recuperación) y Supabase (Google Authenticator). Pendiente del autor: confirmar gestor de contraseñas en las tres cuentas, mover los códigos de recuperación fuera de la carpeta del proyecto (hoy solo los protege `.gitignore`) y crear respaldo del 2FA de Supabase (R-09, asumido sin respaldo por ahora). Registrador, Search Console, analítica y afiliación: NO CREADOS (dependen de dominio y de herramientas sin elegir).
- Plantilla de tarea validada por el autor el 2026-11-08.
- [x] Paso 5: registro de riesgos inicial (R-01 a R-08) en docs/PROCESO.md (apartado 6). Probabilidad e impacto son estimaciones de criterio, no medidas.
- R-01 asumido por el autor (D-012). Sigue sin comprobarse los términos vigentes de Vercel Hobby ni el precio del plan Pro.
Entradas: documentos de F0.2.
Pasos:
1. Plantilla de tarea (objetivo, entradas, salida, criterio de cierre) en docs/.
2. Definición de "hecho" y convención de nombres de chat (ej.: "F2.3 · Plantilla de ficha").
3. Convención de commits (feat, fix, docs, content, data, chore).
4. Inventario de cuentas y accesos (sin contraseñas): GitHub, Vercel, Supabase, registrador,
   Search Console, analítica, afiliación; 2FA y gestor de contraseñas confirmados.
5. Registro de riesgos inicial.
Salida: docs/PROCESO.md y docs/ACCESOS.md.
Cierre: FASES.md con Fase 0 en HECHO, commit, push.

## Criterios de cierre de la Fase 0
- [x] Repo sincronizado (público por D-009), primer commit en main
- [x] README, CONTEXT, FASES, DECISIONS, CLAUDE.md creados y coherentes
- [x] Plantilla de tarea validada (docs/PROCESO.md; validada por el autor el 2026-11-08)
- [x] Entorno local verificado
- [x] Push de cierre realizado según la regla obligatoria
- [x] ACCESOS.md con 2FA y gestor de contraseñas confirmados por el autor (declarado por el autor el 2026-11-08; no verificable desde el repositorio)

## Pendiente heredado de la Fase 0
- R-09: 2FA de Supabase con un único autenticador y sin respaldo (asumido por el autor; ver docs/PROCESO.md).
- 2FA y gestor de contraseñas en los servicios futuros (registrador, Search Console, analítica, afiliación) cuando se creen.


---

# FASE 1 · Estrategia y fundamentos
Estado: EN CURSO (2 de 7 tareas hechas) · Duración estimada: 24-26 h (≈3 semanas a 8-10 h/semana) · Chats: 7

## Objetivo
Dejar definido QUÉ se va a construir en la primera oleada y CON QUÉ criterios, antes de escribir código: qué cuchillos de cocina entran, qué palabras clave los respaldan, cómo se clasifica el catálogo, cómo es una ficha y qué datos guarda. Sin código de producto, sin dominio, sin contenido final.

## Decisiones de partida (registradas en DECISIONS.md, D-013 a D-018)
- Categorías base del catálogo: cuchillos de cocina, navajas, outdoor, caza, EDC y cuchillos japoneses, más piedras de afilar y accesorios. Se amplía por oleadas.
- Primera oleada: SOLO cuchillos de cocina.
- Criterios de clasificación: tipo, uso, acero, origen, precio, marca y nivel de usuario.
- Selección de fichas: primero se buscan online los 10 cuchillos de cocina más populares y se construye a partir de ahí, siempre con investigación de palabras clave (KW research) y matrices de KW.
- Ficha: técnica objetiva + reseña con veredicto/puntuación. Habrá rankings y comparativas.
- Herramientas: solo gratuitas + Claude in Chrome para acceso online. Dominio: .com preferido; sin elegir ni comprar hasta que exista una web mínima bien construida.
- Afiliación: programas y cuentas se dejan para fases posteriores (el modelo de datos reserva los campos).
- Conocimiento propio sin colección grande de cuchillos: la autoría se apoya en criterio experto y datos verificados, nunca en pruebas inventadas.

## Reglas específicas de la fase
- No se afirma haber probado un cuchillo que no se ha probado. Toda reseña declara en qué se basa (datos del fabricante, análisis de especificaciones, fuentes contrastadas, uso propio).
- Los volúmenes de búsqueda con herramientas gratuitas son aproximados: sirven para ordenar y comparar, no como cifras exactas.
- Repo público: en `data/` solo se versionan matrices y listas de elaboración propia. No se copian descripciones, imágenes, reseñas ni tablas de terceros (R-07). Nada de datos crudos de scraping en git.
- Acceso web con Claude in Chrome: lectura manual y puntual. Sin extracción masiva de Amazon.es ni de sitios cuyos términos la prohíban.
- Cada hallazgo guarda su fuente y fecha de consulta.

## F1.1 · Método de investigación y herramientas
Estado: HECHO 2026-11-08 · ~2 h
Resultado: `docs/estrategia/METODO-INVESTIGACION.md`. Quedan declarados en el documento: limitaciones de las herramientas, fuentes legales no verificadas directamente (condiciones de Amazon.es y términos de Google) y una decisión pendiente del autor (cuenta de Google Ads para Keyword Planner, no ejecutada).
Objetivo: fijar cómo se investiga (fuentes, herramientas gratuitas, límites legales y formato de registro) para que F1.2 y F1.3 sean reproducibles.
Entradas: reglas de la fase, R-07.
Pasos:
1. Inventariar herramientas gratuitas utilizables (Google Trends, autocompletado, People Also Ask, Keyword Planner si procede, AlsoAsked/Ubersuggest en límites gratuitos) y sus limitaciones reales.
2. Definir qué fuentes de popularidad se aceptan (rankings de ventas, volumen de reseñas, tendencia de búsqueda, listas de medios especializados) y cómo se pondera cada una.
3. Definir el formato de registro (columnas, fuente, fecha) y la carpeta de trabajo.
Salida: docs/estrategia/METODO-INVESTIGACION.md.
Cierre: método escrito, limitaciones explícitas, formato de registro definido.
Fuera de alcance: ejecutar la investigación.

## F1.2 · Top 10 de cuchillos de cocina por popularidad
Estado: HECHO 2026-11-08 (resultado provisional; ver limitaciones)
Resultado: `docs/estrategia/TOP10-COCINA.md`, `data/estrategia/top10-cocina.csv` y `data/investigacion/evidencias.csv` (51 evidencias). Fuentes usadas: rankings de Amazon.es (A y B, pág. 1 de dos categorías), Google Trends (C, sin señal a nivel de modelo, puntuada 0 para todos) y un solo medio español (D). Declarado en el documento:
- El top 10 refleja ventas baratas de Amazon.es: 6 de 10 son Arcos y 4 son marcas de venta casi exclusiva en Amazon; no entra ninguna premium (Victorinox Fibrox queda 12º por desempate).
- R-10 y D-019: las condiciones de Amazon.es limitan el uso a fines no comerciales y prohíben compilar listas de productos y precios; el autor indicó seguir con Claude in Chrome (sesión iniciada del autor) y asume el riesgo; sin asesoramiento jurídico.
- Fuente D insuficiente (un medio, visto en fragmentos de búsqueda); dos fichas de Arcos con reseñas idénticas (4.199); serie del Arcos 150 mm y medida del Matsato sin verificar; escalas de nota fijadas en esta tarea (heurísticas).
Objetivo: lista justificada de los 10 modelos de cuchillo de cocina más populares en España, con la evidencia de popularidad.
Entradas: docs/estrategia/METODO-INVESTIGACION.md.
Pasos:
1. Recopilar candidatos desde las fuentes definidas en F1.1 (con Claude in Chrome).
2. Puntuar popularidad con la ponderación del método y documentar la evidencia.
3. Elegir los 10 y anotar para cada uno: marca, modelo, tipo, rango de precio, fuentes.
4. Señalar candidatos descartados con motivo.
Salida: data/estrategia/top10-cocina.csv y docs/estrategia/TOP10-COCINA.md.
Cierre: 10 modelos con evidencia y fecha; ninguna descripción ni imagen de terceros copiada.

## F1.3 · Investigación de palabras clave: matrices
Estado: PENDIENTE · ~6 h
Objetivo: matrices de KW que respalden la arquitectura y las primeras fichas y artículos.
Entradas: top 10 (F1.2), método (F1.1).
Pasos:
1. Matriz de categoría: tipos de cuchillo de cocina y usos (semillas → variaciones).
2. Matriz de producto: por cada uno de los 10 modelos (modelo + opiniones, review, precio, vs, comprar, mejor alternativa).
3. Matriz informativa: afilado, cuidado, técnicas, aceros, comparativas de tipo.
4. Clasificar cada KW por intención (informacional, comparativa, transaccional), dificultad estimada y volumen relativo.
5. Agrupar en clústeres e identificar hueco/oportunidad frente a la competencia visible en la SERP.
Salida: data/kw/matriz-categorias.csv, matriz-productos.csv, matriz-informativa.csv y docs/estrategia/KW-CLUSTERS.md.
Cierre: clústeres definidos, KW priorizadas, limitaciones de los datos declaradas.

## F1.4 · Taxonomía y arquitectura de información
Estado: PENDIENTE · ~4 h
Objetivo: cómo se clasifica y navega el catálogo, y cómo se estructura la URL.
Entradas: clústeres (F1.3), criterios de clasificación decididos.
Pasos:
1. Definir las facetas (tipo, uso, acero, origen, precio, marca, nivel de usuario): valores permitidos para cuchillos de cocina.
2. Distinguir qué facetas son categorías indexables y cuáles son filtros no indexables.
3. Diseñar el árbol de navegación (menú principal, subcategorías, hubs de blog) y el patrón de URLs.
4. Definir el enlazado interno entre fichas, rankings, comparativas y blog.
5. Dejar la estructura preparada para las categorías futuras.
Salida: docs/estrategia/TAXONOMIA.md y docs/estrategia/ARQUITECTURA.md.
Cierre: árbol de navegación y URLs aprobados; criterio indexable/filtro justificado con las KW.

## F1.5 · Metodología editorial: ficha, puntuación, rankings y comparativas
Estado: PENDIENTE · ~3 h
Objetivo: definir cómo es una ficha (técnica + reseña) y cómo se puntúa y compara, con honestidad sobre la base de cada juicio.
Entradas: taxonomía (F1.4), reglas de la fase.
Pasos:
1. Plantilla de ficha técnica (campos objetivos y su fuente).
2. Plantilla de reseña: secciones, veredicto, pros/contras, a quién va dirigido.
3. Criterios y escala de puntuación, y declaración de base de cada reseña.
4. Plantillas de ranking y de comparativa (cuándo se crea cada una).
5. Guía de estilo y checklist de supervisión del autor (contenido con IA, R-04).
Salida: docs/estrategia/METODOLOGIA-EDITORIAL.md.
Cierre: plantillas y criterios cerrados; política de transparencia escrita.

## F1.6 · Modelo de datos conceptual
Estado: PENDIENTE · ~3 h
Objetivo: esquema conceptual de datos que sostiene fichas, taxonomía, puntuaciones, rankings, comparativas y enlaces futuros de afiliación.
Entradas: F1.4, F1.5.
Pasos:
1. Entidades y relaciones (cuchillo, marca, categoría/facetas, especificaciones, reseña/puntuación, ranking, comparativa, artículo, enlace de compra, imagen).
2. Campos por entidad, tipos, obligatoriedad y reglas de calidad (fuente, fecha de verificación).
3. Reservar campos para afiliación (sin programas definidos) y para imágenes con su política de origen.
4. Definir qué vive en Supabase y qué en `content/` (Markdown/MDX).
Salida: docs/estrategia/MODELO-DATOS.md (esquema conceptual; sin migraciones SQL).
Cierre: modelo revisado contra la ficha y la taxonomía; ningún campo sin propósito.
Fuera de alcance: crear tablas en Supabase.

## F1.7 · Alcance de la primera oleada y cierre
Estado: PENDIENTE · ~2 h
Objetivo: cerrar la lista de la primera oleada y dejar listas las entradas de la Fase 2.
Entradas: F1.2 a F1.6.
Pasos:
1. Lista final de fichas de la oleada 1, rankings/comparativas y artículos de blog iniciales (mapeados a KW).
2. Estimar esfuerzo de contenido frente a 8-10 h/semana.
3. Actualizar CONTEXT.md, DECISIONS.md y registro de riesgos.
4. Proponer la definición de la Fase 2 para el chat de planificación.
Salida: docs/estrategia/OLEADA-1.md y documentos de proyecto actualizados.
Cierre: alcance de oleada 1 aprobado por el autor.

## Criterios de cierre de la Fase 1
- [x] Método de investigación documentado, con limitaciones declaradas (F1.1, 2026-11-08)
- [x] Top 10 de cuchillos de cocina con evidencia y fecha (F1.2, 2026-11-08; provisional, ver TOP10-COCINA.md sección 5)
- [ ] Matrices de KW (categorías, productos, informativa) y clústeres priorizados
- [ ] Taxonomía, arquitectura de navegación y patrón de URLs aprobados
- [ ] Metodología editorial (ficha, puntuación, rankings, comparativas) aprobada
- [ ] Modelo de datos conceptual aprobado
- [ ] Alcance de la oleada 1 cerrado
- [ ] CONTEXT.md y DECISIONS.md actualizados; push realizado según la regla obligatoria

## Fuera de la Fase 1 (aplazado)
- Dominio y marca (se decide antes del lanzamiento; preferencia .com).
- Programas de afiliación y altas de cuenta.
- Canal de RRSS/YouTube (idea de futuro, no de presente).
- Código, tablas en Supabase y contenido final.
