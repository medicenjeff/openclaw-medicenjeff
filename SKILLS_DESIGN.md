# Diseño de skills

Este repositorio no contiene implementaciones propias de skills; este documento describe los skills operativos declarados por el entorno del agente.

Para cada skill se responden las mismas tres preguntas de diseño:

1. **¿Qué problema resuelve?** Define el objetivo y el valor principal.
2. **¿Cuándo se activa y qué necesita?** Define la señal de entrada y el contexto mínimo.
3. **¿Qué entrega y cómo se sabe que funciona?** Define la salida esperada y el criterio de éxito.

## `summarize-github-issue-pr-notification`

1. **¿Qué problema resuelve?** Convierte una issue, PR o notificación de GitHub extensa en un resumen breve con los puntos principales, decisiones, riesgos y acciones relevantes.
2. **¿Cuándo se activa y qué necesita?** Se activa cuando el usuario pide resumir una issue, un PR o una notificación. Necesita el contenido o una referencia accesible al recurso.
3. **¿Qué entrega y cómo se sabe que funciona?** Entrega un resumen fiel y fácil de escanear, sin inventar información y conservando el contexto técnico importante.

## `suggest-fix-issue`

1. **¿Qué problema resuelve?** Traduce los detalles de una issue en una propuesta de solución técnica accionable.
2. **¿Cuándo se activa y qué necesita?** Se activa cuando el usuario proporciona una issue y solicita una corrección o sugerencia. Necesita el problema, el comportamiento esperado y, cuando estén disponibles, el contexto del código y las restricciones.
3. **¿Qué entrega y cómo se sabe que funciona?** Entrega una solución razonada con cambios concretos, riesgos y validaciones; funciona si permite implementar y comprobar la corrección sin depender de suposiciones ocultas.

## `form-github-search-query`

1. **¿Qué problema resuelve?** Convierte una petición en lenguaje natural en una consulta de búsqueda de GitHub precisa.
2. **¿Cuándo se activa y qué necesita?** Se activa cuando el usuario quiere buscar issues o PRs. Necesita los términos, filtros y el tipo de recurso que desea encontrar.
3. **¿Qué entrega y cómo se sabe que funciona?** Entrega una consulta compatible con la búsqueda de GitHub, con filtros que reflejan la intención del usuario y sin añadir restricciones no solicitadas.

## `show-github-search-result`

1. **¿Qué problema resuelve?** Hace comprensibles los resultados de una búsqueda de GitHub y ayuda a comparar rápidamente sus elementos.
2. **¿Cuándo se activa y qué necesita?** Se activa al mostrar resultados obtenidos mediante una búsqueda de GitHub. Necesita la colección de resultados y sus metadatos principales.
3. **¿Qué entrega y cómo se sabe que funciona?** Entrega una tabla Markdown legible, fiel a los resultados y con enlaces o identificadores suficientes para continuar la investigación.

## `address-pr-comments`

1. **¿Qué problema resuelve?** Convierte comentarios de revisión de un PR en cambios de código verificables y respuestas coherentes.
2. **¿Cuándo se activa y qué necesita?** Se activa cuando el usuario pide atender comentarios de revisión. Necesita el PR activo, los hilos o comentarios y acceso al código afectado.
3. **¿Qué entrega y cómo se sabe que funciona?** Entrega los cambios solicitados, validaciones ejecutadas y comentarios resueltos cuando corresponde; funciona si cada observación queda atendida o explicada con evidencia.

## `create-pull-request`

1. **¿Qué problema resuelve?** Formaliza cambios de una rama en una propuesta de integración revisable en GitHub.
2. **¿Cuándo se activa y qué necesita?** Se activa cuando el usuario solicita abrir un PR. Necesita la rama de origen, el destino, el alcance de los cambios y el título o contexto suficiente para describirlos.
3. **¿Qué entrega y cómo se sabe que funciona?** Entrega un PR correctamente creado, con descripción, alcance y estado adecuados; funciona si los revisores pueden entender qué cambió, por qué y cómo validarlo.

## `project-setup-info-local`

1. **¿Qué problema resuelve?** Proporciona una guía local y coherente para crear la estructura completa de un proyecto nuevo.
2. **¿Cuándo se activa y qué necesita?** Se activa al solicitar la creación o configuración inicial de un proyecto, framework o servidor. Necesita el tipo de proyecto, tecnologías preferidas y restricciones del entorno.
3. **¿Qué entrega y cómo se sabe que funciona?** Entrega pasos de configuración, estructura, dependencias y comandos de verificación; funciona si el proyecto puede arrancar y ejecutar su comprobación básica siguiendo la guía.

## `get-search-view-results`

1. **¿Qué problema resuelve?** Recupera los resultados que ya están visibles en la vista de búsqueda de VS Code para trabajar sobre ellos sin repetir la búsqueda.
2. **¿Cuándo se activa y qué necesita?** Se activa cuando el usuario pide analizar o reutilizar los resultados actuales de Search. Necesita que exista una búsqueda activa en VS Code.
3. **¿Qué entrega y cómo se sabe que funciona?** Entrega los resultados actuales con sus rutas y coincidencias; funciona si refleja la vista activa y permite localizar los archivos relevantes.

## `agent-customization`

1. **¿Qué problema resuelve?** Diseña, revisa y corrige archivos de personalización de agentes, instrucciones, prompts y skills.
2. **¿Cuándo se activa y qué necesita?** Se activa cuando el usuario quiere configurar el comportamiento del agente o diagnosticar por qué una personalización no se aplica. Necesita el archivo objetivo, su alcance y el comportamiento esperado.
3. **¿Qué entrega y cómo se sabe que funciona?** Entrega una personalización válida y aplicable, con frontmatter y patrones correctos; funciona si el agente reconoce la configuración y cambia su comportamiento en el contexto previsto.

## `chronicle`

1. **¿Qué problema resuelve?** Convierte el historial de sesiones de Copilot en búsquedas, resúmenes y recomendaciones útiles.
2. **¿Cuándo se activa y qué necesita?** Se activa al pedir un resumen diario, consejos de uso, búsqueda de sesiones, reindexación o gestión de datos históricos. Necesita el alcance temporal o textual de la consulta y la operación solicitada.
3. **¿Qué entrega y cómo se sabe que funciona?** Entrega información derivada del historial local, con el alcance y los resultados claramente delimitados; funciona si los datos corresponden a las sesiones consultadas y la operación solicitada se completa sin alterar información no indicada.

## Criterios transversales

Todos los skills deben:

- respetar el alcance explícito de la petición;
- declarar incertidumbres en vez de rellenarlas con suposiciones;
- producir una salida comprobable y adecuada al formato solicitado;
- evitar acciones externas o destructivas sin autorización suficiente.
