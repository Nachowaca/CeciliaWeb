# Design Brief — Web Cecilia Rodríguez Lisboa

Galería instagrameable + remates de obras de pintura. Estilo animado, colorido y poco rígido (no el Modernist original, más juguetón: rebote, esquinas redondeadas, transiciones).

## Home
- Header: marca + menú (Galería, Talleres, Clases, Remates destacado)
- Recuadro de la artista: "Artista / Profesora / Tallerista" y "Bellas Artes / Escenógrafa / Realización Teatral"
- Escena de museo animada (caminata hacia el cuadro, 9s) — se mantiene del diseño original
- Chat del asistente: debajo de la escena, achicado (ya no en el footer)

## Galería
- Fondo blanco, tipo pared de museo
- Grilla de obras: 4 por fila en desktop, 2 en tablet, 1 en celular
- Cada obra tiene dos acciones: **Postear en Instagram** (simulado, degradé IG) y **Comprar** (lleva a Remates)
- Cecilia puede subir sus obras tanto desde la web (panel propio) como publicarlas directo desde Instagram

## Panel de Cecilia (`/admin`)
- Login con su Gmail (Google)
- Formulario: foto, título, técnica, medidas, año, precio
- Al publicar, la obra aparece automáticamente en la Galería pública

## Remates
- Sección principal/destacada del menú
- **Pendiente definir**: subasta con tiempo, precio fijo, o mixto — y cómo se cobra

## Chatbot
- Asiste a los visitantes: preguntas sobre remates, talleres/clases, compra de obras
- Le avisa a Cecilia (mail/mensaje) cuando hay un interesado
- Pendiente definir si también asiste a Cecilia (redactar descripciones, textos para Instagram, etc.)

## Talleres / Clases
- Todavía sin diseñar (placeholders)

## Backend (próximo paso)
- Next.js + Supabase: auth con Google, base de datos de obras, storage de imágenes
- Conectar Instagram vía API oficial (requiere cuenta profesional vinculada a Facebook)

## Pendiente
- Definir tipo de remate y forma de cobro
- Diseñar Talleres y Clases
- Rol final del chatbot
- Confirmar cuenta de Instagram profesional/vinculada
- Hosting y dominio definitivos
