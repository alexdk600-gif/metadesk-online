# MetaDesk Online v0.3.0

Aplicación web **independiente y no afiliada a Octarine**. Está inspirada en características generales documentadas públicamente (p. ej., un panel de estadísticas de héroes), pero el código aquí es una implementación nueva y no incorpora código propietario ni de repositorios GPL de terceros.

## Funcionalidad comprobable

- Catálogo y estadísticas profesionales de héroes desde `https://api.opendota.com/api/heroStats`.
- Búsqueda, roles, tiers orientativos, favoritos locales y comparación de hasta tres héroes.
- Historial público de hasta 20 partidas mediante `https://api.opendota.com/api/players/{account_id}/recentMatches`.
- Temporizador manual, importación de JSON, exportación CSV mitigando fórmulas, caché local.
- Interfaz responsive, política CSP y datos de usuario no guardados en servidores propios.

## Desarrollo y pruebas

No hay dependencias npm. Node.js 22+ para las pruebas (la app funciona en navegadores modernos).

```shell
node --test tests/core.test.mjs
node --check app.mjs
node --check core.mjs
```

Para ver la web en local, servir el directorio por HTTP, por ejemplo `python -m http.server 8000` y abrir `http://127.0.0.1:8000`. Para publicarla por HTTPS, subir el contenido de esta carpeta a GitHub Pages, Vercel o un servidor web estático.

## Advertencias

No realiza inyección de procesos, modificación de Dota 2, extracción de datos privados, evasión de suscripciones ni conexión con servidores de Octarine. No es una réplica 100% de Octarine. El tier depende de una heurística simple de victorias en partidas profesionales (min. 20 selecciones); no estima por sí solo probabilidad de ganar una partida. La disponibilidad depende de OpenDota y de sus límites de uso.

El ejecutable `octarine-installer.exe` analizado está compilado con Go 1.27.1 y contiene lógica de instalación y arranque, no necesariamente el cliente completo.