# Errores Conocidos y Prevención de Gotchas - ITecnoFuturo

> **Estándar SDD (Gentle-AI)** | Bitácora de Trampas Típicas de Maquetado, Prevención de Scroll y Soluciones Responsive.

---

## 1. Trampas Frecuentes de Maquetado y Soluciones Blindadas

Este catálogo documenta los errores más comunes cometidos por desarrolladores en proyectos SPA con Tailwind y Vanilla JS, y cómo el código de **ITecnoFuturo** los previene desde su concepción:

### 1. Desbordamiento y Scroll Horizontal en Móviles (Scroll Roto)
* **Causa Raíz**: Uso de anchos absolutos fijos en píxeles (`w-[450px]`), anchos de viewport (`w-screen` o `w-[100vw]` que no descuentan el scrollbar), o márgenes negativos excesivos en contenedores sin corte.
* **Prevención Implementada**:
  - Declarar `overflow-x: hidden` en el elemento `<html>` y `<body>`.
  - Estructurar las secciones con contenedores elásticos: `w-full max-w-7xl mx-auto px-4 sm:px-6 lg:px-8`.
  - En móviles, forzar anchos en porcentaje (`w-full`) en lugar de anchos estáticos.

---

### 2. Menú Hamburguesa Atrapado al Hacer Scroll o Navegar
* **Causa Raíz**: El usuario abre el menú hamburguesa en su teléfono, pulsa un enlace hacia `#proyectos`, la página hace scroll pero el menú permanece desplegado tapando el contenido.
* **Prevención Implementada**:
  - Escuchar el evento `click` en todos los enlaces internos dentro del menú móvil para alternar la clase `hidden` y replegar el panel automáticamente tras la pulsación.

---

### 3. Modal con Scroll Doble o sin Atrapamiento de Teclado
* **Causa Raíz**: Abrir una ventana modal sin fijar el scroll de la página provoca que al scrollear dentro del modal también se mueva el fondo; además, muchos modales no se pueden cerrar con la tecla `Escape`.
* **Prevención Implementada**:
  - Al invocar `abrirModal()`, aplicar `document.body.classList.add('overflow-hidden')`.
  - Al cerrar, remover la clase `overflow-hidden`.
  - Registrar un listener global `keydown` para cerrar el modal inmediatamente si `event.key === 'Escape'`.
  - Cerrar si el usuario hace clic sobre el backdrop exterior translúcido.

---

### 4. Parpadeo Blanco (*FOUC*) al Alternar Modo Oscuro
* **Causa Raíz**: Cargar el script de verificación de tema al final del `<body>` genera un destello de luz blanca antes de que el script aplique la clase `.dark`.
* **Prevención Implementada**:
  - Colocar un pequeño script síncrono inline dentro de `<head>` antes de los estilos:
    ```javascript
    if (localStorage.theme === 'dark' || (!('theme' in localStorage) && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
      document.documentElement.classList.add('dark');
    } else {
      document.documentElement.classList.remove('dark');
    }
    ```

---

### 5. Tarjetas Vacías o Rotas por Imágenes Externas Caídas
* **Causa Raíz**: Si falla la conexión a internet o el servidor externo de imágenes bloquea peticiones, las tarjetas quedan con iconos rotos y desalineadas.
* **Prevención Implementada**:
  - Añadir atributo `loading="lazy"` y un manejador `onerror` en cada etiqueta `<img>` que cargue automáticamente un placeholder visual generado con un gradiente y un icono SVG tecnológico en caso de fallo.

---

### 6. Recarga Accidental de la SPA al Enviar el Formulario
* **Causa Raíz**: Omitir `event.preventDefault()` en el formulario de inscripción genera una recarga completa del navegador (`GET` o `POST`), perdiendo el estado actual y reiniciando la navegación.
* **Prevención Implementada**:
  - Interceptar el evento con `formInscripcion.addEventListener('submit', (e) => { e.preventDefault(); ... })`.
  - Realizar la validación de campos manualmente antes de simular el guardado y mostrar la credencial.

---

### 7. Búsqueda sin Resultados que Deja la Pantalla "Muerta"
* **Causa Raíz**: Si el usuario busca un término que no coincide (ej. "dron cuántico"), la grilla queda vacía sin ninguna explicación, haciendo creer que el sitio se congeló.
* **Prevención Implementada**:
  - Si la longitud de proyectos filtrados es `0`, renderizar el componente **Empty State** con un mensaje empático (*"No se encontraron proyectos para tu búsqueda"*) y un botón destacado para limpiar los filtros de inmediato.

---

### 8. Pérdida de Contraste en Textos Secundarios al Pasar a Modo Claro
* **Causa Raíz**: Definir estilos pensados solo para fondo oscuro provocando que en modo claro los textos se vuelvan invisibles o ilegibles.
* **Prevención Implementada**:
  - Emparejar sistemáticamente todas las utilidades de color:
    - Textos: `text-slate-900 dark:text-slate-100` y `text-slate-600 dark:text-slate-400`.
    - Superficies: `bg-white dark:bg-[#111827]`.
    - Bordes: `border-slate-200 dark:border-slate-800`.
