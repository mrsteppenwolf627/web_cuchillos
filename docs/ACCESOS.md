# ACCESOS · Inventario de cuentas y servicios

El repositorio es PÚBLICO. Este archivo no contiene contraseñas, tokens, claves, correos ni identificadores privados. Solo qué servicios hay, para qué y su estado de seguridad.

Última actualización: 2026-11-08

## Inventario

Estados: VERIFICADO (comprobado y fecha), POR CONFIRMAR (lo debe confirmar el autor), NO CREADO (aún no existe).

| Servicio | Uso | Cuenta | Estado | 2FA | Gestor de contraseñas |
|---|---|---|---|---|---|
| GitHub | Repositorio, secret scanning, push protection | Usuario `mrsteppenwolf627` | VERIFICADO 2026-11-08 (gh autenticado por https; secret scanning y push protection activos) | CONFIRMADO por el autor 2026-11-08; códigos de recuperación guardados | POR CONFIRMAR |
| Vercel | Hosting (plan Hobby) | Equipo "Aitor's projects" | VERIFICADO 2026-11-08: proyecto `web_cuchillos` creado y conectado a `main` del repositorio; despliegue de producción correcto (sin aplicación aún). Identidad verificada por el autor | CONFIRMADO por el autor 2026-11-08; códigos de recuperación guardados | POR CONFIRMAR |
| Supabase | Base de datos (plan free) | Organización `mrsteppenwolf627's Org` | VERIFICADO 2026-11-08: proyecto `web_cuchillos` creado, región eu-central-1, plan Free (NANO). La contraseña de la base de datos la guarda el autor fuera del repositorio | CONFIRMADO por el autor 2026-11-08; aplicación de autenticación (Google Authenticator), única, sin respaldo: Supabase no muestra códigos de recuperación y avisa de bloqueo permanente si se pierde el acceso a la app. Riesgo asumido por el autor (R-09) | POR CONFIRMAR |
| Registrador de dominio | Dominio (única inversión inicial) | — | NO CREADO: dominio sin elegir ni comprar | POR CONFIRMAR | POR CONFIRMAR |
| Google Search Console | Indexación y rendimiento SEO | — | NO CREADO: requiere dominio | POR CONFIRMAR | POR CONFIRMAR |
| Analítica | Medición de tráfico | — | NO CREADO: herramienta sin elegir | POR CONFIRMAR | POR CONFIRMAR |
| Programas de afiliación | Monetización principal | — | NO CREADO: programas sin elegir | POR CONFIRMAR | POR CONFIRMAR |

## Reglas de acceso

- Secretos solo en `.env` local (ignorado por git) y en variables de entorno del proveedor. `.env.example` lleva nombres de variables, nunca valores.
- 2FA obligatorio en todas las cuentas que lo permitan, preferiblemente con app de autenticación.
- Un gestor de contraseñas para todas las credenciales; ninguna en texto plano, notas o chats.
- Códigos de recuperación guardados fuera del repositorio y fuera de los chats. Situación actual (2026-11-08): los de GitHub y Vercel están en archivos de texto en la raíz de la carpeta local del proyecto, protegidos solo por `.gitignore` (patrones `*recovery*`, `*backup-codes*`, `*2fa*`). Es una protección débil: un `git add -f` o un cambio de nombre del archivo los expondría en un repositorio público. Mover esos archivos fuera de la carpeta del proyecto, o al gestor de contraseñas, queda pendiente del autor.
- Acceso de Claude Code con el mínimo permiso necesario; tokens con caducidad cuando el servicio lo permita.
- Si un secreto se sube por error al repositorio: rotarlo de inmediato en el servicio. Borrarlo del historial no basta.

## Observaciones

- Supabase Free: en la organización hay otros proyectos pausados y `kakebo-ahorro` activo, además de `web_cuchillos`. Si el límite de proyectos activos del plan free es 2 (dato a verificar en la documentación vigente), no se podrá reactivar otro proyecto sin pausar uno de los activos.
- Vercel: el despliegue actual muestra "page doesn't exist" porque `src/` aún no tiene aplicación. Es esperado.

## Comprobaciones pendientes del autor

Para cerrar este inventario, el autor debe confirmar por cada servicio existente (GitHub, Vercel, Supabase): 2FA activo y credenciales en gestor de contraseñas. Cuando lo confirme, se actualiza esta tabla con fecha.

## Registro de cambios

- 2026-11-08: creación del inventario (F0.3). Solo GitHub verificado, según F0.1.
- 2026-11-08: proyectos de Vercel y Supabase creados y verificados.
- 2026-11-08: Supabase con un único autenticador (Google Authenticator) y sin respaldo; el autor asume el riesgo y lo deja pendiente (R-09).
- 2026-11-08: 2FA confirmado por el autor en GitHub, Vercel y Supabase. Gestor de contraseñas aún sin confirmar. `.gitignore` ampliado para bloquear archivos de códigos de recuperación.
