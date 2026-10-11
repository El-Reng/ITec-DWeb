# Glosario del Proyecto e Interfaz - ITecnoFuturo

> **Estándar SDD (Gentle-AI)** | Diccionario de Términos de Dominio y Componentes UI.

---

## 1. Términos del Dominio y Negocio
Conceptos rectores de la exposición tecnológica que deben utilizarse con estricta coherencia en títulos, descripciones y microcopy:

| Término | Definición y Contexto en el Sitio |
| :--- | :--- |
| **ITecnoFuturo** | Nombre oficial de la gran exposición tecnológica ficticia de innovación, robótica e inteligencia artificial. |
| **Expo Tecnológica** | Exposición pública e interactiva que exhibe desarrollos técnicos, prototipos y experiencias de vanguardia. |
| **Inteligencia Artificial (IA)** | Sistemas que ejecutan tareas como visión computacional, comprensión de lenguaje y soporte autónomo para la toma de decisiones. |
| **Robótica** | Ingeniería aplicada al diseño, fabricación y control de autómatas físicos y colaborativos. |
| **Automatización** | Integración de sensores, PLC y actuadores para ejecutar procesos mecánicos de manera autónoma. |
| **Domótica** | Tecnologías de automatización inteligente del hogar (iluminación, climatización, seguridad y control por voz). |
| **Visión Artificial** | Análisis algorítmico de imágenes y video en tiempo real para detección, reconocimiento y seguimiento de patrones. |
| **Robótica Asistiva** | Prótesis mecatrónicas y dispositivos diseñados para mejorar la motricidad e independencia de personas con discapacidad. |
| **Prototipo** | Modelo funcional en fase experimental construido para validar hipótesis técnicas en entorno de laboratorio. |
| **Expositor** | Equipo de estudiantes, docentes o investigadores que presentan un desarrollo en su stand de la expo. |
| **Demo en Vivo** | Demostración práctica y dinámica en tiempo real del funcionamiento del proyecto ante el público. |
| **Exhibición** | Muestra estática o guiada con paneles interactivos y explicaciones técnicas de un proyecto terminado. |
| **Agenda** | Cronograma oficial de conferencias magistrales, workshops y demostraciones en vivo durante las dos jornadas. |
| **Inscripción** | Proceso simulado de registro para reservar un pase de acceso libre a la exposición. |
| **Robot Mascota** | Personaje interactivo (*T-Bot*) que representa el espíritu de la expo y da la bienvenida a los visitantes. |

---

## 2. Componentes de Interfaz de Usuario (UI)
Glosario de los bloques visuales e interactivos que componen la SPA:

| Componente | Rol en la Interfaz | Comportamiento Técnico |
| :--- | :--- | :--- |
| **SPA (Single Page Application)** | Arquitectura web de un solo documento. | Navegación fluida por anclas (`#id`) mediante `scroll-behavior: smooth`. |
| **Navbar Sticky** | Barra de navegación superior fija. | Permanece visible al hacer scroll; contiene logotipo, menú, tema y CTA. |
| **Menú Hamburguesa** | Botón de navegación móvil. | Despliega y repliega el menú en celulares; se cierra automáticamente al cliquear un enlace. |
| **Hero Section** | Portada principal de alto impacto visual. | Presenta el lema, fecha, ubicación, mascota SVG y accesos directos principales. |
| **Card de Proyecto** | Tarjeta de presentación de un prototipo. | Contiene imagen, badges de categoría/estado, descripción corta y botón "Ver detalles". |
| **Modal de Ficha Técnica** | Diálogo emergente accesible. | Despliega información técnica ampliada, bloquea el scroll de fondo y responde a tecla `Escape`. |
| **Filtro por Categorías** | Barra de botones interactivos. | Filtra los proyectos visibles en la grilla sin recargar la página. |
| **Buscador en Tiempo Real** | Campo de entrada de texto reactivo. | Filtra instantáneamente las tarjetas mediante el evento `input` en JavaScript. |
| **Empty State (Estado Vacío)** | Bloque de retroalimentación informativa. | Aparece cuando una búsqueda no arroja coincidencias, ofreciendo botón para reiniciar filtros. |
| **Tabs de Agenda** | Selector de pestañas interactivas. | Permite alternar la visualización del cronograma entre el *Día 1* y el *Día 2*. |
| **Formulario de Inscripción** | Interfaz de captura de datos del visitante. | Valida campos requeridos, previene recarga y dispara la confirmación. |
| **Pase Digital Simulado** | Credencial virtual generada en pantalla. | Muestra el resumen del registro, código ficticio y opción de impresión. |
| **Theme Toggle** | Interruptor de Modo Oscuro/Claro. | Alterna la clase `.dark` en `<html>` y almacena la elección en `localStorage`. |
| **Botón Volver Arriba** | Botón flotante de navegación rápida. | Aparece dinámicamente tras cierto scroll y lleva al usuario al tope de la página. |
