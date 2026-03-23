# CLAUDE.md — Woodia Spain Landing Page

## PROYECTO
Landing page de ventas para **Woodia Spain**, servicio de desarrollo Shopify para negocios locales en A Coruña.
Archivo único: `index.html` (HTML + CSS + JS inline).
Sin frameworks, sin dependencias externas salvo Google Fonts.

---

## ROL
Actúas como senior frontend developer especializado en landing pages de alta conversión.
Tu prioridad es velocidad de ejecución y calidad de output — no pidas confirmación en decisiones menores.
Genera siempre código completo y funcional, nunca fragmentos ni placeholders sin explicación.

---

## STACK
- HTML5 semántico
- CSS3 (Grid + Flexbox, variables CSS, mobile-first)
- JavaScript vanilla (ES6+, no jQuery, no frameworks)
- Google Fonts: Inter (weights: 400, 500, 600, 700)

---

## BRAND

| Token | Valor |
|---|---|
| Brand name | Woodia Spain |
| Tagline | Tu tienda Shopify, lista en 48 horas |
| Location | A Coruña, Galicia, España |
| Primary color | `#1a1a2e` (navy oscuro) |
| Accent color | `#e8c547` (gold cálido) |
| Surface | `#f8f8f6` (off-white) |
| Text | `#1a1a1e` |
| Font | Inter |
| WhatsApp | `https://wa.me/34XXXXXXXXX` (reemplazar manualmente) |
| Email | contacto@woodiaspain.com (reemplazar manualmente) |

---

## PRICING

| Plan | Setup | Mensual |
|---|---|---|
| Lanzamiento | 300€ | — |
| Lanzamiento + Mantenimiento | 300€ | +50€/mes |

Nota visible en la página: *"Shopify tiene un coste de 27€/mes que pagas directamente a ellos."*

---

## ESTRUCTURA DE SECCIONES (orden fijo)

1. **NAV** — Logo + CTA "Solicitar presupuesto" sticky con cambio de fondo en scroll
2. **HERO** — Headline principal, subheadline, 2 CTAs, fondo navy con patrón geométrico CSS
3. **SOCIAL PROOF BAR** — 3 stats: "48h", "100% satisfacción garantizada", "Precio fijo"
4. **QUÉ INCLUYE** — Grid de 6 cards con icono SVG inline, título y descripción corta
5. **DEMOS** — 3 tarjetas con mockup de browser (chrome minimalista), nombre de tienda y botón "Ver demo →"
6. **CÓMO FUNCIONA** — 3 pasos numerados (01/02/03) en gold, horizontal desktop / vertical mobile
7. **PRECIOS** — 2 cards, la segunda destacada como "Más popular", lista de features con checkmarks
8. **FAQ** — Acordeón JS puro, 5 preguntas, animación de apertura suave
9. **CONTACTO** — Formulario (sin backend, success message con JS) + botón WhatsApp secundario
10. **FOOTER** — Copyright + links legales placeholder

---

## COPY EXACTO

### Hero
- **H1:** "Tu negocio local, en internet en 48 horas"
- **Subheadline:** "Creo tiendas Shopify profesionales para negocios locales de A Coruña. Precio fijo, sin sorpresas, con garantía de devolución."
- **CTA primario:** "Ver ejemplos" → scroll a #demos
- **CTA secundario:** "Hablar por WhatsApp" → wa.me link

### Qué incluye (6 cards)
1. Tienda Shopify completa — Hasta 20 productos configurados, diseño adaptado a tu negocio
2. Adaptada a móvil — El 80% de tus clientes compra desde el teléfono
3. Pago activado — Stripe y Bizum configurados y listos para cobrar desde el primer día
4. Formación incluida — 30 min de videollamada para que gestiones tu tienda de forma autónoma
5. Entrega en 48h — Desde que me envías los materiales hasta que tu tienda está online
6. Garantía 7 días — Si no estás satisfecho, te devuelvo el dinero sin preguntas

### Cómo funciona
- 01 · Me contactas — Cuéntame tu negocio en 5 minutos por WhatsApp o email
- 02 · Creo tu tienda — En 48h tienes tu tienda Shopify profesional lista para vender
- 03 · Empiezas a vender — Te formo, te entrego todo y ya puedes vender online desde el primer día

### FAQ
1. ¿Necesito saber de informática? → No. Te entrego todo listo y te enseño a usarlo en 30 minutos.
2. ¿Hay costes adicionales? → Shopify son 27€/mes que pagas directamente a ellos. Yo no cobro nada más salvo el mantenimiento opcional.
3. ¿En cuánto tiempo estará lista mi tienda? → 48 horas desde que recibo tus materiales: fotos, textos y lista de productos.
4. ¿Qué pasa si no me gusta el resultado? → Tienes 7 días de garantía. Si no estás satisfecho, te devuelvo el dinero sin preguntas.
5. ¿Puedo añadir más productos después? → Sí, Shopify es muy intuitivo. Te enseño cómo hacerlo en la formación incluida.

### Demos (placeholders hasta tener URLs reales)
- Tienda de Moda — color block `#c9b8a8` — href="#"
- Tienda de Cosmética — color block `#a8c4c9` — href="#"
- Tienda de Suplementos — color block `#1a1a2e` — href="#"

---

## REGLAS DE DESARROLLO

### CSS
- Usar variables CSS en `:root` para todos los colores, espaciados y radios
- Mobile-first: base styles para móvil, media queries `min-width` para desktop
- Breakpoints: `768px` (tablet), `1024px` (desktop)
- Espaciado generoso — secciones con `padding: 80px 0` desktop, `48px 0` móvil
- Nunca usar `!important` salvo que sea estrictamente necesario

### JavaScript
- Todo vanilla ES6+
- IntersectionObserver para fade-in en scroll (clase `visible` añadida al entrar en viewport)
- Acordeón FAQ: toggle clase `open` en el item, animar `max-height` con CSS transition
- Nav: añadir clase `scrolled` al `<nav>` cuando `window.scrollY > 50`
- Formulario: `preventDefault()` + mostrar div `.success-message` con fade-in al submit
- Sin `console.log` en el código final

### Performance
- Imágenes: ninguna (todo CSS y SVG inline)
- Google Fonts: cargar con `display=swap`
- CSS y JS al final del body o en `<head>` con defer donde corresponda

### Accesibilidad
- Todos los botones con texto descriptivo
- Formulario con `<label>` correctamente asociados
- Contraste suficiente (gold sobre navy, blanco sobre navy)
- `aria-expanded` en los items del FAQ

---

## COMANDOS DISPONIBLES

### `/build`
Genera el archivo `index.html` completo desde cero según este CLAUDE.md.
No preguntes nada — toma decisiones de diseño menores de forma autónoma.
Entrega el archivo completo, funcional, listo para abrir en browser.

### `/update-demos`
Recibe 3 URLs de demos Shopify y actualiza los botones "Ver demo →" con los hrefs reales.
También actualiza los color blocks por screenshots reales si se proporcionan imágenes.

### `/update-contact`
Recibe número de WhatsApp y email real y los reemplaza en todos los lugares del HTML.
Formato esperado: número sin espacios con prefijo país (ej: 34612345678).

### `/add-section [nombre]`
Añade una nueva sección al HTML respetando el estilo visual existente.
Ejemplos: `/add-section testimonios`, `/add-section sobre-mi`

### `/optimize`
Revisa el HTML generado y aplica mejoras de rendimiento, accesibilidad y conversión.
Reporta qué cambió y por qué.

---

## ARCHIVOS DEL PROYECTO

```
woodia-landing/
├── index.html          ← único archivo de producción
└── CLAUDE.md           ← este archivo
```

Para subir a GitHub Pages:
1. Crear repo `woodia-landing` (público)
2. Push de `index.html` a rama `main`
3. Settings → Pages → Source: main / root
4. Custom domain: tu dominio de GoDaddy

---

## NOTAS FINALES
- El número de WhatsApp y el email son placeholders — reemplazar antes de publicar
- Las URLs de demo son `#` hasta tener los links reales de Shopify
- El formulario no tiene backend — si se necesita funcionalidad real, integrar Formspree o similar en una iteración posterior