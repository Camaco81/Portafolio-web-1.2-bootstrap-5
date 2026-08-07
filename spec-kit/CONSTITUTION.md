# CONSTITUCIÓN — Portafolio Marco Camacho

> Reglas de Oro inmutables del proyecto. Nada de lo escrito aquí se cambia sin
> una revisión explícita y una actualización coordinada de `SPEC.md` y `PLAN.md`.

## 1. Propósito

Sitio web de portafolio profesional de **Marco Camacho**, desarrollador
Fullstack. Muestra habilidades, experiencia, proyectos destacados, servicios y
un formulario de contacto. Es una SPA estática desplegada en GitHub Pages.

## 2. Stack (inalterable)

| Capa       | Tecnología                                                        |
| ---------- | ----------------------------------------------------------------- |
| Lenguajes  | HTML5, CSS3, JavaScript ES6+ (vanilla, sin build tools)           |
| Framework  | Bootstrap 5.3.3 (CDN) + CSS custom en `css/styles.css`            |
| Iconos     | Bootstrap Icons 1.11.3 (CDN)                                      |
| Tipografías| Google Fonts: Poppins + Roboto Mono                               |
| Backend    | Ninguno — formulario mediante EmailJS 4.x (CDN)                   |
| Despliegue | GitHub Pages (estático, rutas relativas)                          |

### Prohibiciones del stack
- No introducir bundlers, transpiladores ni frameworks de UI nuevos
  (React, Svelte, etc.) sin justificación aprobada en `PLAN.md`.
- No subir claves/secretos públicos de EmailJS al repositorio público.
  La inicialización con la clave pública ya existente se mantiene solo si
  se rota y maneja fuera del HTML en el futuro.

## 3. Reglas de Negocio

1. **Bilingüe ES/EN**: todo texto visible debe tener `data-key` y su traducción
   en `js/translation.js`. El idioma por defecto es español.
2. **Secciones ancla**: `#skills`, `#experiencia`, `#proyectos`, `#servicios`,
   `#contacto` (ids en español, visibles al usuario final como menú).
3. **Propietario del contenido**: la información personal, red social y enlaces
   pertenecen a Marco Camacho; no se inventan proyectos, fechas ni logros.
4. **Proyectos**: cada tarjeta en `#proyectos` debe tener imagen real en
   `/img`, título y descripción traducidos, y enlaces (demo/código) verificados.
   Se elimina un proyecto si su demo ya no está disponible o está obsoleto.
5. **Responsive**: mobile-first, layout con grid de Bootstrap, navegación fija.
6. **Accesibilidad/UX**: botones de idioma siempre visibles; el cambio de idioma
   no pierde el estado del formulario ni rompe el texto.

## 4. Reglas de Código

1. **Sin comentarios** en el código salvo que el usuario los solicite.
2. **Convención de nombres**: clases e ids en inglés; el contenido textual en
   español por defecto. Los `data-key` son claves alfanuméricas separadas por
   guion (`freelance-description`, `sales-system-title`).
3. **Imágenes**: en `/img` con nombres descriptivos (`img/*.png`). No duplicar;
   al eliminar un proyecto se eliminan sus imágenes huérfanas.
4. **Traducciones**: agregar SIEMPRE la clave en ambos idiomas (`es` y `en`);
   nunca dejar una clave solo en un idioma.
5. **JS**: todo se inicializa tras `DOMContentLoaded` (ver `js/animacion.js`).
   El efecto typewriter y el switch de idioma viven en `js/translation.js`;
   las animaciones y el formulario (EmailJS) en `js/animacion.js`.

## 5. Reglas de Spec-Kit (SDD)

1. `CONSTITUTION.md` = reglas inmutables (este archivo).
2. `SPEC.md` = el **QUÉ** y el **POR QUÉ**: historias de usuario con criterios
   de aceptación. No contiene decisiones de implementación.
3. `PLAN.md` = el **CÓMO**: arquitectura, estructura de archivos y tareas
   indexadas (`T-XX`) trazables a historias (`US-XX`).
4. Todo cambio de código debe trazarse a una historia de usuario; si no existe,
   primero se agrega a `SPEC.md` y se planifica en `PLAN.md`.

## 6. Proceso de cambio

1. Nueva necesidad → redactar historia de usuario en `SPEC.md`.
2. Aprobar criterios de aceptación → planificar tareas en `PLAN.md`.
3. Implementar tarea por tarea, actualizando su estado (✅ / 🔄 / ⬜).
4. Verificar en navegador ES + EN y en móvil antes de cerrar la tarea.
