# My Day

My Day es una aplicación web personal para organizar el día, reducir la multitarea, registrar avances y terminar la jornada con menos pendientes en la cabeza.

## Proyecto académico

Este proyecto fue realizado para el **Máster Online en IA e Innovación 2026 de FOUNDERZ**.

La aplicación fue desarrollada con apoyo de herramientas de inteligencia artificial para idear, estructurar requisitos, generar código, revisar la experiencia de usuario y proponer mejoras. La IA no sustituyó el criterio humano: el resultado final se obtuvo mediante iteraciones, pruebas manuales, revisión visual y decisiones propias sobre el problema, las funcionalidades, el tono y el diseño.

El repositorio incluye:

- La aplicación web funcional en un único archivo `index.html`.
- La presentación del proyecto.
- La documentación técnica y visual.
- La evolución de prompts y versiones.
- Capturas de la evolución de la interfaz.
- El PDF final con la presentación y la documentación.

La aplicación combina planificación, concentración, registro de hábitos y revisión diaria en una interfaz cálida y sin presión.

## Contexto del proyecto

My Day fue desarrollado en el marco del Máster Online en IA e Innovación 2026.

El punto de partida fue una necesidad personal: dejar de saltar entre demasiadas tareas, decidir qué es prioritario, encontrar motivación para empezar y registrar lo que queda pendiente sin tener que recordarlo mentalmente al final del día.

La IA se utilizó como colaboradora para idear, estructurar, programar, revisar y proponer mejoras. Las decisiones sobre el problema, el tono, la utilidad y los valores de la aplicación permanecen bajo criterio humano.

## Funcionalidades

### Hoy

- Fecha actual.
- Frase positiva del día.
- Siguiente acción recomendada.
- Modo “Empieza ahora”.
- Progreso diario.
- Métricas de tareas, foco, movimiento y registros.
- Agenda de hoy.
- Referencia de los próximos siete días.
- Gráfico resumido de actividad reciente.

### Tareas

- Crear, editar, completar y eliminar tareas.
- Prioridad.
- Duración estimada.
- Fecha y hora opcional.
- Etiquetas Work, Entreno, Emma, House, Travel y Study.
- Subtareas interactivas.
- Progreso de subtareas.
- Reordenación manual.
- Ocultar o mostrar tareas completadas.
- Sincronización visual con el calendario.

### Productividad y foco

- Modo “Empieza ahora” para convertir una tarea grande en una acción pequeña.
- Temporizador de concentración de 5, 15, 25 y 50 minutos.
- Pausas programadas.
- Mensajes motivadores.
- Registro de sesiones completadas.
- Registro del tiempo de concentración.
- Mensaje de celebración al completar una sesión.

### Calendario

- Eventos locales.
- Tareas planificadas.
- Diferenciación visual entre eventos y tareas.
- Fecha, hora y duración.
- Eventos sin conexión externa.
- Botón “Conectar Google Calendar”.
- Mensaje visible de que OAuth queda pendiente para una fase posterior.

### Registro

- Hábitos configurables.
- Registro rápido de un hábito.
- Registro detallado de ejercicio.
- Fecha y hora.
- Tipo de ejercicio.
- Descripción.
- Duración.
- Nota opcional.
- Alimentación.
- Actividades realizadas.
- Historial de registros.

### Revisión

- Highlights.
- Notas rápidas.
- Elementos para mañana.
- Historial de evolución.
- Métricas y gráfico semanal.
- Exportación e importación JSON.

## Arquitectura técnica

La aplicación está contenida en un único archivo:

```text
index.html
```

El archivo contiene:

- HTML de las vistas.
- CSS de la interfaz.
- JavaScript de la aplicación.
- Modales y formularios.
- Iconos SVG inline.
- Lógica de persistencia.

No requiere instalación de frameworks ni dependencias locales.

### Tecnologías

- HTML5.
- CSS personalizado.
- JavaScript puro.
- Tailwind CSS desde CDN.
- SVG inline para iconos.
- `localStorage` para persistencia.

La aplicación puede abrirse haciendo doble clic sobre `index.html`. Tailwind necesita conexión para descargarse desde CDN; el resto de la lógica se ejecuta localmente.

### Tailwind en producción

El uso de `cdn.tailwindcss.com` es adecuado para un prototipo local y una entrega académica en un único archivo. Tailwind muestra una advertencia porque, en producción, lo recomendable sería compilar los estilos mediante Tailwind CLI o PostCSS.

## Arquitectura de datos

El estado principal se guarda en una estructura única dentro de `localStorage` con la clave `myDayState`.

Incluye, entre otros datos:

```js
{
  tasks: [],
  events: [],
  habits: [],
  habitLogs: [],
  meals: [],
  activities: [],
  highlights: [],
  notes: [],
  tomorrow: [],
  sessions: 0,
  focusSeconds: 0,
  theme: "light",
  hideDone: false
}
```

### Principios de datos

- Cada tarea conserva un identificador propio.
- La misma tarea se representa en Tareas y Calendario sin duplicar su identidad.
- Los eventos manuales se diferencian de las tareas planificadas mediante `kind`.
- Los hábitos son definiciones reutilizables.
- Los registros de hábitos pertenecen a una fecha concreta.
- Los borradores son distintos de los elementos guardados.
- Los datos antiguos reciben valores predeterminados si falta algún campo nuevo.

## Navegación y arquitectura de información

La aplicación se organiza en cuatro momentos:

### Hoy

Ayuda a decidir qué hacer ahora.

### Planificar

Permite preparar tareas, calendario y elementos para mañana.

### Registrar

Permite anotar lo que realmente se hizo: hábitos, comidas y actividades.

### Revisar

Permite consultar highlights, notas, evolución y estadísticas.

Esta organización evita mezclar una intención futura con un registro de algo ya realizado.

## Decisiones UX/UI

### Enfoque mobile first

La interfaz se plantea primero para pantallas pequeñas:

- Una columna principal.
- Botones táctiles amplios.
- Formularios adaptados a móvil.
- Listas verticales.
- Navegación agrupada.
- Menús que se cierran después de seleccionar una opción.
- Sin scroll horizontal intencionado.

En tablet y escritorio, las tarjetas se distribuyen en columnas y el dashboard aprovecha el espacio disponible sin cambiar la lógica principal.

### Reducción de saturación

La pantalla Hoy prioriza:

1. Siguiente acción.
2. Tarea prioritaria.
3. Progreso del día.
4. Agenda.
5. Registros recientes.

La aplicación utiliza mensajes como:

- “Empieza con solo cinco minutos.”
- “Avanzar poco también es avanzar.”
- “¿Cuál es el siguiente paso más pequeño?”
- “No hace falta completar todo para ver tu progreso.”

No utiliza rankings ni penalizaciones.

### Formularios

Se sustituyeron los diálogos `prompt()` por formularios y modales porque permiten:

- Etiquetar mejor los campos.
- Diferenciar crear y editar.
- Mostrar opciones opcionales.
- Cancelar sin guardar.
- Validar la información.
- Usar la aplicación en móvil y teclado.

## Identidad visual

### Concepto

My Day debe transmitir:

- Calma.
- Claridad.
- Cuidado personal.
- Progreso realista.
- Acompañamiento.
- Organización sin presión.
- Avance paso a paso.

No debe transmitir productividad agresiva, competición ni culpa.

### Tipografía

Se utiliza una familia sans-serif del sistema, con Inter como referencia cuando está disponible.

- Títulos con peso alto.
- Texto de lectura amplio.
- Texto secundario con contraste suficiente.
- Interlineado cómodo.
- Jerarquía consistente entre títulos, etiquetas y descripciones.

### Paleta

La interfaz utiliza una combinación cálida de crema, lila, coral, verde y gris verdoso.

- Crema: descanso visual y sensación de cercanía.
- Lila: calma, reflexión y creatividad.
- Verde: avance sostenible y bienestar.
- Coral/naranja: energía para comenzar sin agresividad.
- Gris verdoso: equilibrio y legibilidad.

Los colores de las etiquetas de tareas ayudan a reconocer categorías, pero no son el único recurso: también se muestran textos, iconos o estados explícitos.

### Logo e iconografía

El logo utiliza un símbolo SVG propio inspirado en la idea de organizar el día y avanzar. Los iconos principales se construyen como SVG inline para mantener consistencia y evitar depender de una librería externa.

## Accesibilidad

Se incorporaron medidas básicas de accesibilidad:

- Etiquetas visibles en formularios.
- `aria-label` para botones de iconos.
- `aria-hidden` en iconos decorativos.
- Estados `focus-visible`.
- Botones con tamaño táctil adecuado.
- Uso de texto además del color.
- Estados de éxito y error mediante mensajes.
- Modales cerrables.
- Reducción de animaciones mediante `prefers-reduced-motion`.
- Diseño sin scroll horizontal intencionado.
- Contrastes mejorados en texto secundario y acciones.

### WCAG y niveles de contraste

El objetivo es cumplir como mínimo WCAG 2.2 AA para texto e interfaz. Los textos principales y algunos botones pueden aproximarse a AAA, pero no debe afirmarse que toda la aplicación cumple AAA sin una auditoría completa de todas las combinaciones, estados, tamaños y modos claro/oscuro.

La validación definitiva requiere revisar con una herramienta de contraste:

- Texto normal.
- Texto grande.
- Botones.
- Estados hover, focus, active y disabled.
- Etiquetas de colores.
- Modo claro.
- Modo oscuro.
- Gráficos.

## Historial y gráficos

Los gráficos se utilizan para ayudar a reconocer patrones, no para imponer objetivos.

La vista de estadísticas muestra:

- Tareas completadas.
- Sesiones de foco.
- Eventos realizados.
- Highlights escritos.
- Minutos de ejercicio.
- Evolución de los últimos siete días.

El gráfico se construye con HTML y CSS, sin instalar librerías. Se incluye una descripción textual y se diferencia cuando se muestran datos de ejemplo.

No se deben inventar métricas históricas. Si no existen registros suficientes, la aplicación debe mostrar un estado vacío o identificar claramente cualquier dato de demostración.

## Exportación e importación JSON

La aplicación permite crear una copia de seguridad local sin enviar datos a ningún servidor.

El archivo exportado incluye:

- Nombre de la aplicación.
- Versión del formato.
- Fecha de exportación.
- Tareas.
- Eventos.
- Hábitos.
- Registros.
- Comidas.
- Actividades.
- Highlights.
- Notas.
- Elementos para mañana.
- Estadísticas.
- Preferencias.

La importación valida que exista una estructura compatible, pide confirmación antes de reemplazar datos y no ejecuta código contenido en el JSON.

## Google Calendar: fase 2

La integración real no está implementada.

Para una versión futura sería necesario:

1. Crear un proyecto en Google Cloud.
2. Configurar OAuth 2.0.
3. Crear un Client ID.
4. Cargar Google Identity Services.
5. Solicitar los scopes necesarios de Calendar.
6. Gestionar el consentimiento del usuario.
7. Sincronizar eventos locales y remotos.
8. Gestionar errores, permisos, renovación de tokens y desconexión.
9. Utilizar un backend seguro si alguna operación requiere proteger credenciales.

Nunca se debe incluir un Client Secret en este archivo HTML.

## Verificación

### Comprobado en el proyecto

- Existencia del archivo único `index.html`.
- Sintaxis JavaScript mediante `node --check` sobre el script extraído.
- Persistencia mediante `localStorage` en el código.
- Vistas de Hoy, Planificar, Registrar y Revisar.
- Tareas, hábitos, calendario y estadísticas implementados.
- Ausencia de llamadas `prompt()`.
- Exportación e importación JSON implementadas.
- Google Calendar mantenido como fase futura.

### Verificación pendiente o parcial

- Prueba visual completa en todos los navegadores.
- Auditoría AAA exhaustiva.
- Pruebas con lector de pantalla.
- Pruebas con teclado de todos los recorridos.
- Pruebas en dispositivos móviles físicos.
- Verificación real de OAuth de Google Calendar.

## Ejecución local

1. Guarda el archivo con el nombre `index.html`.
2. Haz doble clic para abrirlo en el navegador.
3. Para una experiencia más estable, abre la carpeta con Visual Studio Code y utiliza Live Server.
4. Haz clic derecho sobre `index.html`.
5. Selecciona **Open with Live Server**.

### URL para visualizarla

Actualmente My Day no tiene una URL pública: funciona como una aplicación local.

Si se abre haciendo doble clic, el navegador utilizará una dirección local con este formato:

```text
file:///ruta/de/tu/carpeta/index.html
```

Si se utiliza Live Server, la dirección habitual será:

```text
http://127.0.0.1:5500/index.html
```

También puede aparecer como `http://localhost:5500/index.html`. El puerto puede cambiar si Live Server está utilizando otro, por lo que hay que abrir la dirección que muestra Visual Studio Code en la esquina inferior derecha o en el navegador.

Para compartir la aplicación con otra persona habría que publicarla en un servicio como GitHub Pages, Netlify o Vercel. Esa publicación todavía no forma parte de esta entrega.

La aplicación funciona localmente. Tailwind y cualquier imagen externa pueden requerir conexión a Internet.

## Créditos

Creado por Rocío.

Portfolio: https://rociogoye.github.io/portfolioros/
