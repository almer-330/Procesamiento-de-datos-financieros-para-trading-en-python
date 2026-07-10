# IA Humana · KB — Procesamiento de Datos Financieros para Trading en Python

Manual personal de consulta del curso. Cada módulo agrupa las lecciones que voy tomando,
convertidas en tarjetas de conocimiento (código, explicaciones, quizzes) para no tener
que volver a ver los videos.

## Estructura del sitio

```
index.html                     → portada con los 14 módulos
assets/css/hub.css              → estilos compartidos de portada y páginas de módulo
modulos/
  01-acciones/index.html        → índice de lecciones del módulo 1
  02-indices-bursatiles/...     → módulos 2–14, placeholders "Próximamente"
  ...
lecciones/
  01-acciones/
    00-conceptos-fundamentales.html
    01-yfinance.html
    02-wallstreet-tiempo-real.html
    02b-fix-wallstreet-yahoo.html
    03-pandas-datareader.html
```

Cada lección es un archivo HTML autocontenido (su propio CSS/JS), tal como las generas
normalmente. Lo único que se le agrega es una barra superior de navegación (breadcrumb)
para poder volver al módulo o a la portada.

## Cómo publicarlo en GitHub Pages

1. Crea un repositorio nuevo en GitHub, por ejemplo `ia-humana-trading-kb`.
2. Dentro de esta carpeta (`site/`), inicializa git y sube el contenido:

   ```bash
   git init
   git add .
   git commit -m "Sitio inicial: módulo 1 - extracción de datos de acciones"
   git branch -M main
   git remote add origin https://github.com/TU_USUARIO/ia-humana-trading-kb.git
   git push -u origin main
   ```

3. En GitHub, ve a **Settings → Pages**, elige la rama `main` y la carpeta raíz `/ (root)`.
4. Tu sitio quedará publicado en:
   `https://TU_USUARIO.github.io/ia-humana-trading-kb/`

## Cómo agregar una lección nueva

1. Genera tu tarjeta de conocimiento en HTML como sueles hacerlo (dark terminal style).
2. Guárdala dentro de `lecciones/<modulo>/`, con un nombre tipo `04-nombre-leccion.html`.
3. Agrégale la barra de navegación superior (breadcrumb) — copia el bloque de estilo y
   HTML que ya tienen las lecciones del módulo 1, ajustando el enlace del módulo y el
   texto de la lección actual.
4. Agrega una tarjeta nueva en `modulos/<modulo>/index.html`, dentro de `.lesson-list`,
   siguiendo el mismo patrón que las tarjetas existentes.
5. Si es la primera lección de un módulo que estaba "Próximamente", actualiza en
   `index.html` (portada):
   - cambia la clase de la tarjeta de `module-card pending` a `module-card ready`
   - cambia el badge de estado a algo como `<span class="module-status ready">N lecciones</span>`
   - actualiza el contador de "Lecciones publicadas" en el hero.

## Cómo agregar un módulo completo con varias lecciones desde cero

Si quieres que Claude te genere directamente la carpeta y el índice del módulo con todas
sus lecciones ya integradas, sube los HTML de las lecciones de ese módulo y pide que se
repita el mismo patrón que se usó para el módulo 1 (extracción de datos de acciones).

---

Manual personal · IA Humana — *No te enseño a usar IA. Te enseño a pensar con ella.*
