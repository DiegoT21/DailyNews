# Despacho Diario

Página personal de noticias diarias sobre inteligencia artificial, tecnología, computación y programación: modelos nuevos, movimientos entre compañías, cambios de precios y brechas de seguridad.

## Contenido

- `index.html` — la página (autocontenida: HTML + CSS + JS, sin build step).

## Publicar con GitHub Pages

1. En este repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch**.
2. Elegí la rama `main` y la carpeta `/ (root)`.
3. Guardá — GitHub publica el sitio en `https://diegot21.github.io/DailyNews/`.

## Actualización de contenido

El contenido de noticias se investiga y reescribe periódicamente (fecha, titulares, resúmenes y fuentes de cada categoría) manteniendo el mismo diseño del archivo.

Cada boletín (`.bulletin`) y tarjeta (`.card`) puede incluir una imagen opcional como primer elemento interno:

```html
<div class="thumb"><img src="URL" alt="..." loading="lazy" onerror="this.parentElement.remove()"></div>
```

Se usan imágenes reales y estables (fotos de sede, logos, banderas) alojadas en Wikimedia Commons (`upload.wikimedia.org` / `thumb.wikimedia.org`) en vez de placeholders genéricos. El `onerror` retira el bloque de imagen si la URL deja de estar disponible, así una nota sin imagen no rompe el diseño.

Al hacer click (o Enter/Espacio) sobre un boletín o tarjeta se abre un modal (`<dialog id="story-modal">`) con la noticia completa. El párrafo corto visible en la tarjeta se mantiene para el listado; para el modal, cada boletín/tarjeta puede incluir un bloque opcional con más contexto (cifras, citas, antecedentes) que solo se muestra ahí:

```html
<p>Resumen corto que se ve en la tarjeta.</p>
<div class="full" hidden>
  <p>Párrafo(s) con más contexto — solo aparecen al expandir la noticia.</p>
</div>
```

Si una nota no tiene `.full`, el modal simplemente repite el párrafo corto de la tarjeta.
