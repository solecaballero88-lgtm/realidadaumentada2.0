# 🌳🦉🤖 Aventura en el monte formoseño

Proyecto que va **todo junto en la misma carpeta**:

| Archivo | Qué es |
|---|---|
| `index.html` | Página de inicio con los 3 botones |
| `lechu.html` | Botón 1: charla en voz alta con el Profesor Lechu solo |
| `escenario.html` | Botón 2: Don Algarrobo, el Profesor Lechu y Botín conversan por turnos |
| `ar.html` | Botón 3: realidad aumentada: enfocás la lámina y aparecen en 3D Lechu, Don Algarrobo y Botín, con los que podés hablar |
| `lamina-profesor-lechu.jpg` | **Lámina del Profesor Lechu** (el marcador): para imprimir o mostrar en otra pantalla |

Agentes de ElevenLabs usados (IDs públicos, no son claves secretas):
- Don Algarrobo: `agent_2701m5hrpabffjmvxtpfft9ywr8x`
- Profesor Lechu: `agent_1101m5k81rs0eyvtapadhj8qqf95`
- Botín (otra cuenta): `agent_6501m5k99cj6fwcbhjrg0y8qbpyk`

---

## Paso 1 — Antes de publicar: habilitar a Botín (una sola vez)
Botín vive en otra cuenta de ElevenLabs, así que esto se hace desde esa cuenta:
1. Abrí el agente Botín → **Security** (Seguridad).
2. En **Overrides**, activá **First message** (primer mensaje).
3. Verificá que la **autenticación** esté desactivada (el agente tiene que ser público).

Sin esto, en la charla de los 3 amigos Botín habla con la voz del navegador y la página lo avisa. Los otros dos agentes ya están configurados.

## Paso 2 — Publicar con https (la cámara y el micrófono no andan abriendo el archivo suelto)
**GitHub Pages**
1. Creá un repositorio (por ejemplo `aventura-monte`).
2. Subí los 4 archivos `.html` a la raíz (**Add file → Upload files**).
3. **Settings → Pages → Deploy from a branch → `main` / `(root)` → Save**.
4. En un minuto queda en `https://TU-USUARIO.github.io/aventura-monte/`.

**Netlify (alternativa):** arrastrá la carpeta con los 4 archivos a netlify.com/drop.

## Paso 3 — Probar cada botón (en el celular o en la compu)
**Botón 1 · Hablar con el Profesor Lechu**
1. Tocá «🎙️ Hablar con el Profesor Lechu» y aceptá el micrófono.
2. Tiene que saludar una sola vez, moverse y mover el pico con la voz.
3. Probá: «¿Por qué las lechuzas ven de noche?», «Contame un chiste», «¿Quién sabe más, vos o Don Algarrobo?».
4. «Finalizar conversación» corta la charla.

**Botón 2 · Charla de los 3 amigos**
1. Tocá «▶ Comenzar la charla» y aceptá el permiso de audio (el micrófono queda silenciado).
2. Hablan de a uno, en orden, sin pisarse: Algarrobo → Lechu → Botín (10 turnos).
3. Si sale un aviso de «voz del navegador», revisá el Paso 1 para Botín.
4. «Detener» corta; «Ver de nuevo» la repite. El guion se edita en `escenario.html`, constante `GUION`.

**Botón 3 · Realidad aumentada (lámina de Lechu + diálogo con los 3 agentes)**
1. Imprimí `lamina-profesor-lechu.jpg` o abrila en otra pantalla (también se descarga desde la propia página).
2. Tocá **📷 Abrir cámara** y aceptá el permiso. La primera vez prepara la lámina y tarda unos segundos; después queda guardada en el dispositivo.
3. Enfocá al Profesor Lechu. Cuando diga «¡Lámina detectada!», aparecen en 3D Lechu (al centro), Don Algarrobo y Botín sobre la lámina.
4. Con **Todos / Solo Lechu / Solo Algarrobo / Solo Botín** elegís a quién ver.
5. Tocá **Hablar con Lechu / Algarrobo / Botín**, aceptá el micrófono y conversá en voz alta. El personaje te saluda, mueve la boca con su voz y los subtítulos muestran lo que se dice. **Cortar voz** termina la charla.
6. Si no tenés cámara o no abre: **🧊 Vista 3D sin cámara** muestra la misma escena sobre la lámina en pantalla y permite hablar igual.
7. **Detener** cierra la cámara y vuelve a la pantalla de instrucciones.

## Consejos para buenos marcadores
- Imágenes con mucho detalle y contraste (fotos, ilustraciones, tapas). Sin fondos lisos ni degradés.
- No uses dos marcadores parecidos entre sí.
- Buena luz y sin reflejos.
- Videos de menos de 15–20 MB; figuras 3D en `.glb` con texturas incluidas.

## Si algo falla
- **No abre cámara o micrófono:** la página no está en https o falta el permiso del navegador.
- **No reconoce el marcador:** poco detalle; probá otra imagen.
- **La cámara no reconoce la lámina:** probá con más luz, sin reflejos y con la lámina entera dentro de la pantalla; si no, copiame el mensaje que aparece sobre los botones.
- **Un personaje no habla:** abrí la consola (F12) y copiame el error.

## Estado
- Revisado: la sintaxis del código de las páginas.
- **Sin probar en un navegador real:** las conexiones con los tres agentes, las voces, la cámara y el reconocimiento de marcadores.
- La lámina es solo la del Profesor Lechu (personaje principal). Sin probar: que MindAR reconozca la lámina en tu celular y que el tamaño de los personajes sobre ella quede bien (se ajusta en `layout()` de `ar.html`).
