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
