BoscTech ONE PAGE
Teléfono caja y botones: +34 914 46 85 03
No somos servicio técnico oficial. No vemos equipos en garantía.

Dominio: NO SE HA PROPORCIONADO. No se ha inventado ninguno; canonical
y og:url siguen sin añadirse hasta que se confirme el dominio real.
El schema.org tampoco incluye "url" por el mismo motivo (ya era así
antes de esta pasada).

Google Analytics:
G-KX5QF1PLD7

HISTORIAL: el repositorio era multipágina (8 páginas /modelos/ de
gamas Bosch y 8 páginas /servicios/ por tipo de electrodoméstico) y
se convirtió a one-page; esas páginas fueron eliminadas en commits
anteriores. Como ya no existen en el sitemap actual, se ha añadido
middleware.mjs para redirigir (301) cualquier URL antigua a la home,
evitando 404 en enlaces indexados o backlinks antiguos. Excluye
/api/* y cualquier ruta con extensión de archivo. Se añadió
"@vercel/functions": "^2.0.3" a package.json como dependencia de esta
función. También se añadieron name/version al package.json, que solo
tenía private/engines/dependencies.

REVISIÓN (fixes aplicados en esta pasada):
- Ya estaba bien: banner de cookies, schema.org LocalBusiness completo
  (areaServed, sameAs), sección SEO "Guía", menú móvil, chatbot real
  (ya corregido en un commit anterior, "era falso"), borde blanco del
  chat, api/contacto.js con SMTP + nodemailer, teléfono consistente.
  No se ha modificado ninguno de estos.
- Meta robots: no existía. Añadido.
- H1 de portada reescrito, corto, directo y totalmente afirmativo
  (sin interrogación ni condicionales — antes usaba "si merece la
  pena repararlo"), incluye la marca: "Tu Bosch no funciona. Aquí lo
  revisamos y respondemos." Tamaño del H1 aumentado: clamp(38-53px) →
  clamp(46-74px) en escritorio, 38px → 46px en móvil.

Formulario: usa SMTP_HOST, SMTP_PORT, SMTP_USER, SMTP_PASS y CONTACT_EMAIL en Vercel. El correo no aparece visible en la web.

REVISIÓN ADICIONAL (checklist unificado de la familia, a petición del cliente):
- H1 repetía la plantilla "no funciona. Aquí lo revisamos..." usada
  en varios repos. Reescrito: "Tu Bosch hace ruido o no arranca. Lo
  revisamos." (9 palabras).
- Texto decorativo ".hero:before" ("REPARACIÓN · BOSCH · MADRID") no
  se ocultaba en móvil como en otros repos con el mismo patrón de
  ticker de fondo; añadido display:none en el breakpoint ≤550px.
- Franja de aviso de servicio técnico independiente añadida también
  como banner fijo debajo del menú (ya existía un aviso similar en el
  hero y en el footer; se mantiene, esta franja lo refuerza igual que
  en el resto de la familia).
- Añadido "Sábados, domingos y días festivos estamos cerrados" debajo
  del horario.
- BUG REAL — el formulario no tenía ninguna casilla de consentimiento
  de política de privacidad. Añadida, con enlace a
  https://kelatos.com/privacy-policy/ en azul y subrayado.
- Ninguno de los botones CTA del hero (WhatsApp ni teléfono) tenía
  icono. Añadidos ambos.
- Formulario verificado: fetch a /api/contacto coincide con
  api/contacto.js; conexión correcta.

REVISIÓN ADICIONAL (a petición del cliente):
- Quitados del hero los 3 pills ("Averías y problemas de
  funcionamiento", "Reparación en Madrid", "Valoración antes de
  decidir") y el aviso "No somos servicio técnico oficial..." de esa
  ubicación concreta (se mantiene igual en la sección de contacto, en
  el footer y en la franja fija bajo el menú, así que el aviso de
  independencia sigue visible en todo el sitio).
- Sustituido por una insignia de precio: "✓ Diagnóstico: 20 € + IVA".
  Añadida también una fila "Diagnóstico: 20 € + IVA" en la caja de
  información, para que sea coherente en toda la página.

REVISIÓN ADICIONAL (checklist unificado de la familia, a petición del cliente — repo 24/48):
- BUG REAL — enlace de Cal.com desactualizado. Actualizado a
  https://cal.com/kelatos/30min?embed=true&theme=light&attendeePhoneNumber=%2B34&overlayCalendar=true.
- Verificado: el correo soporte@kelatos.com no aparece visible.
- BUG REAL — el mensaje prellenado de WhatsApp decía "¡Hola Kelatos!".
  Corregido a "¡Hola BoscTech!".
- Verificado: el menú móvil ya se cerraba correctamente al pulsar un
  enlace.
- Verificado: iconos SVG con ancho/alto iguales (proporcionales); sin
  distorsión.
- BUG REAL — el H1 en móvil (dentro de @media(max-width:550px), el
  breakpoint más estrecho de este repo) estaba en 46px. Corregido a
  48px.
- BUG REAL — botones del hero (.btn) con border-radius de 13px y sin
  estado hover. Aumentado a border-radius:999px; añadido
  filter:brightness(.88) en wa/collect (colores sólidos) y relleno
  sólido rojo (#d71920) + texto blanco en el botón de teléfono (.call,
  estilo contorno) al pasar el ratón.
- Verificado: la insignia "✓ Diagnóstico: 20 € + IVA" (.diag-badge) es
  una etiqueta única de precio, no el patrón de franja de insignias de
  4 elementos de la familia Dyson; no aplica la reubicación.

REVISIÓN ADICIONAL (nueva regla de menú móvil, a petición del cliente):
- BUG REAL — la franja de aviso de independencia estaba dentro de
  <header>. Movida fuera de <header>, como hermana justo después de
  él y antes del hero: sigue siendo la misma franja amarilla de ancho
  completo.
- Verificado: el header (element selector "header{position:sticky;
  top:0}") ya se mantenía fijo/pegado arriba al hacer scroll; no
  requería cambios.
- Verificado de nuevo: el checklist de 7 puntos ya estaba aplicado de
  una pasada anterior; no requería cambios.
