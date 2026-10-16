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

La sección "Reserva tu sesión" muestra integrada la agenda "Prácticas Sesiones de Coaching"
(iframe en `index.html`), con un enlace de respaldo a https://calendar.app.google/291NgWWic4htYcRh8.
Si cambias de agenda, reemplaza ambas URLs.

## 3. Probar en local

Abre `index.html` con doble clic, o en VS Code usa la extensión **Live Server**.

## 4. Publicación (Cloudflare Workers)

El repositorio está conectado a Cloudflare Workers (`wrangler.jsonc` sirve esta carpeta
como archivos estáticos; `.assetsignore` excluye los que no forman parte de la página).
Dominio: `coaching.ifcpro.net`.

## 5. Actualizar

Cada `git push` a la rama principal publica la nueva versión automáticamente.
Las otras ramas generan vistas previas con su propia URL, útil para probar cambios.
