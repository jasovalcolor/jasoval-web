# Jasoval Color — Web Corporativa

## Descripción del proyecto
Web corporativa estática para jasovalcolor.com. Reemplaza la anterior web en WordPress.

## URL
- Producción: https://www.jasovalcolor.com
- Dominio: jasovalcolor.com (CNAME/A record en One.com apuntando a Vercel)

## Repositorio
- GitHub: jasovalcolor/jasoval-web
- Rama principal: main
- Deploy automático en Vercel al hacer push

## Stack técnico
- HTML + CSS + JS puro (single file: index.html)
- Sin frameworks ni dependencias externas
- Fuente: Montserrat (Google Fonts) — toda la página
- Desplegado en Vercel (gratis)

## Colores / Variables CSS
Idénticos al catálogo B2B (jasovalcolor/jasoval-catalogo-b2b):
- `--navy`:      #0f314a (azul marino principal)
- `--navy-dark`: #0a2236
- `--navy-mid`:  #164469
- `--navy-lite`:  #1e5b8a
- `--accent`:    #3b9fd1 (azul claro)
- `--bg`:        #f0f4f8
- `--surface`:   #ffffff
- `--border`:    #e2e8f0
- `--text`:      #1a2e42
- `--muted`:     #64748b

## Estructura de la página
1. **Header sticky** — logo JC + nav (Quiénes somos, Productos, Contacto) + CTA "Ver catálogo B2B"
2. **Hero** — logo grande, H1, subtítulo, botones CTA + contactar
3. **Stats strip** — banda navy con contadores animados (+500 clientes, 25 años, 26 productos)
4. **Quiénes somos** — texto empresa + placeholder foto + ticker de valores
5. **Catálogo CTA** — tarjeta oscura destacada con enlace a catalogo.jasovalcolor.com
6. **Contacto** — info de contacto (tel, email, dirección, WhatsApp) + formulario
7. **Footer** — logo, links, dirección completa
8. **WhatsApp flotante** — botón fijo esquina inferior derecha

## Contacto de la empresa
- Teléfono: +34 647 594 095
- Email: javierlopez@jasovalcolor.com
- Dirección: Carr. de Cádiz, Km 889,7 · 46460 Silla, Valencia
- Web: www.jasovalcolor.com

## Pendiente / Por hacer
1. **Formspree** — sustituir `action="https://formspree.io/f/XXXXXXXX"` por el ID real del formulario
2. **Foto real** — sustituir el placeholder de "Quiénes somos" por foto de las instalaciones
3. **Vercel deploy** — conectar este repo en vercel.com y configurar dominio jasovalcolor.com
4. **DNS One.com** — añadir registro A o CNAME apuntando a Vercel para jasovalcolor.com
5. **Google My Business** — registrar empresa
