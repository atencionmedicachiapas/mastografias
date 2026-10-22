# Metas de Mastografía · Marco para GitHub Pages

Página que muestra la plataforma de Apps Script dentro de un marco propio, para que el navegador use el **favicon institucional** y se pueda **instalar como aplicación** en computadora y celular.

## Archivos

| Archivo | Uso |
|---|---|
| `index.html` | Marco a pantalla completa con la plataforma y pantalla de carga. La liga `/exec` está en la variable `APP_URL`. |
| `manifest.webmanifest` | Nombre, colores e íconos de la aplicación instalada. |
| `sw.js` | Service worker mínimo para permitir la instalación. No guarda datos de la plataforma. |
| `favicon.ico` | Favicon institucional (archivo oficial `Salud_Logo.ico`). |
| `apple-touch-icon.png` | Ícono en iPhone / iPad. |
| `icon-192.png`, `icon-512.png`, `icon-maskable-512.png` | Íconos de la aplicación instalada (Android, Chrome, Edge). |

## Publicar

1. En la plataforma de Apps Script, reemplaza `Api.gs` (ahora permite mostrarse dentro del marco) y publica **Implementar › Gestionar implementaciones › Editar › Nueva versión**. La liga `/exec` no cambia.
2. En GitHub crea un repositorio (por ejemplo `metas-mastografia`) y sube todos los archivos de esta carpeta a la raíz.
3. **Settings › Pages › Build and deployment**: *Source* = **Deploy from a branch**, rama **main**, carpeta **/ (root)**. Guarda.
4. En uno o dos minutos la página queda en `https://<usuario>.github.io/metas-mastografia/`. Esa es la liga que se comparte.

## Instalar como aplicación

- **Chrome / Edge (computadora):** ícono de instalar en la barra de direcciones, o menú › *Instalar Metas de Mastografía*.
- **Android (Chrome):** menú › *Agregar a pantalla de inicio* / *Instalar aplicación*.
- **iPhone (Safari):** botón Compartir › *Agregar a pantalla de inicio*.

## Notas

- Si se crea una implementación nueva de Apps Script (con otra liga `/exec`), solo cambia `APP_URL` en `index.html`.
- Algunos navegadores (Safari, modo incógnito) bloquean el almacenamiento dentro de marcos: la plataforma funciona igual, pero puede pedir el código de acceso al recargar.
- Si los íconos cambian, incrementa la versión en `sw.js` (`mastografia-marco-v2`) para que se actualicen en las aplicaciones instaladas.
