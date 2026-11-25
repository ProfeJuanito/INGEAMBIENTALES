# CLAUDE.md — Misión Ambiental · COLMAYOR (INGEAMBIENTALES)

> **REPO PÚBLICO en GitHub.** Todo lo que se commitee aquí es visible para cualquiera.

## Qué es
Aplicativo web interactivo de orientación vocacional para estudiantes de último año de bachillerato:
seis "mundos" (agua, biodiversidad, obra/erosión, eficiencia industrial, aire, residuos) con minijuegos,
votaciones por equipos y un modo docente para proyectar en clase. Promociona el programa de Ingeniería
Ambiental del Colegio Mayor de Antioquia. Los casos de `cases.js` son simulaciones didácticas ficticias.

## Stack y estructura
HTML + CSS + JavaScript vanilla, sin compilación ni dependencias. Estado solo en `localStorage`.
- `index.html` — estructura; carga CSS/JS con `?v=futuro20261028` (subir la versión al cambiar archivos).
- `app.js` — navegación por fragmentos (`#inicio`, `#programa`…), exploración, votaciones, bitácora.
- `arcade.js` / `arcade.css` — cuatro minijuegos de acción (táctil y teclado).
- `art.js` — diagramas e instrumentos SVG originales.
- `cases.js` — cuatro casos didácticos (datos ficticios).
- `worlds-extra.js` / `.css` — mundos de aire y residuos; `worlds-integration.js` une los seis mundos e insignias.
- `program.js` — info institucional, malla (pénsum 1323: 10 semestres, 165 créditos), videos y fuentes con fecha de consulta.
- `styles.css`, `game-theme.css`, `anime-theme.css`, `comic-characters.css`, `program-garden.css`, `future-nav.css` — capas visuales.
- `assets/` — ilustraciones .webp (generadas con IA, declarado en README), fuentes .woff2 con sus licencias, `icon.svg`.
- `descargas/Mision-Ambiental-COLMAYOR.zip` — versión en un solo HTML (ojo: `*.zip` está en `.gitignore`; se versionó antes).
- `.nojekyll` — GitHub Pages publica los estáticos tal cual.

## Cómo correrlo
No hay build. Servidor estático local (Python real = miniconda, no el alias de la Store):
```
C:\Users\Admin\miniconda3\python.exe -m http.server 8080
```
y abrir `http://localhost:8080/`. Abrir `index.html` directo también funciona (rutas relativas).
No hay tests automatizados; la verificación descrita en el README fue manual en Chromium (390, 768 y 1440 px).

## Despliegue
GitHub Pages desde `main`, carpeta raíz (`/`). Cada push a `main` publica. Remoto: `ProfeJuanito/INGEAMBIENTALES`.
La URL de Pages que figura en el README apunta a otra cuenta de GitHub: confirmar cuál es la vigente antes de citarla.

## Estado y pendientes
Historial (más reciente primero): sync desde el PC "JUANITO" (25-nov-2026); destacar "Tu futuro" y compactar
apoyos/competencias/malla; simplificar retos y malla completa; personajes de cómic por reto; aventura anime
con seis mundos; rediseño con cuatro minijuegos; publicación inicial para Pages.
No hay TODO/FIXME en el código. Pendiente implícito: los datos de `program.js` (PIN 2027-1, tarifas 2026,
convocatorias) tienen vigencia por periodo y deben re-verificarse en fuentes oficiales del COLMAYOR.
El ZIP de `descargas/` hay que regenerarlo a mano si cambia la app.

## Reglas del proyecto
- Vive en Google Drive `Mi unidad\COLMAYOR\APPS\INGEAMBIENTALES` y se sincroniza entre dos PCs:
  trabajar en **un PC a la vez**, `git pull` al empezar y **commit + push al terminar**.
- **Público:** nunca subir `.env`, claves, tokens, correos, teléfonos ni datos personales del dueño o de estudiantes.
  No agregar datos reales de estudiantes, notas ni listados (la app no los necesita: todo queda en el navegador).
- `node_modules/` y entornos `.venv` fuera de Drive (p. ej. `C:\venvs\ingeambientales`) si alguna vez se agregan.
- Mantener rutas relativas (Pages sirve desde la subruta del repo) y el tono: frases breves para bachillerato.
- No usar imágenes generadas que parezcan fotos reales; las ilustraciones son estilo cómic/anime y así se declara.
- Todo en español.
