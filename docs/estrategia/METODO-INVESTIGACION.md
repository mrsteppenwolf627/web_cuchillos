# MÉTODO DE INVESTIGACIÓN Y HERRAMIENTAS (F1.1)

Última actualización: 2026-11-08
Alcance: cómo se investiga en la Fase 1 (F1.2 top 10 y F1.3 palabras clave). Este documento NO contiene resultados de investigación.
Repositorio público: aquí solo hay método y fuentes citadas, sin texto, imágenes ni tablas de terceros (R-07).

## 1. Reglas que gobiernan todo el método

1. Cada hallazgo guarda fuente y fecha de consulta. Sin fuente y fecha, no existe.
2. Los volúmenes de búsqueda con herramientas gratuitas son aproximados: sirven para ordenar y comparar, nunca como cifra exacta.
3. Acceso web con Claude in Chrome: lectura manual y puntual. Sin extracción masiva ni automatizada.
4. En `data/` solo se versionan matrices y listas de elaboración propia. Nada de datos crudos de scraping en git (`data/raw/` está ignorado).
5. Una reseña o ficha nunca afirmará una prueba que no se ha hecho (D-017). Aquí se aplica a la investigación: se registra qué se vio, dónde y cuándo, no qué "se probó".
6. Solo herramientas gratuitas (D-018). Si una herramienta exige pago, tarjeta o cuenta nueva no listada en `docs/ACCESOS.md`, se detiene el uso y se consulta al autor.

## 2. Inventario de herramientas gratuitas

Estado de verificación: "contrastado" = coincide en varias fuentes consultadas el 2026-11-08; "dudoso" = fuentes contradictorias o una sola fuente secundaria. Las cifras de planes gratuitos cambian sin aviso: reconfirmar en la propia herramienta antes de depender de ellas.

| Herramienta | Para qué sirve aquí | Límites reales | Verificación | Uso en Fase 1 |
|---|---|---|---|---|
| Google Trends | Comparar interés relativo entre términos, estacionalidad, picos; región España | Índice relativo 0-100 respecto al máximo del periodo y región; no da volumen absoluto. Se re-normaliza al cambiar ventana. Basado en muestra: la misma consulta puede variar algo, sobre todo en términos de poco volumen. Comparación de hasta 5 términos a la vez. Términos ambiguos distorsionan | Contrastado | SÍ, manual. Siempre con un término ancla fijo para comparar entre lotes |
| Autocompletado de Google | Detectar formulaciones reales y cola larga a partir de una raíz | Señal cualitativa, sin volumen. Depende de ubicación, idioma, historial y momento. Se consulta a mano: las consultas automatizadas a Google Search no están permitidas sin permiso | Contrastado (política); contenido variable | SÍ, manual, sesión sin iniciar sesión cuando sea posible |
| People Also Ask (PAA) | Preguntas relacionadas para la matriz informativa | Cualitativo, cambia por consulta y fecha, sin volumen. No se extrae de forma automatizada | Contrastado | SÍ, manual |
| Google Keyword Planner | Ideas de palabras clave y volumen aproximado de Google | Exige cuenta de Google Ads. Sin gasto activo muestra rangos amplios (p. ej. 1K-10K) en lugar de cifras. Agrupa variantes próximas. Hay un camino para crear la cuenta sin campaña, pero requiere acceso nuevo no inventariado | Contrastado | CONDICIONAL: solo si el autor crea la cuenta (ver sección 8, decisión pendiente). Hasta entonces, no se usa |
| Ubersuggest (plan gratuito) | Volumen aproximado, dificultad y sugerencias | Varias fuentes coinciden en 3 búsquedas/informes al día en el plan gratuito; una fuente cita extensión de Chrome con ~40/día (dudoso). Base de datos de volumen estimada por la propia herramienta | Contrastado (3/día); dudoso (extensión) | SÍ, como contraste, con presupuesto de 3 consultas/día |
| AlsoAsked | Árbol de preguntas PAA | Las fuentes se contradicen sobre si existe plan gratuito y su tamaño (desde "sin plan gratuito" hasta "3 búsquedas/día") | Dudoso | NO se planifica depender de ella. Si el plan gratuito está disponible al abrirla, uso oportunista |
| AnswerThePublic | Preguntas y preposiciones por tema | Una fuente secundaria cita 3 búsquedas/día en el plan gratuito | Dudoso | Opcional, oportunista |
| Google Search Console | Datos reales de impresiones y consultas | Requiere un sitio verificado; hoy no hay dominio | No aplicable | NO en Fase 1 (posterior al lanzamiento) |
| Claude in Chrome | Lectura manual de páginas públicas con la sesión del autor | Sujeto a los términos de cada sitio; no sustituye a una API. Si aparece CAPTCHA o bloqueo, se detiene | — | SÍ, lectura puntual (sección 5) |
| Herramientas de pago y APIs de SERP (Semrush, Ahrefs, SerpApi, etc.) | — | Excluidas por D-018. Algunas tienen planes gratuitos mínimos; no se adoptan | — | NO |

Limitación de conjunto: con estas herramientas NO se obtiene volumen absoluto fiable por palabra clave en España. El método lo asume: se trabaja con órdenes de magnitud, rangos y comparaciones relativas, y las decisiones de F1.3 deben ser robustas a un error de volumen de al menos un orden de magnitud.

## 3. Fuentes de popularidad aceptadas y ponderación

Unidad de análisis: modelo concreto (marca + serie + formato/tamaño). La definición de qué tipos de cuchillo de cocina entran en el top 10 (p. ej. mondador frente a cuchillo cocinero) se resuelve en F1.2, no aquí.

| Fuente | Qué mide | Sesgos conocidos | Peso |
|---|---|---|---|
| A. Rankings de ventas de tiendas (p. ej. "más vendidos" de Amazon.es, lectura manual) | Ventas relativas actuales por categoría | Dominan los productos baratos y de reposición; el ranking fluctúa; depende de la categoría elegida por la tienda; posible manipulación por ofertas | 35 % |
| B. Volumen de reseñas/valoraciones en tiendas | Base instalada acumulada | Favorece a los modelos antiguos; reseñas incentivadas o variantes agrupadas; la nota media no es calidad objetiva | 25 % |
| C. Tendencia y demanda de búsqueda (Trends, autocompletado, Ubersuggest) | Interés real de los usuarios por modelo o marca | Relativo, ambiguo (marca frente a modelo), ruido de campañas estacionales | 25 % |
| D. Listas de medios especializados y guías de compra | Qué modelos recomienda la prensa y las guías | Muchos medios cobran por afiliación y se copian entre sí; mide recomendación, no ventas | 15 % |

Los pesos son una heurística del método, no un dato; se pueden revisar en F1.2 si la evidencia lo justifica, dejando constancia por escrito.

Cálculo (se aplica en F1.2):
1. Cada fuente puntúa al modelo de 0 a 3 (0 = sin evidencia; 1 = presencia débil; 2 = presencia clara; 3 = posición destacada).
2. Puntuación = suma de (peso x nota / 3) x 100. Resultado de 0 a 100.
3. Condición de entrada al top 10: evidencia en al menos DOS fuentes distintas y al menos una de ellas entre A, B o C. Un modelo solo respaldado por listas de medios (D) no entra.
4. En caso de empate, prima la evidencia más reciente y la de mayor confianza.
5. La lista final se acompaña de la matriz de evidencia que la sostiene.

## 4. Formato de registro

Carpeta de trabajo (versionada, elaboración propia): `data/investigacion/`
Carpeta de datos crudos o capturas (NO versionada): `data/raw/` (ya ignorada por git). Nada de capturas de pantalla, HTML guardado ni exportaciones de terceros en git.

Archivo de evidencias: `data/investigacion/evidencias.csv` (UTF-8, separador coma, una fila por dato observado). Columnas:

| Columna | Contenido | Regla |
|---|---|---|
| id | EV-0001, EV-0002... | Correlativo, no se reutiliza |
| fecha_consulta | AAAA-MM-DD | Obligatoria |
| fase_tarea | F1.2 / F1.3 | Obligatoria |
| fuente_tipo | ventas / reseñas / busqueda / medio / herramienta | Una de las cinco |
| fuente_nombre | Nombre de la tienda, medio o herramienta | Obligatoria |
| url | Dirección consultada | Obligatoria si es pública; sin parámetros de sesión ni afiliación |
| consulta | Término buscado o categoría navegada | Obligatoria |
| entidad | Modelo o palabra clave a la que se refiere el dato | Obligatoria |
| metrica | posicion / n_resenas / indice_trends / rango_volumen / sugerencia / mencion | Una de la lista |
| valor | Valor observado, tal cual | Si es un rango, se escribe el rango |
| escala | Unidad o escala (p. ej. "0-100 relativo", "posición en categoría") | Obligatoria |
| confianza | alta / media / baja | Según sección 6 |
| limitacion | Sesgo o salvedad aplicable | Obligatoria si la confianza no es alta |
| notas | Observación libre y breve, en palabras propias | Sin copiar texto de terceros |

Reglas de registro:
- Se anota el dato (posición, número, rango, mención), nunca el texto, la imagen ni la reseña de terceros.
- Un dato = una fila. Una consulta repetida otro día = otra fila con otra fecha.
- Las matrices derivadas (top 10, matrices de KW) citan los `id` de evidencia que las sostienen.
- Cadencia de caducidad: un dato de ventas, posición o tendencia con más de 90 días se vuelve a consultar antes de usarlo en una decisión de oleada. Es un umbral del método, no una norma externa.

## 5. Límites legales y de acceso

Resumen operativo; no es asesoramiento jurídico. Ante la duda, no se hace y se pregunta al autor.

| Sitio o fuente | Permitido | No permitido |
|---|---|---|
| Amazon.es | Lectura manual y puntual de páginas públicas (categoría "más vendidos", fichas) con Claude in Chrome, anotando solo datos propios | Scraping, robots o herramientas de extracción automática, recorrido masivo de fichas o reseñas, evadir bloqueos o CAPTCHA, usar el contenido (descripciones, imágenes, reseñas) en el repositorio o en las fichas. Los términos de Amazon excluyen minería de datos, robots y herramientas de extracción |
| Google Search (autocompletado, PAA, resultados) | Consultas manuales de una persona | Consultas automatizadas, scripts, extracción de resultados o de rankings sin permiso expreso |
| Google Trends | Consulta manual y exportación manual a CSV desde la interfaz | Scrapers o bibliotecas no oficiales de forma masiva |
| Medios especializados | Lectura manual; registrar qué modelos recomiendan y el nombre de la fuente | Copiar texto, imágenes, puntuaciones o tablas; reproducir su estructura |
| Sitios de fabricante | Lectura manual de datos técnicos objetivos para contrastar | Copiar descripciones comerciales (se reescribe con palabras propias, con datos verificables) |
| Cualquier sitio con inicio de sesión | Nada: no se accede a datos que requieran cuenta ajena | Todo |

Ritmo de lectura: umbral operativo del método (no una cifra legal) de como máximo unas 30 páginas por sitio y sesión de investigación, con pausas, siempre a mano. Si el sitio muestra un aviso, CAPTCHA o bloqueo, se detiene la sesión y no se reintenta.

## 6. Niveles de confianza

- Alta: dato directo de la fuente primaria, visto y fechado por nosotros, sin ambigüedad.
- Media: dato de la fuente primaria con sesgo conocido (p. ej. ranking de tienda) o contrastado por una sola fuente.
- Baja: dato de una fuente secundaria, estimación de herramienta gratuita o coincidencia ambigua de términos.

Un dato de confianza baja no puede sostener solo una decisión; necesita corroboración de otra fuente.

## 7. Protocolo reproducible para F1.2 y F1.3

F1.2 (top 10):
1. Fijar la lista de candidatos desde las fuentes A y D (lectura manual puntual).
2. Completar B y C para cada candidato.
3. Registrar cada dato en `evidencias.csv`.
4. Aplicar el cálculo de la sección 3 y generar el top 10 con la matriz de evidencia.

F1.3 (palabras clave):
1. Partir de los 10 modelos y de las categorías base de la oleada 1.
2. Autocompletado y PAA a mano por término raíz.
3. Trends para comparar candidatos en lotes con término ancla fijo.
4. Ubersuggest dentro del presupuesto de 3 consultas/día para contrastar volúmenes de las palabras clave prioritarias.
5. Registrar cada dato como evidencia y construir las matrices a partir de ellas.

## 8. Limitaciones explícitas y puntos abiertos

Limitaciones del método:
1. No hay volumen absoluto fiable por palabra clave. Todo volumen es orden de magnitud.
2. Trends es relativo y muestreado; no sirve para estimar tráfico.
3. Los rankings de ventas de tienda favorecen productos baratos y de reposición; el top 10 puede quedar sesgado hacia precio bajo.
4. Las cifras de planes gratuitos proceden en parte de fuentes secundarias y cambian; AlsoAsked y AnswerThePublic quedan como dudosas.
5. Todo el acceso es manual y puntual: la cobertura es limitada y depende del criterio del investigador. Es un coste asumido por R-07.
6. La ponderación (35/25/25/15) es una heurística no validada.

No verificado durante F1.1 (declarado para no dar por cierto lo que no se comprobó):
- No se pudo abrir la página de condiciones de uso de Amazon.es (fuera de la lista de acceso de la sesión). La restricción de robots y minería de datos se apoya en citas de sus condiciones recogidas por fuentes secundarias. Antes de F1.2, el autor o una sesión con acceso debería leer las condiciones vigentes de Amazon.es.
- Los términos de servicio vigentes de Google no se leyeron directamente; la prohibición de consultas automatizadas se apoya en fuentes secundarias y en versiones archivadas de sus términos.
- Disponibilidad y estructura actuales de "más vendidos" en Amazon.es: se comprobará en F1.2 con lectura manual.

Decisión pendiente del autor (fuera del alcance de F1.1, no ejecutada): crear o no una cuenta de Google Ads solo para usar Keyword Planner con rangos de volumen. Implica un acceso nuevo, que debería inventariarse en `docs/ACCESOS.md`. Sin ella, el método funciona con las demás herramientas.

## 9. Fuentes consultadas para este método (fecha de consulta: 2026-11-08)

- Google Trends, escala relativa 0-100, muestreo y re-normalización: documentación de conectores y guías de terceros (docs.adriel.com, digidop.com, meetglimpse.com, serpapi.com).
- Keyword Planner, rangos sin gasto activo y cuenta sin campaña: searchengineland.com (2016-2017, histórico), guías de 2026 (dynomapper.com, webtonic.io, seologist.com).
- Ubersuggest, límites de plan gratuito: dupple.com (octubre de 2026), ruzuku.com, toolradar.com, themarketingagency.ca (extensión de Chrome, dudoso).
- AlsoAsked y AnswerThePublic: help.alsoasked.com, toolradar.com, wildandfreetools.com (fuentes contradictorias).
- Condiciones de Amazon (robots y minería de datos): conductatlas.com y paymentservices.amazon.com (secundarias; sin lectura directa de Amazon.es).
- Consultas automatizadas a Google: itechguides.com y versiones archivadas en policies.google.com/terms/archive (secundarias).

## 10. Control de cambios

- 2026-11-08: versión inicial (F1.1).
