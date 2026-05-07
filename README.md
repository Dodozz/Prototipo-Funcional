<br/>

<div align="center">

# tech<span style="color: #C8412B;">/</span>white

**Prototipo Funcional · Boceto Pre-Producción v0.1**

_e-commerce de hardware gaming — estética paper/ink_

<br/>

[![Stage](https://img.shields.io/badge/STAGE-Wireframe%20%7C%20Lo--Fi-1C1B19?style=flat-square&labelColor=E2DAC4&color=1C1B19)](.)
[![Version](https://img.shields.io/badge/V-0.1-C8412B?style=flat-square&labelColor=1C1B19&color=C8412B)](.)
[![File](https://img.shields.io/badge/FILE-tech--white.fig-1C1B19?style=flat-square&labelColor=EDE6D5&color=1C1B19)](.)
[![Author](https://img.shields.io/badge/BY-DODOZ-1C1B19?style=flat-square&labelColor=E2DAC4&color=1C1B19)](.)
[![Zero Deps](https://img.shields.io/badge/DEPENDENCIES-0-4F6B3C?style=flat-square&labelColor=E2DAC4&color=4F6B3C)](.)

<br/>

</div>

---

## Qué es esto

**TECH/WHITE** es un prototipo funcional de tienda en línea de hardware gaming, construido como un archivo HTML único que simula la experiencia completa de un e-commerce real — navegación SPA, carrito persistente, checkout por pasos y un *Setup Builder* interactivo.

La interfaz usa una **estética paper/ink wireframe**: fondo pergamino, tipografía manuscrita para anotaciones, stamps, sticky notes y líneas punteadas. Es un boceto vivo, diseñado para documentar decisiones UX antes del desarrollo en producción.

> _No es un template. No es un mockup estático. Es un prototipo que funciona._

---

## Stack

| Capa | Tecnología |
|------|-----------|
| Markup | HTML5 semántico |
| Estilos | CSS puro — Custom Properties (design tokens) |
| Lógica | Vanilla JS — sin frameworks, sin bundler |
| Persistencia | `localStorage` para carrito y sesiones |
| Dependencias | **0** — cero `npm install`, cero `node_modules` |

---

## Vistas

La app funciona como un **SPA sin router** — cada sección se muestra/oculta con `display: none/block`:

| Vista | Sección | Descripción |
|-------|---------|-------------|
| **Home** | Hero, categorías, productos destacados, ofertas, testimonios | Landing con CTA y anotaciones de diseño |
| **Catálogo** | Sidebar de filtros + grid 3 columnas | Exploración con filtros por categoría, marca, precio y stock |
| **Detalle** | Galería, specs, atributos, breadcrumbs | Ficha de producto con cantidad y agregar al carrito |
| **Carrito** | Lista de items + resumen sticky | Gestión del carrito con cantidades, eliminación y cupones |
| **Checkout** | Stepper de 3 pasos (dirección → envío → pago) | Flujo de compra con opciones de envío |
| **Cuenta** | Login / registro con tabs | Auth simulado que persiste en localStorage |
| **Setup Builder** | Presupuesto + caso de uso → build recomendada | Feature diferenciador: recomienda 4 piezas compatibles |

---

## Funcionalidades clave

### Carrito persistente
- Los items se guardan en `localStorage` y sobreviven recarga de página.
- Badge en el ícono del carrito se actualiza en tiempo real.
- Toast confirma cada acción.

### Setup Builder
- Slider de presupuesto ($5K — $50K MXN).
- Selección de caso de uso: Gaming / Streaming / Creador / Trabajo.
- Botón "Agregar todo" mete las 4 piezas recomendadas al carrito.

### Anotaciones de diseño
- Sticky notes, callouts y flechas manuscritas documentan decisiones UX.
- Toggle "Notas" (esquina superior derecha) las muestra/oculta.
- Leyenda en la esquina inferior izquierda explica la simbología.

### Navegación SPA
- Sin reload. Sin frameworks. Todo en un solo archivo.
- Las anotaciones se ocultan en responsive (< 1024px).

---

## Design Tokens

El sistema visual está definido en `:root` como CSS Custom Properties:

```
--paper:        #F4EFE3   ← fondo principal (papel pergamino)
--paper-dim:    #EDE6D5   ← fondos secundarios
--paper-deep:   #E2DAC4   ← fondos profundos / sombras
--ink:          #1C1B19   ← texto principal
--ink-soft:     #5A5751   ← texto secundario
--ink-faint:    #8A857B   ← texto terciario
--line:         #C7C0B0   ← líneas finas
--line-strong:  #A39B86   ← líneas gruesas
--pen-red:      #C8412B   ← acentos, badges, CTA
--pen-blue:     #2B4C7E   ← callouts técnicos
--pen-green:    #4F6B3C   ← estados positivos
--highlight:    #F5E89A   ← resaltado tipo marcador
```

### Tipografías

| Token | Fuente | Uso |
|-------|--------|-----|
| `--serif` | Fraunces | Títulos, precios, jerarquía display |
| `--mono` | JetBrains Mono | Body, labels, metadata, datos |
| `--hand` | Caveat | Anotaciones, sticky notes, sellos |
| `--hand-tight` | Kalam | Callout técnico |

---

## Cómo usar

1. Clona o descarga el repositorio:
   ```bash
   git clone <url-del-repo>
   ```
2. Abre `index.html` en cualquier navegador moderno. No necesitas servidor local, bundler ni nada:
   ```bash
   # Simplemente abre el archivo
   start index.html
   ```
3. Navega entre las vistas usando la barra de navegación.
4. Agrega productos al carrito, explora el Setup Builder, revisa el checkout.

---

## Estructura del archivo

Todo vive dentro de un único `index.html`:

```
index.html
├── <style>        → ~1800 líneas de CSS (tokens, layout, componentes, responsive)
├── <body>
│   ├── #status-bar           → Barra superior con metadata del prototipo
│   ├── .toggle-notes         → Botón para mostrar/ocultar anotaciones
│   ├── .legend               → Leyenda de simbología del boceto
│   ├── .app
│   │   ├── #navbar           → Navegación con brand, links y acciones
│   │   ├── #view-home        → Hero + categorías + productos + ofertas + testimonios
│   │   ├── #view-catalogo    → Catálogo con sidebar de filtros
│   │   ├── #view-product     → Detalle de producto
│   │   ├── #view-cart        → Carrito con resumen
│   │   ├── #view-checkout    → Checkout con stepper
│   │   ├── #view-cuenta      → Login / registro
│   │   ├── #view-builder     → Setup Builder
│   │   └── <footer>          → Footer con links
│   ├── #toast                → Notificaciones
│   └── <script>              → Datos, estado, render, navegación, carrito, utilidades
```

---

## Datos de producto

El array `PRODUCTS` contiene 12 artículos en 3 categorías:

| Categoría | Productos |
|-----------|-----------|
| Hardware | RTX 4060 Ti, Ryzen 7 7800X3D, Corsair DDR5 32GB, Samsung 980 Pro 2TB, NZXT H7 Flow |
| Monitores | Samsung Odyssey G5, LG UltraGear 32", ASUS ROG Swift 240Hz |
| Periféricos | Logitech G Pro X Superlight 2, Razer BlackWidow V4 Pro, HyperX Cloud III, Logitech G502 X Plus |

---

## Responsive

| Breakpoint | Comportamiento |
|------------|----------------|
| > 1024px | Layout completo con grid multi-columna y anotaciones |
| 641–1024px | Grids a 2 columnas, sidebar oculto, anotaciones deshabilitadas |
| ≤ 640px | Layout single-column, navegación minimalista |

---

## Créditos

- **Autor**: DODOZ
- **Ubicación**: CDMX, México
- **Fecha**: 05·05·26
- **Tipografías**: [Fraunces](https://github.com/undercasetype/Fraunces) · [JetBrains Mono](https://www.jetbrains.com/labs/mono/) · [Caveat](https://fonts.google.com/specimen/Caveat) · [Kalam](https://fonts.google.com/specimen/Kalam)

---

<div align="center">

**© 2026 TECH/WHITE · Prototipo** — Hecho con ♡ en CDMX

</div>