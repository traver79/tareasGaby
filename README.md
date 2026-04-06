# Tareas · Gaby

Aplicación web ligera para gestionar tareas de forma simple, con diseño limpio y soporte PWA (instalable y con funcionamiento offline básico).

## Características

- Alta de tareas con formulario (fecha, descripción y estado).
- Estados de tarea:
  - `PENDIENTE`
  - `EN_CURSO`
  - `FINALIZADO`
- Interfaz visual en tarjetas con estilos responsivos.
- Soporte **PWA** mediante:
  - `manifest.json`
  - `service worker` para caché de recursos principales.
- Tipografías de Google Fonts integradas.

## Estructura del proyecto

- `index.html`: aplicación principal (HTML, CSS y JS en un solo archivo).
- `sw.js`: service worker para caché y modo offline básico.
- `manifest.json`: configuración de la app instalable.
- `generar-iconos.html`: utilidad para generar y descargar iconos `icon-192.png` y `icon-512.png`.

## Uso local

1. Abre una terminal en la carpeta del proyecto.
2. Levanta un servidor estático (recomendado para service worker), por ejemplo:

```bash
python3 -m http.server 8080
```

3. Abre en el navegador:

```text
http://localhost:8080
```

## Notas sobre PWA

- Para que el service worker funcione correctamente debes servir la app desde `http://localhost` o `https`.
- Si cambias archivos cacheados en `sw.js`, incrementa la versión de caché (`gaby-tasks-v1` → `gaby-tasks-v2`) para forzar actualización.

## Generación de iconos

1. Abre `generar-iconos.html` en el navegador.
2. El archivo dibuja automáticamente los iconos y dispara su descarga.
3. Coloca los PNG en la raíz del proyecto con estos nombres:
   - `icon-192.png`
   - `icon-512.png`

## Próximas mejoras sugeridas

- Persistencia de tareas en `localStorage` o backend.
- Filtros por estado y fecha.
- Búsqueda de tareas.
- Sincronización en la nube.
