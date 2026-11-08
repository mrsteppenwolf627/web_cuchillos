# ACCESOS · Inventario de cuentas y servicios

El repositorio es PÚBLICO. Este archivo no contiene contraseñas, tokens, claves, correos ni identificadores privados. Solo qué servicios hay, para qué y su estado de seguridad.

Última actualización: 2026-11-08

## Inventario

Estados: VERIFICADO (comprobado y fecha), POR CONFIRMAR (lo debe confirmar el autor), NO CREADO (aún no existe).

| Servicio | Uso | Cuenta | Estado | 2FA | Gestor de contraseñas |
|---|---|---|---|---|---|
| GitHub | Repositorio, secret scanning, push protection | Usuario `mrsteppenwolf627` | VERIFICADO 2026-11-08 (gh autenticado por https; secret scanning y push protection activos) | POR CONFIRMAR | POR CONFIRMAR |
| Vercel | Hosting (plan Hobby) | Del autor | POR CONFIRMAR si existe la cuenta | POR CONFIRMAR | POR CONFIRMAR |
| Supabase | Base de datos (plan free) | Del autor | POR CONFIRMAR si existe la cuenta | POR CONFIRMAR | POR CONFIRMAR |
| Registrador de dominio | Dominio (única inversión inicial) | — | NO CREADO: dominio sin elegir ni comprar | POR CONFIRMAR | POR CONFIRMAR |
| Google Search Console | Indexación y rendimiento SEO | — | NO CREADO: requiere dominio | POR CONFIRMAR | POR CONFIRMAR |
| Analítica | Medición de tráfico | — | NO CREADO: herramienta sin elegir | POR CONFIRMAR | POR CONFIRMAR |
| Programas de afiliación | Monetización principal | — | NO CREADO: programas sin elegir | POR CONFIRMAR | POR CONFIRMAR |

## Reglas de acceso

- Secretos solo en `.env` local (ignorado por git) y en variables de entorno del proveedor. `.env.example` lleva nombres de variables, nunca valores.
- 2FA obligatorio en todas las cuentas que lo permitan, preferiblemente con app de autenticación.
- Un gestor de contraseñas para todas las credenciales; ninguna en texto plano, notas o chats.
- Códigos de recuperación guardados fuera del repositorio y fuera de los chats.
- Acceso de Claude Code con el mínimo permiso necesario; tokens con caducidad cuando el servicio lo permita.
- Si un secreto se sube por error al repositorio: rotarlo de inmediato en el servicio. Borrarlo del historial no basta.

## Comprobaciones pendientes del autor

Para cerrar este inventario, el autor debe confirmar por cada servicio existente: 2FA activo y credenciales en gestor de contraseñas. Cuando lo confirme, se actualiza esta tabla con fecha.

## Registro de cambios

- 2026-11-08: creación del inventario (F0.3). Solo GitHub verificado, según F0.1.
