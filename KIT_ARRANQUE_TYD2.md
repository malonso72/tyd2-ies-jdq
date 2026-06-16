# Kit de arranque · TyD 2º ESO (tyd2-ies-jdq)

Última actualización: junio 2026
Mantenedor: Manuel Alonso Herrera (malonso72@gmail.com)
Repositorio: github.com/malonso72/tyd2-ies-jdq
Web en vivo: https://tyd2-ies-jdq.malonso72.workers.dev

---

## Quién soy y qué hago aquí

- Profesor de Tecnología y Digitalización en el IES Jiménez de Quesada (Santa Fe, Granada).
- Esta es la web docente del curso **Tecnología y Digitalización · 2º ESO**.
- Cloudflare Workers (Static Assets). Despliegue manual con `npx wrangler deploy` desde la raíz del repo. No hay auto-deploy desde GitHub.

## Otros repos que llevo

Si te pido tocar algo de OTRO curso, no es este repo. Dilo y abrimos otro chat.

- `tyd3-ies-jdq` — Tecnología y Digitalización · 3º ESO
- `tec4-ies-jdq` — Tecnología · 4º ESO
- `cyr1-ies-jdq` — Computación y Robótica · 1º ESO
- `teci2-ies-jdq` — Tecnología e Ingeniería II · 2º Bachillerato (tiene su propio KIT_ARRANQUE_TECI.md)
- `tecnologia-ies-jdq` — hub general

## Tono y forma de trabajar

- Español, conciso, sin verborrea.
- No uses emojis salvo que yo los use primero.
- Cambio en varios pasos → primero RECAP de lo entendido y espera mi OK antes de tocar nada.
- Cambio claro y autocontenido → hazlo y resumes al final.
- Los deploys los hago yo (`git push` + `npx wrangler deploy`); tú no tienes credenciales.
- A veces se cuelga `.git/index.lock` y bloquea commits desde GitHub Desktop. Hay que borrarlo del disco.
- Antes de cambios grandes en ficheros del repo, deja un backup con sufijo `.bak_<descripcion>` por si revertimos.

## Decisiones que NO hay que rediscutir

### Estructura del libro digital de cada unidad

- `unidades/0X-nombre/libro-digital.html` contiene `const banco = { 1: {...}, 2: {...}, ..., N: {...} }` con bloques numerados. Cada bloque tiene `titulo`, `desc_html`, `teoria_html` (con LaTeX `\\[ ... \\]` para MathJax), `ejs` (lista de ejercicios resueltos paso a paso) y `teoria_imgs` (claves que apuntan a `const imgs = {...}` mapeando a data URLs).
- Imágenes EMBEBIDAS como data URLs en `const imgs`. Eso hace los ficheros grandes pero autocontenidos.
- Esquemas vectoriales → SVG inline (no JPEG), con `width` y `height` EXPLÍCITOS y subíndices con `<tspan>` (NO uses caracteres Unicode ₁ ₂ ₜ — fallan con algunos fonts).

### Unidad 5 · Electricidad / Circuitos

- En **paralelo** uso la fórmula **producto entre suma**: R_eq = R₁·R₂ / (R₁+R₂). La fórmula general aparece SOLO en la teoría, junto con la del producto entre suma. En los ejercicios resueltos solo usamos la del producto entre suma. Es 2º ESO.
- La llamo "**R_eq**" (resistencia equivalente), NO R_t. En la teoría se menciona "también llamada resistencia total" para alumnos con esa terminología previa.
- En serie igual: R_eq, no R_t.
- Hay actividades en `unidades/05-electricidad/actividades/index.html` y autocomprobación en `unidades/05-electricidad/autocomprobacion/`.

### Proyecto Noria motorizada

- En `proyectos/noria/`.
- Imagen principal de la landing: `Noria_VistaFrontal.png` (vista acotada técnica). NO el póster.
- Póster: SOLO descarga (PDF + PNG). No es la imagen principal.
- **NO hay cuadernillo del alumno**. Se llama "**dosier del grupo**" (mismo contenido conceptual, sin plantilla preimpresa para que cada grupo lo organice).
- Recurso del profesor: `Noria_Plan_10sesiones.html` — planificación por sesiones, formato A4.

### Exámenes (cuando te pida uno)

Esquema por defecto salvo que te diga otra cosa:
- Word `.docx` para alumno + solucionario aparte (también `.docx`).
- Cabecera con datos del alumno (nombre, grupo, fecha) + caja "NOTA __/10".
- **Teoría tipo test**, 4 opciones, cuadradito ☐ delante. Sin penalización por error.
- **Ejercicios** con cálculos, espacio en blanco con borde inferior para que el alumno escriba.
- Solucionario: respuestas correctas marcadas en VERDE, desarrollo paso a paso.
- Si necesitas elegir tensión de pila para un ejercicio, usa 12 V por defecto (números redondos). Alternativas: 4,5 V o 9 V.

## Estado al cerrar este chat (junio 2026)

### Cambios SIN DESPLEGAR a la web en vivo

Para que lleguen a producción necesito (esto lo hago YO):
1. Borrar `tyd2-ies-jdq/.git/index.lock` si sigue ahí.
2. `git add -A && git commit -m "U5 paralelo SVG + noria v2" && git push`
3. `npx wrangler deploy` desde la raíz del repo.

Ficheros tocados que están en disco pero quizá aún no en producción:
- `unidades/05-electricidad/libro-digital.html` — SVG del paralelo con `width/height` y `<tspan>` en vez de Unicode subscripts. R_t renombrado a R_eq en bloques 10 (serie) y 11 (paralelo). Teoría con mención "también llamada resistencia total".
- `unidades/05-electricidad/img/paralelo_esquema_preview.{svg,png}` — preview del nuevo esquema (no es necesaria, es solo referencia).
- `proyectos/noria/index.html` — vista frontal como hero, cuadernillo fuera, plan v2 dentro, copy reescrita a "dosier del grupo".
- `proyectos/noria/assets/Noria_VistaFrontal.png` (nuevo · 1,4 MB)
- `proyectos/noria/assets/Noria_Plan_10sesiones.html` (nuevo · 41 KB)
- `proyectos/noria/assets/Noria_Cuadernillo_Alumno.{pdf,docx}` — BORRADOS.

Hay backups por si reviertes: `libro-digital.html.bak_req`, `libro-digital.html.bak_paralelo_fix`, `libro-digital.html.bak_productosuma`.

### Examen U5 2º ESO listo

Generado en `Downloads/` (NO está en el repo porque no es contenido web):
- `Examen_U5_Circuitos_2ESO.docx`
- `Examen_U5_Circuitos_2ESO_SOLUCIONARIO.docx`

Estructura: 12 preguntas test (0,25 c/u = 3 pts) + 7 ejercicios (1 pt c/u = 7 pts). Ejercicios 3 (serie) y 4 (paralelo) tienen sub-apartados a) R_eq y b) I_t con pila de 12 V.

## Cómo arrancar conmigo en septiembre

Cuando vuelva, espera a que te diga la tarea. No audites el repo ni propongas cosas por tu cuenta. Solo:

1. Lee este kit.
2. Confirma "listo, todo cargado" y queda a la espera.
3. Yo te indico la tarea concreta.

Si la tarea no es de este repo (TyD 2º ESO), avisa para abrir un chat separado para el repo correspondiente.
