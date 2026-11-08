# FASES.md · Web de cuchillos (catálogo + blog)

> Documento maestro del proyecto ("la biblia"). Se actualiza al cerrar cada tarea.
> Método: 1 chat = 1 tarea. El chat de planificación es independiente.
> REGLA OBLIGATORIA: toda tarea termina con actualización de este archivo, commit y push a GitHub.

Última actualización: 2026-11-08 (F0.1 paso 1 verificado en Windows; falta gh)

## Estado global

| Fase | Nombre | Estado |
|---|---|---|
| 0 | Estructura del proyecto | EN CURSO (F0.1 hecha; F0.2 y F0.3 pendientes) |
| 1+ | Por definir (una a una, en el chat de planificación) | — |

---

# FASE 0 · Estructura del proyecto
Estado: EN CURSO · Duración estimada: 3-4 h · Chats: 3

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
Estado: HECHO (2026-11-08), con una excepción documentada en el paso 1
Progreso 2026-11-08:
- [x] Paso 2: git init, rama main.
- [x] Paso 3: .gitignore.
- [x] Paso 4: .env.example vacío.
- [x] Paso 5: .nvmrc = 24. Basado en el Node que reporta la app de escritorio de Claude (v24.22.0), que no es necesariamente el Node instalado en el sistema del autor: confirmar con `node -v`.
- [x] Paso 6: repo https://github.com/mrsteppenwolf627/web_cuchillos creado, remoto origin añadido, historial subido a main. CAMBIO DE DECISIÓN 2026-11-08: el repo pasó de PRIVADO a PÚBLICO por orden expresa del autor (facilita el trabajo; secret scanning no existe en repos privados del plan actual). Consecuencia: todo lo que se suba es visible; nada de secretos, datos con licencia dudosa ni borradores sensibles.
- [~] Paso 1: verificado en el equipo Windows del autor el 2026-11-08: git 2.52.0.windows.1 OK; Node v24.12.0 OK (coincide con .nvmrc = 24); npm 11.8.0 OK; pnpm/yarn no instalados (se usa npm); remoto origin, `git status` limpio y sincronizado con origin/main, user.name y user.email configurados. FALTA: GitHub CLI (gh) no instalado (no está en PATH ni en las rutas habituales), por lo que `gh auth status` no se puede verificar. Pendiente: instalar gh y autenticarlo (con confirmación del autor) y volver a comprobar `gh --version` y `gh auth status`.
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
Estado: PENDIENTE
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
Estado: PENDIENTE
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
- [ ] Repo privado sincronizado, primer commit en main
- [ ] README, CONTEXT, FASES, DECISIONS, CLAUDE.md creados y coherentes
- [ ] Plantilla de tarea validada
- [ ] Entorno local verificado
- [ ] Push de cierre realizado según la regla obligatoria
