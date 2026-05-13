# Pendientes · TyD 2º ESO

Lista de lo que queda por completar. Se actualiza con cada sprint.

## ✅ Completado en v1.1.0 (merge 2026-05-13)

- [x] **U4 Máquinas simples**: integrado el cuadernillo de mecanismos en
  `unidades/04-maquinas-simples/libro-digital.html` (809 KB) + 3 interactivos
  (`palancas.html`, `poleas.html`, `transmision.html`) + `actividades/index.html`.
- [x] **U5 Electricidad**: integrado el material de circuitos en
  `unidades/05-electricidad/libro-digital.html` (1.228 KB) + 3 interactivos cgmp
  (`cgmp.html`, `cgmp-mecanismos.html`, `cgmp-test.html`) sumados a los 3 ya
  existentes + `actividades/index.html`.
- [x] **U0 Dibujo técnico, U1 Tecnología y proceso, U2 Materiales,
  U3 Estructuras**: cada una con su `libro-digital.html` real (1.225–2.022
  líneas) + esqueleto de `actividades/`, `autocomprobacion/`, `interactivos/`,
  `proyecto/`.
- [x] `teoria.html` y `actividades.html` antiguos de U0–U5 convertidos en
  redirects al libro digital y a `actividades/` respectivamente.
- [x] El antiguo `unidades/04-maquinas-simples/interactivos/index.html`
  (agrupador "Próximamente") convertido en redirect al hub U4.

## Bloqueante para v1.2.0

- [ ] **U6 Ordenador y digital**: sigue siendo placeholder. Falta
  `libro-digital.html`, interactivos, actividades y proyecto.
- [ ] **U7 Programación (Scratch)**: sigue siendo placeholder. Falta
  `libro-digital.html` con bloques de Scratch, retos y rúbrica.
- [ ] **U8 Tecnologías emergentes**: sigue siendo placeholder. Falta
  `libro-digital.html`, interactivos (App Inventor, IA) y proyecto.
- [ ] Quitar el `<span class="pending-badge">Contenido en desarrollo</span>`
  de las tarjetas U6, U7 y U8 en el `index.html` cuando su material esté
  integrado (U0–U5 ya pueden quitarlo: tienen contenido real).

## Sub-bloque: completar autocomprobación y proyecto

- [ ] `autocomprobacion/index.html` de U0–U5 sigue siendo placeholder
  (8 líneas). Construir batería de preguntas de autoevaluación.
- [ ] `proyecto/index.html` de U0–U5 sigue siendo placeholder. Definir
  proyectos concretos (taller, montaje, programación, etc.).

## Pendientes de Manuel (no bloqueantes)

- [ ] **Criterios de evaluación LOMLOE concretos** por unidad. Rellenar el
  `<details class="criterios">` de cada `unidades/NN-slug/index.html`.
- [ ] **Bullets de "saber/hacer/evaluar"**: los actuales son una primera
  aproximación al currículo LOMLOE Andalucía. Revisar y ajustar a la
  programación oficial del departamento si difiere.
- [ ] **Duración estimada de las unidades**: rangos orientativos. Validar
  con la programación didáctica del departamento.
- [ ] **Proyectos integradores transversales**: definir los proyectos que se
  incluirán en `proyectos/` (a nivel de curso, no de unidad) y crearlos
  desde `assets/templates/PLANTILLA_proyecto.html`.
- [ ] **Herramientas**: añadir simuladores, glosario, calculadoras según
  vayan haciendo falta. Carpeta `herramientas/` está vacía.
- [ ] **Material imprimible (PDFs)**: cuando se generen.

## Mejoras técnicas detectadas (auditoría 2026-05-13)

- [ ] **Falsos positivos en `comprobar_enlaces.py`**: detecta como enlaces
  rotos las plantillas literales de JavaScript (`${imgs[k]}`, `${v.url}`,
  etc.) que aparecen en los `libro-digital.html` de U4 y U5. Mejorar el
  script para ignorar enlaces dentro de bloques `<script>` o con `${...}`.
- [ ] **Libros digitales pesados** (>300 KB): U4 (809 KB) y U5 (1.228 KB)
  pesan tanto porque embeben imágenes en `data:image/...` base64 (9 en U4,
  27 en U5). Pendiente decidir si vale la pena extraerlas a `img/` para
  reducir tamaño de carga inicial. Pro de mantenerlas: portabilidad
  (un solo archivo). Contra: rendimiento y caché.

## Infraestructura

- [x] **`git init`**: hecho. Repo activo con commits `Initial commit`,
  `index`, `actualización` y rama `backup-pre-v1.1.0` como snapshot del
  estado v1.0.0.
- [ ] **Configuración del worker Cloudflare**: crear el subdominio
  `tyd2-ies-jdq.malonso72.workers.dev`. Probar primer deploy con
  `npx wrangler deploy`.
- [ ] **Google Search Console**: añadir verificación si se quiere indexar
  (siguiendo el patrón de TECI con `googleXXX.html`).
- [ ] **Contador de visitas**: decidir si se añade GoatCounter como en TECI.

## Decisiones a discutir con Manuel

- En CyR se ha usado `trimestres/` (no `unidades/`) como carpeta raíz de
  los 3 trimestres porque encaja mejor con la semántica del curso. El brief
  v1.0.0 §4 sugería `unidades/` para ambos sitios; §6.1 mostraba
  `t3-ciberseguridad/` sin prefijo. Se ha aplicado el espíritu del brief.
  Si Manuel prefiere `unidades/`, basta con renombrar la carpeta y ajustar
  los enlaces del `index.html`.
- Las tarjetas U0–U5 del `index.html` siguen con badge "Contenido en
  desarrollo". Decidir si se quita ahora (ya hay libro digital) o se
  espera a tener también `autocomprobacion/` y `proyecto/` reales.
