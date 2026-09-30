# Evolución de prompts del proyecto My Day

Este documento recoge los principales prompts utilizados durante el desarrollo de My Day. Se distingue entre el objetivo de cada solicitud y el resultado que se pudo comprobar en la aplicación. La conexión real con Google Calendar mediante OAuth se mantuvo siempre como una funcionalidad futura.

## 1. Creación inicial de la aplicación

### Objetivo
Crear una aplicación web de productividad llamada My Day en un único archivo `index.html`.

### Solicitud principal
La aplicación debía incluir un panel diario, tareas, prioridades, etiquetas, calendario, temporizador Pomodoro, modo “Empieza ahora”, highlights, notas, elementos para mañana, estadísticas, modo claro/oscuro, diseño responsive y almacenamiento en `localStorage`.

### Decisiones derivadas
- HTML, CSS y JavaScript puro.
- Tailwind CSS desde CDN.
- Datos de ejemplo para mostrar una aplicación completa desde el primer acceso.
- Google Calendar preparado para una futura fase, sin simular OAuth.

### Resultado comprobado
Se creó una primera versión funcional de My Day en un único archivo HTML, con persistencia local y datos de ejemplo.

## 2. Revisión de cobertura funcional

### Objetivo
Comprobar si la aplicación cumplía todos los requisitos iniciales.

### Problemas detectados
- El modo “Empieza ahora” iniciaba principalmente el temporizador, pero no siempre explicaba el primer paso.
- Las subtareas no eran completamente interactivas.
- La frase del día necesitaba una lógica de selección y permanencia diaria más clara.
- Faltaban controles de reorganización manual.
- La integración de Google Calendar debía quedar mejor documentada.

### Resultado
Se definió una segunda etapa centrada en completar la lógica de productividad y comprobar las interacciones en navegador.

## 3. Mejora del modo “Empieza ahora” y las subtareas

### Objetivo
Convertir una tarea grande en una acción concreta y pequeña, y permitir dividir tareas en subtareas reales.

### Cambios solicitados
- Generar un primer paso accionable.
- Mostrar únicamente la siguiente acción recomendada.
- Permitir iniciar el temporizador desde ese primer paso.
- Añadir subtareas con estado, edición, eliminación y progreso.
- Guardar todos los cambios en `localStorage`.

### Resultado comprobado
La aplicación incorporó una función que transforma títulos como “Preparar presentación” en una acción inicial más concreta y permite iniciar una sesión de foco vinculada a esa tarea.

## 4. Frase positiva diaria

### Objetivo
Evitar que la frase motivadora fuese siempre la misma y mantenerla estable durante el día.

### Cambios solicitados
- Selección aleatoria.
- Una frase diferente cada día.
- Persistencia durante el día.
- Evitar repetir inmediatamente las frases disponibles.
- Guardar la frase en `localStorage`.

### Resultado comprobado
Se incorporó un historial de frases utilizadas y una lógica que selecciona una frase nueva cuando cambia la fecha.

## 5. Reorganización y sincronización de tareas

### Objetivo
Mejorar el control de prioridades y hacer que las tareas aparecieran también en el calendario.

### Cambios solicitados
- Prioridad clara.
- Orden automático por prioridad.
- Controles para subir y bajar tareas.
- Fecha, hora opcional, duración, etiqueta y subtareas.
- Una única identidad para cada tarea.
- Sincronización entre Tareas y Calendario.
- Tareas sin hora agrupadas aparte.

### Resultado comprobado
Las tareas utilizan un identificador persistente y pueden aparecer en la agenda cuando tienen fecha y hora. Las tareas sin hora se diferencian de los eventos manuales.

## 6. Highlights, notas y “Para mañana”

### Objetivo
Diferenciar los borradores de los contenidos guardados.

### Cambios solicitados
- Botones explícitos de guardar.
- Listas independientes.
- Edición y eliminación.
- Fechas de creación o actualización.
- Diferenciar notas libres de tareas planificadas.

### Resultado comprobado
Highlights, notas y elementos para mañana se almacenan como listas en `localStorage`. Se mantuvo compatibilidad con datos antiguos que estaban guardados como texto único.

## 7. Habit tracker y registros diarios

### Objetivo
Ampliar My Day para registrar ejercicio, alimentación y actividades sin convertirlo en una hoja de cálculo.

### Cambios solicitados
- Crear hábitos configurables.
- Registrar hábitos en una fecha concreta.
- Registrar tipo de ejercicio, descripción, duración, hora y notas.
- Permitir marcar rápidamente un hábito como hecho.
- Consultar y editar registros anteriores.
- Añadir resúmenes semanales.

### Resultado comprobado
Se separaron los conceptos de “crear hábito” y “registrar ejercicio”. Los registros incluyen fecha, hora opcional, tipo, descripción, duración y nota. También se añadieron formularios para alimentación y actividades.

## 8. Navegación y arquitectura de vistas

### Objetivo
Evitar que los submenús flotantes dejaran visible la pantalla principal detrás y confundieran al usuario.

### Cambios solicitados
Organizar la aplicación en cuatro áreas principales:

- Hoy.
- Planificar.
- Registrar.
- Revisar.

Con vistas secundarias para tareas, calendario, hábitos, alimentación, actividades, highlights, notas y estadísticas.

### Resultado comprobado
Se añadieron vistas agrupadas, breadcrumbs, botón “Volver”, acceso directo a Hoy y navegación móvil. La vista secundaria sustituye al contenido principal en lugar de quedar únicamente superpuesta.

## 9. Auditoría UX/UI y responsive

### Objetivo
Revisar la aplicación como arquitecto, desarrollador frontend y diseñador UX/UI.

### Cambios solicitados
- Mobile first.
- Sin scroll horizontal.
- Diseño responsive para móvil, tablet y ordenador.
- Formularios en lugar de `prompt()`.
- Estados vacíos claros.
- Mejor jerarquía visual.
- Contraste y navegación por teclado.
- Modos claro y oscuro.

### Resultado comprobado
Se eliminaron las llamadas a `prompt()`, se añadieron formularios y modales, se incorporó `focus-visible`, se ocultó el desbordamiento horizontal y se mejoraron varios contrastes y tamaños táctiles.

## 10. Header, footer, marca e iconografía

### Objetivo
Crear una identidad más reconocible para My Day.

### Cambios solicitados
- Header global.
- Footer global.
- Logo propio.
- Iconos SVG en lugar de emojis para las acciones principales.
- Manual de marca.
- Enlace al portfolio de Rocío.
- Explicación de colores, tipografía y tono.

### Resultado comprobado
Se añadió un footer global con autoría, portfolio y aviso de almacenamiento local. Se incorporaron iconos SVG para varias acciones y una primera identidad basada en calma, avance y organización amable.

### Limitación detectada
La identidad visual tuvo varias iteraciones y no siempre se visualizó correctamente en el navegador integrado por problemas de caché o por abrir una ruta diferente del archivo actualizado.

## 11. Historial, evolución y gráficos

### Objetivo
Mostrar el progreso sin convertirlo en una evaluación rígida.

### Cambios solicitados
- Historial de hábitos, tareas, ejercicio, actividades y sesiones.
- Resumen de siete días.
- Gráfico accesible sin librerías externas.
- Utilizar datos reales y diferenciar los datos de ejemplo.

### Resultado comprobado
Se añadió una vista de estadísticas con métricas y un gráfico de barras de minutos de ejercicio. Posteriormente se incorporó un gráfico resumido de actividad directamente en la vista Hoy.

## 12. Exportación e importación JSON

### Objetivo
Proteger los datos del usuario ante la pérdida de `localStorage`.

### Cambios solicitados
- Exportar todas las estructuras relevantes a un archivo JSON.
- Incluir versión y fecha de exportación.
- Importar y validar datos.
- Pedir confirmación antes de reemplazar la información.
- No ejecutar código incluido en el archivo.

### Resultado comprobado
Se implementaron botones para exportar e importar una copia de seguridad JSON desde la sección de estadísticas. La importación valida la estructura básica y no ejecuta el contenido del archivo.

## 13. Rediseño del dashboard

### Objetivo
Acercar My Day a una experiencia de dashboard visual, cálida y modular, inspirada en referencias de planners digitales.

### Cambios solicitados
- Hero principal más expresivo.
- Métricas destacadas.
- Agenda y registros visibles.
- Gráficos en el dashboard.
- Tarjetas modulares.
- Navegación superior, sin menú lateral.
- Identidad visual más fuerte.

### Resultado comprobado
La pantalla Hoy se actualizó con:

- Hero con degradados lila, coral y verde.
- Métricas diferenciadas por color.
- Gráfico de actividad de los últimos siete días visible en la pantalla principal.
- Header con una línea cromática de marca.
- Mayor protagonismo para “Empieza ahora”.
- Fondo, sombras y tarjetas más cercanos a una aplicación dashboard.

## Estado actual

### Implementado
- Aplicación en un único `index.html`.
- Tareas y subtareas.
- Calendario local.
- Hábitos y registros.
- Alimentación y actividades.
- Temporizador Pomodoro.
- Highlights, notas y Para mañana.
- Estadísticas y gráficos.
- Modo claro y oscuro.
- Persistencia en `localStorage`.
- Exportación e importación JSON.
- Diseño responsive.
- Preparación documental para Google Calendar.

### Pendiente o limitado
- OAuth real con Google Calendar.
- Verificación visual completa en todos los navegadores.
- Comprobación AAA exhaustiva de todos los componentes y estados.
- Posibles mejoras futuras de ilustraciones, iconografía y personalización visual.

## Criterio de colaboración con IA

La IA se utilizó para idear, estructurar, programar, revisar y proponer mejoras. Las decisiones sobre el problema, el tono, la utilidad real, la ausencia de presión y la dirección visual pertenecen al criterio humano del proyecto.

La aplicación no se plantea como una herramienta para exigir más productividad, sino como un apoyo para reducir la multitarea, registrar lo realizado y terminar el día con menos pendientes en la cabeza.
