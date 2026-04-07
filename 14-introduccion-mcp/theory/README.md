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

## 7. Qué sigue siendo responsabilidad del estudiante

Aunque el MCP permita crear un diagrama automáticamente, el estudiante debe validar:

- si el flujo representado es correcto
- si las dependencias del DAG están bien dibujadas
- si los nombres de tareas coinciden con el proyecto
- si el diagrama es útil para comunicar el pipeline

## 8. Qué se aprende realmente en este módulo

Más allá de instalar una herramienta, este módulo enseña:

- cómo extender un agente con herramientas externas
- cómo pensar en integración y no solo en prompting
- cómo traducir una estructura técnica a una representación visual

## 9. Ideas clave para llevarse

- MCP hace que un agente sea más operativo
- un servidor MCP expone capacidades concretas
- el agente sigue necesitando contexto y validación humana
- visualizar un pipeline ayuda a entenderlo y comunicarlo mejor
