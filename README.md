# Web de cuchillos

Catálogo/directorio de cuchillos (una ficha de producto por cuchillo, clasificada por tipo, uso y otros criterios) más un blog (técnicas, afilado, información). Mercado: España, castellano. Objetivo: ingresos pasivos, principalmente por afiliación desde las fichas, con SEO/GEO como canal de adquisición.

> Estado: Fase 0 (estructura del proyecto). Todavía no hay código de producto, dominio ni contenido.

## Documentos

| Archivo | Contenido |
|---|---|
| [FASES.md](FASES.md) | Documento maestro: fases, tareas, estado y criterios de cierre. Fuente de verdad del plan. |
| [CONTEXT.md](CONTEXT.md) | Visión, alcance, stack, restricciones, supuestos y riesgos. |
| [DECISIONS.md](DECISIONS.md) | Registro de decisiones con fecha y motivo. |
| [CLAUDE.md](CLAUDE.md) | Reglas de trabajo para Claude Code. |

## Estructura

```
docs/      Documentación auxiliar (plantillas, proceso)
content/   Contenido editorial (fichas, artículos)
data/      Datos del catálogo (los volcados pesados no se versionan)
src/       Código de la aplicación
```

## Arrancar en local

Aún no hay aplicación que ejecutar (no existe `package.json`). Requisitos del entorno ya fijados:

- Git y GitHub CLI (`gh`) autenticado.
- Node 24 (ver `.nvmrc`) y npm. No se usan pnpm ni yarn.
- Variables de entorno: copiar `.env.example` a `.env.local`. Nunca se versiona ningún `.env*` salvo `.env.example`.

Las instrucciones de instalación y ejecución se añadirán aquí cuando se cree la aplicación.

## Método de trabajo

1 chat = 1 tarea. Cada tarea tiene objetivo, entradas, salida y criterio de cierre definidos en `FASES.md`. Toda tarea termina con la actualización de `FASES.md`, commit y push.

## Repositorio público

El repositorio es público (ver `DECISIONS.md`, D-009). No se suben secretos, datos con licencia dudosa ni borradores sensibles.
