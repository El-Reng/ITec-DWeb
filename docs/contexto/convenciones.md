# Convenciones de Código y Diseño - ITecnoFuturo

> **Estándar SDD (Gentle-AI)** | Convenciones Semánticas, Paleta de Colores, Tipografía y Responsive.

---

## 1. Reglas Semánticas de HTML5
Para cumplir con estándares profesionales de accesibilidad y SEO técnico:

- **Contenedores Estructurales**: Usar estrictamente `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>` y `<footer>`.
- **Botones vs Enlaces**:
  - Toda acción que no navegue a otra URL o ID debe ser un `<button type="button">`.
  - Todo enlace de navegación interna o externa debe ser un `<a href="...">`.
  - Prohibido asignar listeners de clic a etiquetas `<div>` o `<span>` sin rol semántico.
- **Formularios**:
  - Todo campo debe contar con su etiqueta `<label>` asociada mediante `for="id"`.
  - Atributos requeridos explícitos: `required`, `type="email"`, `min="1"`.
- **Imágenes**:
  - Atributo `alt` descriptivo obligatorio en cada imagen para lectores de pantalla.

---

## 2. Paleta Oficial de Colores (Tailwind CSS)
Configurada a nivel global para garantizar una estética de innovación y alto contraste:

| Token / Rol | Código HEX | Clases Tailwind Dark | Clases Tailwind Light |
| :--- | :--- | :--- | :--- |
| **Fondo Principal** | `#080B14` | `bg-[#080B14]` | `bg-slate-50` |
| **Fondo de Tarjetas** | `#111827` | `bg-[#111827]` | `bg-white` |
| **Primario (Índigo)** | `#6366F1` | `bg-indigo-600` / `text-indigo-400` | `bg-indigo-600` / `text-indigo-600` |
| **Acento (Cian)** | `#06B6D4` | `bg-cyan-500` / `text-cyan-400` | `bg-cyan-600` / `text-cyan-600` |
| **Acento (Violeta)** | `#A78BFA` | `bg-purple-500` / `text-purple-400` | `bg-purple-600` / `text-purple-600` |
| **Texto Principal** | `#F8FAFC` | `text-slate-50` | `text-slate-900` |
| **Texto Secundario** | `#94A3B8` | `text-slate-400` | `text-slate-600` |
| **Bordes y Divisores**| `#334155` | `border-slate-700` | `border-slate-200` |

### Estados Semánticos de Proyectos
- **Demo en vivo**: Fondo verde esmeralda translúcido con pulso (`bg-emerald-500/10 text-emerald-400 border-emerald-500/30`).
- **Prototipo**: Fondo cian tecnológico (`bg-cyan-500/10 text-cyan-400 border-cyan-500/30`).
- **Exhibición**: Fondo violeta distinguido (`bg-purple-500/10 text-purple-400 border-purple-500/30`).

---

## 3. Tipografía y Jerarquía Visual
- **Fuente Principal**: **Inter** (`font-sans`), importada desde Google Fonts:
  ```html
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
  ```
- **H1 (Hero Title)**: `text-4xl sm:text-5xl lg:text-6xl font-extrabold tracking-tight`.
- **H2 (Secciones)**: `text-3xl sm:text-4xl font-bold tracking-tight`.
- **H3 (Tarjetas / Modales)**: `text-xl sm:text-2xl font-semibold`.
- **Cuerpo de Párrafo**: `text-base leading-relaxed text-slate-400 dark:text-slate-400`.
- **Badges / Tags**: `text-xs font-semibold uppercase tracking-wider px-3 py-1 rounded-full`.

---

## 4. Adaptabilidad y Diseño Responsive (Mobile-First)
- **Breakpoints**:
  - `Móvil (<640px)`: 1 columna, padding reducido (`px-4`), menú hamburguesa visible.
  - `Tablet (640px - 1023px)`: 2 columnas en catálogo, navegación compacta.
  - `Escritorio (>=1024px)`: 3 columnas en catálogo, menú horizontal completo, hero en doble bloque (texto + robot mascota).
- **Zonas Táctiles**: Todo botón debe tener una altura mínima de `44px` (`py-2.5 px-4`) para pulsación cómoda con el dedo.
- **Scroll Seguro**: Contenedor principal protegido con `overflow-x-hidden` para evitar cualquier desplazamiento horizontal espurio.

---

## 5. Microinteracciones y Efectos Hover
- **Tarjetas**: Elevación sutil al pasar el cursor: `transition-all duration-300 hover:-translate-y-1.5 hover:shadow-xl hover:shadow-cyan-500/10`.
- **Imágenes**: Ligero zoom fluido al entrar a la tarjeta: `transition-transform duration-500 group-hover:scale-105`.
- **Botones**: Transición de gradiente y brillo sin saturar visualmente: `transition-all duration-200 hover:brightness-110 active:scale-95`.
- **Accesibilidad Motriz**: Soporte para `motion-reduce:transition-none` para usuarios con sensibilidad al movimiento.
