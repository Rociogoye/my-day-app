# Actividad del módulo 2 · Colaborar eficazmente con la IA

## Contexto del proyecto

Este proyecto se desarrolla en el marco del Máster Online en IA e Innovación 2026. Como aplicación práctica de los contenidos del módulo, decidí diseñar una herramienta digital para una necesidad real de organización y productividad personal.

La necesidad parte de una experiencia concreta: intentar atender demasiadas tareas a la vez, tener dificultad para priorizar, procrastinar ante actividades grandes y mantener demasiados pendientes en la memoria. My Day nace para ayudar a organizar el día, concentrarse en una acción posible y registrar lo que queda pendiente.

## Objetivo

El objetivo era idear, desarrollar y ejecutar una aplicación web con un uso real: ayudar a planificar el día, priorizar tareas, reducir la procrastinación, registrar hábitos y liberar espacio mental.

La IA debía ayudar a convertir una idea inicial en un prototipo funcional, pero sin sustituir las decisiones sobre el problema, el tono ni la experiencia de usuario.

## Papel de la IA

La inteligencia artificial participó como colaboradora técnica y creativa. Ayudó a:

- Convertir la idea inicial en requisitos.
- Proponer estructuras de navegación.
- Generar HTML, CSS y JavaScript.
- Diseñar formularios y componentes.
- Sugerir mejoras de UX/UI.
- Detectar posibles errores.
- Organizar la documentación y la presentación.

La IA no recibió la responsabilidad completa del proyecto. El resultado se construyó mediante iteraciones y pruebas humanas.

## Técnicas utilizadas

### 1. Prompting avanzado e iterativo

El trabajo no se resolvió con un único prompt. Se empezó con una descripción general de My Day y, a medida que la aplicación se probaba, se formularon instrucciones más específicas.

Los prompts posteriores abordaron problemas concretos como:

- Sincronización entre tareas y calendario.
- Subtareas interactivas.
- Modo “Empieza ahora”.
- Registro detallado de ejercicio.
- Navegación móvil.
- Ausencia de scroll horizontal.
- Formularios en lugar de `prompt()`.
- Accesibilidad y contraste.
- Historial y gráficos.
- Exportación e importación JSON.
- Identidad visual, header y dashboard.

Cada nuevo prompt se basó en una observación real del estado anterior de la aplicación.

### 2. Pensamiento crítico guiado

Después de cada propuesta de la IA se evaluó si la solución:

- Resolví­a realmente el problema.
- Era comprensible para la persona usuaria.
- Evitaba generar presión o culpa.
- Funcionaba en móvil y escritorio.
- Conservaba los datos correctamente.
- Era coherente con la identidad visual de My Day.
- Diferenciaba una funcionalidad solicitada de una funcionalidad realmente implementada.

La IA podía proponer una solución, pero su aceptación dependía de las pruebas y del criterio humano.

## Decisiones delegadas y no delegadas

### Decisiones apoyadas en la IA

- Propuestas de funcionalidades.
- Estructuras iniciales de código.
- Alternativas de arquitectura.
- Textos de interfaz.
- Ideas para navegación y responsive design.
- Propuestas visuales.
- Detección inicial de errores.
- Organización de documentación.

### Decisiones mantenidas bajo criterio humano

- Definir el problema que debía resolver la aplicación.
- Elegir las funcionalidades realmente útiles.
- Decidir qué información debía tener prioridad.
- Definir un tono amable y no culpabilizante.
- Decidir qué propuestas aceptar, modificar o descartar.
- Probar la aplicación como usuaria real.
- Evaluar si una interacción era intuitiva.
- Decidir cuándo una pantalla estaba demasiado saturada.
- Comprobar qué estaba implementado realmente.
- Mantener Google Calendar como una fase futura y no simular una conexión real.

## Iteraciones y pruebas humanas

El resultado final surgió de un ciclo repetido:

```text
Idea → prompt → propuesta → prueba humana → detección de problemas → nuevo prompt → mejora
```

Durante las pruebas se detectaron, entre otros, estos problemas:

- Menús que se superponían a la pantalla principal.
- Falta de una forma clara de volver atrás.
- Tareas que no se reflejaban correctamente en el calendario.
- Diferencias entre crear un hábito y editar un registro de ejercicio.
- Borradores que no estaban suficientemente diferenciados de los elementos guardados.
- Exceso de pestañas en móvil.
- Necesidad de mostrar el gráfico de forma más visible.
- Una identidad visual demasiado débil en las primeras versiones.

Cada observación produjo nuevas instrucciones y cambios. Por eso la aplicación final no es el resultado de aceptar automáticamente una generación de IA, sino de una serie de decisiones y validaciones.

## Prácticas para evitar la sobreconfianza

Para evitar una dependencia excesiva de la IA se utilizaron estas prácticas:

- Revisar manualmente las funciones después de cada cambio.
- Probar tareas, calendario, hábitos, formularios y temporizador.
- Reformular los prompts cuando una respuesta era demasiado general.
- Comprobar la sintaxis JavaScript.
- Revisar la persistencia en `localStorage`.
- Diferenciar entre lo pedido, lo sugerido y lo realmente implementado.
- No afirmar que Google Calendar estaba conectado.
- Documentar las limitaciones y pruebas pendientes.
- Revisar la experiencia visual en escritorio y móvil.

## Retos y dilemas

Uno de los principales retos fue equilibrar cantidad de funcionalidades y claridad. Añadir más opciones podía hacer que la aplicación fuera más completa, pero también podía saturar a la persona usuaria.

Otro reto fue decidir cuándo una solución técnicamente posible no era una buena solución de experiencia de usuario. Por ejemplo, una navegación con muchos submenús podía funcionar desde el punto de vista del código, pero resultar confusa en escritorio y móvil.

También fue necesario mantener una frontera clara entre una demostración local y una integración real. Por eso se decidió no simular OAuth de Google Calendar y dejar documentada su implementación para una fase posterior.

## Reflexión final

No delegué todo el proyecto en la IA. La IA aportó velocidad, alternativas y apoyo técnico, pero las pruebas humanas y las decisiones de diseño fueron las que guiaron el resultado final.

Yo definí el problema, seleccioné las funcionalidades, marqué el tono, revisé las propuestas, observé los errores y decidí qué debía cambiar. El desarrollo se realizó mediante iteraciones, no mediante una única respuesta automática.

Este proceso cambió mi forma de pensar la colaboración con IA. Entendí que utilizarla eficazmente no consiste solo en pedir una respuesta, sino en saber formular el problema, dar contexto, evaluar críticamente, probar el resultado y volver a iterar.

La IA funcionó como copiloto, no como piloto automático. My Day es el resultado de una colaboración en la que la tecnología complementó el criterio humano sin sustituirlo.
