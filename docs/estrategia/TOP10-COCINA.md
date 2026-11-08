# TOP 10 DE CUCHILLOS DE COCINA POR POPULARIDAD (F1.2)

Fecha de consulta: 2026-11-08 · Método: `METODO-INVESTIGACION.md` (F1.1) · Evidencias: `data/investigacion/evidencias.csv` (IDs EV-xxxx) · Datos: `data/estrategia/top10-cocina.csv`
Estado: resultado PROVISIONAL según el método. Mide popularidad de venta en Amazon.es, no calidad. Lee primero la sección 5.
Repositorio público: solo marca, modelo, tamaño, posiciones, recuentos y bandas de precio. Sin descripciones, imágenes ni reseñas de terceros (R-07).

## 1. Resultado

| # | Marca | Modelo | Formato | Tipo | Precio (banda) | Puntos | A | B | C | D | Confianza | Evidencias |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Arcos | Universal (cuchillo cocinero) | 200 mm | chef | 10-25 € | 51,7 | 3 | 2 | 0 | 0 | media | EV-0001, 0002 |
| 2 | Arcos | Cuchillo de cocina negro (serie sin confirmar) | 150 mm | cocina | 10-25 € | 51,7 | 3 | 2 | 0 | 0 | baja | EV-0003, 0004 |
| 3 | Arcos | Latina (jamonero) | 250 mm | jamonero | <10 € | 51,7 | 3 | 2 | 0 | 0 | media | EV-0005, 0006 |
| 4 | HOSHANHO | Cuchillo chef, mango pakkawood | 200 mm | chef | 25-50 € | 51,7 | 3 | 2 | 0 | 0 | media | EV-0007, 0008 |
| 5 | Arcos | Maitre (santoku) | 170 mm | santoku | 10-25 € | 45,0 | 2 | 2 | 0 | 1 | baja | EV-0009, 0010 |
| 6 | Arcos | Universal (jamonero alveolado) | 240 mm | jamonero | 10-25 € | 43,3 | 3 | 1 | 0 | 0 | media | EV-0011, 0012 |
| 7 | Arcos | Serie 2900 (chef) | 200 mm | chef | 10-25 € | 43,3 | 3 | 1 | 0 | 0 | media | EV-0013 a 0016 |
| 8 | PAUDIN | Cuchillo chef, acero al carbono | 200 mm | chef | 25-50 € | 40,0 | 2 | 2 | 0 | 0 | media | EV-0017, 0018 |
| 9 | Matsato | Cuchillo cocinero, acero japonés | 27,8 cm (sin aclarar) | chef | 25-50 € | 40,0 | 2 | 2 | 0 | 0 | media | EV-0019, 0020 |
| 10 | MOSFiATA | Cuchillo cebollero con afilador y funda | 200 mm | chef | 25-50 € | 40,0 | 2 | 2 | 0 | 0 | media | EV-0021, 0022 |

Las bandas de precio son tramos gruesos a partir de lo visto en Amazon.es el 2026-11-08; no son precios de referencia.

## 2. Cómo se ha aplicado el método

Fuentes (pesos de F1.1: A 35 %, B 25 %, C 25 %, D 15 %; puntos = Σ peso × nota / 3 × 100):
- **A, ventas:** posición en los rankings de Amazon.es "Cuchillos de cocinero" y "Cuchillos de cocina" (pág. 1 de cada uno, lectura manual).
- **B, reseñas:** número de valoraciones de la ficha listada en esos rankings.
- **C, búsqueda:** Google Trends, España, 12 meses (dos comparaciones manuales).
- **D, medios:** un único medio español (El Independiente, sección De Tiendas), visto solo en resultados de búsqueda.

Reglas de nota que fija esta tarea (F1.1 no las definía; son heurísticas, no datos):
- A: posiciones 1-5 = 3; 6-15 = 2; 16-30 = 1; fuera = 0.
- B: ≥10.000 reseñas = 3; 2.000-9.999 = 2; 500-1.999 = 1; <500 = 0.
- C: **0 para todos los modelos.** Trends no da señal a nivel de modelo (ver sección 5). Como se aplica igual a todos, no altera el orden; el máximo alcanzable es 75 puntos.
- D: 2 si el medio cita ese modelo; 1 si cita otro producto de la misma línea; 0 si no lo cita.
- Condición de entrada (F1.1): evidencia en dos fuentes distintas, una de ellas A, B o C. Los diez la cumplen con A y B.
- Desempate (regla añadida aquí): mejor posición en A y después más reseñas. Las posiciones de dos categorías distintas no son del todo comparables.
- Tipo y formato: la unidad es el modelo individual (marca + serie + tamaño). Quedan fuera sets, bloques, soportes, accesorios y cuchillos infantiles; los sets se listan aparte porque pesan en ventas (sección 4).
- Dos fichas de la misma serie y tamaño (Arcos 2900, variantes de color) cuentan como un modelo, con las reseñas sumadas.

## 3. Evidencia de popularidad (resumen)

- Ranking "Cuchillos de cocinero": Arcos Universal 200 mm es el nº 1; Arcos 150 mm, el nº 3; HOSHANHO, el nº 5; Victorinox Fibrox, el nº 16; Wüsthof Classic Ikon, el nº 30.
- Ranking "Cuchillos de cocina": los jamoneros de Arcos ocupan los puestos 3 y 4, y el santoku Maitre, el 6.
- Reseñas: el cuchillo individual con más valoraciones observado es Victorinox Fibrox (14.479); le siguen Matsato (9.919) y PAUDIN (8.438).
- Trends, "cuchillo arcos": media ≈35 sobre 100 y máximo hacia dic-2025. "cuchillo victorinox" solo muestra dos picos aislados; "cuchillo wüsthof", "cuchillo zwilling" y "cuchillo tefal" ≈0. Lectura visual, confianza baja.
- Medio: El Independiente cita 11 productos o líneas (EV-0031 a 0041), entre ellos Kai Shun, Global G-3, IKEA 365+, WMF Grand Gourmet y Zwilling Professional S.

## 4. Candidatos descartados

| Candidato | Puntos | Motivo |
|---|---|---|
| Tefal EverSharp santoku 165 mm | 36,7 | Queda 11º. Empata con Victorinox Fibrox y gana el desempate por posición en A (8 frente a 16). Es el primer descartado. |
| Victorinox Fibrox 200 mm | 36,7 | Queda 12º por desempate, pese a tener el mayor nº de reseñas individual. Su resultado depende de la escala A elegida (frontera en el puesto 15). |
| Tefal Ice Force 150 mm | 33,3 | Pocas reseñas (248). El medio lo cita. |
| Wüsthof Classic Ikon 200 mm | 20,0 | Posición 30 y 1.569 reseñas; sin cita en el medio. |
| Kai Shun, Global G-3, IKEA 365+, WMF Grand Gourmet, Zwilling Professional S, 3 Claveles Sakura, Tramontina Dynamic | n/c | Solo aparecen en el medio (D). No cumplen la condición de entrada. No consta que sean poco vendidos: no se observó su posición ni reseñas, porque se leyó solo la pág. 1 de dos categorías y IKEA no vende en Amazon. |
| Sets (Amazon Basics 14 pzas, Tramontina Plenus 4 pzas, MasterChef 5 pzas, Arcos Nova mondadores de 3 y 6 pzas, entre otros) | n/c | No son un modelo individual (política de tipo, sección 2). Tienen muchas reseñas y pesan en ventas. |
| Bloques, barras magnéticas, soportes, cuchillos infantiles | n/c | No son cuchillos de cocina de uso adulto o son accesorios. |
| Resto de fichas de las dos páginas leídas | ≤31,7 | Puntúan por debajo del décimo puesto. |

## 5. Limitaciones y riesgos (sin matizar)

1. **El resultado refleja ventas baratas de Amazon.es.** Seis de los diez son Arcos y cuatro más son marcas de venta casi exclusiva en Amazon (HOSHANHO, PAUDIN, Matsato, MOSFiATA). Entre los diez no hay ninguna marca premium. Es el sesgo que F1.1 ya advertía (limitación 3 del método), ahora medido. Con los datos recogidos no se puede decir si falta Victorinox, Zwilling o Wüsthof por popularidad real o por el diseño de la medición.
2. **Condiciones de uso de Amazon.es (R-10).** Se leyeron el 2026-11-08 (versión del 2025-11-28). La licencia es para fines personales no comerciales; prohíbe el uso comercial y compilar listas de productos o precios, además de robots y extracción. La web es comercial. Tras exponérselo, el autor indicó en el chat que se continuara con Claude in Chrome (D-019); no se ha obtenido asesoramiento jurídico. Mitigación aplicada: dos páginas de ranking, sin extracción automática, y en el repo solo posiciones, recuentos y bandas de precio. La sesión de Chrome estaba iniciada con la cuenta del autor: una restricción por incumplimiento podría afectar a esa cuenta. Para la lectura de las condiciones y la prueba de acceso se usó antes el navegador integrado, sin sesión.
3. **Fuente C inutilizable a nivel de modelo.** Los términos de modelo exacto no alcanzan volumen en Trends. A nivel de marca, "arcos" es ambiguo y la lectura del gráfico fue visual. No se usó Ubersuggest ni el autocompletado.
4. **Fuente D insuficiente.** Un solo medio, con enlaces de afiliación declarados, visto en fragmentos de resultados de búsqueda y no leído completo. El método pide listas de varios medios.
5. **Reseñas.** Dos fichas distintas de Arcos (150 mm y santoku Maitre) muestran exactamente 4.199 reseñas: probable agrupación de variantes. Por eso su confianza es baja. Hay variantes agrupadas o reseñas incentivadas en el conjunto del ranking (sesgo B del método).
6. **Datos no verificables:** la serie del Arcos de 150 mm y si los 27,8 cm del Matsato son longitud total o de la hoja. Antes de crear fichas hay que contrastarlos con la ficha técnica del fabricante.
7. **Cobertura.** Solo la pág. 1 de dos categorías (2 de las ~30 páginas por sesión que admite el método). Ninguna posición se ha recontrastado en otro día. Las posiciones de Amazon cambian con frecuencia.
8. **Heurísticas.** Las escalas de nota A y B, la regla D y el desempate los fijé al ejecutar la tarea. Con otras escalas el orden cambia; el caso más sensible es Victorinox Fibrox frente a Tefal EverSharp.

## 6. Control de cambios

- 2026-11-08: versión inicial (F1.2).
