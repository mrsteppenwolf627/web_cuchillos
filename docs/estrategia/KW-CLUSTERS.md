# CLÚSTERES DE PALABRAS CLAVE Y PATRONES PROGRAMÁTICOS (F1.3)

Fecha de consulta: 2026-11-08 · Método: `METODO-INVESTIGACION.md` (F1.1) · Entrada: `TOP10-COCINA.md` (F1.2)
Evidencias: `data/investigacion/evidencias.csv`, EV-0052 a EV-0147 (96 filas nuevas) · Matrices: `data/kw/matriz-categorias.csv`, `matriz-productos.csv`, `matriz-informativa.csv`, `matriz-patrones.csv`
Estado: resultado PROVISIONAL. Los volúmenes cubren solo 3 familias de términos y son estimaciones de herramienta. Lee primero la sección 7.
Repositorio público: solo términos de búsqueda, dominios, cifras de herramienta y valoraciones propias. Sin texto, imágenes ni estructura de páginas de terceros (R-07).

## 1. Resultado en una página

- **152 palabras clave y 16 patrones** en cuatro matrices: 52 de categoría, 60 de producto (10 modelos x 6 patrones), 40 informativas y 16 patrones programáticos.
- **Solo 18 de las 152 palabras clave tienen volumen** (12 %), todas de las familias jamonero, santoku y cocinero. Las informativas y las de producto no tienen ninguna cifra de volumen. El resto se ordena por señal cualitativa (autocompletado, People Also Ask, SERP).
- **Google Trends quedó bloqueado (HTTP 429)** y no aporta ningún dato. No hay comparación relativa entre términos ni estacionalidad.
- **14 clústeres.** Los de prioridad P1: jamonero (K1), santoku y su comparativa con el cuchillo cocinero (K2), cuchillo cocinero con cola larga de marca (K3), modelos de las cuatro marcas de venta casi exclusiva en Amazon (K7), afilado (K9) y aceros (K10).
- **Patrones: 9 pasan con condiciones, 6 no pasan y 1 se aplaza.** Ninguno pasa sin condiciones. Las condiciones más restrictivas: un mínimo de modelos fichados por página y datos verificados del fabricante (sección 6).
- **Oportunidad frente a la SERP** (solo por tipo de dominio, no por contenido): moderada en santoku, comparativa cocinero frente a santoku, acero inoxidable frente a carbono y jamonero; baja en la cabeza "mejor cuchillo de cocina" y en "arcos universal opiniones" (sección 4).

## 2. Cómo se ha hecho

Pasos de F1.3 y herramientas realmente usadas (todo manual, sin sesión iniciada, 2026-11-08):

| Paso | Qué se hizo | Evidencias |
|---|---|---|
| 1-3 (semillas y variaciones) | Autocompletado de Google en 42 raíces (tipos, usos, marcas y modelos del top 10, afilado, cuidado, aceros, comparativas, calificadores) | EV-0052 a EV-0093 |
| 3 (PAA) | People Also Ask en 7 consultas | EV-0094 a EV-0100 |
| 5 (SERP) | Dominios orgánicos de la página 1 en esas mismas 7 consultas | EV-0101 a EV-0107 |
| 3 (Trends) | Un lote previsto (ancla "cuchillo arcos" + 4 términos). Respuesta HTTP 429. Se detuvo el uso según la sección 5 del método y no se reintentó | EV-0108 |
| 4 (volumen) | Ubersuggest sin cuenta, 3 consultas ("cuchillo santoku", "cuchillo jamonero", "cuchillo cocinero"); se registraron 39 palabras clave con cifra | EV-0109 a EV-0147 |

No se usaron: Keyword Planner (decisión pendiente del autor, F1.1 sección 8), AlsoAsked y AnswerThePublic (disponibilidad dudosa según F1.1).

Reglas que fija esta tarea (F1.1 no las definía; son heurísticas, no datos):
- **Banda de volumen:** A >= 1.000; B 300-999; C 100-299; D < 100; n/d si no hay cifra.
- **Dificultad estimada:** `alta` = al menos dos medios generalistas o una tienda especializada fuerte entre los resultados observados; `media` = mezcla de medios sectoriales y tiendas; `baja-media` = solo tiendas, marcas o sitios no editoriales; `baja` = SD de Ubersuggest menor de 25 sin SERP; `no evaluada` = ni SERP ni SD. La columna `base_dificultad` dice en qué se apoya cada valor. Confianza baja en todos los casos.
- **Prioridad (categoría e informativa):** P1 = señal en al menos dos fuentes de F1.3 y dificultad distinta de alta, y además relación con el top 10 (categoría) o con una pregunta de las SERP (informativa); P2 = señal fuerte en una fuente o relación con el top 10; P3 = señal débil, accesorios o fuera de la oleada 1.
- **Prioridad (producto):** P1 = señal observada del patrón + confianza media del modelo en F1.2 + dificultad no alta. P2 = señal observada con confianza baja del modelo o dificultad alta. P3 = patrón sin señal observada. Si el patrón no pasa la prueba de viabilidad, la prioridad final queda `aplazada`.
- La ausencia de una sugerencia de autocompletado **no** implica ausencia de demanda: solo no se observó.

## 3. Clústeres

Volúmenes: Ubersuggest, España, estimación de herramienta (ver sección 7). Fila `K` = cluster de las matrices.

| K | Clúster | Cabezas y volumen | Intención | Dificultad | Relación con el top 10 | Prioridad |
|---|---|---|---|---|---|---|
| K1 | Jamonero | cuchillo jamonero 4,4K; jamonero arcos 1,0K; profesional 720; 3 claveles 320 | transaccional y comparativa | media | 2 de 10 (nº 3 y nº 6) | P1 |
| K2 | Santoku y santoku frente a cocinero | santoku 2,9K; para qué sirve 260; arcos 170; japonés 110 | informacional y comparativa | baja-media | 1 de 10 (nº 5, confianza baja) | P1 |
| K3 | Cuchillo cocinero / chef | cocinero 140; de cocinero profesional 720; cocinero profesional 390; cocinero arcos 210 | transaccional | no evaluada (cabeza); media por SD (arcos) | 6 de 10 | P1 solo la cola de marca; cabeza P2 |
| K7 | Modelos de HOSHANHO, PAUDIN, Matsato y MOSFiATA | sin volumen; autocompletado con opiniones, precio, reseña o canal de compra en las 4 marcas | comparativa y transaccional | no evaluada | 4 de 10 | P1 (opiniones, review, comprar; precio aplazado) |
| K9 | Afilado | "cómo afilar un cuchillo" sin volumen (no consultado); 10 variantes de autocompletado y 4 PAA | informacional | media | indirecta | P1 solo la cabeza |
| K10 | Aceros y materiales | sin volumen; 4 PAA y 4 variantes de autocompletado | comparativa e informacional | baja-media | indirecta | P1 |
| K4 | Tipos de cuchillo y usos | sin volumen | informacional | no evaluada | indirecta | P2 |
| K5 | Mejor cuchillo para [uso] | sin volumen; 8 usos en autocompletado | comparativa | media (jamón); resto no evaluada | indirecta | P2 |
| K6 | Modelos y series de Arcos | modelo sin volumen; familias jamonero arcos 1,0K, cocinero arcos 210, santoku arcos 170 | comparativa y transaccional | alta (único modelo evaluado: Universal) | 6 de 10 | P2 |
| K8 | Comparativas y alternativas entre modelos | solo se observó "arcos maitre vs universal" | comparativa | no evaluada | pares de los 10 | P2 |
| K11 | Cuidado y técnica | sin volumen; lavavajillas con 9 variantes | informacional | no evaluada | indirecta | P2 |
| K13 | Presupuesto y sets | sin volumen; "juego de cuchillos de cocina" con 10 variantes | transaccional | no evaluada | los sets quedaron fuera del top 10 (F1.2) | P2 baratos; P3 sets |
| K14 | Cabeza "mejor cuchillo de cocina" y marcas | sin volumen; 9 variantes de autocompletado y 4 PAA | comparativa | alta | indirecta | P2 |
| K12 | Japoneses y damasco | damasco 20-30; resto sin volumen | transaccional e informacional | no evaluada | Matsato declara acero japonés (no verificado) | P3 (categoría de oleadas posteriores, D-014) |

Palabras clave P1 (detalle en las matrices):
- Categoría: cuchillo jamonero; cuchillo jamonero arcos; mejor cuchillo jamonero; mejor cuchillo para cortar jamón; cuchillo santoku; cuchillo santoku para qué sirve; cuchillo cocinero vs santoku; cuchillo cocinero arcos.
- Informativa: cómo afilar un cuchillo; acero inoxidable o acero al carbono (3 variantes); qué es mejor, santoku o chef; para qué se usa el santoku; qué cuchillo es mejor para cortar jamón; cómo saber si un cuchillo jamonero es bueno.
- Producto: 7 palabras clave de 5 modelos (opiniones de HOSHANHO, Serie 2900, PAUDIN, Matsato y MOSFiATA; review y compra de Matsato). Los 4 "precio" quedan aplazados por el patrón P-02.

## 4. Hueco y oportunidad frente a la SERP

Se observó una sola vez, sin sesión iniciada, la página 1 de 7 consultas. Se registran dominios, no contenido: el "hueco" es una hipótesis hasta leer las páginas.

| Consulta | Dominios orgánicos identificados (en orden) | Dificultad | Lectura |
|---|---|---|---|
| mejor cuchillo de cocina | losutensiliosdelchef.com, elindependiente.com, knivesandtools.es, ganiveteriacasalama.com, directoalpaladar.com, hola.com, amazon.es | alta | Tres medios generalistas, una tienda especializada fuerte y Amazon. Hueco bajo para un sitio nuevo |
| cuchillo santoku para qué sirve | cuchillalia.com, opinel.com, 3claveles.com, cuchillosjaponeses.com | baja-media | Solo tiendas y marcas; ningún gran medio entre los identificados |
| cómo afilar un cuchillo | directoalpaladar.com, victorinox.com, 3claveles.com (+3 sin identificar) | media | Un medio de cocina, una marca y una tienda |
| arcos universal cuchillo opiniones | ibergour.es, elle.com, amazon.es, esquire.com (+2 sin identificar) | alta | Dos revistas generalistas y Amazon. Es el único modelo del top 10 cuya SERP se miró |
| cuchillo cocinero vs santoku | knivesandtools.es, ganiveteriaroca.com, sharpedgeshop.com, shanzuchef.com (+1 sin identificar) | baja-media | Solo tiendas |
| acero inoxidable o acero al carbono cuchillo | ganiveteriaroca.com, opinel.com, utset.com, armas.es, knivesandtools.es, kobaknife.com, reliance-foundry.com (+1 sin identificar) | baja-media | Tiendas y sitios industriales |
| mejor cuchillo jamonero | mundiberico.com, ganiveteriaroca.com, directoalpaladar.com, knivesandtools.es, verema.com, elconfidencialdigital.com, rribericos.es, cuchillalia.com, valledearas.com | media | Medios gastronómicos y tiendas de jamón y cuchillería |

Lecturas de las matrices sin interpretar más allá de los datos:
- El santoku (2,9K) y el jamonero (4,4K) tienen en Ubersuggest más volumen que el término base "cuchillo cocinero" (140), aunque esa cifra es incoherente con su variante "de cocinero profesional" (720), lo que indica agrupación de variantes por la herramienta.
- F1.2 situó 6 modelos chef, 2 jamoneros y 1 santoku en el top 10. Los volúmenes observados no permiten concluir cuál de esos tipos concentra más demanda real (sección 7, punto 1).
- Los sets de cuchillos tienen señal clara en autocompletado (10 variantes) y quedaron fuera del top 10 por la regla de tipo de F1.2.
- Marcas de venta casi exclusiva en Amazon: las cuatro (HOSHANHO, PAUDIN, Matsato, MOSFiATA) tienen sugerencias de opiniones, precio, reseña o canal de compra. Matsato suma "es bueno", "original", "mercado libre" y "aliexpress".

## 5. Priorización: resumen por matriz

| Matriz | Filas | P1 | P2 | P3 | Aplazadas |
|---|---|---|---|---|---|
| Categoría (`matriz-categorias.csv`) | 52 | 8 | 22 | 22 | — |
| Informativa (`matriz-informativa.csv`) | 40 | 8 | 16 | 16 | — |
| Producto (`matriz-productos.csv`, prioridad final) | 60 | 7 | 4 | 39 | 10 (patrón P-02 precio: 10 filas, una por modelo) |
| Patrones (`matriz-patrones.csv`) | 16 | 2 | 5 | 2 | 7 |

## 6. Patrones programáticos y prueba de viabilidad (D-020)

Prueba: qué dato o criterio propio hace distinta cada página. Sin él, el patrón no pasa. Las "páginas potenciales" son recuentos de entidades observadas, no objetivos ni volumen.

| Patrón | Páginas oleada 1 | Prueba | Dato o criterio propio | Condición o motivo |
|---|---|---|---|---|
| P-01 [modelo] opiniones, review, comprar | 10 | PASA CONDICIONADA | Ficha verificada con fuente y fecha, puntuación propia, veredicto con base declarada (D-017), alternativas desde datos | No es prueba de uso ni suma de opiniones de terceros; sin datos verificados no se publica |
| P-02 [modelo] precio | 0 | NO PASA | Ninguno: precio de tienda es dato de terceros; R-10 | Solo banda de precio; reevaluar con fuente autorizada |
| P-03 [modelo] vs [modelo] | hasta 16 (1 con señal) | PASA CONDICIONADA | Tabla de especificaciones comparadas y veredicto por perfil | Pares del mismo tipo o con demanda, y con diferencias reales; si no, no se indexa |
| P-04 mejor cuchillo para [uso] | 3 posibles | PASA CONDICIONADA | Ranking propio e idoneidad por uso | Mínimo 3 modelos adecuados fichados; jamón no llega con 2 jamoneros |
| P-05 [marca] [tipo] | 2 | PASA CONDICIONADA | Comparación de series de la marca por tipo (Universal, 2900, Latina) | Marca con al menos 2 modelos fichados del tipo |
| P-06 [tipo] para qué sirve | 0 programático | NO PASA | Ninguno por página: contenido de referencia común | Solo como artículo o hub redactado por el autor |
| P-07 [tipo] [medida] | 0 | NO PASA | Ninguno: la medida es un valor de ficha | Filtro de ficha, no página |
| P-08 [tipo] [tienda] | 0 | NO PASA | Ninguno: sin datos propios de stock ni precio | R-07, R-10 |
| P-09 cómo afilar [método] | 0 programático | PASA CONDICIONADA | Procedimiento por método y tipo de filo | Solo artículos redactados y revisados por el autor |
| P-10 [accesorio de afilado] | 0 | APLAZADA | No evaluado | Accesorios: oleadas posteriores (D-014) |
| P-11 [servicio local] | 0 | NO PASA | Ninguno: servicio local | Intención de servicio presencial |
| P-12 mejores marcas [origen o nivel] | 0 | PASA CONDICIONADA | Ranking propio de marcas | Faceta de origen verificada y al menos 5 fichas por grupo |
| P-13 [modelo] original / es bueno | 0 | NO PASA | Ninguno verificable | La autenticidad no se puede comprobar desde aquí |
| P-14 [tipo] de [acero] | 0 | PASA CONDICIONADA | Descripción técnica del acero con datos del fabricante | Acero declarado en la ficha; "damasco" exige dato verificable |
| P-15 mejor cuchillo de cocina [calificador] | 0 | PASA CONDICIONADA | Ranking propio por calificador | Facetas pobladas; D-020 sitúa estos hubs tras las primeras fichas |
| P-16 mejor alternativa a [modelo] | 6 | PASA CONDICIONADA | Alternativas por tipo, precio y puntuación | Mínimo 3 alternativas del mismo tipo; sin señal de demanda observada |

Combinatoria de referencia: 10 modelos dan 45 pares posibles para P-03; 26 combinaciones marca-tipo tienen sugerencia observada para P-05 (Arcos 8, Victorinox 5, 3 Claveles 4, Tramontina 4, Global 3, Zwilling 2). Sin la regla de condición, ambas cifras crecen más rápido que el catálogo (R-11).

## 7. Limitaciones y riesgos (sin matizar)

1. **El volumen no cubre casi nada.** Solo 3 familias (santoku, jamonero, cocinero) tienen cifras, y son estimaciones de una herramienta gratuita. De los 152 términos, 134 se ordenan solo por señal cualitativa. Cualquier decisión de oleada debe aguantar un error de un orden de magnitud o más (limitación 1 del método).
2. **Trends no aporta datos** (HTTP 429 al primer intento; detenido por la regla de bloqueo). La demanda relativa entre familias descansa en Ubersuggest. No hay estacionalidad ni comparación entre lotes con ancla.
3. **Ubersuggest.** 3 consultas sin cuenta (la web ofrece más solo con registro, y crear cuentas queda fuera del método). De sus 39 cifras registradas, 28 llevan la marca "Outdated" y 11 una antigüedad de entre hoy y 6 meses. La dificultad PD vale 100 en la mayoría de filas, sin información útil, y la SD está en 5-44 en todas; ambas son escalas propias de la herramienta. Hay incoherencias (cocinero) que sugieren agrupación de variantes.
4. **Una sola consulta por término y por día**, sin sesión iniciada, en google.com con interfaz en español (la página indicaba España; no se verificó la ubicación por IP). Autocompletado, PAA y SERP varían por momento y ubicación, y pueden reflejar campañas puntuales de marca.
5. **Dificultad estimada por tipo de dominio**, no por autoridad ni contenido. No se leyó ninguna página competidora. 7 SERP, página 1, solo resultados orgánicos con título; no se registran anuncios, bloques de compra ni respuestas de IA. Algunos dominios no pudieron identificarse por los enlaces de redirección de Google.
6. **Todas las escalas de banda, dificultad y prioridad las fijé al ejecutar la tarea.** Con otras reglas cambian los P1.
7. **Dos de los 10 modelos tienen confianza baja en F1.2** (Arcos 150 mm y Maitre). Sus filas de producto heredan esa limitación; el Arcos de 150 mm no tiene ninguna señal asignable.
8. **Los patrones y su viabilidad son de diseño.** Los recuentos de páginas son entidades observadas. La unicidad real solo se puede comprobar con la ficha técnica (F1.5) y el modelo de datos (F1.6).
9. **Sin datos verificados de fabricante** para ningún modelo; los patrones P-01, P-03, P-05, P-14 y P-16 dependen de ellos.
10. **Marcas de Amazon:** su señal puede deberse a la propia dinámica de la plataforma y no a demanda independiente. No hay evidencia fuera de Amazon (hereda la limitación 1 de F1.2).
11. **Contenido masivo por IA (R-04, R-11).** Que un patrón pase la prueba no garantiza que los buscadores traten bien las páginas; solo indica que existe un dato propio que las diferencia.
12. **Incidencia de proceso.** Un lote de 4 raíces de autocompletado se descartó porque una ventana emergente de Google quitó el foco al cuadro de búsqueda; esas raíces se repitieron. El dato registrado es el de la repetición.

## 8. Control de cambios

- 2026-11-08: versión inicial (F1.3).
