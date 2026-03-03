# Proyecto SONORA Studio - Componentes Astro

Este proyecto ha sido transformado de un HTML estático a una aplicación Astro componetizada.

## Estructura de Componentes

### 📁 Layouts

#### `MainLayout.astro`
**Props:**
- `title?: string` - Título de la página (default: "SONORA Studio | Alquiler por Horas")

**Descripción:** Layout principal que incluye todos los estilos globales, fuentes y estructura HTML base.

---

### 📁 Components

#### `Navigation.astro`
**Props:** Ninguno (estático)

**Descripción:** Barra de navegación fija con logo, menú desktop y botón para menú móvil.

---

#### `MobileMenu.astro`
**Props:** Ninguno (estático)

**Descripción:** Menú móvil overlay con navegación y botón de reserva.

---

#### `HeroSection.astro`
**Props:** Ninguno (estático)

**Descripción:** Sección hero principal con título, descripción, botones CTA y estadísticas del estudio.

---

#### `ServiceCard.astro`
**Props:**
- `title: string` - Título del servicio
- `description: string` - Descripción del servicio
- `price: string` - Precio (ej: "$30")
- `priceDetail: string` - Detalle del precio (ej: "por hora")
- `features: string[]` - Array de características/beneficios
- `icon: string` - Emoji o icono
- `recommended?: boolean` - Marca el servicio como recomendado (default: false)
- `delay?: string` - Clase de delay para animación (ej: "reveal-delay-1")

**Descripción:** Tarjeta de servicio individual con características y precio.

---

#### `ServicesSection.astro`
**Props:** Ninguno (usa ServiceCard internamente)

**Descripción:** Sección de servicios que muestra las dos modalidades de alquiler.

---

#### `ProducerSection.astro`
**Props:** Ninguno (estático)

**Descripción:** Sección sobre el productor residente con información, credenciales y especialidades.

---

#### `TestimonialCard.astro`
**Props:**
- `rating: number` - Calificación en estrellas (1-5)
- `text: string` - Texto del testimonio
- `author: string` - Nombre del autor
- `role: string` - Rol o descripción del autor
- `delay?: string` - Clase de delay para animación

**Descripción:** Tarjeta de testimonio individual con estrellas y autor.

---

#### `TestimonialsSection.astro`
**Props:** Ninguno (usa TestimonialCard internamente)

**Descripción:** Sección de testimonios que muestra 3 opiniones de clientes.

---

#### `GalleryItem.astro`
**Props:**
- `title: string` - Título de la imagen
- `icon: string` - Emoji representativo
- `gridClass?: string` - Clases de grid para tamaño (default: "aspect-square")
- `delay?: string` - Clase de delay para animación

**Descripción:** Item individual de galería con placeholder y título.

---

#### `GallerySection.astro`
**Props:** Ninguno (usa GalleryItem internamente)

**Descripción:** Sección de galería con imágenes del estudio y lista de equipamiento.

---

#### `ContactSection.astro`
**Props:** Ninguno (estático)

**Descripción:** Sección de contacto con información de contacto y formulario.

---

#### `Footer.astro`
**Props:** Ninguno (estático)

**Descripción:** Footer con logo, navegación y copyright.

---

#### `Lightbox.astro`
**Props:** Ninguno (estático)

**Descripción:** Lightbox modal para visualizar imágenes de la galería.

---

#### `SectionDivider.astro`
**Props:** Ninguno (estático)

**Descripción:** Línea divisora decorativa entre secciones.

---

## Archivo Principal

### `src/pages/index.astro`

Importa y organiza todos los componentes en el orden correcto. Incluye scripts para:
- Toggle de menú móvil
- Scroll reveal animations
- Lightbox gallery
- Form handling
- Navbar scroll effect
- Smooth scroll

---

## Características Implementadas

✅ **Componentización completa** - Todo el HTML ha sido dividido en componentes reutilizables  
✅ **Props tipados** - Uso de TypeScript para props con interfaces  
✅ **Estilos globales** - Todos los estilos CSS en MainLayout  
✅ **Interactividad preservada** - Scripts para menú móvil, galería, formulario  
✅ **Animaciones** - Scroll reveal, transitions, floating elements  
✅ **Responsive** - Diseño adaptable a mobile y desktop  
✅ **Accesibilidad** - ARIA labels, reduced motion support  

---

## Uso de Componentes con Props

### Ejemplo: ServiceCard

```astro
<ServiceCard
  title="Con Productor"
  description="Servicio completo con productor profesional"
  price="$50"
  priceDetail="por hora"
  icon="🎵"
  recommended={true}
  delay="reveal-delay-1"
  features={[
    'Acceso completo al estudio',
    'Productor profesional dedicado',
    'Mezcla y masterización'
  ]}
/>
```

### Ejemplo: TestimonialCard

```astro
<TestimonialCard
  rating={5}
  text="Increíble experiencia en el estudio"
  author="Laura Méndez"
  role="Cantautora"
  delay="reveal-delay-1"
/>
```

### Ejemplo: GalleryItem

```astro
<GalleryItem 
  title="Sala de Control" 
  icon="🎛️"
  gridClass="aspect-square md:col-span-2"
  delay="reveal-delay-1"
/>
```

---

## Instalación y Ejecución

```bash
# Instalar dependencias
npm install

# Ejecutar en desarrollo
npm run dev

# Build para producción
npm run build

# Preview de producción
npm run preview
```

---

## Notas Importantes

- No se agregó nada que no estuviera en el HTML original
- Los placeholders de imágenes se mantienen como en el original (emojis)
- La funcionalidad JavaScript se preservó completamente
- Tailwind CSS se carga desde CDN como en el original
- Todos los estilos se mantienen en el Layout para evitar duplicación
