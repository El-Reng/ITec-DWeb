# Registro de Decisiones de Arquitectura (ADRs) - ITecnoFuturo

> **Estándar SDD (Gentle-AI)** | Historial Cronológico de Decisiones Técnicas y Protocolo de Guardas.

---

## Protocolo de Autorización Previa Obligatoria (Control de Guardas)
Cualquier modificación estructural que implique:
1. Alterar el modelo de datos o campos de las tarjetas.
2. Modificar las reglas de negocio o campos obligatorios de la inscripción.
3. Incorporar librerías o dependencias externas no aprobadas.
4. Modificar la paleta de colores oficial o la estructura de secciones.

**DEBE detener la ejecución directa**, explicar el impacto técnico y funcional al usuario y **solicitar confirmación explícita previa** antes de editar cualquier archivo.

---

## Registro de Decisiones de Arquitectura (ADRs)

### [ADR-001] Adopción de Antigravity Operating System (AGY-OS)
- **Fecha y Hora**: 2026-09-15 20:55:00 -03:00
- **Estado**: Aceptado
- **Contexto**: Se requiere un marco de trabajo de ingeniería de software de alto rendimiento, ágil y riguroso para guiar el desarrollo con el asistente.
- **Decisión**: Integrar los 6 pilares de AGY-OS: Rol Senior Product Engineer, Stack predeterminado de alta velocidad, Definition of Done estricta, Control de Guardas, Contexto Vivo en `docs/contexto/` y SDD Adaptativo con memoria continua (Gentle-AI & Engram).
- **Consecuencias**: Todo cambio se fundamenta técnicamente (POR QUÉ antes del CÓMO) y la memoria del proyecto se mantiene sincronizada sin amnesia de contexto.

---

### [ADR-002] Arquitectura SPA Single-File con HTML5, Tailwind CSS vía CDN y Vanilla JS
- **Fecha y Hora**: 2026-09-15 22:05:00 -03:00
- **Estado**: Aceptado
- **Contexto**:
  El proyecto es un trabajo académico para la carrera de desarrollo web. El estudiante debe demostrar su capacidad para estructurar HTML semántico, aplicar estilos modernos con utilidades y manipular el DOM con JavaScript nativo, garantizando que el código sea 100% defendible oralmente ante los profesores.
- **Decisión**:
  1. Construir una SPA autocontenida en un único archivo `index.html`.
  2. Utilizar **Tailwind CSS v3 vía CDN** (`https://cdn.tailwindcss.com`) con configuración personalizada inyectada mediante script.
  3. Resolver toda la interactividad con **JavaScript Vanilla ES6+**, evitando React, Vue, Angular, Node.js o bases de datos externas.
  4. Modo oscuro controlado mediante la clase `.dark` en la etiqueta `<html>` y persistencia en `localStorage`.
- **Consecuencias**:
  - Máxima portabilidad: abre al instante en cualquier navegador con doble clic.
  - Cero dependencias npm rotas, sin pasos de transpilación ni bundles opacos.

---

### [ADR-003] Gestión de Datos en Cliente y Simulación Local
- **Fecha y Hora**: 2026-09-15 22:08:00 -03:00
- **Estado**: Aceptado
- **Contexto**:
  El evento y sus proyectos son ficticios. No se debe implementar backend ni base de datos real.
- **Decisión**:
  1. Definir los 6 proyectos y la agenda de 2 días en arreglos de objetos JavaScript inmutables en memoria.
  2. Implementar la búsqueda y el filtrado en tiempo real evaluando directamente estas colecciones.
  3. Procesar el formulario de inscripción mediante `event.preventDefault()` y validar localmente sin enviar datos a un servidor.
- **Consecuencias**:
  - Experiencia inmediata y reactiva de alta velocidad.
  - Sin costos de hosting ni riesgos de indisponibilidad de servidor durante la evaluación académica.

---

### [ADR-004] Robot Mascota Vectorial Integrado y Generador de Credencial Digital
- **Fecha y Hora**: 2026-09-15 22:12:00 -03:00
- **Estado**: Aceptado
- **Contexto**:
  Se requiere que el evento transmita una atmósfera futurista memorable y que el formulario no sea un simple aviso estático, aportando un factor diferenciador en la defensa oral.
- **Decisión**:
  1. Diseñar al robot mascota (*T-Bot*) como un SVG vectorial optimizado con animación flotante e interacción de bienvenida.
  2. Al enviar la inscripción con éxito, generar una **Credencial de Pase Digital** estilizada con datos del asistente, código de acceso ficticio y botón para imprimir o guardar.
- **Consecuencias**:
  - Acabado visual superior y robustez técnica garantizada sin assets externos pesados.

---

### [ADR-005] T-Bot como Asistente Flotante Persistente (Overlay Fixed)
- **Fecha y Hora**: 2026-09-16 17:19:00 -03:00
- **Estado**: Aceptado
- **Contexto**:
  El robot mascota original ocupaba un bloque estático en el Hero. Se requirió que acompañara al usuario durante toda la navegación sin importar el scroll, operando de manera análoga a un asistente interactivo contextual.
- **Decisión**:
  1. Ubicar el widget de T-Bot con `position: fixed` en la esquina inferior derecha con `z-index: 9999`.
  2. Implementar diseño estilo EVA minimalista (blanco y geométrico) sobre contenedor tecnológico oscuro contrastante.
  3. Añadir mini-animaciones reactivas al clic (`botTalk`, `botWave`) junto a una burbuja flotante con tips tecnológicos rotativos del evento.
- **Consecuencias**:
  - Interfaz dinámica de alta retención que enriquece la experiencia de usuario en cualquier sección de la SPA.

---

### [ADR-006] Paleta Institucional Roja ITec en Modo Claro y Coherencia de Componentes
- **Fecha y Hora**: 2026-10-10 17:50:00 -03:00
- **Estado**: Aceptado
- **Contexto**:
  La identidad visual institucional del ITec Río Cuarto emplea tonalidades rojas. El modo claro presentaba disonancias con botones y badges que mantenían azules del modo oscuro.
- **Decisión**:
  1. Adoptar rojo institucional (`#C0392B`) y rubí (`#E74C3C`) para todos los elementos activos en modo claro: botones primarios de navbar, hero, formulario, modales y badges.
  2. Preservar intacta la paleta futurista índigo/cian/azul oscuro en el modo oscuro.
  3. Mantener el robot mascota con contenedor oscuro en ambos modos para preservar el contraste visual sobre fondos claros.
- **Consecuencias**:
  - Máxima coherencia cromática institucional en modo claro y estética futurista intacta en modo oscuro.
