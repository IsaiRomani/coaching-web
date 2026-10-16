# Página de coaching

Sitio estático (HTML + CSS, sin build) para publicar en Cloudflare Pages.

```
index.html    contenido de la página (busca los comentarios "EDITAR")
styles.css    estilos; los colores están en las variables de :root
favicon.svg   icono de la pestaña
_headers      cabeceras de seguridad y caché para Cloudflare Pages
```

## 1. Personalizar

- Textos: edita directamente `index.html`.
- Foto: sube `foto.jpg` a esta carpeta y reemplaza el `<div class="portrait">` por
  `<img class="portrait" src="foto.jpg" alt="David Romaní">`.

## 2. Agenda de Google Calendar

El botón "Ver horarios disponibles" abre la agenda de citas:
https://calendar.app.google/gUaTFDAka4KVDw3v6

Para mostrar el calendario dentro de la página en lugar del botón, en Google Calendar abre
la agenda > Compartir > Sitio web > Calendario integrado, y usa ese `<iframe>`
(la URL termina en `?gv=true`).

## 3. Probar en local

Abre `index.html` con doble clic, o en VS Code usa la extensión **Live Server**.

## 4. Publicación (Cloudflare Workers)

El repositorio está conectado a Cloudflare Workers (`wrangler.jsonc` sirve esta carpeta
como archivos estáticos; `.assetsignore` excluye los que no forman parte de la página).
Dominio: `coaching.ifcpro.net`.

## 5. Actualizar

Cada `git push` a la rama principal publica la nueva versión automáticamente.
Las otras ramas generan vistas previas con su propia URL, útil para probar cambios.
