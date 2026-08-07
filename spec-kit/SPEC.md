# SPEC — Portafolio Marco Camacho

> El **QUÉ** y el **POR QUÉ** del proyecto. Historias de usuario con criterios
> de aceptación. No contiene decisiones técnicas (eso vive en `PLAN.md`).

## Visión

Portafolio profesional de una sola página, en español e inglés, que posiciona a
Marco Camacho como desarrollador Fullstack y muestra sus proyectos reales,
experiencia y servicios. Debe transmitir confianza y calidad técnica y permitir
contacto directo.

## Personas

- **Reclutador / Cliente potencial**: evalúa el portafolio, revisa proyectos y
  contacta.
- **Marco (propietario)**: mantiene y actualiza contenido (experiencia y
  proyectos) sin escribir código complejo.

## Historias de usuario

### US-01 — Encabezado (Hero)
**Como** visitante, **quiero** ver de inmediato quién es Marco y qué hace,
**para** decidir si sigue explorando.

Criterios de aceptación:
- [ ] Muestra nombre, rol con efecto typewriter y foto real.
- [ ] Botones "Contáctame" y "Ver Proyectos" navegan a las secciones
      `#contacto` y `#proyectos`.
- [ ] Redes sociales (GitHub, Instagram, LinkedIn) abren en pestaña nueva.

### US-02 — Habilidades
**Como** visitante, **quiero** ver el stack técnico organizado por áreas
(frontend, backend, base de datos), **para** evaluar la cobertura técnica.

Criterios de aceptación:
- [ ] Tres tarjetas: Frontend, Backend, Database & Tools.
- [ ] Barras de progreso animadas al hacer scroll (`data-width`).
- [ ] Los niveles reflejan competencia real de Marco.

### US-03 — Experiencia
**Como** visitante, **quiero** ver la trayectoria profesional en una línea de
tiempo, **para** entender el contexto y la evolución de Marco.

Criterios de aceptación:
- [ ] La entrada más reciente (freelance) dice **"Nov 2025 - Actualidad"**.
- [ ] La descripción del rol actual menciona la mejora de un **software de
      gestión integral para ISP** (módulos de ventas, inventario y facturación).
- [ ] Las fechas y títulos están traducidos ES/EN.

### US-04 — Proyectos destacados
**Como** visitante, **quiero** ver proyectos con captura real, título,
tecnologías, descripción y enlaces de demo/código, **para** validar experiencia
práctica.

Criterios de aceptación:
- [ ] Cada tarjeta usa una imagen real de `/img`.
- [ ] Los enlaces "Ver Demo" y "Código" abren en pestaña nueva y funcionan.
- [ ] Se **eliminan** los proyectos *Calculadora de IMC* y *Conversor de
      Divisas* (obsoletos/duplicados).
- [ ] Se **agrega** el proyecto *Sistema de Ventas y Gestión de Inventario*
      (captura `img/sassposs.png`), relacionado con el software ISP.
- [ ] Título, tecnologías y descripción traducidos ES/EN.

### US-05 — Servicios
**Como** cliente potencial, **quiero** conocer los servicios ofrecidos,
**para** entender cómo Marco puede ayudarme.

Criterios de aceptación:
- [ ] Tres servicios: Frontend, Backend y Aplicaciones completas.
- [ ] Textos traducidos ES/EN.

### US-06 — Contacto
**Como** cliente potencial, **quiero** enviar un mensaje y ver datos de
contacto, **para** iniciar una conversación.

Criterios de aceptación:
- [ ] Formulario con nombre, email, asunto y mensaje (validación requerida).
- [ ] Envío simulado con feedback visual ("Enviando..." → "¡Enviado!").
- [ ] Tarjetas con email, ubicación y disponibilidad.

### US-07 — Internacionalización
**Como** visitante de habla no hispana, **quiero** cambiar el idioma a inglés
y viceversa, **para** leer el contenido en mi idioma.

Criterios de aceptación:
- [ ] Botones ES/EN en la barra de navegación.
- [ ] Todo texto con `data-key` se traduce en ambos idiomas.
- [ ] Al alternar, ningún texto queda sin traducir (todas las claves existen en
      `es` y `en`).

## Criterios globales de aceptación

- [ ] Responsive en móvil, tablet y escritorio (grid de Bootstrap).
- [ ] Animaciones de aparición (`fade-in`) y barras de progreso funcionan.
- [ ] Sin enlaces rotos ni imágenes huérfanas en `/img`.
- [ ] El formulario de contacto envía correos reales vía EmailJS y muestra
      feedback visual.
