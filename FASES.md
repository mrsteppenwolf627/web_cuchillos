# FASES.md · Web de cuchillos (catálogo + blog)

> Documento maestro del proyecto ("la biblia"). Se actualiza al cerrar cada tarea.
> Método: 1 chat = 1 tarea. El chat de planificación es independiente.
> REGLA OBLIGATORIA: toda tarea termina con actualización de este archivo, commit y push a GitHub.

Última actualización: 2026-11-08 (F0.3: 2FA confirmado en las 3 cuentas; pendiente solo gestor de contraseñas y ubicación de los códigos de recuperación)

## Estado global

| Fase | Nombre | Estado |
|---|---|---|
| 0 | Estructura del proyecto | EN CURSO (F0.1 y F0.2 hechas; F0.3 ejecutada; falta confirmar gestor de contraseñas para cerrar la Fase 0) |
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
Estado: EJECUTADA, PENDIENTE CONFIRMACIÓN GESTOR DE CONTRASEÑAS (2026-11-08)
Progreso 2026-11-08:
- [x] Paso 1: plantilla de tarea en docs/PROCESO.md (apartado 1).
- [x] Paso 2: definición de "hecho" (apartado 2) y convención de nombres de chat (apartado 4).
- [x] Paso 3: convención de commits (apartado 5).
- [~] Paso 4: inventario creado en docs/ACCESOS.md. Verificados GitHub, Vercel (proyecto web_cuchillos, Hobby) y Supabase (proyecto web_cuchillos, Free, eu-central-1). 2FA confirmado por el autor el 2026-11-08 en GitHub y Vercel (códigos de recuperación) y Supabase (Google Authenticator). Pendiente del autor: confirmar gestor de contraseñas en las tres cuentas, mover los códigos de recuperación fuera de la carpeta del proyecto (hoy solo los protege `.gitignore`) y crear respaldo del 2FA de Supabase (R-09, asumido sin respaldo por ahora). Registrador, Search Console, analítica y afiliación: NO CREADOS (dependen de dominio y de herramientas sin elegir).
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
- [ ] Push de cierre realizado según la regla obligatoria (push de F0.3 hecho; el cierre de Fase 0 queda para tras resolver los pendientes)
- [ ] ACCESOS.md con 2FA (confirmado) y gestor de contraseñas (pendiente) confirmados por el autor
