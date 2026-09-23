---
name: Cecilia Rodríguez Lisboa — Galería y Remates
description: Galería instagrameable + remates de obra, sistema Modernist evolucionado con más color y movimiento
colors:
  bg: "#f5f0e8"
  surface: "#ece5da"
  text: "#201e1d"
  accent: "#1d4ed8"
  accent-hover: "#ae1800"
  accent-pressed: "#7c1405"
  accent-tint: "#fff2ef"
  accent-deep: "#7c1405"
  divider: "color-mix(in srgb, #201e1d 40%, transparent)"
  neutral-700: "#605d5d"
  scene-wall: "#ebe3d6"
  scene-floor: "#cfc4b3"
  scene-frame: "#231f1c"
typography:
  heading:
    fontFamily: "Archivo, system-ui, sans-serif"
    fontWeight: 800
    letterSpacing: "-0.03em"
  body:
    fontFamily: "Archivo, system-ui, sans-serif"
    fontWeight: 400
    fontSize: "15px"
    lineHeight: 1.55
  kicker:
    fontSize: "11px"
    fontWeight: 600
    letterSpacing: "0.12em"
rounded:
  sm: "8px"
  md: "14px"
  lg: "24px"
  pill: "999px"
spacing:
  1: "4px"
  2: "8px"
  3: "12px"
  4: "16px"
  6: "24px"
  8: "32px"
components:
  button-primary:
    backgroundColor: "{colors.accent}"
    textColor: "{colors.bg}"
    rounded: "{rounded.pill}"
    padding: "10px 16px"
  button-primary-hover:
    backgroundColor: "{colors.accent-hover}"
  button-secondary:
    backgroundColor: "transparent"
    textColor: "{colors.text}"
    rounded: "{rounded.pill}"
  card:
    backgroundColor: "#ffffff"
    rounded: "{rounded.lg}"
    padding: "24px"
---

# DESIGN.md

## Overview

Sistema visual **Modernist evolucionado**: sobre la base plana/arquitectónica original (Archivo, cero radios, líneas de 2px) se le sumó rebote (`cubic-bezier(.34,1.56,.64,1)`), esquinas redondeadas y color, a pedido explícito del cliente ("animado, colorido, poco rígido"). El sistema Modernist original (radios 0, sin rebote) queda documentado aparte en `design_handoff_cecilia_home/styles.css` como referencia histórica — no se edita.

## Colors

Fondo bone (`#f5f0e8`) y superficie tostada (`#ece5da`) sobre tinta casi negra (`#201e1d`). Un solo acento: azul cobalto `#1d4ed8`, con su rampa de hover/pressed/tint/deep. Los divisores usan tinta al 40% de opacidad, nunca gris plano. La escena de museo tiene su propia paleta física (pared, piso, marco) que no se mezcla con el resto del sitio.

## Typography

Una sola familia, Archivo, en tres pesos: 300 solo para la frase de la pared de la sala, 800 para títulos (siempre con letter-spacing negativo, `-0.03em`) y 400 para texto de cuerpo. Los "kickers" (etiquetas de sección) son mayúsculas 11px con tracking positivo (`0.12em`) — el contraste entre tracking negativo en títulos y positivo en kickers es intencional. Sin itálicas; el peso 300 se reserva a la frase.

## Layout

- Contenedor central `max-width: 1360px` (Home) / `1100px` (Panel), padding lateral 32px que baja a 16px en ≤900px.
- Galería/Remates: grilla de 4 columnas en desktop → 2 en tablet (≤1100px) → 1 en celular (≤560px).
- Panel de Cecilia: layout de dos columnas (`.9fr 1.4fr`) que colapsa a una sola columna en ≤900px.
- Sección de chat en Home: dos columnas (texto + widget) que colapsan a una en ≤800px.

## Elevation & Depth

Tres niveles de sombra suave con tinte de tinta (`--shadow-sm/md/lg`, nunca negro puro). Se usan en tarjetas del panel y al hacer hover sobre tarjetas de obra. La escena de museo es la única zona con sombras dramáticas (drop shadows del marco, inset bevels) — deliberadamente más teatral que el resto del sitio, que es plano.

## Shapes

Radios de tres tamaños: `8px` (chico, inputs/fotos), `14px` (medio, tarjetas), `24px` (grande, contenedores destacados) — más un `999px` para botones/pills y chips. Esto reemplaza los radios en 0 del Modernist original; es el cambio más visible del sistema evolucionado.

## Components

- **btn-primary**: fondo acento, texto bone, pill. Hover sube 2px y escala levemente con rebote; nunca transición lineal.
- **btn-secondary**: borde divisor, fondo transparente.
- **gcard** (tarjeta de obra en Galería/Remates): imagen 1:1, radio lg, sombra sm, hover `translateY(-6px) rotate(-.4deg)` + sombra lg. Precio siempre en acento, negrita.
- **chat widget**: fondo blanco (no bone, para legibilidad), burbujas con radio 14px y esquina "cola" de 4px, punto de estado con pulso animado.
- **item-card** (panel, Talleres/Clases): cabecera con número circular en acento sobre fondo surface, cuerpo con padding generoso (32px).
- **tabs** (panel): pills, activa = fondo tinta/texto bone.

- **mockup de obra** (`.mock`): cada obra se muestra sola en un marco CSS sobre pared (madera, negro, blanco, sobre mesa o sin marco), elegible por obra desde el panel. Marco fino y grande para que la obra no se pierda; hover eleva el marco 5px y profundiza la sombra.
- **ficha de obra**: modal (dos columnas, una en celular) con mockup grande, técnica, medidas opcionales, estado, precio y botones Comprar / Postear. Cierra con X, clic afuera o Esc.
- **estado de obra**: etiqueta (`.chip`) Reservada (ámbar) o Vendida (tinta) sobre el mockup; las disponibles no llevan etiqueta. Comprar queda deshabilitado con el nombre del estado.
- **hovers**: sutiles. Menú con línea azul que se desliza; botones suben 1px y crecen 2%; tarjetas suben 4px. El bloque del nombre en la Home recibe una luz azul tenue (16% de opacidad) desde la esquina inferior izquierda, con fundido de 0,7s.
- **miniatura de Instagram**: tarjeta de perfil (@ce_lisboa) con grilla de 6 imágenes y botón grande "Seguir en Instagram", en vez de un ícono con link. Hoy usa las obras de ejemplo como imágenes.
- **frase en la pared**: "El arte no reproduce aquello que es visible, sino que hace visible aquello que no siempre lo es." en Archivo 300, a la derecha del cuadro destacado, alineada a la derecha y en tinta al 90%; aparece con fundido al final de la caminata. En celular pasa arriba del cuadro. Se probó una foto de sala como fondo y se descartó: el fondo sigue siendo la pared arena/crema con degradado.
- **retrato**: foto circular de 46px junto al nombre en el encabezado (`assets/cecilia-retrato.jpg`).
- **recorrido guiado**: 8 pasos con foco animado sobre la web real (`?tour=1` o botón flotante).

## Do's and Don'ts

- **Hacer**: rebote (`--bounce`) en toda transición interactiva; kickers en mayúscula con tracking positivo; un solo acento (azul cobalto) para toda acción primaria.
- **No hacer**: no usar gris plano para texto (siempre tinta con opacidad); no mezclar radios del Modernist original (0) con el sistema actual; no usar otra tipografía además de Archivo; no prometer visualmente algo simulado (pagos, Instagram real) sin dejarlo claro en el copy.
