# Evolución visual y funcional de My Day

## Alcance de la revisión

Se revisaron las versiones disponibles dentro del proyecto:

- `sources/index.html`
- `sources/index-v2.html`
- `sources/index-v3.html`
- `index.html`, versión actual de trabajo

También se tuvieron en cuenta las capturas compartidas durante la conversación. Las capturas mostradas en el chat no están almacenadas como archivos dentro de esta carpeta, por lo que no se incrustan automáticamente en este documento. No se han generado imágenes ficticias.

## Línea temporal

| Versión | Evidencia disponible | Evolución principal |
|---|---|---|
| `sources/index.html` | Archivo HTML de 21.250 bytes | Prototipo inicial con panel Hoy, tareas, calendario, estadísticas y persistencia local básica. |
| `sources/index-v2.html` | Archivo HTML de 24.268 bytes | Ampliación de funcionalidades y preparación de más interacciones entre tareas, calendario y datos locales. |
| `sources/index-v3.html` | Archivo HTML de 28.214 bytes | Mayor desarrollo de la navegación, formularios y lógica de productividad. |
| `index.html` | Archivo HTML de 63.467 bytes | Versión actual: tareas, subtareas, hábitos, ejercicio, alimentación, actividades, temporizador, vistas agrupadas, estadísticas, gráficos, exportación/importación JSON, tema claro/oscuro y responsive. |

## Versión inicial: `sources/index.html`

### Funcionalidades visibles en el código

- Vista principal del día.
- Lista de tareas.
- Calendario local.
- Estadísticas iniciales.
- Persistencia mediante `localStorage`.
- Preparación para Google Calendar, sin OAuth real.

### Características visuales

La estructura era principalmente funcional. La pantalla se organizaba alrededor de tarjetas y navegación sencilla, pero todavía no existía una identidad visual tan definida ni una arquitectura de vistas agrupadas.

### Problemas que motivaron la siguiente versión

- Menos separación entre planificación, registro y revisión.
- Menos detalle en los formularios.
- Menor integración entre tareas y calendario.
- Menos herramientas de seguimiento personal.

## Segunda versión: `sources/index-v2.html`

### Evolución funcional

- Mayor cantidad de interacciones en tareas y calendario.
- Más preparación para sincronizar representaciones de una misma tarea.
- Continuidad de `localStorage`.
- Mantenimiento de Google Calendar como integración futura.

### Evolución visual

La aplicación comienza a tener una estructura más clara de producto, con tarjetas, acciones visibles y una jerarquía más cercana a un planner digital.

## Tercera versión: `sources/index-v3.html`

### Evolución funcional

- Formularios más completos.
- Navegación más desarrollada.
- Mejor separación entre vistas.
- Mayor preparación para tareas, eventos y estadísticas.

### Evolución visual

Se consolida el estilo cálido de My Day: superficies claras, bordes redondeados, colores suaves y una presentación más amable que una lista de productividad tradicional.

## Versión actual: `index.html`

### Funcionalidades incorporadas

- Panel Hoy con fecha, frase diaria, siguiente acción y progreso.
- Tareas con prioridad, duración, fecha, hora, etiquetas y subtareas.
- Reordenación manual.
- Calendario con tareas y eventos diferenciados.
- Modo “Empieza ahora”.
- Temporizador de concentración con pausas.
- Registro de sesiones y tiempo de foco.
- Hábitos configurables.
- Registros diarios de ejercicio.
- Alimentación y actividades.
- Highlights, notas y Para mañana.
- Historial y estadísticas.
- Gráfico de actividad visible también en Hoy.
- Exportación e importación JSON.
- Modo claro y oscuro.
- Footer con autoría y portfolio.
- Navegación agrupada: Hoy, Planificar, Registrar y Revisar.
- Breadcrumbs y opción de volver.
- Formularios y modales en lugar de `prompt()`.
- Persistencia en `localStorage`.

### Evolución visual final

La pantalla Hoy fue reforzada para acercarse a un dashboard visual de planner:

- Hero principal con degradado lila, coral y verde.
- Tarjeta destacada para la intención del día.
- Bloque visual para “Empieza ahora”.
- Cuatro métricas con acentos cromáticos diferentes.
- Gráfico de actividad de los últimos siete días.
- Agenda del día y referencia semanal.
- Registro rápido de hábitos y actividades.
- Header con una línea cromática de marca.
- Fondo con degradado radial suave.

## Comparación global

| Aspecto | Primeras versiones | Versión actual |
|---|---|---|
| Organización | Vistas principalmente funcionales | Arquitectura Hoy / Planificar / Registrar / Revisar |
| Tareas | Lista básica | Prioridad, orden, subtareas, duración y calendario |
| Calendario | Eventos locales | Eventos y tareas con una fuente de datos coherente |
| Hábitos | Registro limitado | Hábitos configurables y registros diarios |
| Productividad | Temporizador básico | Modo “Empieza ahora”, foco, pausas y sesiones |
| Historial | Estadísticas iniciales | Métricas, evolución y gráficos |
| Datos | `localStorage` básico | Persistencia ampliada y copias JSON |
| Diseño | Tarjetas suaves | Dashboard con hero, métricas y gráfico visible |
| Accesibilidad | Parcial | Formularios etiquetados, focus visible y responsive mejorado |

## Screenshots

Durante el proyecto se compartieron capturas de distintas etapas, entre ellas:

1. Panel inicial con navegación superior y tarjetas de progreso.
2. Versión con navegación agrupada en Planificar, Registrar y Revisar.
3. Vista móvil con menú y adaptación responsive.
4. Modal de creación de hábito.
5. Modal de edición de registro de ejercicio.
6. Dashboard de referencia utilizado para orientar el rediseño visual.
7. Versión actual con hero, métricas y agenda.

Las imágenes originales deben conservarse fuera del código si se desea incorporarlas en una entrega visual final. Para documentar una comparación “antes/después” con imágenes incrustadas, es necesario disponer de esos archivos PNG/JPG en una carpeta del proyecto.

## Cambios de criterio

La evolución no consistió solo en añadir funcionalidades. También se modificó el criterio de producto:

- De una lista de tareas a un acompañante diario.
- De una pantalla con muchas acciones a una navegación por momentos del día.
- De medir productividad a registrar avances reales.
- De exigir cumplimiento a ofrecer una siguiente acción posible.
- De una interfaz funcional a una identidad visual cálida y reconocible.
