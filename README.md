# onchained.info

Web de servicios de OnChained (Series 1 de CellsForge LLC). HTML, CSS y JS a pelo, sin build: `index.html` es la página entera.

## Publicar

Cada push a `main` la publica en GitHub Pages (workflow «Publicar en GitHub Pages»). La primera vez hay que activarlo desde el navegador:

1. Settings › Pages › **Source: GitHub Actions**.
2. Settings › Pages › **Custom domain: `onchained.info`** y marcar «Enforce HTTPS» cuando el DNS resuelva.
3. En el DNS de `onchained.info`:
   - `A` → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `AAAA` → `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`, `2606:50c0:8003::153`
   - `CNAME www` → `blockchain-networks-io.github.io`

El fichero `CNAME` del repo es lo que le dice a Pages qué dominio sirve: no lo borres.

## Editar

- Textos y secciones: `index.html`.
- Colores y maqueta: `styles.css` (los colores están arriba, en `:root`).
- El formulario de contacto abre el cliente de correo hacia `hello@onchained.info`. Para recibirlo sin cliente de correo, cambiar el `action` por un servicio tipo Formspree.
- `og.svg` es la imagen de las previsualizaciones (X, LinkedIn, WhatsApp). Si alguna red no acepta SVG, exportarla a PNG 1200×630 con el mismo nombre y cambiar la etiqueta `og:image`.
