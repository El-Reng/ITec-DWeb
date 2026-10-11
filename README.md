# Seminario Antigravity — ITecnoFuturo 🪐

> **Materia**: Diseño y Desarrollo Web — Sede Campus ITec Río Cuarto  
> **Seminario**: Desarrollo Agéntico con Google Antigravity 2.0  
> **Metodología**: Spec-Driven Development (Gentle-AI) & Antigravity Operating System (AGY-OS)  
> **Referencia Oficial**: [Guía del Estudiante — Seminario Antigravity](https://msambrenil.github.io/Seminario-Antigravity/)

---

## 🎯 Contexto y Objetivo del Seminario

El **Seminario de Google Antigravity 2.0** introduce un cambio de paradigma en la construcción web: transicionar del desarrollo manual tradicional hacia el rol de **Director Técnico y Arquitecto de Software Agéntico**. 

A través de un flujo estructurado de 7 clases y el estándar **Spec-Driven Development (SDD)** inspirado en [Gentle-AI](https://github.com/Gentleman-Programming/gentle-ai), se concibió, especificó y maquetó una **Single Page Application (SPA)** autocontenida para un evento tecnológico ficticio denominado **ITecnoFuturo**.

---

## 🚀 Proyecto: ITecnoFuturo 2026

**ITecnoFuturo** es la web promocional para una gran exposición de innovación tecnológica a realizarse en la Sede Campus del Instituto Tecnológico ITec de Río Cuarto. 

### Características Principales:
1. **SPA Autocontenida (Archivo Único)**:
   - Todo el sitio reside en `index.html`, sin necesidad de transpiladores, dependencias de Node.js ni servidores externos.
   - 3 secciones principales con navegación instantánea sin recarga: **Inicio**, **Catálogo de Proyectos** e **Inscripción y Agenda**.
2. **Catálogo & Fichas Modales Accesibles**:
   - 6 proyectos canónicos de innovación: *DomoticHome IA*, *Atlas Assist*, *MecaHand*, *VisionGuard AI*, *AutoFactory Lab* y *NeuraCore*.
   - Coherencia textual estricta: el texto visible de la tarjeta es el comienzo exacto de la ficha técnica extendida.
   - Modal interactivo con bloqueo de scroll y cierre por botón `X`, botón *Cerrar*, clic en backdrop o tecla `Escape`.
3. **Asistente Mascota T-Bot Persistente (Overlay Fixed)**:
   - Widget flotante fijo en pantalla (`position: fixed`) estilo EVA (minimalista y blanco) sobre base contrastante.
   - Microinteracciones: animación de flotación constante (`floatY`), reacciones al clic (`botTalk` / `botWave`) y burbuja de tips tecnológicos rotativos.
4. **Paleta Dual con Identidad Institucional**:
   - **Modo Oscuro**: Fondo profundo `#080B14`, tarjetas `#111827`, texto `#F1F5F9` y acentos futuristas en índigo y cian.
   - **Modo Claro**: Fondo cálido `#FFF8F7` con botones y acentos unificados en **rojo institucional ITec** (`#C0392B` / `#E74C3C`).
   - Detección temprana anti-FOUC y persistencia del tema en `localStorage`.
5. **Formulario con Estados UI & Credencial Digital**:
   - Validación reactiva de campos obligatorios.
   - Estado Success que genera un **Pase Digital Oficial** con ID ficticio único y código QR vectorial.

---

## 📂 Estructura de Entregables del Repositorio

Siguiendo las pautas de entrega del seminario, esta rama reúne todos los artefactos requeridos:

```text
├── index.html                   # SPA completa y funcional (HTML5 + Tailwind CSS v3 CDN + Vanilla JS)
├── REPORTE_VERIFICACION_SDD.md  # Reporte formal de verificación técnica y cumplimiento de la Definition of Done
├── GEMINI.md                    # Conector maestro de contexto del agente Antigravity
├── docs/
│   └── contexto/                # Suite de Contexto Vivo (Master Context - Estándar SDD)
│       ├── arquitectura.md      # Arquitectura modular, stack aprobado y modelo de datos canónico
│       ├── convenciones.md      # Guía de estilos, tokens de color (claro/oscuro) y accesibilidad
│       ├── decisiones.md        # Registro de decisiones de arquitectura (ADR-001 al ADR-006)
│       ├── glosario.md          # Diccionario de términos de negocio y componentes UI
│       ├── flujo-de-trabajo.md  # Fases de desarrollo SDD y los 12 criterios de la Definition of Done
│       ├── errores-conocidos.md # Catálogo de prevención de gotchas y desbordes de maquetado
│       └── memoria.md           # Memoria continua Engram (historial persistente de sesiones)
└── video-demo.mp4               # Demostración en video (2-3 min) del funcionamiento y modos claro/oscuro
```

---

## 🛠️ Stack Tecnológico Utilizado

- **HTML5 Semántico**: `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`.
- **Tailwind CSS v3 (CDN)**: Configuración inyectada con paleta personalizada y `darkMode: 'class'`.
- **JavaScript Vanilla (ES6+)**: Gestión reactiva del DOM, filtros, agenda interactiva y modales sin librerías externas.
- **Tipografía**: *Inter* (Google Fonts).

---

## 🎖️ Metodología y Calidad (DoD)

El desarrollo cumplió rigurosamente con los 12 criterios de la **Definition of Done (DoD)** y la verificación de los 4 estados de interfaz (**Loading**, **Empty**, **Error** y **Success**), garantizando cero errores de sintaxis en consola y una experiencia de usuario sólida y accesible.
