# Página de coaching

Sitio estático (HTML + CSS, sin build) para publicar en Cloudflare Pages.

```
index.html    contenido de la página (busca los comentarios "EDITAR")
styles.css    estilos; los colores están en las variables de :root
favicon.svg   icono de la pestaña
_headers      cabeceras de seguridad y caché para Cloudflare Pages
```

## 1. Personalizar

Abre `index.html` y busca `EDITAR`. Cambia:
- Tu nombre (título, encabezado, "Sobre mí", pie).
- Tu historia y formación.
- Temas, duración, costo y correo de contacto.
- Tu foto: guarda `foto.jpg` en esta carpeta y reemplaza el `<div class="portrait">` por
  `<img class="portrait" src="foto.jpg" alt="Tu Nombre">`.

## 2. Crear la agenda en Google Calendar

1. En Google Calendar (web): **Crear > Agenda de citas**.
2. Define duración (60 min), horarios disponibles, tiempo entre citas y máximo de reservas por día.
3. En "Conferencia", elige **Google Meet** para que cada reserva genere su enlace.
4. En "Formulario de reserva", pide nombre, correo y opcionalmente una pregunta como "¿Qué tema te gustaría trabajar?".
5. Guarda, abre la agenda y pulsa **Compartir > Sitio web > Calendario integrado**.
6. Copia la URL que va dentro de `src="..."` y pégala en `index.html` en los dos lugares que dicen `TU_ID_DE_AGENDA` (el iframe y el enlace de respaldo; en el enlace puedes quitar `?gv=true`).

## 3. Probar en local

Abre `index.html` con doble clic, o en VS Code usa la extensión **Live Server**.

## 4. Publicar en Cloudflare Pages

1. Sube esta carpeta a un repositorio de GitHub.
2. En Cloudflare: **Workers & Pages > Crear > Pages > Conectar a Git**, elige el repositorio.
3. Configuración de compilación:
   - Framework: **Ninguno**
   - Comando de compilación: *(vacío)*
   - Directorio de salida: `/`
4. Guardar e implementar. Tendrás una URL tipo `tu-proyecto.pages.dev`.
5. En el proyecto: **Dominios personalizados > Configurar dominio**, escribe p. ej. `coaching.ifcpro.net`.
   Como el dominio ya está en Cloudflare, el DNS se crea solo y el HTTPS se activa en minutos.

## 5. Actualizar

Cada `git push` a la rama principal publica la nueva versión automáticamente.
Las otras ramas generan vistas previas con su propia URL, útil para probar cambios.
