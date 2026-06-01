# Jasoval Color — Web Corporativa

## Proyecto
Web corporativa estática para jasovalcolor.com construida en HTML/CSS/JS puro desplegada en Vercel.
Sustituye la web actual en WordPress con Elementor.
El diseño se aprueba aquí en Vercel y luego se lanza apuntando el dominio jasovalcolor.com a Vercel.

## URLs
- Producción actual (WordPress): https://www.jasovalcolor.com
- Staging (Vercel): https://jasoval-web.vercel.app
- Repositorio: https://github.com/jasovalcolor/jasoval-web
- Rama: main — deploy automático en Vercel al hacer push

## Stack técnico
- HTML + CSS + JS puro (sin frameworks)
- Fuente: Montserrat (Google Fonts)
- Hosting: Vercel (gratis)
- vercel.json: `{ "cleanUrls": true, "trailingSlash": false }`

## Datos de empresa
- Nombre: Jasoval Color
- Teléfono: +34 647 594 095
- Email: javierlopez@jasovalcolor.com
- Dirección: Carr. de Cádiz, Km 889,7 · 46460 Silla, Valencia
- WhatsApp: https://wa.me/34647594095
- Catálogo B2B: https://catalogo.jasovalcolor.com
- Años de experiencia: 25+
- Sector: Fabricantes de Gel Coat, resinas y materiales composite

## Colores CSS
```css
--navy:      #0f314a   /* azul marino principal */
--navy-dark: #0a2236
--navy-mid:  #164469
--navy-lite: #1e5b8a
--accent:    #3b9fd1   /* azul claro / CTA */
--accent-2:  #2e8bbf
--bg:        #f5f5f7
--surface:   #ffffff
--border:    #d2d2d7
--text:      #1d1d1f
--muted:     #86868b
```

---

## Estructura de páginas (estado actual)

### Páginas creadas ✅
- `/` → index.html — Home principal
- `/contacto` → contacto.html — Página de contacto independiente
- `/composites/gel-coat` → composites/gel-coat/index.html — Hub gel coat
- `/composites/gel-coat/iso-npg` → composites/gel-coat/iso-npg.html — Ficha producto
- `/blog` → blog/index.html — Listado artículos con filtros por categoría
- `/blog/que-pintura-usar-en-piscinas-de-fibra-de-vidrio` → blog post completo

### Páginas pendientes
- `/composites/gel-coat/ortoftalico`
- `/composites/gel-coat/marino`
- `/composites/gel-coat/transparente`
- `/composites/gel-coat/parafinado`
- `/composites/gel-coat/colores` — carta RAL completa
- `/composites/resinas`
- `/composites/catalizadores`
- `/composites/fibras`
- Páginas legales: `/aviso-legal`, `/privacidad`, `/cookies`

---

## Navegación (todas las páginas deben tener)
```html
<a href="/#especialidades">Especialidades</a>
<a href="/composites/gel-coat">Composites</a>
<a href="/#nosotros">Nosotros</a>
<a href="/blog">Blog</a>
<a href="/contacto">Contacto</a>
<a href="https://catalogo.jasovalcolor.com" target="_blank" class="nav-cta">Catálogo B2B</a>
```

---

## SEO — Estrategia general

### Decisión de migración
- Migrar a Vercel: SÍ. Razones: velocidad, Core Web Vitals móvil, diseño superior
- URLs: mantener IDÉNTICAS a WordPress para no perder rankings
- WordPress tiene posts en raíz: `/slug/` — Vercel debe replicar exactamente
- Riesgo SEO: bajo si URLs coinciden. Temporal (4-8 semanas) si cambia contenido
- Content nuevo es mejor → Google lo premiará a medio plazo

### Keywords principales (de Keyword Planner)
| Keyword | Búsquedas/mes | Prioridad |
|---|---|---|
| gel coat | 5.000 | Máxima — target del hub /composites/gel-coat |
| gelcoat blanco | 500 | Alta — trabajar desde hub + ficha ISO-NPG |
| pintura gel coat | 50 (+900% crecimiento) | Alta — tendencia fuerte, incluir "pintura" en títulos |
| gel coat pintura | 50 (+900% crecimiento) | Alta — mismo fenómeno |
| gel coat transparente | 50 | Media — merece página propia |
| gel coat parafinado | 50 | Media — merece página propia |
| gel coat isoftálico | 50 | Media — ya cubierto por ISO-NPG |
| gel coat precio | 50 | Media — intención comercial |
| gel coat problemas | 50 | Blog |
| gel coat para moldes | 50 | Blog |
| gel coat que es | 50 | Blog o hub |
| tipos de gel coat | 50 | Hub |

**Insight clave**: usuarios buscan "pintura" no solo "gel coat". Incluir siempre la palabra "pintura" en títulos y contenido de páginas de producto.

### Tráfico actual en WordPress (Search Console)
| Artículo | Clics/mes |
|---|---|
| ¿Qué pintura usar en piscinas de fibra de vidrio? | ~509 |
| La proporción correcta catalizador-resina poliéster | ~485 |
| Cómo aplicar gel coat en piscinas | ~202 |
| Cómo reparar gel coat barco | ~146 |
| Resina que no endurece | ~100 |
| Reparar plato de ducha | ~80 |
| Fabricar molde de fibra de vidrio | ~60 |

**Total blog actual**: ~1.600 clics/mes. Proteger estas URLs es prioritario.

---

## SEO — On-page checklist por página

### Cada página debe tener:
- [ ] `<title>` entre 50-60 caracteres con keyword principal
- [ ] `<meta name="description">` entre 150-155 caracteres
- [ ] Un solo `<h1>` que incluya la keyword principal
- [ ] H2 para secciones, H3 para subsecciones (nunca saltar niveles)
- [ ] `<link rel="canonical" href="https://www.jasovalcolor.com/...">` apuntando al dominio real
- [ ] `lang="es"` en el html
- [ ] `<meta property="og:title">` y `<meta property="og:description">` para redes

### Structured data (Schema.org) por tipo de página

**Home** — pendiente:
```json
Organization: nombre, logo, url, dirección, teléfono, email, redes sociales
LocalBusiness: dirección completa, coordenadas, horario, teléfono
WebSite: con SearchAction
```

**Páginas de producto** — pendiente en hub, parcialmente en iso-npg:
```json
Product: nombre, descripción, brand, sku
Offer: precio o "consultar"
BreadcrumbList: ruta de migas de pan
```

**Artículos de blog** — ✅ completo en el artículo creado:
```json
Article: headline, autor, fecha publicación, fecha modificación
FAQPage: preguntas del acordeón
BreadcrumbList: pendiente añadir
```

**Contacto** — pendiente:
```json
LocalBusiness: dirección, horario, teléfono, coordenadas GPS
```

---

## SEO — Blog strategy

### Artículos prioritarios por crear (en orden)
1. Migrar los 5 artículos con tráfico de WordPress (misma URL, contenido mejorado)
2. "Gel coat que se fisura: causas y cómo evitarlo" — problema/solución, alta conversión
3. "Gel coat que no cura o queda blando: qué está fallando" — conecta con venta catalizador
4. "Qué es el gel coat y para qué sirve" — captura "gel coat que es" (50/mes)
5. "Cuánto cuesta el gel coat: precio por kilo y m²" — intención comercial
6. "Gel coat parafinado vs no parafinado: diferencias" — duda técnica frecuente
7. "Tipos de gel coat: cuál elegir según tu aplicación" — enlaza a todas las fichas
8. "Pintura para fibra de vidrio: gel coat, epoxi o poliuretano" — captura tendencia +900%
9. "Gel coat con burbujas o porosidades: causas y solución"
10. "Gel coat que amarillea: por qué pasa y cómo evitarlo"

### Calendario orientativo
- Mes 1: Migrar artículos con tráfico de WordPress
- Mes 2: Qué es gel coat + Tipos de gel coat
- Mes 3: Gel coat que se fisura + Gel coat que no cura
- Mes 4: Precios + Parafinado vs no parafinado
- Mes 5: Pintura para fibra de vidrio (tendencia +900%)
- Mes 6: Artículos de náutica (temporada mayo-julio)

### Estructura de cada artículo blog
- Title tag: 50-60 chars con keyword + año (ej: "... Guía Completa 2026")
- Meta description: 150-155 chars
- Schema: Article + FAQPage
- Hero en navy con autor + fecha + tiempo lectura
- Breadcrumb: Inicio > Blog > Artículo
- Sidebar: tabla de contenidos, producto relacionado, artículos similares
- Barra de progreso de lectura (JS)
- FAQ acordeón al final (mínimo 5 preguntas)
- Author box con nombre y cargo
- 3 artículos relacionados al pie
- WhatsApp flotante + footer completo

---

## SEO — Arquitectura de URLs

### Estructura hub and spoke
```
/                                    ← Home
/composites/gel-coat                 ← Hub gel coat (SEO: "gel coat" 5.000/mes)
/composites/gel-coat/iso-npg         ← Ficha producto (ventas, no SEO)
/composites/gel-coat/ortoftalico     ← Ficha producto
/composites/gel-coat/marino          ← Ficha producto
/composites/gel-coat/transparente    ← Ficha producto
/composites/gel-coat/parafinado      ← Ficha producto
/composites/gel-coat/colores         ← Carta RAL
/blog                                ← Hub blog
/blog/slug-del-articulo              ← Artículos individuales
/contacto                            ← Contacto
```

### Regla para decidir si un producto merece página propia
| Búsquedas del tipo | Decisión |
|---|---|
| +500/mes | Página propia con SEO completo |
| 50-500/mes | Sección dentro del hub con anchor link |
| 0-50/mes | Solo línea en tabla comparativa |

### Colores NO merecen página individual
Gelcoat blanco, gris, azul, RAL 9010, RAL 9016 son el mismo producto en distinto color.
Se gestionan con tabla/selector de colores dentro de cada página de producto.

---

## SEO — Plan de migración WordPress → Vercel

### Principio fundamental
Si la URL es IDÉNTICA en WordPress y Vercel, Google no nota el cambio.
Solo hay que hacer redirects para URLs que cambien de estructura.

### Proceso
1. Exportar sitemap de WordPress: jasovalcolor.com/sitemap.xml
2. Cruzar con Search Console para identificar URLs con tráfico
3. Para URLs que cambien: añadir redirect en vercel.json
4. Día de migración: cambiar DNS (A record y CNAME en el registrador)
5. +24h: verificar que todas las URLs cargan correctamente
6. +48h: enviar nuevo sitemap en Search Console
7. +30 días: revisar Search Console para 404s o caídas de tráfico
8. +3-6 meses: si todo correcto, apagar WordPress

### Redirects en vercel.json
```json
{
  "cleanUrls": true,
  "trailingSlash": false,
  "redirects": [
    { "source": "/slug-wordpress", "destination": "/nueva-url-vercel", "permanent": true }
  ]
}
```

### DNS para el dominio
En el registrador del dominio, configurar:
| Tipo | Nombre | Valor |
|---|---|---|
| A | @ | 76.76.21.21 |
| CNAME | www | cname.vercel-dns.com |

---

## SEO — Reglas de contenido

### Siempre incluir "pintura" junto a "gel coat"
Los usuarios buscan "pintura para piscina de fibra de vidrio" no solo "gel coat".
Todos los títulos y contenido deben usar ambos términos.

### E-E-A-T (Experience, Expertise, Authoritativeness, Trustworthiness)
- Mencionar siempre: "25 años de experiencia", "fabricantes en Valencia"
- Autor identificado en artículos de blog (Javier López, especialista composite)
- Datos técnicos específicos (proporciones, temperaturas, tiempos de curado)

### GEO (Generative Engine Optimization) — SEO para IA 2026
- FAQs en todas las páginas de producto y artículos de blog
- Schema FAQPage en el código
- Respuestas directas y concisas en los primeros párrafos
- Listas y tablas comparativas que las IAs pueden citar fácilmente

---

## Componentes estándar (replicar en todas las páginas)

### Header
```html
<header> con logo "JC" + nav completo + CTA "Catálogo B2B"
Script: header.dark al hacer scroll en hero
Hamburger para móvil con nav.open toggle
```

### Footer
```html
4 columnas: brand + Blog + Composites + Empresa
© 2026 Jasoval Color · dirección · email · teléfono
```

### WhatsApp flotante
```html
<a class="wa" href="https://wa.me/34647594095" target="_blank">
```

### Breadcrumb
```html
<nav class="breadcrumb">
Inicio > Sección > Página actual
```

### Animaciones reveal
```js
IntersectionObserver con clase .reveal → .visible
threshold: 0.1, transition: opacity + translateY
```

---

## Pendiente — Tareas antes del lanzamiento

### SEO
- [ ] Revisar título y meta description página a página con extensión "SEO Meta in 1 Click"
- [ ] Añadir Schema Organization + LocalBusiness en index.html
- [ ] Añadir Schema Product en todas las fichas de producto
- [ ] Añadir Schema BreadcrumbList en todas las páginas con breadcrumb
- [ ] Añadir Schema LocalBusiness en contacto.html
- [ ] Configurar Google Search Console para jasovalcolor.com en Vercel
- [ ] Crear sitemap.xml
- [ ] Crear robots.txt

### Contenido
- [ ] Migrar 5 artículos con tráfico de WordPress (misma URL)
- [ ] Crear páginas de producto: ortoftálico, marino, transparente, parafinado, colores
- [ ] Completar sección /composites/resinas, /catalizadores, /fibras
- [ ] Crear páginas legales: aviso legal, privacidad, cookies

### Técnico
- [ ] Formspree: sustituir ID placeholder en formulario de contacto
- [ ] Revisar Core Web Vitals en móvil con PageSpeed Insights antes del lanzamiento
- [ ] Favicon: usar favicon-jasoval.svg (guardado en Desktop del usuario)
- [ ] Preparar redirects de URLs de WordPress que cambien estructura

### Lanzamiento
- [ ] Cambiar DNS en registrador (A record: 76.76.21.21, CNAME www: cname.vercel-dns.com)
- [ ] Añadir dominio jasovalcolor.com en Vercel → Settings → Domains
- [ ] Enviar sitemap en Search Console
- [ ] Monitorizar 30 días en Search Console tras lanzamiento
