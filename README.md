# onchained.info

Web de servicios de OnChained (Series 1 de CellsForge LLC). HTML, CSS y JS a pelo, sin build: `index.html` es la página entera.

## Ramas

`main` es donde se trabaja; **`production` despliega** al hacer push (como en mucho-finance y cellsforge). Para publicar: PR de `main` a `production` y mergear, o «Run workflow» de «Deploy to Production».

## Publicar en el EC2 (la primera vez)

1. **Secrets del repo** (Settings › Secrets and variables › Actions): `SSH_HOST`, `SSH_USER` y `SSH_KEY`, los mismos que en cellsforge (es el mismo EC2).
2. **«Servidor: preparar EC2»** en Actions: primero en modo `diagnostico` para ver el estado; luego `aplicar`. Instala nginx si falta, crea `/var/www/onchained` y escribe el bloque de nginx para `onchained.info` (solo HTTP: Cloudflare Flexible pone el TLS).
3. **«Deploy to Production»**: sincroniza los ficheros por rsync y comprueba que nginx contesta 200.
4. **Cloudflare**: registro `A` de `onchained.info` y de `www` a la IP del EC2 con el proxy (nube naranja), SSL en *Flexible* y «Always Use HTTPS».

## Editar

- Textos y secciones: `index.html`.
- Colores y maqueta: `styles.css` (los colores están arriba, en `:root`).
- El formulario de contacto abre el cliente de correo hacia `info@onchained.info`. Para recibirlo sin cliente de correo, cambiar el `action` por un servicio tipo Formspree.
- `og.svg` es la imagen de las previsualizaciones (X, LinkedIn, WhatsApp). Si alguna red no acepta SVG, exportarla a PNG 1200×630 con el mismo nombre y cambiar la etiqueta `og:image`.
