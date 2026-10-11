# Arquitectura del Sistema - ITecnoFuturo

> **Estándar SDD (Gentle-AI)** | Documento de Arquitectura de Software y Maquetado SPA.

---

## 1. Visión General del Proyecto
**ITecnoFuturo** es una **Single Page Application (SPA)** moderna, futurista y profesional desarrollada con fines académicos. Su propósito es promocionar una gran exposición tecnológica ficticia de dos jornadas en la **Sede Campus del Instituto Tecnológico ITec de Río Cuarto**.

El sitio permite a los visitantes explorar prototipos de innovación en Inteligencia Artificial, Robótica, Automatización, Domótica, Visión Artificial y Robótica Asistiva; consultar la agenda de charlas y talleres; e inscribirse de manera simulada.

---

## 2. Stack Tecnológico Aprobado (Tecnologías Permitidas)
Para garantizar máxima portabilidad, rendimiento nativo y una defensa oral clara ante el tribunal académico:

- **Estructura**: **HTML5 Semántico** puro (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<figure>`, `<aside>`, `<footer>`).
- **Framework CSS**: **Tailwind CSS v3 vía CDN** (`https://cdn.tailwindcss.com`) configurado con paleta personalizada de colores futuristas y soporte de modo oscuro por clase (`darkMode: 'class'`).
- **Lógica e Interactividad**: **JavaScript Vanilla (ES6+)** nativo sin frameworks reactivos, encapsulado y estructurado con responsabilidades bien separadas.
- **Tipografía**: Fuente **Inter** importada desde Google Fonts con fallback a fuentes sans-serif seguras del sistema.
- **Iconografía y Recursos Visuales**: SVGs inline optimizados para nitidez infinita, imágenes temáticas de alta fidelidad (Unsplash) y robot mascota vectorial integrado.

---

## 3. Tecnologías Prohibidas (Límites Técnicos Estrictos)
Queda estrictamente prohibido introducir las siguientes tecnologías y prácticas:

- ❌ **Sin frameworks reactivos**: Prohibido usar React, Vue, Angular, Svelte o similares.
- ❌ **Sin backend ni entornos de servidor**: Prohibido Node.js, Express, Python, Django, PHP o Java.
- ❌ **Sin bases de datos**: Prohibido el uso de PostgreSQL, MySQL, MongoDB, Firebase o Supabase.
- ❌ **Sin APIs externas de IA**: Prohibido integrar llamadas a OpenAI, Gemini u otros modelos. La IA es la **temática** del evento, no un backend de la página.
- ❌ **Sin estilos inline**: Prohibido el uso de atributos `style="..."` (salvo propiedades dinámicas de CSS personalizadas indispensables). Toda la presentación debe resolverse mediante utilidades de Tailwind CSS.
- ❌ **Sin pasarelas reales**: Prohibido añadir cobros, pasarelas de pago o autenticaciones reales. La inscripción es una experiencia interactiva simulada en el navegador.

---

## 4. Mapa Modular de Secciones (Arquitectura de Arriba hacia Abajo)

```plaintext
┌─────────────────────────────────────────────────────────────┐
│ 1. NAVBAR FIXED                                             │
│    - Logo + Badge ITecnoFuturo                              │
│    - Navegación Smooth Scroll (Inicio, Sobre, Proyectos...) │
│    - Theme Toggle (Modo Oscuro / Modo Claro)                │
│    - Botón CTA Inscripción + Menú Hamburguesa Móvil         │
├─────────────────────────────────────────────────────────────┤
│ 2. HERO / PORTADA                                           │
│    - Título del Evento + Lema Futurista                     │
│    - Fechas Ficticias & Sede Campus ITec Río Cuarto         │
│    - Botones de Acción: [Explorar Proyectos] [Inscribirme]  │
│    - Robot Mascota Interactivo (T-Bot) con Tooltip Saludo   │
├─────────────────────────────────────────────────────────────┤
│ 3. SOBRE ITECNOFUTURO                                       │
│    - Propósito, Valores de Innovación y Misión Académica    │
│    - 6 Ejes Tecnológicos (IA, Robótica, Automatización...)  │
├─────────────────────────────────────────────────────────────┤
│ 4. PROYECTOS DESTACADOS                                     │
│    - Showcase de los 3 desarrollos experimentales clave     │
├─────────────────────────────────────────────────────────────┤
│ 5. EXPLORADOR & CATÁLOGO DE PROYECTOS                       │
│    - Buscador en tiempo real por nombre y expositor         │
│    - Filtros por categoría (Todos, IA, Robótica, etc.)      │
│    - Grilla Responsive (1 col móvil, 2 tablet, 3 desktop)   │
│    - 4 Estados UI: Loading, Éxito, Detalle y Empty State    │
├─────────────────────────────────────────────────────────────┤
│ 6. MODAL INTERACTIVO DE FICHA TÉCNICA                       │
│    - Vista expandida del proyecto seleccionado              │
│    - Tecnologías, expositor, descripción y estado           │
│    - Accesible: Cierre por botón X, Escape y Backdrop       │
├─────────────────────────────────────────────────────────────┤
│ 7. AGENDA DEL EVENTO (CRONOGRAMA DE 2 DÍAS)                 │
│    - Tabs interactivos: [Día 1: Robótica] [Día 2: IA]       │
│    - Lista cronológica con tipo de actividad y expositor    │
├─────────────────────────────────────────────────────────────┤
│ 8. INFORMACIÓN DE SEDE & ACCESO                             │
│    - Datos del Campus ITec Río Cuarto, horarios y acceso    │
│    - Disclaimer de evento ficticio con fines educativos     │
├─────────────────────────────────────────────────────────────┤
│ 9. FORMULARIO DE INSCRIPCIÓN SIMULADA                       │
│    - Campos: Nombre, Email, Perfil, Asistentes, Interés     │
│    - Validación de campos y confirmación visual inmediata   │
│    - Credencial Digital Virtual generada dinámicamente      │
├─────────────────────────────────────────────────────────────┤
│ 10. FOOTER INSTITUCIONAL                                    │
│     - Identidad, enlaces rápidos, redes y créditos ITec     │
└─────────────────────────────────────────────────────────────┘
```

---

## 5. Modelo de Datos en Memoria (JavaScript)
Los proyectos y la agenda se gestionan como estructuras de datos puras en memoria:

```javascript
// Estructura canónica de un proyecto
{
  id: "domotica-home",
  nombre: "DomoticHome IA",
  categoria: "domotica",
  categoriaLabel: "IA / Domótica",
  expositor: "Laboratorio de Domótica Aplicada — ITec",
  descripcionCorta: "Sistema experimental que combina procesamiento de lenguaje natural con domótica inteligente para controlar la iluminación, climatización y seguridad del hogar mediante comandos de voz…",
  descripcionLarga: "Sistema experimental que combina procesamiento de lenguaje natural con domótica inteligente para controlar la iluminación, climatización y seguridad del hogar mediante comandos de voz. A diferencia de los asistentes comerciales, DomoticHome IA funciona completamente de forma local, sin enviar ningún audio a la nube, priorizando la privacidad de la familia. El prototipo incluye cuatro nodos IoT distribuidos por una habitación modelo.",
  tecnologias: ["Procesamiento de Voz", "IoT", "Microcontroladores ESP32", "Privacidad Local"],
  estado: "Demo en vivo", // "Demo en vivo" | "Prototipo" | "Exhibición"
  imagen: "https://images.unsplash.com/photo-1558002038-1055907df827?auto=format&fit=crop&w=800&q=80"
}
```
