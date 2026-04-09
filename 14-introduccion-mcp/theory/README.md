# Teoría - Módulo 14

## 1. ¿Qué es MCP?

MCP significa **Model Context Protocol**.

Es un protocolo que permite conectar un modelo o agente con herramientas externas de forma estructurada.

En términos simples, MCP hace posible que un agente:

- descubra herramientas
- invoque herramientas
- reciba resultados de esas herramientas
- combine esos resultados con su razonamiento

## 2. Qué problema resuelve MCP

Sin MCP, un agente suele trabajar solo con:

- el prompt del usuario
- los archivos visibles
- su propia capacidad de razonamiento

Con MCP, el agente puede ampliar sus capacidades usando herramientas como:

- generadores de diagramas
- conectores a documentación
- conectores a bases de datos
- servicios de archivos
- herramientas de análisis

## 3. Arquitectura básica

En una integración MCP suelen aparecer estos elementos:

- **cliente MCP**: la aplicación que usa el agente, por ejemplo Claude Code
- **servidor MCP**: el componente que expone herramientas
- **herramientas**: funciones concretas que el agente puede invocar
- **usuario**: quien da la tarea o supervisa el resultado

## 4. Cómo se ve el flujo

Un flujo simplificado es este:

1. el usuario pide una tarea
2. el agente decide que necesita una herramienta
3. el cliente llama al servidor MCP
4. la herramienta responde
5. el agente integra el resultado

## 5. Qué valor aporta MCP en ingeniería de datos

En ingeniería de datos, MCP puede ayudar a:

- documentar pipelines
- visualizar arquitecturas
- consultar documentación técnica
- automatizar contextos
- conectar agentes con herramientas reales del ecosistema

## 6. Qué aprenderemos con draw.io MCP

En este módulo usaremos el MCP oficial de draw.io para que el agente pueda abrir diagramas en draw.io a partir de:

- XML
- CSV
- Mermaid

Para el laboratorio, la opción más sencilla será usar **Mermaid**, porque ya tenemos un flujo técnico definido desde el DAG del tema 12.

## 7. Funciones principales del MCP de draw.io

Según la documentación oficial del servidor MCP de draw.io, las funciones principales expuestas son estas:

- `open_drawio_xml`
- `open_drawio_csv`
- `open_drawio_mermaid`

### `open_drawio_xml`

Esta función abre draw.io usando contenido XML nativo del formato draw.io o mxGraph.

Sirve cuando:

- quieres control total del diagrama
- necesitas una estructura más detallada
- quieres definir manualmente elementos, conexiones o propiedades visuales

En la práctica, es la opción más potente pero también la más compleja.

### `open_drawio_csv`

Esta función toma un contenido tabular en formato CSV y lo transforma en un diagrama.

Sirve cuando:

- tienes información jerárquica o repetitiva
- quieres construir organigramas
- quieres convertir una tabla simple en un grafo visual

Puede ser útil si quieres diagramar relaciones de tablas, dominios o estructuras repetidas sin escribir XML.

### `open_drawio_mermaid`

Esta función toma sintaxis Mermaid y la abre en draw.io.

Sirve cuando:

- ya tienes un flujo descrito como grafo
- quieres diagramar procesos rápidamente
- necesitas una forma simple y legible de representar pipelines o DAGs

Para este curso, esta es la función más útil porque permite representar muy bien:

- DAGs de Airflow
- flujos de datos
- pasos de arquitectura

## 8. Parámetros comunes de estas funciones

Las tres funciones comparten una lógica similar de parámetros:

- `content`: contenido del diagrama
- `lightbox`: modo de solo visualización
- `dark`: modo visual, por ejemplo `auto`, `true` o `false`

El parámetro más importante siempre es:

- `content`

porque ahí va el XML, el CSV o el Mermaid que será transformado en el diagrama.

## 9. Cuándo conviene usar cada una

Una regla práctica para este curso sería:

- usa `open_drawio_mermaid` para flujos, DAGs y procesos
- usa `open_drawio_csv` para relaciones tabulares sencillas
- usa `open_drawio_xml` cuando necesites un control visual o estructural más fino

## 10. Qué sigue siendo responsabilidad del estudiante

Aunque el MCP permita crear un diagrama automáticamente, el estudiante debe validar:

- si el flujo representado es correcto
- si las dependencias del DAG están bien dibujadas
- si los nombres de tareas coinciden con el proyecto
- si el diagrama es útil para comunicar el pipeline

## 11. Qué se aprende realmente en este módulo

Más allá de instalar una herramienta, este módulo enseña:

- cómo extender un agente con herramientas externas
- cómo pensar en integración y no solo en prompting
- cómo traducir una estructura técnica a una representación visual

## 12. Ideas clave para llevarse

- MCP hace que un agente sea más operativo
- un servidor MCP expone capacidades concretas
- el agente sigue necesitando contexto y validación humana
- visualizar un pipeline ayuda a entenderlo y comunicarlo mejor
