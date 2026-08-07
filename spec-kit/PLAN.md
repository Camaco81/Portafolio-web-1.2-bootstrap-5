# PLAN — Portafolio Marco Camacho

> El **CÓMO** técnico. Estructura, decisiones y tareas indexadas (`T-XX`)
> trazables a historias de usuario (`US-XX`) de `SPEC.md`.

## Arquitectura

SPA estática de una sola página. Sin servidor, sin build tools.

```
PortafolioBootstrap-5-1.2/
├── index.html          ← Página única (todo el contenido + CDNs)
├── css/styles.css      ← Estilos custom (tema oscuro, glass-card, animaciones)
├── js/
│   ├── translation.js  ← Diccionario ES/EN + switch de idioma + typewriter
│   └── animacion.js    ← Animaciones scroll, barras de progreso, formulario (EmailJS)
├── img/                ← Capturas de proyectos, iconos, logo y foto
├── spec-kit/           ← Metodología SDD (CONSTITUTION, SPEC, PLAN)
└── README.md
```

## Decisiones técnicas vigentes

- **CDN Bootstrap 5.3.3** + **Bootstrap Icons** + **Google Fonts** cargados en
  `index.html` (sin empaquetador).
- **i18n**: atributo `data-key` en cada elemento traducible; `switchLanguage()`
  en `translation.js` reemplaza `textContent` (o placeholder/value según tipo).
  Cada clave debe existir en `es` y `en`.
- **Formulario**: `js/animacion.js` maneja el submit con EmailJS real
  (`emailjs.sendForm('default_service', 'template_qfa4c2d', this)`) y feedback
  visual bilingüe. La inicialización `emailjs.init()` vive en `index.html`.

## Tareas (estado del backlog)

| ID   | Historia | Descripción                                          | Estado |
| ---- | -------- | ---------------------------------------------------- | ------ |
| T-01 | US-01    | Hero: nombre, typewriter, foto, CTAs, redes sociales | ✅     |
| T-02 | US-02    | Sección habilidades con barras de progreso animadas  | ✅     |
| T-03 | US-03    | Línea de tiempo de experiencia                       | ✅     |
| T-04 | US-04    | Grid de proyectos con tarjetas y overlays            | ✅     |
| T-05 | US-05    | Sección de servicios                                 | ✅     |
| T-06 | US-06    | Formulario de contacto + tarjetas de contacto        | ✅     |
| T-07 | US-07    | Sistema de traducción ES/EN con `data-key`           | ✅     |

### Cambios v2.0 (noviembre 2025 → actualidad)

| ID   | Historia | Descripción                                             | Estado |
| ---- | -------- | ------------------------------------------------------- | ------ |
| T-08 | US-03    | Actualizar fecha freelance a "Nov 2025 - Actualidad" y   | ✅     |
|      |          | descripción con software de gestión integral para ISP    |        |
| T-09 | US-04    | Eliminar proyectos: Calculadora de IMC y Conversor de    | ✅     |
|      |          | Divisas (HTML + traducciones + imágenes huérfanas)       |        |
| T-10 | US-04    | Agregar proyecto "Sistema de Ventas y Gestión de         | ✅     |
|      |          | Inventario" con `img/sassposs.png` y traducciones ES/EN  |        |
| T-11 | US-03/04 | Documentar metodología SDD en `spec-kit/`                | ✅     |
| T-12 | —        | Eliminar `js/main.js` (código muerto)                  | ✅     |
| T-13 | US-06    | Conectar formulario a EmailJS real (`sendForm` con        | ✅     |
|      |          | `default_service` + `template_qfa4c2d`). Depende de que el |        |
|      |          | template en el dashboard envíe a marco.camacho.dev@gmail.  |        |
|      |          | com y use {{name}}, {{email}}, {{subject}}, {{message}}    |        |
| T-14 | US-01    | Rotar/ocultar la clave pública de EmailJS del HTML        | ⬜     |
| T-15 | US-02    | Reemplazar emojis de habilidades por Bootstrap Icons      | ✅     |
|      |          | (Vue→lightning, Python→filetype-py, PHP→filetype-php,    |        |
|      |          | MongoDB→database-fill, Firebase→fire, Bootstrap→fill)    |        |
| T-16 | US-02    | Añadir tarjeta "IA & Herramientas": Gemini, DeepSeek,     | ✅     |
|      |          | IDEs con IA integrada, Prompt Engineering & cursos        |        |
| T-17 | US-07    | Mejorar i18n: placeholders del formulario, enlaces "Ver    | ✅     |
|      |          | Demo/Código", títulos de tarjetas, `<html lang>`,         |        |
|      |          | persistencia del idioma en localStorage, fix botón envío  |        |
| T-18 | US-01    | SEO: meta description, author y Open Graph                | ✅     |
| T-19 | —        | Eliminar imágenes huérfanas `img2/3/4.png` y comprimir     | ⬜     |
|      |          | `gym-track.png` (~1 MB)                                   |        |
| T-20 | US-06    | Accesibilidad: autocomplete, aria-labels y contraste del  | ⬜     |
|      |          | formulario                                                |        |

## Definición de Hecho (DoD)

1. Cambios visibles en `index.html` con su `data-key` correspondiente.
2. Claves agregadas en **ambos** idiomas en `translation.js`.
3. Verificado en navegador: ES y EN, escritorio y móvil.
4. Sin imágenes huérfanas en `/img` ni enlaces rotos.
5. Tareas marcadas y trazadas a su historia de usuario.
