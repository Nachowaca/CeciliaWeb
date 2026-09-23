# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Stack

Prototipo estático en HTML/CSS/JS puro (sin build, sin framework), pensado para migrar a Next.js + Supabase cuando se conecte el backend real.

## Users

Dos audiencias por igual:
- **Compradores/coleccionistas** que descubren obras de Cecilia en la Galería, ven precio y hacen un pedido en Remates.
- **Alumnos potenciales** que buscan información de talleres y clases (horarios, modalidad).

## Product Purpose

Web personal de Cecilia Rodríguez Lisboa (artista plástica) que funciona como galería "instagrameable" + canal de venta de obra (remates) + información de talleres/clases, con un panel propio donde ella misma administra todo el contenido sin depender de terceros ni de conocimientos técnicos.

## Positioning

Dos diferenciales válidos en conjunto:
1. **Panel propio, sin depender de terceros**: Cecilia controla obras, precios, talleres y textos de Inicio desde un panel simple (login con Gmail), sin pedirle nada a nadie ni depender de Instagram.
2. **Remates con proceso propio**: en vez de vender por DM, el visitante arma un carrito con las obras que le interesan y deja un pedido formal (nombre + contacto) que Cecilia responde para coordinar.

## Operating Context

- Cecilia sube y edita contenido desde su panel (`Cecilia Admin v2.html`) en cualquier momento, sin ayuda técnica.
- Visitantes navegan Galería → arman su selección → Remates → dejan pedido. El chat del asistente asiste en paralelo (dudas, contacto, novedades).
- Hoy el prototipo corre localmente (`python3 -m http.server`) y guarda todo en `localStorage` del navegador — no hay backend compartido todavía.

## Capabilities and Constraints

- Galería con 4 obras por fila (desktop), precio visible, acciones "Postear en Instagram" y "Comprar".
- Remates muestra solo las obras que el visitante eligió (no el catálogo completo); carrito lateral con formulario de pedido.
- Talleres/Clases: páginas reales editables (título, descripción, horario, hasta 3 fotos por ítem).
- Panel de Cecilia con 4 pestañas (Inicio, Galería, Talleres, Clases), login con Google — **hoy simulado**, no autentica de verdad.
- Persistencia actual: `localStorage` (clave `cecilia_site_v1`), no compartido entre navegadores/visitantes — pendiente migrar a Supabase.
- **Límite explícito**: no inventar obras ni precios como si fueran reales — las fotos de stock (picsum.photos) y precios son placeholders hasta que Cecilia cargue contenido real.
- **Límite explícito**: no prometer ni insinuar cobro online funcionando — hoy el pedido en Remates termina en "Cecilia te contacta para coordinar", no hay pasarela de pago conectada.
- El botón "Postear en Instagram" es simulado (no pega contra la API real todavía).

## Brand Commitments

- Nombre: Cecilia Rodríguez Lisboa — Artista / Profesora / Tallerista, Bellas Artes / Escenógrafa / Realización Teatral.
- Estilo visual explícitamente pedido: animado, colorido, poco rígido (rebote, esquinas redondeadas, transiciones) — evolución del sistema "Modernist" original, que queda documentado como referencia histórica en `Cecilia Home.html` / `styles.css` (no se toca).
- Escena de museo animada (caminata de 9s hacia el cuadro) es un elemento de marca a preservar.

## Evidence on Hand

- Foto real de Cecilia frente a sus obras: `design_handoff_cecilia_home/assets/obra-boceto.webp` (usada hoy como boceto por defecto de la obra destacada).
- Resto de imágenes (obras de Galería, fotos de talleres/clases) son de stock (picsum.photos) — pendiente de reemplazo por contenido real.
- Repo: https://github.com/Nachowaca/CeciliaWeb

## Product Principles

1. Cecilia edita todo sola, sin código y sin depender de nadie — esa autonomía es no negociable.
2. Nunca mostrar como real algo que hoy es simulado (pagos, Instagram, autenticación) — placeholders claros hasta conectar backend.
3. La animación y el tono juguetón son parte de la identidad, no un extra descartable.
4. Vender obra y captar alumnos pesan igual — ninguna sección subordina a la otra.
5. Todo cambio de diseño se prueba primero en el prototipo local antes de tocar el repo.

## Accessibility & Inclusion

Sin requerimiento específico confirmado todavía.
