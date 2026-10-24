# STAGE · Sistema de Venta de Boletos

Segunda entrega del proyecto: maquetación con **HTML5 semántico y CSS3 puro** (Flexbox, Grid y diseño responsive) de dos pantallas del flujo diseñado en Figma en la Primera entrega.

## Integrantes

| Integrante | Usuario de GitHub | Carnet |
| --- | --- | --- |
| Ricardo Pocasangre | [RicardoPocasangre](https://github.com/RicardoPocasangre) | 00032226 |
| Camila Alfaro | [Camilaalfaro26](https://github.com/Camilaalfaro26) | 00032426 |

## Diseño de referencia

Prototipo de la Primera entrega en Figma: [Primera Entrega - Sistema de Venta de Boletos](https://www.figma.com/design/RdALBt2AcF812BOZjiEqiA/Primera-Entrega---Sistema-de-Venta-de-Boletos?node-id=0-1&t=5GVYhDX6FPgEWPx7-1)

## Pantallas maquetadas

| Archivo | Pantalla en Figma | Descripción |
| --- | --- | --- |
| `index.html` | W05 · Listado y búsqueda de eventos (T01 y M02 para tablet y móvil) | Hero con buscador, filtros por categoría y cuadrícula de eventos. |
| `pages/detalle-evento.html` | W06 · Detalle del evento (T02 y M03 para tablet y móvil) | Información del evento, zonas y precios, y tarjeta de compra. |

Las dos pantallas se enlazan entre sí con rutas relativas: cada tarjeta del listado lleva al detalle, y el logo o el enlace «Eventos» regresan al listado.

## Estructura del proyecto

```
.
├── index.html                  # Listado y búsqueda de eventos
├── pages/
│   └── detalle-evento.html     # Detalle del evento
├── css/
│   └── style.css               # Hoja de estilos externa (única)
├── img/                        # Logo, favicon e íconos PNG
└── README.md
```

## Cómo visualizarlo

No requiere instalación ni compilación. Clona el repositorio y abre `index.html` en el navegador:

```bash
git clone https://github.com/RicardoPocasangre/STAGE.git
cd STAGE
# abrir index.html con doble clic o con la extensión Live Server
```

La tipografía *Plus Jakarta Sans* se carga desde Google Fonts; sin conexión se usa la fuente del sistema.

## Decisiones de maquetación

- **HTML semántico**: `header`, `nav`, `main`, `section`, `article`, `aside` y `footer`, con jerarquía de encabezados `h1 → h2 → h3` y `alt` descriptivo en todas las imágenes.
- **CSS Grid** para la estructura de página (columnas con líneas con nombre y `subgrid` para el hero a todo el ancho), la cuadrícula de tarjetas, el detalle en dos columnas y las filas de zonas.
- **CSS Flexbox** para el header, la navegación, los chips, las filas de datos, el footer y las barras de compra.
- **Una sola hoja de estilos** con variables en `:root` tomadas del sistema de diseño de Figma, clases reutilizables y unidades relativas (`rem`, `fr`, `%`, `clamp()`).
- **Menú móvil sin JavaScript**: el menú hamburguesa usa un `checkbox` y el selector `:checked`.

## Diseño responsive

Se parte de una base común y se adapta con exactamente tres breakpoints:

| Vista | Media query | Cambios principales |
| --- | --- | --- |
| Desktop | `min-width: 1024px` | Navegación en línea, hero oscuro con buscador, 4 columnas de tarjetas, detalle en 2 columnas con compra lateral. |
| Tablet | `min-width: 768px` y `max-width: 1023px` | Menú hamburguesa (un solo menú arriba), 2 columnas de tarjetas, detalle en una columna. |
| Mobile | `max-width: 767px` | 1 columna, menú hamburguesa con acceso a Mi perfil y barra de compra fija. |

No hay desplazamiento horizontal en ninguna de las tres vistas.

## Flujo de trabajo con Git

- `main`: versión estable de la entrega.
- `develop`: integración de los módulos.
- `feat/*`: una rama por módulo (`base-estilos`, `recursos-graficos`, `header-footer`, `listado-eventos`, `detalle-evento`, `responsive-tablet`, `documentacion`, `responsive-mobile`), integradas en `develop` con *merge*.
