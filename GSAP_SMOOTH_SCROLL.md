# GSAP ScrollTrigger - Documentación de Cambios

## Resumen

Se implementó **scroll con transiciones de secciones** usando GSAP ScrollTrigger. Las secciones tienen animaciones de entrada/salida controladas por el scroll.

## Paquetes Instalados

- **gsap** (^3.12.0) - Core library con ScrollTrigger

## Archivos Modificados

### 1. `src/components/Navbar.astro`

- **Limpiado**: Se eliminó todo el código de scroll GSAP que se había agregado incorrectamente
- **Simplificado**: Solo contiene la lógica del menú móvil y el cambio de fondo del navbar
- Los enlaces del navbar now son enlaces normales (`href="#id"`)

### 2. `src/layouts/Layout.astro`

**Agregado:**

- Importación de GSAP y ScrollTrigger
- Estilos CSS para `.section-wrapper` y `.section-content`
- Script con animaciones de transición de secciones:
  - **onEnter**: La sección entra con fade + slide up (opacity 0→1, y: 80→0)
  - **onLeave**: La sección sale con fade + slide up (opacity 1→0, y: 0→-80)
  - **onEnterBack**: La sección entra desde arriba con fade + slide
  - **onLeaveBack**: La sección sale hacia abajo
- Actualización del nav activo según la sección visible
- Respeto de `prefers-reduced-motion`

### 3. `src/components/Hero.astro`

- Agregado `id="inicio"` a la sección Hero

### 4. `package.json`

- Agregada dependencia `gsap`

## Comportamiento

| Acción | Animación |
|--------|-----------|
| Scroll hacia abajo | Sección actual sale (fade + slide up), siguiente entra |
| Scroll hacia arriba | Sección actual sale hacia abajo, anterior entra |
| Nav links | Se actualiza automáticamente según sección visible |

## Configuración

| Parámetro | Valor |
|-----------|-------|
| Trigger start | `top center` |
| Trigger end | `bottom center` |
| Duración entrada | 0.8s |
| Duración salida | 0.6s |
| Easing | `power3.out` / `power3.in` |
| Reduced motion | Deshabilitado (salto instantáneo) |

## Notas

- **No es scroll capturado**: El usuario puede hacer scroll normal
- **Las secciones animan**: Cuando una sección entra al viewport, entra con animación; cuando sale, sale con animación
- El navbar se actualiza para mostrar la sección activa
- Funciona con scroll tradicional (rueda del ratón)
