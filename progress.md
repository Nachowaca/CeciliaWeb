# Progress — Web Cecilia Rodríguez Lisboa

## Hecho
- Repo en GitHub: https://github.com/Nachowaca/CeciliaWeb
- Prototipo animado (`design_handoff_cecilia_home/`):
  - **Home** (`Cecilia Home v2.html` + `styles-v2.css`): header, recuadro de la artista, escena de museo animada, chat del asistente (movido debajo de la escena, achicado).
  - **Galería** (`Cecilia Home v2.html`): fondo blanco tipo pared, grilla de 4 obras en una fila (2 en tablet, 1 en celular), botones "Postear en Instagram" (simulado) y "Comprar" (lleva a Remates).
  - **Panel de Cecilia** (`Cecilia Admin v2.html`): login simulado con Google, formulario para subir obra (foto, título, técnica, medidas, año, precio) que se publica al instante en una lista de "Publicadas".
  - Estilo general: rebote, redondeado, colorido — más animado que el diseño Modernist original (que sigue intacto en `Cecilia Home.html` / `styles.css`).

## Pendiente
1. **Remates**: diseño de la sección (subasta con tiempo / precio fijo / mixto) y cómo se cobra (Mercado Pago, WhatsApp, etc.).
2. **Talleres y Clases**: siguen siendo placeholders, sin diseñar.
3. **Chatbot**: hoy es solo para visitantes (simulado). Definir si también asiste a Cecilia (textos, descripciones, Instagram).
4. **Backend real** (próximo paso grande, con Supabase):
   - Login real con Google
   - Base de datos de obras
   - Storage de imágenes
   - Conectar "Publicar en la Galería" para que la obra aparezca de verdad en la Galería pública
   - Conectar "Postear en Instagram" a la API oficial de Instagram (requiere cuenta profesional vinculada a Facebook)
5. Confirmar si la cuenta de Instagram de Cecilia ya es profesional/vinculada a Facebook.
6. Hosting y dominio definitivos (hoy corre en servidor local de prueba).

## Cómo probarlo localmente
```bash
cd design_handoff_cecilia_home
python3 -m http.server 8934
```
Abrir `http://localhost:8934/Cecilia%20Home%20v2.html` y `http://localhost:8934/Cecilia%20Admin%20v2.html`.
