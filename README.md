# Samuel Cobos CV — Notas de rutas locales

Este proyecto contiene una web de CV con una página principal estilo NetSuite (index.html) y una página específica de clientes (clients.html) con un grid de logos y popups descriptivos.

## Cambio de rutas de logos
- Antes: se propuso usar rutas absolutas del sistema (por ejemplo, `file:///C:/Users/.../Downloads/...`).
- Ahora: todas las imágenes de logos en `clients.html` apuntan a la carpeta del proyecto `images/clients/`.
- Motivo: las rutas absolutas locales funcionan solo en tu PC y no sirven al desplegar (GitHub Pages/Netlify). Al estar dentro del repositorio, los logos se publican correctamente.

### Dónde colocar los archivos
Coloca los logos en:
```
Samu-web/
└─ images/
   └─ clients/
      ActiveNutrition.png
      BossInfo.png
      Doodle.png
      Egonzehnder.png
      Elli.png
      Noventiq.jpeg
      Pureon.png
      Purple.jpg
      Remira.png
      Vigience.png
      Wallbox.png
```
Asegúrate de que los nombres coincidan exactamente con los usados en `clients.html`.

### Si quieres volver a usar rutas locales absolutas
No recomendado para despliegue, pero posible para pruebas rápidas. Cambia los `src` en `clients.html` de, por ejemplo:
```
<img src="images/clients/Noventiq.jpeg" ... />
```
A:
```
<img src="file:///C:/Users/thdom/CascadeProjects/Samu-web/images/clients/Noventiq.jpeg" ... />
```
Ten en cuenta:
- Solo funcionará en tu máquina.
- Al publicar, los navegadores bloquearán rutas `file:///` por seguridad o no existirán en el servidor.

## Desarrollo local
- Abre `index.html` o `clients.html` directamente en el navegador, o sirve la carpeta con un servidor estático.
- Estructura principal:
  - `index.html`: dashboard CV (topbar, sidebar, portlets).
  - `clients.html`: grid de clientes con modal popup.
  - `styles.css`: estilos globales (tema NetSuite-like, componentes, modal, grids).
  - `images/`: imágenes del sitio (foto de perfil y logos en `images/clients`).

## Despliegue
- Recomendado: Netlify o GitHub Pages.
- Al desplegar, las rutas relativas (`images/clients/...`) funcionarán sin cambios.
- Si usas GitHub Pages para este repo:
  1. Push a `main` (ya configurado).
  2. En Settings → Pages, selecciona Source: `Deploy from a branch`, Branch: `main`, Folder: `/root`.
  3. Espera a que genere la URL.

## Actualizar contenido
- Email de contacto: editar en `index.html` (`mailto:thdominguez5@gmail.com`).
- LinkedIn: botón en `index.html` (y también visible en `clients.html` dentro del topbar al volver a Home).
- Descripciones de clientes: actualizar objeto `descriptions` en `clients.html` (modal).

## Notas
- El diseño incluye soporte para `prefers-reduced-motion` y estilos de foco accesibles.
- Si ves que un logo no carga, comprueba ruta y nombre de archivo (sensible a mayúsculas/minúsculas en algunos servidores).
