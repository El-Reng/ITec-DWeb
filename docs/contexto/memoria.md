# Engram - Memoria Activa y Persistente del Agente

## Directivas Maestras Guardadas (`mem_save`)
- **Directiva Global**: Antigravity Operating System (AGY-OS) con `trigger: always_on`.
- **Proyecto Activo**: **ITecnoFuturo — Expo de Innovación, Robótica e Inteligencia Artificial**.
- **Institución de Referencia**: Sede Campus del Instituto Tecnológico ITec de Río Cuarto (ficticio/académico).
- **Límites Técnicos Aceptados**:
  - Arquitectura: SPA en un único archivo `index.html`.
  - Estilos: Tailwind CSS v3 cargado vía CDN con configuración personalizada de colores y `darkMode: 'class'`.
  - Lógica: JavaScript Vanilla (ES6+) estructurado, limpio y sin librerías externas.
  - Tipografía: Inter (Google Fonts).
  - Cero dependencias backend, bases de datos o frameworks complejos (React/Vue/Angular).
- **Entidades de Datos Clave**:
  - 6 Proyectos de muestra: **DomoticHome IA** (renombrado desde Rubi Home AI), Atlas Assist, MecaHand, VisionGuard AI, AutoFactory Lab, NeuraCore.
  - Agenda de 2 Días con conferencias, talleres y demostraciones.
  - Formulario simulado para 4 tipos de visitantes con retroalimentación visual inmediata.
  - Robot Mascota (*T-Bot*): widget `position:fixed` siempre visible (esquina inferior derecha), estilo EVA (blanco/minimalista), animaciones CSS `botTalk`/`botWave` al clic, burbuja de tips rotativos.
- **Calidad y DoD**:
  - 4 Estados UI contemplados (Loading, Empty, Error, Success).
  - Menú hamburguesa funcional con cierre automático.
  - Modal accesible con bloqueo de scroll y soporte de tecla Escape.
  - Modo Claro / Oscuro con persistencia en `localStorage`.
  - **Modo Claro**: paleta roja (primario `#C0392B`, fondo `#FFF8F7`) inspirada en identidad de ITec.
  - **Modo Oscuro**: sin cambios (índigo `#6366F1`, cian `#06B6D4`, fondo `#080B14`).
  - Coherencia textual card/modal: `descripcionCorta` es el INICIO literal de `descripcionLarga`.

## Resumen de Sesiones (`mem_session_summary`)
- **Sesión 2026-09-15 20:26**: Preparación del entorno de desarrollo Windows (Git, Node, npm, PowerShell execution policy).
- **Sesión 2026-09-15 20:55**: Activación de AGY-OS y reglas maestras permanentes.
- **Sesión 2026-09-15 22:04**: Entrevista de definición inicial completada. Recepción de las especificaciones completas de los 5 bloques para **ITecnoFuturo**. Sincronización de `docs/contexto/`.
- **Sesión 2026-09-15 22:12**: Importación de biblioteca de skills AAS Core en `.agents/skills/`.
- **Sesión 2026-09-15 22:56**: Auditoría integral y Poda Inteligente de skills (39 conservadas).
- **Sesión 2026-09-16 02:50**: Primera versión de `index.html` construida y entregada. Validación JS OK.
- **Sesión 2026-09-16 17:19**: **Reescritura total** de `index.html` por petición del usuario. Cambios: (1) T-Bot → widget flotante fijo overlay `position:fixed`, EVA-style, animaciones CSS. (2) Modo claro rojo ITec. (3) Rubi Home AI → DomoticHome IA. (4) Coherencia card/modal garantizada. Validación JS: 3/3 bloques OK.
- **Sesión 2026-10-10 17:50**: **Corrección de modal, interacción de cards y unificación de botones**:
  1. *Fix Modal Inicial*: Se solucionó el conflicto de especificidad CSS en `#modal-backdrop`. El selector `#modal-backdrop { display: flex }` anulaba la clase `.hidden` de Tailwind al cargar. Se configuró `#modal-backdrop.hidden { display: none !important }` y `#modal-backdrop:not(.hidden) { display: flex }`, garantizando arranque cerrado y apertura/cierre fluido tanto por botón X, botón "Cerrar", tecla Escape y backdrop.
  2. *Interactividad de Cards*: Se aseguró el renderizado inicial con `renderCards()` en `DOMContentLoaded` y se convirtió el botón "Ver detalles →" en un `<button>` con detención de propagación y llamada explícita a `openModal()`.
  3. *Unificación de Botones en Modo Claro*: Todos los botones de acción (`btn-primary-dark`, botón de inscripción del navbar, formulario y modal) adoptan el gradiente/color rojo institucional `#C0392B` en modo claro (`html.light .btn-primary-dark { background: linear-gradient(...) !important }`), eliminando los azules disonantes.
  4. *T-Bot Mascota*: Se fijó el estilo de contenedor oscuro y tecnológico del robot para ambos modos (`!important`), manteniendo excelente contraste y visibilidad sobre el fondo claro.
