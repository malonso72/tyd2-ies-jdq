# Pendientes · TyD 2º ESO

Lista de lo que queda por completar. Se actualiza con cada sprint.

## Bloqueante para v1.1.0 (Fase C del brief)

- [ ] **U4 Máquinas simples**: integrar el cuadernillo `mecanismos_2eso v9`
  en `unidades/04-maquinas-simples/actividades.html`. Manuel debe indicar
  la ruta local del archivo. Ajustar rutas internas a `assets/css/` y
  `assets/js/` del nuevo entorno. Verificar MathJax y vídeos.
- [ ] **U5 Electricidad**: idem con `circuitos_2eso v1` →
  `unidades/05-electricidad/actividades.html`.
- [ ] Generar `teoria.html` con contenido real para U4 y U5 a partir de la
  parte teórica embebida en los HTMLs originales (si la hubiera).
- [ ] Quitar el `<span class="pending-badge">Próximamente</span>` de las
  tarjetas U4 y U5 en el `index.html` cuando su material esté integrado.

> **Nota:** las tarjetas U4 y U5 actualmente NO tienen el badge "Próximamente"
> en el index porque ya tienen al menos el hub funcional, pero su material
> de actividades es placeholder. Revisar criterio con Manuel.

## Pendientes de Manuel (no bloqueantes)

- [ ] **Criterios de evaluación LOMLOE concretos** por unidad. Rellenar el
  `<details class="criterios">` de cada `unidades/NN-slug/index.html`.
- [ ] **Bullets de "saber/hacer/evaluar"**: los actuales son una primera
  aproximación al currículo LOMLOE Andalucía. Revisar y ajustar a la
  programación oficial del departamento si difiere.
- [ ] **Duración estimada de las unidades**: rangos orientativos. Validar
  con la programación didáctica del departamento.
- [ ] **Proyectos integradores**: definir los proyectos que se incluirán
  en `proyectos/` y crearlos desde `assets/templates/PLANTILLA_proyecto.html`.
- [ ] **Herramientas**: añadir simuladores, glosario, calculadoras según
  vayan haciendo falta.
- [ ] **Material imprimible (PDFs)**: cuando se generen.

## Infraestructura

- [ ] **`git init`**: el sistema en el que se generó este repo no tenía
  git instalado. Manuel debe ejecutar al recibirlo:
  ```bash
  cd tyd2-ies-jdq && git init -b main && git add . && \
  git commit -m "Bootstrap del sitio TyD 2º ESO [v1.0.0]"
  ```
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
