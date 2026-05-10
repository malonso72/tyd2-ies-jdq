# TyD 2º ESO · IES Jiménez de Quesada

**Tecnología y Digitalización · 2º ESO · Curso 2025-26**
Profesor: Manuel Alonso Herrera · Santa Fe (Granada)

Sitio estático servido por Cloudflare Workers Static Assets en
[tyd2-ies-jdq.malonso72.workers.dev](https://tyd2-ies-jdq.malonso72.workers.dev).

## Estructura

```
tyd2-ies-jdq/
├── index.html                  Hub principal con las 9 unidades
├── unidades/                   9 unidades didácticas
│   └── NN-slug/
│       ├── index.html          Hub de la unidad
│       ├── teoria.html
│       ├── actividades.html
│       └── img/
├── herramientas/               Simuladores, glosarios, calculadoras
├── proyectos/                  Trabajos integradores
├── _soluciones/                Privado, NO se despliega (.assetsignore)
├── img/                        fachadaiesjdq.jpg, logoantiguo.jpg
├── assets/
│   ├── css/                    common, hub, unidad, proyecto
│   ├── js/                     common, header, search
│   └── templates/              PLANTILLA_*
├── documentacion/              Privado: PROGRAMACION, DECISIONES, PENDIENTES
└── scripts/                    Auditoría: imágenes, archivos pesados, enlaces
```

## Despliegue

```bash
# Test local
python3 -m http.server 8000

# Validación pre-push
python3 scripts/comprobar_enlaces.py
python3 scripts/auditar_imagenes_huerfanas.py
python3 scripts/auditar_archivos_pesados.py --umbral 300

# Deploy (Cloudflare)
npx wrangler deploy
```

## Versionado

SemVer. Versión actual visible en pie del index.

- `1.0.X` parche: errata, ajuste menor
- `1.X.0` menor: añadir contenido a una unidad
- `X.0.0` mayor: añadir o reorganizar unidades

Cada commit lleva la versión al final del mensaje: `Añade ... [v1.X.Y]`.

## Convenciones

- HTML + CSS + JS vanilla. Sin frameworks.
- Tipografía: Barlow + Barlow Condensed + JetBrains Mono.
- Paleta: naranja-cobre (`--principal #D4700A`) con acento azul (`#1B4F8A`).
- Accesibilidad: skip-link, focus-visible, alt en imágenes, contraste AA.
- Modo impresión: oculta navegación, expande soluciones.

Modelo de referencia: `teci2-ies-jdq` (TECI II, 2º Bachillerato).
