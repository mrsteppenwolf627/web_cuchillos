# ARQUITECTURA DE INFORMACIÓN (F1.4)

Fecha: 2026-11-08 · Entradas: `TAXONOMIA.md` (F1.4), `KW-CLUSTERS.md` y `data/kw/matriz-patrones.csv` (F1.3), D-014, D-015, D-020, R-04, R-11
Estado: PROPUESTA pendiente de aprobación del autor. Sin código ni tablas: solo estructura, URLs y reglas.
Repositorio público: sin contenido de terceros (R-07).

## 1. Resultado en una página

- **Ocho familias de página** con patrón de URL fijo (sección 3). Las fichas tienen URL plana (`/ficha/{slug}/`) para que reclasificar un cuchillo no rompa enlaces.
- **Tres estados por página** (sección 5): E1 publicar e indexar, E2 publicar sin indexar, E3 no generar. **Por defecto, toda página programática es E3** y pasa a E1 solo si cumple su umbral (sección 6).
- **Filtros sin URL rastreable** (cliente o fragmento `#`), según la guía vigente de Google sobre navegación por facetas (sección 5.3).
- **Control de la explosión combinatoria (D-020):** una tabla de umbrales por familia y su aplicación a los datos de hoy (sección 6.2). Con los 10 modelos del piloto, el máximo de páginas indexables de catálogo es **15** (9 fichas, 1 categoría, 1 hub de tipo, 1 ficha de marca, 2 de marca x tipo y 1 comparativa de tipos), y **hoy ninguna ficha tiene datos verificados**, así que las páginas publicables ahora son 0.
- **Consecuencia que condiciona la oleada 1 (sección 6.3):** los hubs de las dos cabezas con mayor volumen, jamonero y santoku, no llegan al umbral con 2 y 1 fichas. Quedan en E2 hasta que haya 3 fichas del tipo.
- **Cinco decisiones del autor pendientes** (sección 9).

## 2. Principios

1. **Una intención, una URL.** Si dos páginas responden a la misma búsqueda, una se elimina o se fusiona.
2. **Jerarquía de navegación en migas y menús, no en la URL de la ficha.** La ficha es la unidad estable del catálogo; sus categorías cambian.
3. **Default-deny.** Ninguna página programática existe, ni se indexa, sin cumplir su umbral. Es la defensa principal frente a R-04 y R-11.
4. **Todo indexable es alcanzable en 3 clics o menos desde la portada y recibe al menos 2 enlaces internos desde páginas E1.**
5. **El sitio crece añadiendo datos, no plantillas.** Una página nueva exige datos propios (prueba de viabilidad de F1.3, umbral de unicidad de F1.5).

## 3. Familias de página y patrón de URL

Reglas de URL generales: minúsculas, sin tildes ni eñes (`ñ` pasa a `n`), guiones como separador, castellano, barra final, sin parámetros en páginas indexables, sin fechas en la URL.

| Familia | Patrón de URL | Ejemplo | Patrón F1.3 | Estados posibles |
|---|---|---|---|---|
| Portada | `/` | — | — | E1 |
| Categoría | `/{categoria}/` | `/cuchillos-de-cocina/` | — | E1, E3 |
| Hub de tipo | `/{categoria}/{tipo}/` | `/cuchillos-de-cocina/jamonero/` | — | E1, E2, E3 |
| Marca x tipo | `/{categoria}/{tipo}/{marca}/` | `/cuchillos-de-cocina/jamonero/arcos/` | P-05 | E1, E3 |
| Ficha (reseña) | `/ficha/{marca}-{serie}-{tipo}-{medida}/` | `/ficha/arcos-latina-jamonero-250/` | P-01 | E1, E3 |
| Marca | `/marca/{marca}/` | `/marca/arcos/` | — (P-12 usa marcas) | E1, E3 |
| Ranking | `/mejores/{slug}/` | `/mejores/cuchillos-para-cortar-verduras/` | P-04, P-15, P-12 | E1, E3 |
| Comparativa de modelos | `/comparativa/{a}-vs-{b}/` | `/comparativa/arcos-maitre-vs-arcos-universal/` | P-03 | E1, E3 |
| Comparativa de tipos | `/comparativa/{tipo-a}-vs-{tipo-b}/` | `/comparativa/cocinero-vs-santoku/` | — (K2, P1) | E1, E3 |
| Artículo | `/blog/{slug}/` | `/blog/como-afilar-un-cuchillo/` | P-06, P-09 | E1 |
| Tema del blog | `/blog/tema/{tema}/` | `/blog/tema/afilado/` | — | E1, E3 |
| Páginas fijas | `/metodologia/`, `/aviso-de-afiliacion/`, `/sobre/` | — | — | E1 |
| Legales | `/aviso-legal/`, `/privacidad/`, `/cookies/` | — | — | contenido fuera de F1.4 |

Reglas de slug:
- **Ficha:** `marca-serie-tipo-medida`, con la medida en mm o cm sin unidad solo si desambigua. Ejemplos: `arcos-universal-cocinero-200` y `arcos-universal-jamonero-240` (misma serie, tipos distintos). El slug **no cambia una vez publicada la ficha;** si se corrige, redirección 301 al nuevo.
- **Ficha plana por una razón técnica:** el tipo de una ficha puede cambiar (por ejemplo, la decisión de cocinero o cebollero en `TAXONOMIA.md` 7.1). Con tipo en la URL, cada cambio exige una redirección. El tipo aparece en las migas y en el slug solo como desambiguación.
- **Ficha con prefijo neutro `/ficha/`** (y no `/cuchillo/`) porque D-013 incluye piedras de afilar y accesorios, que no son cuchillos.
- **Comparativa de modelos:** los dos slugs se ordenan alfabéticamente. `a-vs-b` y `b-vs-a` no pueden coexistir; el segundo redirige al primero con 301. Evita 2 URLs por par.
- **Hubs de tipo:** slug de tipo en singular, como las búsquedas ("cuchillo jamonero"). El slug del tipo `cocinero` queda pendiente (`TAXONOMIA.md`, 7.1).
- **Ranking:** slug que describe el criterio. Los calificadores (`calidad-precio`, `baratos`) son rankings editoriales, no filtros de faceta.
- **Slugs reservados** (no se pueden usar como marca ni como tipo): `ficha`, `marca`, `mejores`, `comparativa`, `blog`, `metodologia`, `aviso-de-afiliacion`, `sobre`, `aviso-legal`, `privacidad`, `cookies`, y las categorías futuras de la sección 8.

## 4. Árbol de navegación

### 4.1 Estructura

```
Portada
├─ Cuchillos de cocina            /cuchillos-de-cocina/
│   ├─ Cocinero                   /cuchillos-de-cocina/cocinero/        (6 fichas en el piloto)
│   │   └─ Arcos                  /cuchillos-de-cocina/cocinero/arcos/  (marca x tipo, 2 fichas)
│   ├─ Jamonero                   /cuchillos-de-cocina/jamonero/        (2 fichas)
│   │   └─ Arcos                  /cuchillos-de-cocina/jamonero/arcos/  (marca x tipo, 2 fichas)
│   └─ Santoku                    /cuchillos-de-cocina/santoku/         (1 ficha)
├─ Mejores                        /mejores/{slug}/       (rankings)
├─ Comparativas                   /comparativa/{a}-vs-{b}/
├─ Blog
│   └─ Temas: afilado · aceros y materiales · cuidado y uso · guías de tipos
└─ Marcas (pie de página)         /marca/{marca}/
```

Fichas: no aparecen en el árbol; cuelgan de su hub de tipo (migas) y se listan en él.

### 4.2 Reglas de menú
- **Menú principal (máximo 5 entradas):** Cuchillos de cocina (desplegable con los tipos que tengan hub), Mejores, Comparativas, Blog (desplegable con temas), Marcas.
- **Una entrada de menú solo existe si lleva a una página E1 o E2.** Si no hay ningún ranking E1, "Mejores" no aparece. Nunca un enlace de menú a una página E3.
- **Pie de página:** Metodología, Aviso de afiliación (obligatorio y visible, CLAUDE.md), Sobre, legales.
- **Migas (obligatorias en todas las páginas salvo portada):**
  - Ficha: Portada > Cuchillos de cocina > {Tipo} > {Marca modelo}.
  - Marca x tipo: Portada > Cuchillos de cocina > {Tipo} > {Marca}.
  - Artículo: Portada > Blog > {Tema} > {Título}.
  - La ruta de la miga de la ficha sale de su tipo principal, no de la URL.

### 4.3 Temas del blog
Cuatro temas, derivados de los clústeres de F1.3:

| Tema | Clústeres | Prioridad de F1.3 | Observación |
|---|---|---|---|
| Afilado | K9 | P1 (solo cabeza) | P-09: solo artículos redactados y revisados por el autor |
| Aceros y materiales | K10 | P1 | 4 PAA y 4 variantes de autocompletado |
| Cuidado y uso | K11 | P2 | lavavajillas, guardado, sujetar el cuchillo |
| Guías de tipos | K2, K3, K4 | P1 (santoku) | "para qué sirve" y "qué es mejor": P-06 NO PASA como lote, sí como artículo |

Los artículos tienen URL plana `/blog/{slug}/` por el mismo motivo que las fichas: un artículo puede cambiar de tema. La lista concreta de artículos de la oleada 1 la fija F1.7.

## 5. Estados de indexación y mecánica técnica

### 5.1 Los tres estados

| Estado | Significado | Respuesta HTTP | Meta robots | Sitemap | Enlazable |
|---|---|---|---|---|---|
| **E1** Publicar e indexar | Cumple su umbral | 200 | `index,follow`; canonical a sí misma | Sí | Sí |
| **E2** Publicar sin indexar | Útil al usuario, bajo el umbral | 200 | `noindex,follow`; **sin** canonical hacia otra URL | No | Sí, desde menús y migas |
| **E3** No generar | Variante sin valor propio | 404 (o 301 si existe equivalente) | — | No | No |

### 5.2 Reglas
- **El estado se calcula, no se escribe a mano:** una función de indexabilidad por familia evalúa en cada build los umbrales de la sección 6 a partir de los datos. Una página sube a E1 o baja a E2 o E3 al cambiar los datos. Requisito para F1.6: los umbrales deben poder contarse desde el modelo de datos.
- **E2 se limita a hubs de tipo con 1 o 2 fichas** (navegación del usuario). El resto de familias, o cumplen el umbral (E1) o no existen (E3).
- **No se combina `noindex` con canonical a otra URL.** Señales contradictorias.
- **No se bloquea con `robots.txt` ninguna página E2:** para que se lea el `noindex`, la página debe poder rastrearse.
- **Las páginas E1 no dependen de enlaces desde páginas E2.** Riesgo conocido, no verificado en esta tarea: los buscadores pueden dejar de seguir enlaces de páginas `noindex` mantenidas mucho tiempo. Cada E1 recibe sus 2 enlaces mínimos desde otras E1 (portada, categoría, fichas, marca).
- **Sitemaps separados por familia** (`sitemap-fichas.xml`, `-hubs.xml`, `-marcas.xml`, `-rankings.xml`, `-comparativas.xml`, `-blog.xml`) para vigilar la tasa de indexación por familia (R-11). Requiere Search Console, **todavía sin crear** (`docs/ACCESOS.md`).

### 5.3 Filtros de interfaz (faceta como filtro)
- Los filtros (precio, acero, origen, nivel, medida, orden) son **estado en el cliente o fragmento `#`**, sin URL con parámetros que el servidor sirva.
- Motivo: la guía de Google para navegación por facetas recomienda, si no se quieren indexar esas URLs, impedir su rastreo con `robots.txt` o usar fragmentos `#`, y señala que `rel="canonical"` reduce el rastreo solo con el tiempo. Consultada en fragmentos de búsqueda el 2026-11-08; no se leyó la página completa.
- Si en el desarrollo se necesitaran parámetros: `&` como separador, orden fijo de filtros, 404 para combinaciones sin resultados y `Disallow` del patrón en `robots.txt`. **Verificar contra la documentación vigente de Google antes de implementar;** es un punto técnicamente delicado (un `Disallow` impide leer cualquier `noindex` o canonical de esas URLs).
- Una combinación de filtros que se quiera indexar se promueve a **página con URL propia** (ranking o marca x tipo) y deja de ser un filtro.

## 6. Control de la explosión combinatoria (D-020)

### 6.1 Umbrales por familia

Los umbrales son **heurísticas fijadas en esta tarea**, no datos. "Ficha E1" = ficha publicada e indexable. El contenido mínimo propio de cada familia (umbral de unicidad) lo fija F1.5; aquí solo se fija el recuento mínimo.

| Familia | Patrón | Pasa a E1 si | Si no cumple | Notas |
|---|---|---|---|---|
| Ficha | P-01 | Campos obligatorios verificados con fuente y fecha (lista en F1.6) + puntuación y veredicto con base declarada (D-017) + umbral de unicidad de F1.5 | E3 (borrador fuera del build) | Es la unidad de unicidad: sin ficha verificada no hay página |
| Categoría | — | 5 fichas E1 o más | E3 | Se enlaza desde la portada |
| Hub de tipo | — | 3 fichas E1 del tipo + versión mínima del hub (D-020) | 1-2 fichas: E2. 0 fichas: E3 | Versión mínima: introducción editorial, listado y ranking del tipo |
| Marca x tipo | P-05 | 2 fichas E1 de esa marca y tipo | E3 | Con 1 ficha es la propia ficha, no una página de patrón |
| Marca | — | 3 fichas E1 de la marca | E3 | La marca se muestra como texto en la ficha |
| Ranking por uso | P-04 | 3 fichas E1 adecuadas al uso según criterio de F1.5 | E3 | Uso no asignado a ningún modelo hasta F1.5 |
| Ranking por calificador | P-15 | Facetas pobladas con dato verificado + 3 fichas E1 que cumplan el calificador | E3 | D-020: hubs tras las primeras fichas y rankings |
| Ranking de marcas por origen o nivel | P-12 | 5 fichas E1 por grupo con la faceta verificada | E3 | Hoy 0 de 10 con origen verificado |
| Tipo x acero | P-14 | 2 fichas E1 del tipo con acero declarado por el fabricante | E3 | `damasco` exige dato verificable |
| Comparativa de modelos | P-03 | Ambas fichas E1 + mismo tipo o demanda observada + diferencias medibles en el número de campos que fije F1.5 | E3 | **Default E3.** Orden alfabético del slug |
| Comparativa de tipos | K2 | Artículo redactado y revisado por el autor que cumpla el umbral de F1.5 + hubs de ambos tipos existentes (E1 o E2) | E3 | `cocinero-vs-santoku`: K2, P1 |
| Alternativas a un modelo | P-16 | **No tiene URL.** Es una sección de la ficha (mínimo 3 alternativas del mismo tipo) | — | Sin señal de demanda observada; evita 6 páginas casi duplicadas de las fichas |
| Artículo de blog | P-06, P-09 | Redactado y revisado por el autor; cumple checklist de F1.5 | no se publica | No hay generación en lote |

**Combinaciones que nunca generan página** (patrones NO PASA de F1.3): [modelo] precio (P-02), [tipo] [medida] (P-07), [tipo] [tienda] (P-08), [servicio local] (P-11), [modelo] original / es bueno (P-13) y [tipo] para qué sirve como lote (P-06). Accesorios de afilado (P-10) están aplazados a oleadas posteriores (D-014).

**Regla general:** más de dos facetas combinadas en una URL no genera página. Las únicas combinaciones de facetas con página propia son marca x tipo y tipo x acero.

### 6.2 Aplicación a los datos de hoy (piloto de 10 modelos)

Supone que cada ficha cumple sus campos verificados. **Hoy ninguna lo hace** (limitación 9 de F1.3): las páginas publicables ahora son 0.

| Familia | Candidatas del piloto | E1 con recuento | E2 | E3 (no se generan) |
|---|---|---|---|---|
| Ficha | 10 | 9 | — | 1 (nº 2, sin clasificar) |
| Categoría | 1 | 1 | — | — |
| Hub de tipo | 3 (cocinero, jamonero, santoku) | 1 (cocinero, 6 fichas) | 2 (jamonero con 2; santoku con 1) | — |
| Marca x tipo | 2 con 2 fichas (Arcos cocinero: nº 1 y 7; Arcos jamonero: nº 3 y 6); Arcos santoku tiene 1 | 2 | — | 1 (Arcos santoku) |
| Marca | 5 | 1 (Arcos, 6 modelos; uno sin clasificar no cuenta: 5 fichas E1) | — | 4 (1 ficha cada una) |
| Ranking por uso | hasta 3 posibles (verduras, cebolla, carne) | 0 (uso sin asignar) | — | todos |
| Ranking por calificador | 7 calificadores observados | 0 (facetas sin poblar) | — | todos |
| Tipo x acero | 0 | 0 | — | todos |
| Comparativa de modelos | hasta 16 pares del mismo tipo | 0 hasta que F1.5 fije el criterio | — | todos |
| Comparativa de tipos | 1 (cocinero frente a santoku) | 1 (si el artículo se redacta) | — | — |
| **Total E1 (máximo)** | | **15** (9 fichas + 1 categoría + 1 hub de tipo + 2 marca x tipo + 1 marca + 1 comparativa de tipos) | 2 | |

Observaciones sobre la tabla:
- La marca Arcos tiene 6 modelos pero el nº 2 no está clasificado, por lo que solo 5 fichas E1 cuentan para su umbral (3). Sigue cumpliéndolo.
- El par con señal de P-03 ("arcos maitre vs universal") es entre tipos distintos y su serie "Universal" es ambigua (hay un Universal cocinero y un Universal jamonero). Se resuelve al fichar.

### 6.3 Consecuencias para la oleada 1 (sin decidir)
1. **Las cabezas de mayor volumen no tienen hub indexable el primer día.** Jamonero (Planner 1 mil-10 mil, Ubersuggest 4,4K) tiene 2 fichas y santoku (Planner 1 mil-10 mil, Ubersuggest 2,9K) tiene 1. Con el umbral de 3 fichas, ambos hubs quedan en E2. Sus búsquedas informativas (K1, K2) se cubren con artículos de blog (E1), que no compiten con el hub mientras este sea E2.
2. **Las vías para que un hub pase a E1** son alcanzar 3 fichas del tipo o rebajar el umbral. Ambas son decisiones de F1.7 y del autor (sección 9, punto 3).
3. **La cola de marca sí se sirve desde el principio:** Arcos x jamonero (la KW "jamonero arcos" tiene Planner 1 mil-10 mil) y Arcos x cocinero son E1 con 2 fichas cada una.
4. **El resto de rankings no existen aún** por falta de uso, origen y nivel poblados (F1.5 y datos de fabricante).

## 7. Enlazado interno

### 7.1 Mapa de enlaces obligatorios

| Desde | Hacia | Forma |
|---|---|---|
| Ficha | Hub de tipo y marca x tipo (si E1) | Migas + bloque "más cuchillos de este tipo" |
| Ficha | 3 alternativas del mismo tipo | Sección de la ficha (sustituye a P-16 como URL) |
| Ficha | Rankings y comparativas E1 que la incluyen | Bloque "dónde aparece" |
| Ficha | Artículo relevante (por ejemplo, afilado o aceros) | Enlace contextual, máximo 2 |
| Hub de tipo | Todas las fichas del tipo, marca x tipo, ranking del tipo, artículo "para qué sirve" y comparativa de tipos | Listado + bloque de guías |
| Marca x tipo | Fichas de la marca en ese tipo, hub de tipo | Listado |
| Ranking | Fichas incluidas (ancla: marca y modelo), hub de tipo, `/metodologia/` | Listado + criterio |
| Comparativa de modelos | Las dos fichas, hub de tipo | Cabecera + tabla |
| Artículo | Hub de tipo o ficha solo si aportan al lector; de vuelta, el hub enlaza al artículo | Enlace contextual |
| Todas | Aviso de afiliación (donde haya enlaces de compra) | Pie y bloque junto al enlace |

### 7.2 Reglas
- **Anclas descriptivas y variadas:** marca y modelo, tipo, criterio. No repetir una ancla exacta de palabra clave en todos los enlaces a una página.
- **Reciprocidad:** si el artículo enlaza a un hub o ficha, el hub o la ficha enlaza al artículo cuando es el recurso que responde su pregunta principal.
- **Sin huérfanas:** toda página E1 tiene al menos 2 enlaces desde otras E1 (principio 4).
- **Sin enlaces a E3.** Los enlaces a E2 solo desde menú, migas y el listado de su categoría.
- **Una página, un objetivo.** Los artículos que responden "para qué sirve el santoku" y "qué es mejor, santoku o chef" enlazan entre sí y con el hub, y no repiten el mismo contenido.
- **Profundidad máxima 3 clics:** Portada > Hub de tipo > Ficha (2 clics), Portada > Blog > Tema > Artículo (3 clics).

## 8. Preparación para categorías futuras

- **Mismo patrón:** `/{categoria}/{tipo}/`, fichas en `/ficha/`, marcas en `/marca/`. Cada categoría define su propia lista de tipos y usos; marca, acero, origen, precio y nivel se heredan.
- **Slugs de categoría reservados (D-013):** `cuchillos-de-cocina`, `navajas`, `cuchillos-outdoor`, `cuchillos-de-caza`, `cuchillos-edc`, `piedras-de-afilar`, `accesorios`. "Japoneses" queda pendiente (sección 9, punto 2).
- **Una ficha, una categoría principal.** Navajas y EDC se solapan en la práctica; se resuelve al abrir esas oleadas, aplicando el principio 1 de `TAXONOMIA.md` y sin duplicar URLs.
- **Piedras de afilar y accesorios** no son cuchillos: tipos, facetas y campos propios (F1.6). Por eso el prefijo `/ficha/` es neutro.
- **Ampliar es añadir datos:** una categoría nueva no cambia el patrón ni las reglas de umbral. Empieza con todas sus páginas en E3 hasta cumplir el recuento.
- **Fuera de la oleada 1:** `/marca/` mezcla categorías (una marca con fichas en varias). Si una marca es dominante en una sola, la ficha de marca sigue siendo única y lista por categoría.

## 9. Decisiones propuestas para aprobar por el autor

| Nº | Decisión | Propuesta | Alternativa y coste |
|---|---|---|---|
| 1 | Ficha con URL plana `/ficha/{slug}/` | Plana, con la jerarquía en migas | Con tipo en la ruta (`/cuchillos-de-cocina/jamonero/{slug}/`): más señal temática, pero redirige cada cambio de tipo |
| 2 | Categoría "japoneses" (D-013) | Colección transversal, sin rama propia | Rama propia: duplica fichas con santoku, nakiri y origen Japón |
| 3 | Umbral de 3 fichas para el hub de tipo | Mantenerlo (default-deny, R-11) | Rebajar a 2 para tipos con rango de Planner superior a 1 mil: serviría al hub jamonero, pero con 2 fichas el contenido propio es escaso |
| 4 | Sinónimo cocinero / cebollero / chef | Un tipo, slug a fijar tras comparar SERP | Dos tipos: riesgo de canibalizar la misma intención |
| 5 | Alternativas (P-16) como sección, no como URL | Sección de la ficha | Página propia: 6 páginas casi duplicadas sin demanda observada |

## 10. Limitaciones y riesgos (sin matizar)

1. **Los umbrales (5, 3, 3, 2, 3 y 5 fichas) son criterios de diseño sin contraste empírico.** Pueden ser demasiado estrictos (se pierde tráfico) o demasiado laxos (R-11). Se revisan con datos de indexación; hoy no existe Search Console.
2. **Con 10 fichas el programático casi no despega:** máximo 15 páginas E1 de catálogo (sección 6.2), 0 publicables hasta que haya datos verificados. El volumen de SEO programático de D-020 depende de ampliar fichas y de F1.5/F1.6, no de la arquitectura.
3. **`noindex` de larga duración en hubs E2.** Un hub E2 prolongado (jamonero, santoku) puede dejar de transmitir enlaces. Mitigado por la regla de no depender de E2, no verificado.
4. **Filtros con fragmento `#`:** el usuario no puede compartir ni guardar un filtro por URL. Se acepta a cambio de no abrir superficie de rastreo.
5. **Señales de demanda provisionales** (limitaciones de F1.3): los slugs de tipo, los usos y la prioridad de hubs se apoyan en rangos amplios y en autocompletado de una sola consulta.
6. **URL plana de ficha:** pierde señal temática en la ruta. Se compensa con el slug (marca-serie-tipo-medida), las migas y el enlazado.
7. **Posible canibalización** entre hub de tipo y artículo "para qué sirve" para la misma cabeza ("cuchillo santoku"). Mitigado por la regla de una intención por URL y por el enlazado entre ambos; se vigila con Search Console cuando exista.
8. **Complejidad técnica real.** La función de indexabilidad por build, los sitemaps por familia y los redireccionamientos de slug son trabajo de desarrollo no trivial en Next.js. Se detalla al planificar el desarrollo, no aquí.
9. **Sin asesoramiento jurídico** sobre páginas legales ni aviso de afiliación: solo se reservan las URLs.

## 11. Fuentes

- Google Search Central, "Managing crawling of faceted navigation URLs" (developers.google.com/crawling/docs/faceted-navigation), consultada el 2026-11-08 en fragmentos de resultados de búsqueda.
- Google Search Central Blog, "Crawling December: Faceted navigation" (developers.google.com/search/blog/2024/12/crawling-december-faceted-nav), consultada el 2026-11-08 en fragmentos de resultados de búsqueda.

## 12. Control de cambios

- 2026-11-08: versión inicial (F1.4). Propuesta pendiente de aprobación del autor.
