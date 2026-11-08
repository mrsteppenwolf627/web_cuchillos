# PROCESO · Método de trabajo

Complementa `CLAUDE.md` (reglas para Claude Code) y `FASES.md` (fuente de verdad del plan). Si algo de este documento contradice `FASES.md`, manda `FASES.md`.

## 1. Plantilla de tarea

Cada tarea se define en `FASES.md` con estos campos y se ejecuta en un chat propio (1 chat = 1 tarea).

```markdown
## Fx.y · Nombre de la tarea
Estado: PENDIENTE | EN CURSO | HECHO (fecha)
Objetivo: una frase; qué queda resuelto al terminar.
Entradas: documentos, datos, accesos o tareas previas necesarias.
Pasos:
1. ...
Salida: archivos o resultados concretos y dónde viven.
Cierre: condiciones verificables para dar la tarea por hecha.
Fuera de alcance: lo que NO se hace en esta tarea (opcional, recomendado).
```

Reglas de la plantilla:
- Cada paso es verificable (se puede comprobar si está hecho o no).
- La salida nombra rutas de archivo, no intenciones.
- El cierre incluye siempre la regla obligatoria (apartado 3).
- Una tarea no se abre si sus entradas no existen.

## 2. Definición de "hecho"

Una tarea está HECHA solo si se cumplen todas:
1. Todos los pasos están completados o descartados con motivo escrito.
2. La salida existe en el repositorio y cumple el criterio de cierre de la tarea.
3. Los documentos afectados son coherentes entre sí (`README`, `CONTEXT`, `DECISIONS`, `FASES`, `CLAUDE`).
4. Ningún secreto, `.env*` (salvo `.env.example`) ni dato de licencia dudosa en el commit.
5. `FASES.md` actualizado: estado, fecha de última actualización y criterios.
6. Commit convencional y push a `main` verificados en GitHub.

Lo que no se pudo verificar se deja marcado como pendiente de verificación; no se da por hecho.

## 3. Cierre obligatorio de tarea

1. Actualizar `FASES.md`.
2. Commit con formato convencional (apartado 5).
3. Push a `main` y comprobar que el commit aparece en GitHub.

## 4. Nombre de los chats

Formato: `Fx.y · Nombre corto de la tarea`, igual al de `FASES.md`.

Ejemplos: `F0.3 · Proceso y accesos`, `F2.3 · Plantilla de ficha`.

El chat de planificación se llama `PLAN · Fases` y solo define o revisa fases; no ejecuta tareas.

## 5. Convención de commits

Formato: `tipo: descripción en minúscula, imperativo, sin punto final`. Opcional: `tipo(ámbito): ...`.

| Tipo | Uso |
|---|---|
| `feat` | Funcionalidad nueva de la web |
| `fix` | Corrección de un error |
| `docs` | Documentación del proyecto (`README`, `FASES`, `docs/`, etc.) |
| `content` | Fichas y artículos en `content/` |
| `data` | Datos del catálogo en `data/` (solo versionables) |
| `chore` | Configuración, dependencias, mantenimiento |

Un commit por unidad lógica. Nunca force push ni reescritura de historial sin confirmación explícita.

## 6. Registro de riesgos inicial

Origen: `CONTEXT.md`. Probabilidad (P) e impacto (I) son estimaciones de criterio, no medidas: Alta / Media / Baja.

| ID | Riesgo | P | I | Mitigación | Estado |
|---|---|---|---|---|---|
| R-01 | Vercel Hobby limita el uso comercial; una web con afiliación podría incumplir los términos | Alta | Alta | Revisar los términos vigentes antes de publicar con afiliación; plan alternativo de hosting o plan de pago | Asumido por el autor el 2026-11-08: si procede, pasará al plan Pro (importe indicado por el autor: 20 USD, sin verificar contra la tarifa vigente). Términos de uso comercial sin comprobar |
| R-02 | Supabase free se pausa por inactividad (en la organización ya hay proyectos pausados) | Media | Media | Gestionado por el autor (actividad periódica o reactivación) | Asumido |
| R-03 | Sin copia de la base de datos fuera de GitHub (`data/dumps/` está ignorado por git) | Media | Alta | Definir copia periódica externa antes de tener datos propios valiosos | Abierto, sin resolver |
| R-04 | Penalización de buscadores por contenido masivo generado con IA | Media | Alta | Contenido original, diferenciado, con datos verificables y supervisión del autor; crecimiento por oleadas | Abierto |
| R-05 | Competencia alta en afiliación de producto | Alta | Media | Nicho en español, calidad de fichas y navegación, vías de monetización complementarias | Asumido |
| R-06 | Fuga de datos o secretos por repositorio público | Baja | Alta | Secret scanning y push protection activos (D-011); `.gitignore`; no subir `.env*` ni datos dudosos | Mitigado, mantener |
| R-07 | Scraping de fuentes con licencia o términos de uso problemáticos | Media | Media | Solo fuentes públicas/legales; datos crudos fuera del repo (`data/raw/` ignorado); revisar términos de cada fuente | Abierto |
| R-08 | Hito de ingresos a ~3 meses no se cumple | Media | Media | Es orientativo; el posicionamiento es de largo plazo; revisar al cierre de cada oleada | Asumido |
| R-09 | Supabase con un único autenticador (Google Authenticator) y sin códigos de recuperación: perder el móvil bloquea la cuenta de forma permanente | Baja | Alta | Pendiente: segundo autenticador independiente del móvil (gestor con 2FA o clave secreta guardada). Mientras tanto, cuidado del móvil | Asumido por el autor el 2026-11-08, respaldo pendiente |
| R-10 | Las condiciones de uso de Amazon.es (versión 2025-11-28) limitan el uso a fines personales no comerciales y prohíben compilar listas de productos o precios, además de robots y extracción. La web es comercial y F1.2 lee rankings de Amazon.es. Con Claude in Chrome se usa la sesión iniciada del autor: una restricción podría afectar a su cuenta de Amazon | Media | Media | Lectura manual y puntual (2 páginas de ranking en F1.2); sin extracción automática; en el repo solo posiciones, recuentos y bandas de precio; ver D-019. Sin asesoramiento jurídico | Asumido por el autor el 2026-11-08 (D-019) |
| R-11 | SEO programático genera páginas de poco valor o casi duplicadas y activa las políticas de contenido escalado de los buscadores | Media | Alta | Prueba de viabilidad por patrón (F1.3), umbral de unicidad por página (F1.5), noindex para lo que no lo cumpla (F1.4), lanzamiento por lotes y revisión de indexación | Abierto (D-020) |

Revisión: al cerrar cada fase. Un riesgo nuevo se añade al final con el siguiente ID; uno resuelto no se borra, se marca como cerrado.
