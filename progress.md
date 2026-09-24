# Progress — Web Cecilia Rodríguez Lisboa

Repo: https://github.com/Nachowaca/CeciliaWeb
Prototipo en `design_handoff_cecilia_home/` (HTML/CSS/JS estático, sin backend todavía).

## Actualización
Acento cambiado de rojo a azul cobalto `#1d4ed8` (contraste 6:1 AA), porque el azul es el color predilecto de Cecilia. Se agregó un recorrido guiado en la Home (botón "Recorrido guiado" / `?tour=1`) para presentarle la web.

## Cómo retomar
- **Web publicada** (limpia): https://nachowaca.github.io/CeciliaWeb/
- **Con recorrido guiado** (para presentar): `.../design_handoff_cecilia_home/Cecilia%20Home%20v2.html?tour=1`
- **Panel de Cecilia**: `.../design_handoff_cecilia_home/Cecilia%20Admin%20v2.html`
- **Local**: `cd design_handoff_cecilia_home && python3 -m http.server 8934`, luego abrir `http://localhost:8934/Cecilia%20Home%20v2.html`.
- Los datos del panel viven en `localStorage` (clave `cecilia_site_v1`), por navegador y dirección; hasta Supabase no se comparten.
- Sin subir a git a propósito: `assets/fondo1.jpeg` y `assets/Gemini_Generated_Image_...jpeg` (fondos de sala descartados, 1,4MB c/u).
- Próximo: ver la sección "Próximo" más abajo (empezar por celular).

## Hecho hoy (2026-09-23)
- Acento cambiado de rojo a azul cobalto `#1d4ed8`.
- Recorrido guiado (`?tour=1`) y publicación en GitHub Pages: https://nachowaca.github.io/CeciliaWeb/
- Mockups de marco automáticos en Galería y Remates (madera, negro, blanco, mesa, sin marco), elegibles por obra desde el panel. Marco más fino y grande.
- Recorte guiado 4:5 al subir obras (y fix del selector de archivo).
- Ficha de obra (modal) con medidas opcionales.
- Estado de obra: Disponible / Reservada / Vendida, editable desde el panel; bloquea la compra.
- Hovers sutiles en menú, botones y tarjetas; luz azul tenue en el nombre de la Home; texto del inicio 4px más chico.
- Miniatura de Instagram (@ce_lisboa) debajo del chat, con imágenes de ejemplo.
- Retrato de Cecilia junto al nombre del encabezado.
- Recorrido guiado ampliado a 11 pasos.
- Limpieza de código (helper `mockHTML`, listas de marco/estado compartidas, token `--grad-ig`, retrato de 191KB a 10KB).
- Frase en la pared de la sala, a la derecha del cuadro destacado (Archivo 300). Se probó una foto de sala como fondo y se volvió al fondo neutro arena/crema.
- Pendiente de decidir: `assets/fondo1.jpeg` y `assets/Gemini_Generated_Image_...jpeg` (fondos de sala de 1,4MB, sin usar ni subir a git).

## Próximo
1. Revisar celular (Home, galería, ficha, carrito, chat, tour).
2. Paleta 100% azul (fondo, escena de museo, tonos secundarios).
3. Talleres/Clases con tarjetas de fotos grandes y botón "Consultar".
4. Chat como burbuja flotante; vista previa y aviso de guardado en el panel; filtros en la Galería.
5. Miniatura de Instagram real: widget de terceros o API oficial (junto con Supabase).
6. Accesibilidad (aviso de bajo contraste del detector), carga de imágenes.
7. Backend Supabase, definir tipo de remate y cobro, obras reales.

## Hecho hasta ahora

### Home (`Cecilia Home v2.html` + `styles-v2.css`)
- Header con menú, botón Remates destacado y carrito con contador.
- Recuadro de la artista (kicker, nombre, 2 renglones) — editable desde el panel.
- Escena de museo animada (caminata de 9s hacia el cuadro). Carga por defecto la foto real de Cecilia (`assets/obra-boceto.webp`) como boceto, con fallback aunque ya haya datos guardados en el navegador.
- Chat del asistente debajo de la escena: fondo blanco (legible), con un texto al lado explicando su uso. El bot responde remates, talleres/clases, compra de obras, mail de contacto, obras nuevas y eventos (simulado — no manda nada real todavía).
- Todo con estilo animado: rebote, esquinas redondeadas, transiciones (a pedido, distinto del Modernist original que sigue intacto en `Cecilia Home.html` / `styles.css`).

### Galería
- Fondo blanco tipo pared de museo, 4 obras por fila en desktop (2 tablet, 1 celular).
- Cada obra: precio + botón "Postear en Instagram" (simulado) + "Comprar" (agrega al carrito y lleva a Remates).

### Remates
- Ya no muestra todo el catálogo: solo las obras que el usuario eligió comprar (su selección/carrito).
- Carrito: ícono con contador, lista de obras con precio y opción de quitar.
- Flujo de pedido: pide nombre y contacto, confirma "Cecilia va a coordinar pago y entrega" (simulado).

### Talleres / Clases
- Ya no son placeholders: páginas reales que muestran título, descripción, horario y hasta 3 fotos por ítem.
- Contenido editable desde el panel de Cecilia.

### Panel de Cecilia (`Cecilia Admin v2.html`)
- Login simulado con Google.
- 4 pestañas: **Inicio** (textos principales + obra destacada), **Galería** (alta/baja de obras con precio), **Talleres**, **Clases** (alta/edición/baja con confirmación, hasta 3 fotos c/u).
- Guarda todo en `localStorage` (clave `cecilia_site_v1`) — la Home lee esos datos y se actualiza sola. Es un ensayo funcional real de "editar sin tocar código", pendiente de mover a una base de datos de verdad.
- Diseño pulido: jerarquía en tarjetas, sombras, responsive en pantallas chicas.

## Pendiente / próximos pasos

1. **Backend real (Supabase)** — el paso grande:
   - Login real con Google (hoy es un botón que solo simula)
   - Base de datos de obras, talleres, clases y textos de Inicio (hoy vive en `localStorage`, no se comparte entre visitantes)
   - Storage de imágenes (hoy son URLs de picsum.photos o fotos en base64 guardadas en el navegador)
   - Conectar "Publicar" para que la obra aparezca de verdad en la Galería pública (para todos, no solo en tu navegador)
2. **Pagos/cobro en Remates**: hoy el pedido termina en "Cecilia te contacta". Definir si en algún momento se cobra online (Mercado Pago) o queda todo por WhatsApp/mail.
3. **Instagram real**: conectar "Postear" a la API oficial (requiere que la cuenta de Cecilia sea profesional y esté vinculada a una página de Facebook — confirmar si ya lo es).
4. **Chatbot real**: hoy las respuestas son por palabras clave, en el navegador. Conectar a un backend que realmente le mande el mensaje a Cecilia (mail o WhatsApp).
5. **Contenido real**: reemplazar las fotos de stock (picsum) por obras reales de Cecilia, y cargar los talleres/clases reales.
6. **Hosting y dominio definitivos** — hoy corre en un servidor local de prueba (`python3 -m http.server`).

## Cómo seguir mañana
```bash
cd design_handoff_cecilia_home
python3 -m http.server 8934
```
Abrir:
- `http://localhost:8934/Cecilia%20Home%20v2.html`
- `http://localhost:8934/Cecilia%20Admin%20v2.html`

El repo ya tiene todo pusheado a `main`. Para seguir en otra compu, ver instrucciones de clonado en el mensaje anterior o simplemente `git pull`.
# Design Brief — Web Cecilia Rodríguez Lisboa

Galería instagrameable + remates de obras de pintura, con panel propio para que Cecilia edite todo sin tocar código. Estilo animado, colorido y poco rígido (no el Modernist original: rebote, esquinas redondeadas, transiciones).

## Home
- Header: marca + menú (Galería, Talleres, Clases, Remates destacado) + carrito con contador
- Recuadro de la artista: textos editables desde el panel (hoy: "Artista / Profesora / Tallerista" y "Bellas Artes / Escenógrafa / Realización Teatral")
- Escena de museo animada (caminata hacia el cuadro, 9s) — se mantiene del diseño original. Carga por defecto la foto real de Cecilia como boceto de la obra destacada
- Chat del asistente: debajo de la escena, fondo blanco (legible), con texto al lado explicando qué puede preguntarse

## Galería
- Fondo blanco, tipo pared de museo
- Grilla de obras: 4 por fila en desktop, 2 en tablet, 1 en celular
- Cada obra tiene precio + dos acciones: **Postear en Instagram** (simulado, degradé IG) y **Comprar** (suma al carrito y lleva a Remates)
- Cecilia puede subir sus obras tanto desde la web (panel propio) como publicarlas directo desde Instagram

## Remates
- Sección principal/destacada del menú
- Muestra solo las obras que el visitante eligió comprar (no el catálogo completo)
- Carrito lateral: lista de obras + precio + quitar, formulario de pedido (nombre + contacto)
- Al confirmar: mensaje de que Cecilia va a coordinar pago y entrega (simulado, sin cobro online todavía)
- **Pendiente definir**: ¿en algún momento pasa a ser subasta con tiempo, precio fijo, o mixto? ¿se cobra online (Mercado Pago) o queda todo por WhatsApp/mail?

## Talleres / Clases
- Páginas reales (ya no placeholders): título, descripción, horario/modalidad y hasta 3 fotos por ítem
- Editables desde el panel: alta, edición y baja (con confirmación)

## Panel de Cecilia (`Cecilia Admin v2.html`)
- Login con su Gmail (Google) — hoy simulado, un botón que "entra" sin autenticación real
- 4 pestañas:
  - **Inicio**: textos principales (kicker, nombre, 2 renglones) y obra destacada (foto, título, técnica, medidas)
  - **Galería**: subir obra (foto, título, técnica, precio), aparece al instante, se puede eliminar
  - **Talleres** / **Clases**: agregar, editar y eliminar ítems con hasta 3 fotos cada uno
- Todo se guarda en el navegador (`localStorage`) y la Home lo lee en vivo — funciona como ensayo real de "editar sin programar", a la espera de una base de datos de verdad

## Chatbot
- Asiste a los visitantes: remates, talleres/clases, compra de obras, mail de contacto, obras nuevas, eventos
- Le avisa a Cecilia (mail/mensaje) cuando hay un interesado — hoy simulado, no manda nada real
- Pendiente definir si también asiste a Cecilia (redactar descripciones, textos para Instagram, etc.)

## Backend (próximo paso grande)
- Next.js + Supabase: auth real con Google, base de datos (obras/talleres/clases/textos), storage de imágenes
- Conectar Instagram vía API oficial (requiere cuenta profesional vinculada a Facebook — confirmar si ya lo es)

## Pendiente
- Definir tipo de remate y forma de cobro
- Backend real (Supabase) para que los cambios del panel se vean en cualquier navegador, no solo en el propio
- Conectar Instagram y el chatbot a algo real
- Reemplazar fotos de stock por obras reales de Cecilia
- Hosting y dominio definitivos

