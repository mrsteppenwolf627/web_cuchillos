# TAXONOMÍA DEL CATÁLOGO (F1.4)

Fecha: 2026-11-08 · Entradas: `KW-CLUSTERS.md` y matrices de `data/kw/` (F1.3), `TOP10-COCINA.md` (F1.2), D-013, D-015, D-020
Estado: PROPUESTA pendiente de aprobación del autor. Complementa `ARQUITECTURA.md` (navegación, URLs, umbrales de indexación).
Repositorio público: solo criterios de clasificación y términos de búsqueda propios. Sin contenido de terceros (R-07).

## 1. Resultado en una página

- **7 facetas** (las de D-015) con valores permitidos para cuchillos de cocina, cardinalidad y fuente de verdad (sección 3).
- **Dos facetas por categoría** (tipo y uso) y **cinco comunes** (marca, acero, origen, precio, nivel). Los valores de tipo y uso cambian por categoría; las demás se heredan.
- **Indexable o filtro (sección 5):** solo **tipo** es categoría indexable por sí sola. **Marca** y **uso** lo son bajo condiciones (marca solo combinada con tipo, o con 3 fichas o más; uso solo como ranking con 3 modelos adecuados). **Acero, origen, precio y nivel son filtros** y solo generan página indexable a través de los patrones P-14, P-12 y P-15, cuando se cumplan sus condiciones.
- **Con los datos de hoy solo tres facetas se pueden rellenar para los 10 modelos del piloto:** tipo (9 de 10), marca (10 de 10) y banda de precio (10 de 10). Acero, origen, uso y nivel quedan sin poblar (sección 6). Esto limita qué páginas pueden existir en la oleada 1.
- **Tres puntos abiertos para el autor** (sección 7): sinónimo cocinero / cebollero / chef, solape entre la categoría "japoneses" (D-013) y el origen Japón, y el modelo nº 2 del top 10, que no encaja en ningún tipo verificado.

## 2. Principios de clasificación

1. **Una ficha, una categoría principal.** Cada ficha pertenece a una sola categoría y a un solo tipo. Lo transversal (usos, aceros, orígenes) se expresa con facetas, no con ramas duplicadas del árbol.
2. **Valor verificable o "no declarado".** Un valor de faceta solo se asigna si hay fuente (ficha del fabricante o criterio editorial documentado de F1.5). Si no, el valor es `no declarado`. Nunca se rellena por suposición (CLAUDE.md: dato no verificable se indica).
3. **Lista cerrada.** Los valores permitidos son los de las tablas siguientes. Un valor nuevo se añade en este documento, con fecha y motivo, antes de usarse en una ficha.
4. **Marketing no es clasificación.** Expresiones comerciales ("acero japonés", "profesional", "premium") no son valores por sí mismas. Se traducen a un valor verificable o se descartan.
5. **La demanda observada no crea valores ni páginas por sí sola.** Los valores proceden de las matrices de F1.3 (autocompletado, PAA, SERP, rangos de Planner y Ahrefs), que son señales provisionales. Que un valor exista aquí no implica que tenga página (eso lo decide `ARQUITECTURA.md`, sección 6).

## 3. Facetas y valores permitidos (cocina, oleada 1)

### 3.1 Tipo (D-015) · obligatoria · 1 valor por ficha

Forma y función de la hoja. Fuente: ficha del fabricante (nombre del tipo y dimensiones) más criterio editorial.

| Valor | Slug | Fichas en el piloto | Señal en F1.3 |
|---|---|---|---|
| cocinero (sinónimos: chef, cebollero; ver 7.1) | `cocinero` | 6 | cebollero: Planner 1 mil-10 mil, Ahrefs >1000; cocinero: Planner 100-1 mil, Ahrefs <100; chef: Planner 100-1 mil |
| santoku | `santoku` | 1 | Ubersuggest 2,9K; Planner 1 mil-10 mil; Ahrefs >1000 |
| jamonero | `jamonero` | 2 | Ubersuggest 4,4K; Planner 1 mil-10 mil; Ahrefs >1000 |
| nakiri | `nakiri` | 0 | solo "para qué sirve" (10-100) |
| pan | `pan` | 0 | Planner 100-1 mil (P3) |
| mondador | `mondador` | 0 | solo "para qué sirve" (10-100) |
| deshuesador | `deshuesador` | 0 | Planner 100-1 mil (P3) |
| fileteador | `fileteador` | 0 | no observado como tipo; aparece como uso ("filetear pescado") |
| sin clasificar | — | 1 (nº 2) | estado transitorio: la ficha no se publica (sección 7.3) |

- Los valores sin fichas están permitidos pero **no generan página** hasta tener fichas (`ARQUITECTURA.md`, sección 6).
- `fileteador` se incluye por completitud del dominio; no tiene señal de tipo en las matrices.
- Los sets o juegos de cuchillos (K13) no son un tipo: son un formato de producto (sección 4). Quedaron fuera del top 10 por la regla de tipo de F1.2.

### 3.2 Uso (D-015) · opcional · 0 a N valores por ficha

Para qué tarea es adecuado el cuchillo. Fuente: criterio de idoneidad de F1.5 (forma y largo de hoja, flexibilidad), declarado en la página. Hasta que F1.5 lo fije, **ningún modelo tiene uso asignado**.

| Valor | Slug | Origen del valor |
|---|---|---|
| jamón | `jamon` | autocompletado y SERP ("mejor cuchillo para cortar jamón") |
| verduras | `verduras` | autocompletado ("cortar verduras"); subuso `cebolla` ("cortar cebolla") |
| carne | `carne` | autocompletado |
| pescado | `pescado` | autocompletado ("filetear pescado") |
| embutido | `embutido` | autocompletado |
| fruta | `fruta` | autocompletado ("cortar sandía") |

- Los seis valores salen del autocompletado de "mejor cuchillo para" (8 usos observados, sin volumen). Son señal cualitativa, no demanda medida.
- **Excluido: "abrir ostras".** Corresponde a una herramienta (ostrero) sin tipo de cuchillo de cocina asociado en el catálogo. Reevaluar si se amplía la categoría.
- Subuso `cebolla`: valor hijo de `verduras`. Se mantiene como subvalor, no como valor propio, para no multiplicar rankings casi idénticos.

### 3.3 Acero (D-015) · opcional · 1 familia por ficha

Fuente: ficha del fabricante. **Solo se asigna si el fabricante declara el acero.**

| Campo | Valores | Notas |
|---|---|---|
| familia | `inoxidable`, `carbono`, `no declarado` | `no declarado` es el valor por defecto |
| grado | texto libre con fuente (por ejemplo 440C, 420) | opcional; sin grado verificable queda vacío. Se guarda como atributo de ficha, no como faceta |
| construcción | `monolitico`, `laminado` | `damasco` se registra como `laminado` solo con dato verificable (capas, origen). No es una familia de acero |

- **"Acero japonés" (Matsato) no es un valor válido:** es una declaración comercial sin grado. La familia queda `no declarado` salvo que el fabricante dé el grado.
- "Damasco" (K12, P3) es una construcción o un acabado, no una aleación. No ocupa un lugar en `familia`.

### 3.4 Origen (D-015) · opcional · 1 valor por ficha

Definición: **país de fabricación declarado por el fabricante.** No es el país de la sede de la marca.

| Valores | Notas |
|---|---|
| `espana`, `alemania`, `japon`, `otro` (país indicado), `no declarado` | Los tres primeros salen del autocompletado de "marcas de cuchillos de cocina" (españoles, alemanes, japoneses). Colombia apareció en el autocompletado y queda fuera del mercado objetivo |

- Para las marcas de venta casi exclusiva en Amazon (HOSHANHO, PAUDIN, Matsato, MOSFiATA), F1.2 no recoge origen: **valor `no declarado`**. No se infiere.
- Para Arcos, F1.2 no recoge el origen de fabricación con fuente: **sin verificar** hasta F1.6/ficha.

### 3.5 Precio (D-015) · obligatoria · 1 banda por ficha

Solo **banda**, nunca precio exacto (R-10; el precio de tienda es dato de terceros y cambia).

| Banda | Slug | Fichas en el piloto |
|---|---|---|
| menos de 10 EUR | `p0-10` | 1 |
| 10-25 EUR | `p10-25` | 5 |
| 25-50 EUR | `p25-50` | 4 |
| 50-100 EUR | `p50-100` | 0 |
| más de 100 EUR | `p100-mas` | 0 |

- Las tres primeras bandas son las de F1.2. **Las dos superiores las fija esta tarea como heurística:** el piloto no tiene ningún modelo por encima de 50 EUR, así que no están contrastadas.
- Una banda es una etiqueta editorial con fecha de revisión; no se actualiza por cambios diarios de precio.

### 3.6 Marca (D-015) · obligatoria · 1 valor por ficha

Fuente: fabricante o marca comercial que figura en la ficha. Lista abierta (cada marca es una entidad; su ficha de marca se define en F1.6).

Piloto: Arcos (6 modelos: nº 1, 2, 3, 5, 6 y 7), HOSHANHO, PAUDIN, Matsato y MOSFiATA (1 cada una).

### 3.7 Nivel de usuario (D-015) · opcional · 1 valor por ficha

Para quién va dirigido. **Es un juicio editorial**, no un dato del fabricante.

| Valor | Slug | Señal en F1.3 |
|---|---|---|
| iniciación | `iniciacion` | ninguna observada |
| intermedio | `intermedio` | ninguna observada |
| profesional | `profesional` | jamonero profesional (Ubersuggest 720), cocinero profesional (390), "mejor cuchillo de cocina profesional" |

- Los tres valores son una escala propuesta aquí; **los criterios de asignación los define F1.5.** Hasta entonces ningún modelo tiene nivel.
- "Profesional" en las búsquedas suele ser un calificador comercial del producto ("cuchillo profesional") más que un perfil de usuario. Hasta que F1.5 fije el criterio, **no se usa el término "profesional" como valor en una ficha.**

## 4. Atributos de ficha que NO son facetas

Se guardan en la ficha y pueden servir de filtro de interfaz. Nunca generan página indexable.

| Atributo | Motivo |
|---|---|
| medida de hoja (cm) | P-07 NO PASA: la medida es un valor de ficha, no un tema distinto |
| material del mango | sin señal observada como tema |
| formato (`individual` o `set`) | los sets quedaron fuera del top 10 (F1.2); si se incorporan, se hace con regla propia |
| grado y construcción del acero | atributos del acero (3.3) |
| puntuación y veredicto | datos editoriales de F1.5 |
| tienda o precio exacto | P-02 y P-08 NO PASAN; R-10 |

## 5. Facetas: ¿categoría indexable o filtro?

**Criterio.** Una faceta (o una combinación) puede generar una página indexable solo si cumple las cuatro condiciones:
1. Hay señal de búsqueda observada en las matrices de F1.3.
2. Existe un dato o criterio propio que hace distinta a la página (prueba de viabilidad, D-020).
3. Hay fichas suficientes (umbral de `ARQUITECTURA.md`, sección 6).
4. No duplica la intención de otra página.

Si falla alguna, la faceta es **filtro**: interfaz en el cliente, sin URL rastreable propia (`ARQUITECTURA.md`, sección 5).

| Faceta | Decisión | Justificación con las KW y la matriz de patrones | Página indexable resultante |
|---|---|---|---|
| Tipo | **CATEGORÍA INDEXABLE** | Cabezas con mayor volumen de F1.3: jamonero, santoku, cebollero; clústeres K1, K2, K3, K4 | Hub de tipo |
| Marca | **CONDICIONADA** | P-05 PASA CONDICIONADA (jamonero arcos 1 mil-10 mil, cocinero arcos y santoku arcos 100-1 mil); sin señal de la marca sola | Marca x tipo (2 fichas del tipo); ficha de marca (3 fichas o más) |
| Uso | **CONDICIONADA** | P-04 PASA CONDICIONADA; 8 usos sin volumen; 3 fichas adecuadas por uso | Ranking por uso |
| Acero | **FILTRO** (indexable cuando haya datos) | P-14 PASA CONDICIONADA, prioridad P3; ningún modelo del piloto tiene acero verificado; los artículos K10 (inoxidable o carbono) son de blog | Tipo x acero (P-14) cuando haya 2 fichas con acero verificado |
| Origen | **FILTRO** (indexable cuando haya datos) | P-12 PASA CONDICIONADA, P2; exige origen verificado y 5 fichas por grupo; hoy 0 de 10 | Ranking de marcas por origen (P-12) |
| Precio | **FILTRO** | El precio de tienda es dato de terceros (P-02 NO PASA, R-10); las bandas cambian con el mercado | Solo rankings editoriales con calificador (P-15: "calidad precio", "baratos") |
| Nivel | **FILTRO** (indexable cuando F1.5 lo defina) | Sin señal propia; "profesional" aparece como calificador de tipo (jamonero y cocinero profesional) | Ranking por calificador (P-15) cuando F1.5 fije el criterio y haya fichas |

Resumen de combinaciones (detalle y umbrales en `ARQUITECTURA.md`, sección 6):
- **Nunca indexables como página de faceta:** medida (P-07), tienda (P-08), precio exacto (P-02), autenticidad (P-13), servicio local (P-11), combinaciones de tres facetas o más.
- **Solo dos combinaciones de faceta** pueden ser páginas: marca x tipo y tipo x acero. El resto de patrones indexables son rankings editoriales (uso, calificador, origen) o comparativas, que no son combinaciones libres de facetas.

## 6. Aplicación a los 10 modelos del piloto (prueba de la taxonomía)

Datos de `data/estrategia/top10-cocina.csv`. "SV" = sin verificar contra el fabricante.

| Nº | Marca | Modelo | Tipo | Precio | Acero | Origen | Uso | Nivel |
|---|---|---|---|---|---|---|---|---|
| 1 | Arcos | Universal 200 mm | cocinero | p10-25 | no declarado | SV | pendiente F1.5 | pendiente F1.5 |
| 2 | Arcos | 150 mm (serie sin confirmar) | **sin clasificar** | p10-25 | no declarado | SV | pendiente F1.5 | pendiente F1.5 |
| 3 | Arcos | Latina 250 mm | jamonero | p0-10 | no declarado | SV | pendiente F1.5 | pendiente F1.5 |
| 4 | HOSHANHO | chef mango pakkawood 200 mm | cocinero | p25-50 | no declarado | no declarado | pendiente F1.5 | pendiente F1.5 |
| 5 | Arcos | Maitre 170 mm | santoku | p10-25 | no declarado | SV | pendiente F1.5 | pendiente F1.5 |
| 6 | Arcos | Universal alveolado 240 mm | jamonero | p10-25 | no declarado | SV | pendiente F1.5 | pendiente F1.5 |
| 7 | Arcos | Serie 2900 200 mm | cocinero | p10-25 | no declarado | SV | pendiente F1.5 | pendiente F1.5 |
| 8 | PAUDIN | chef acero al carbono 200 mm | cocinero | p25-50 | carbono (SV: lo indica el título del anuncio) | no declarado | pendiente F1.5 | pendiente F1.5 |
| 9 | Matsato | cocinero "acero japonés" | cocinero | p25-50 | no declarado ("acero japonés" no es grado) | no declarado | pendiente F1.5 | pendiente F1.5 |
| 10 | MOSFiATA | cebollero con afilador y funda 200 mm | cocinero | p25-50 | no declarado | no declarado | pendiente F1.5 | pendiente F1.5 |

Lectura:
- **Pobladas hoy:** tipo 9 de 10, marca 10 de 10, banda de precio 10 de 10. El tipo del nº 10 sale de la decisión de F1.2 (lo clasificó como chef aunque el anuncio dice "cebollero").
- **Acero:** 1 de 10 con familia declarada (nº 8, sin verificar). **Origen, uso y nivel:** 0 de 10.
- **Consecuencia:** con los datos de hoy solo se pueden construir páginas apoyadas en tipo, marca y banda de precio. Rankings por uso, por origen, por acero o por nivel dependen de F1.5 y de datos de fabricante que aún no existen (limitación 9 de F1.3).
- **Distribución por tipo del piloto:** cocinero 6, jamonero 2, santoku 1, sin clasificar 1.

## 7. Puntos abiertos para el autor

### 7.1 Cocinero, cebollero y chef: ¿un tipo o dos?
- Datos: "cuchillo cebollero" tiene rango Planner 1 mil-10 mil y Ahrefs >1000; "cuchillo cocinero", 100-1 mil y <100; "cuchillo chef", 100-1 mil. Son rangos amplios y pueden agrupar variantes (limitaciones 13 y 14 de F1.3).
- F1.2 trató el anuncio de un "cebollero" (nº 10) como chef. No se ha leído ninguna SERP que confirme que Google equipara los tres términos.
- **Propuesta:** un solo valor de tipo (`cocinero`) con `cebollero` y `chef` como sinónimos. El slug definitivo del hub (`cocinero` o `cebollero`) **no se fija ahora:** se fija al producir el hub (D-020: después de las fichas), tras comparar las SERP de "cuchillo cebollero" y "cuchillo cocinero". Si difieren, se separan en dos tipos.
- Riesgo si se unifica mal: canibalización (dos páginas para una misma intención) o pérdida de la cabeza de mayor rango. Es una hipótesis de diseño, no un dato.

### 7.2 Categoría "japoneses" (D-013) frente a origen Japón
- D-013 lista "cuchillos japoneses" como categoría base. Como categoría con ramas propias duplicaría fichas con los tipos de cocina (santoku, nakiri) y con el valor de origen `japon`.
- **Propuesta:** "japoneses" se trata como **colección transversal** (página de selección que enlaza a fichas), no como rama del árbol. Las fichas conservan su URL y su categoría principal (principio 1). Se decide al abrir esa oleada; K12 es P3 y está fuera de la oleada 1 (D-014).
- Esto reinterpreta la lectura literal de D-013: requiere confirmación del autor antes de aplicarlo.

### 7.3 Modelo nº 2 sin tipo
- F1.2 lo registra como "cocina/universal pequeño", confianza baja y serie sin confirmar. No encaja en los tipos observados en las KW (un 150 mm universal no equivale a cocinero ni a mondador sin dato de fabricante).
- **Propuesta:** valor transitorio `sin clasificar`; la ficha no se publica hasta verificar serie y tipo. No se crea un tipo nuevo para él sin evidencia de demanda.

## 8. Limitaciones y riesgos (sin matizar)

1. **Los valores salen de señales provisionales.** Las listas de tipo y uso se derivan de autocompletado y SERP con una consulta por término (limitaciones 4 y 5 de F1.3). Un valor ausente aquí puede tener demanda no observada.
2. **Las escalas de precio superior (50-100 y más de 100) y de nivel de usuario son heurísticas fijadas en esta tarea,** sin contraste con el piloto ni con datos de mercado.
3. **Los umbrales de fichas por página** (`ARQUITECTURA.md`) son criterios de diseño, no resultados medidos. Se ajustarán con datos de indexación cuando haya Search Console (hoy sin crear, `docs/ACCESOS.md`).
4. **Uso y nivel dependen de F1.5.** Esta tarea fija los valores permitidos, no los criterios de asignación. Hasta F1.5, ambas facetas están vacías para todos los modelos.
5. **Ninguna ficha tiene datos de fabricante verificados** (limitación 9 de F1.3). Acero, origen y grado no se pueden poblar con garantía.
6. **Riesgo de contenido escalado (R-04, R-11).** Una taxonomía rica permite generar muchas combinaciones; la protección está en las condiciones de indexación (`ARQUITECTURA.md`), no en la taxonomía.
7. **Reclasificación.** Cambiar el tipo de una ficha publicada cambia sus enlaces y hubs. Las URLs de ficha no incluyen el tipo para evitar redirecciones masivas (`ARQUITECTURA.md`, sección 3).

## 9. Control de cambios

- 2026-11-08: versión inicial (F1.4). Propuesta pendiente de aprobación del autor.
