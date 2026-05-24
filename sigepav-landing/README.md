# SIGEPAV — Landing Page

Página web one-page para promocionar SIGEPAV.

## Estructura

```
sigepav-landing/
├── index.html          ← La página completa (HTML + CSS + JS en un solo archivo)
└── logo-sigepav.png    ← Logo oficial de SIGEPAV
```

## Secciones incluidas

1. **Navegación fija** con menú responsive
2. **Hero** con tagline, dashboard mockup interactivo y tarjetas flotantes (QR + IA)
3. **Transparencia Proactiva** (sección destacada con 4 pasos del flujo + QR demo)
4. **Características** — los 8 módulos del sistema con iconos
5. **Cómo Funciona** — proceso de 4 pasos (Contrata → Configura → Capacita → Opera)
6. **Precios** — 3 planes (Campus $1,000 / Institución $3,500 / Enterprise Custom)
7. **Demo** — vistas reales del sistema con 4 tabs (Dashboard / Comisiones / Vehículos / QR Ciudadano)
8. **Contacto** — formulario funcional + canales de contacto
9. **FAQ** — 7 preguntas frecuentes con acordeón
10. **Footer** institucional

## Cómo usar la página

### Opción 1 — Hosting estático (Recomendado para promo)
La página es 100% estática (HTML/CSS/JS), súbela tal cual a:
- **GitHub Pages** (gratis, ideal para promo)
- **Netlify** (gratis, drag & drop la carpeta)
- **Vercel** (gratis)
- Cualquier servidor con cPanel / hosting tradicional

### Opción 2 — Integrar con tu backend Express
Si quieres servirla desde tu Server.js:

```js
// En tu Server.js
const path = require('path');
app.use('/landing', express.static(path.join(__dirname, 'sigepav-landing')));

// Y para el formulario de contacto, agrega un endpoint:
app.post('/api/contacto', (req, res) => {
  const { nombre, institucion, correo, telefono, flotilla, mensaje } = req.body;
  // Guarda en DB, envía email, lo que necesites
  res.json({ ok: true });
});
```

Luego, en el `<script>` del index.html, descomenta el bloque del fetch en el handler del formulario.

## Personalización rápida

Las cosas más comunes que probablemente quieras cambiar:

| Qué | Dónde está | Búscalo así |
|---|---|---|
| Correo de contacto | Sección contacto + footer | `contacto@sigepav.mx` |
| Teléfono | Sección contacto | `+52 492 000 0000` |
| Precios | Sección pricing | `$1,000`, `$3,500` |
| Tagline del hero | Sección hero | `Tu flotilla institucional, transparente` |
| Texto de los módulos | Sección features | `Registro vehicular`, etc. |
| Colores | Variables CSS al inicio | `:root { --azul-800, --dorado, ... }` |

## Paleta de colores (CSS vars)

- `--azul-900: #001a3d` (azul más oscuro)
- `--azul-800: #002b60` (azul SIGEPAV principal)
- `--azul-700: #003d80` (azul medio)
- `--azul-600: #006dc8` (azul claro/links)
- `--dorado: #d4a017` (acento dorado)
- `--dorado-claro: #ffd966` (highlight)

## Tipografías

- **Display (títulos)**: Space Grotesk
- **Body (texto)**: Manrope

Ambas se cargan desde Google Fonts vía CDN.

## Notas técnicas

- 100% responsive (desktop, tablet, móvil)
- Sin dependencias de build (no necesitas npm, webpack, etc.)
- Smooth scroll entre secciones
- Menú móvil hamburguesa
- FAQ con acordeón animado
- Tabs de demo interactivos
- Animaciones CSS sutiles al cargar
- Iconos SVG inline (no dependen de CDN) para los críticos
- Font Awesome via CDN para iconos secundarios
- Mockup del dashboard con CSS puro

## Compatibilidad

Funciona en Chrome, Edge, Firefox, Safari (últimas 2 versiones). En IE11 NO funciona (no es 2026 ya bro 😄).
