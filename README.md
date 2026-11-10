# Portfolio de Lihuel Ibañez

Sitio estático (HTML, CSS y JS en un solo archivo) que se publica en GitHub Pages con GitHub Actions.

## Estructura

- `public/index.html`: la página completa
- `public/Lihuel_Ibanez_CV.pdf`: el CV que descargan los botones "Download CV"
- `public/assets/`: capturas de pantalla de tus apps (ver más abajo)
- `public/og-image.png` y `public/favicon.svg`: imagen de vista previa al compartir y favicon
- `.github/workflows/deploy.yml`: publica `public/` en GitHub Pages en cada push a `main`

## Publicar en GitHub Pages

1. Crea un repositorio vacío en GitHub (sin README ni .gitignore), por ejemplo `portfolio`. Puede ser público; las cuentas gratuitas necesitan repo público para usar Pages.
2. En esta carpeta, conecta y sube el código:

   ```bash
   git remote add origin https://github.com/TU-USUARIO/portfolio.git
   git push -u origin main
   ```

   Con la CLI de GitHub puedes hacer los dos pasos juntos: `gh repo create portfolio --public --source=. --push`
3. En GitHub, entra a **Settings, Pages** y en **Source** elige **GitHub Actions**. Es un paso único.
4. Espera a que termine el workflow (pestaña **Actions**, 1 o 2 minutos). Tu sitio queda en:

   `https://TU-USUARIO.github.io/portfolio/`

   Si llamas al repo `TU-USUARIO.github.io`, la URL queda en la raíz: `https://TU-USUARIO.github.io/`.

Si el primer workflow falla por no tener Pages activado, haz el paso 3 y vuelve a correrlo desde **Actions, Deploy to GitHub Pages, Run workflow**.

Para actualizar el sitio, edita los archivos de `public/`, haz commit y push a `main`. Se publica solo.

## Vista previa al compartir

`index.html` tiene el texto `https://YOUR-PROJECT.web.app` en dos meta tags (`og:url` y `og:image`). No lo cambies: el workflow lo reemplaza por tu URL real de GitHub Pages al publicar. Si compartes el link en LinkedIn y no ves la imagen, pega la URL en el Post Inspector de LinkedIn para refrescarla.

## Dominio propio (opcional)

En **Settings, Pages, Custom domain** puedes configurar uno. Si lo haces, GitHub crea un archivo `CNAME`; guárdalo dentro de `public/`.

## Capturas de pantalla

La galería "Screens" solo aparece cuando hay imágenes en `public/assets/`. Guarda las capturas con estos nombres (PNG o WebP verticales, de unos 600 px de ancho, funcionan bien):

| Archivo | Muestra |
| --- | --- |
| `ueno-home.png` | Home de Ueno |
| `ueno-expenses.png` | Análisis de gastos |
| `ueno-marketplace.png` | Marketplace |
| `pickers-tracking.png` | Tracking de entregas |
| `pickers-proof.png` | Prueba de entrega |

Puedes poner solo algunas. Usa capturas de la app pública o de pantallas que tu empleador permita mostrar, sin datos reales de usuarios. Para cambiar nombres o textos, busca `<section id="screens"` en `public/index.html`.

## Formulario de contacto

Por defecto, el botón "Send message" abre el correo del visitante con el mensaje armado. Para que se envíe de verdad a tu Gmail:

1. Crea un formulario gratis en formspree.io, con tu email como destino.
2. Copia el endpoint, del tipo `https://formspree.io/f/xxxxxxxx`.
3. Pégalo en `formEndpoint` dentro de `var CFG=` al final de `public/index.html`, y haz commit y push.

## Datos pendientes

En el bloque `var CFG=` al final de `public/index.html`:

- `whatsapp`: link tipo `https://wa.me/549XXXXXXXXXX`
- `calendly`: link a tu agenda
- `formEndpoint`: endpoint de Formspree (ver arriba)
