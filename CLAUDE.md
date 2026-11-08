# CLAUDE.md · Reglas para Claude Code

Proyecto: web de cuchillos (catálogo + blog). Contexto en `CONTEXT.md`, plan en `FASES.md`, decisiones en `DECISIONS.md`.

## Fuente de verdad
`FASES.md` es la fuente de verdad del plan. Si una instrucción o una tarea lo contradice, avisa antes de actuar.

## Método de trabajo
- 1 chat = 1 tarea. Ejecuta la tarea asignada con su objetivo, entradas, salida y criterio de cierre según `FASES.md`.
- No replanifiques: existe un chat de planificación aparte.
- No amplíes el alcance. Si detectas algo fuera de alcance, señálalo sin ejecutarlo.

## Cierre de tarea (OBLIGATORIO)
1. Actualizar `FASES.md` (estado, fecha de última actualización, criterios).
2. Commit con formato convencional: `feat`, `fix`, `docs`, `content`, `data`, `chore`.
3. Push a `main` y verificar que llegó a GitHub.

## Seguridad
- El repositorio es PÚBLICO. Nunca subir secretos, archivos `.env*` (salvo `.env.example`), datos con licencia dudosa ni borradores sensibles.
- No ejecutar acciones destructivas o irreversibles (borrados, `reset --hard`, force push, migraciones destructivas) sin confirmación explícita.

## Contenido
- Fichas y artículos originales y diferenciados; nunca copia de descripciones de fabricante.
- Apoyados en datos verificables. Si un dato no es verificable, indicarlo.
- Enlaces de afiliación siempre con aviso de afiliación visible.

## Estilo de trabajo
- Respuestas concisas, densas y ordenadas por prioridad, sin relleno.
- Señalar de forma explícita lo técnicamente difícil, arriesgado o dudoso. No minimizar la complejidad.

## Entorno
Node 24 (`.nvmrc`), npm. Stack: Next.js + Supabase + Vercel Hobby.

## Estructura
`docs/` documentación auxiliar · `content/` contenido editorial · `data/` datos (`data/raw/` y `data/dumps/` ignorados por git) · `src/` código.
