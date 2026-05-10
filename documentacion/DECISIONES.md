# Decisiones de diseño · TyD 2º ESO

Bitácora de decisiones técnicas y editoriales del proyecto.
Formato: `YYYY-MM-DD · Decisión` con justificación.

## 2026-05-10 · Bootstrap del sitio (v1.0.0)

- **Modelo de referencia:** `teci2-ies-jdq` (TECI II, 2º Bach.). Misma filosofía
  vanilla y misma tipografía (Barlow + Barlow Condensed + JetBrains Mono).
- **Estructura por unidades didácticas integradas** (no por bloques temáticos
  separados como TECI). Cada unidad tiene `index.html` (hub), `teoria.html`,
  `actividades.html` y opcionalmente `reto.html`. Justificación: en ESO la
  separación rígida `teoria/ ejercicios/ examenes/` propia de PEvAU no aplica.
- **Paleta naranja-cobre** (`--principal #D4700A` + acento azul `#1B4F8A`)
  para diferenciar visualmente del azul de TECI II y del verde-cian de CyR.
- **CSS modular** en cuatro archivos: `common.css` (variables + cabecera +
  mini-test), `hub.css` (index y hubs), `unidad.css` (páginas internas) y
  `proyecto.css` (proyectos integradores). Las paletas viven en `:root` de
  `common.css` para poder cambiarlas en un solo sitio.
- **JS modular**: `common.js` (mini-test, soluciones colapsables, MathJax,
  sidebar activa), `header.js` (cabecera reutilizable), `search.js` (buscador
  global del index).
- **Solucionarios privados** en `_soluciones/`, excluido del despliegue vía
  `.assetsignore` (convención TECI).
- **Cloudflare Workers Static Assets** como hosting (no Pages). Se mantiene la
  configuración mínima en `wrangler.toml` calcada del modelo TECI.

## Convenciones

- Slug de unidad: `NN-kebab-case` con dos dígitos (`00-`, `01-`, ..., `08-`)
  para que el orden alfabético coincida con el orden didáctico.
- Commits: español, verbo en imperativo, versión al final entre corchetes.
- Sin frameworks. Sin CDNs salvo Google Fonts y MathJax (cuando aplique).
