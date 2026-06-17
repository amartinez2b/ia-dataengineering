# Teoría - Módulo 13

## 1. ¿Qué es MCP?

MCP significa **Model Context Protocol**.

Es un protocolo que permite conectar un agente con herramientas externas de forma estructurada.

En términos prácticos, MCP hace posible que un agente:

- descubra herramientas disponibles
- invoque herramientas concretas
- reciba resultados de esas herramientas
- combine esos resultados con su razonamiento

## 2. Arquitectura básica de MCP

En una integración MCP suelen aparecer estos elementos:

- **cliente MCP**: la aplicación que usa el agente, por ejemplo Codex o Claude Code
- **servidor MCP**: el componente que expone herramientas
- **herramientas**: funciones concretas que el agente puede invocar
- **usuario**: quien da la tarea, revisa el resultado y valida la calidad

Un flujo básico se ve así:

1. el usuario pide una tarea
2. el agente detecta que necesita una herramienta
3. el cliente llama al servidor MCP
4. la herramienta responde
5. el agente integra el resultado en su trabajo

## 3. Qué valor aporta MCP en ingeniería de datos

En ingeniería de datos, MCP es útil porque permite que el agente deje de trabajar solo con prompts y archivos.

Con MCP, el agente puede:

- diagramar arquitecturas
- inspeccionar esquemas de bases de datos
- consultar metadatos reales
- generar documentación a partir de fuentes vivas
- reducir trabajo manual repetitivo

## 4. Por qué conviene combinar skills con MCP

Una **skill** especializa al agente en una tarea.

Un **MCP** le da acceso a una herramienta.

Cuando se combinan, el flujo mejora bastante:

- la skill guía cómo pensar el problema
- el MCP permite ejecutar algo concreto sobre una herramienta real

En este módulo, esa combinación aparece en el ejercicio de arquitectura:

- la skill `architecture-diagram-generator` ayuda a diseñar la arquitectura y producir un entregable HTML
- draw.io MCP permite abrir y trabajar el diagrama en draw.io a partir de Mermaid

## 5. Qué hace el MCP de draw.io

El MCP oficial de draw.io permite abrir diagramas en draw.io a partir de distintos formatos.

Las funciones principales expuestas por el servidor son:

- `open_drawio_xml`
- `open_drawio_csv`
- `open_drawio_mermaid`

### `open_drawio_mermaid`

Para este curso, la función más útil es:

- `open_drawio_mermaid`

porque permite transformar un grafo Mermaid en un diagrama editable dentro de draw.io.

Eso es especialmente valioso para:

- flujos de arquitectura
- pipelines de datos
- DAGs
- modelos conceptuales simples

## 6. Qué hace la skill `architecture-diagram-generator`

La skill `architecture-diagram-generator` está pensada para producir diagramas técnicos como archivos `.html` autocontenidos.

Su valor dentro del curso es que ayuda a:

- estructurar mejor los componentes de una arquitectura
- decidir zonas, capas y conexiones
- producir un entregable visual inicial
- traducir una idea arquitectónica a una representación más clara

En este módulo no reemplaza a draw.io. Lo complementa.

## 7. Qué hace el MCP de MySQL

El MCP de MySQL permite conectar el agente a una base de datos real para inspección y consulta controlada.

Según la documentación del proyecto, el servidor ofrece:

- una herramienta principal de consulta como `mysql_query`
- recursos de esquema para tablas, columnas, índices y relaciones detectadas

Eso permite que el agente pueda:

- listar tablas
- revisar columnas y tipos
- identificar claves aparentes
- observar relaciones potenciales
- resumir un esquema real

## 8. Cómo pasar de tablas reales a un modelo de datos

Un modelo de datos inicial no nace de adivinar. Nace de observar:

- nombres de tablas
- nombres de columnas
- tipos de datos
- claves aparentes
- relaciones potenciales

Con ayuda del MCP de MySQL, el agente puede proponer:

- entidades principales
- posibles dimensiones y tablas transaccionales
- relaciones candidatas
- cardinalidades probables
- advertencias cuando algo no es concluyente

En este curso, eso se traduce en un modelo de datos técnico inicial, no en una “verdad absoluta” del negocio.

## 9. Qué precauciones hay que tomar

Cuando se conecta un agente a herramientas reales, hay que cuidar:

- no guardar credenciales sensibles en el repositorio
- usar accesos de solo lectura cuando sea posible
- no permitir operaciones destructivas sin justificación
- validar que el diagrama o modelo generado sí representa la realidad
- distinguir entre relación confirmada y relación inferida

## 10. Qué sigue siendo responsabilidad del estudiante

Aunque MCP acelera mucho el trabajo, el estudiante sigue siendo responsable de validar:

- si la arquitectura propuesta tiene sentido técnico
- si el diagrama comunica bien el flujo
- si el modelo de datos no inventa relaciones dudosas
- si el agente interpretó correctamente tablas y columnas
- si el resultado final sirve para otra persona del equipo

## 11. Qué se aprende realmente en este módulo

Más allá de instalar herramientas, este módulo enseña:

- cómo extender un agente con capacidades operativas reales
- cómo combinar prompting, skills y herramientas externas
- cómo transformar metadatos en documentación útil
- cómo pasar de una idea técnica a un entregable visual o estructural

## 12. Ideas clave para llevarse

- MCP hace que un agente sea más operativo
- una skill y un MCP resuelven problemas distintos y complementarios
- draw.io MCP sirve muy bien para diagramar a partir de Mermaid
- MySQL MCP permite inspeccionar datos reales y no solo imaginar su estructura
- la validación humana sigue siendo indispensable
