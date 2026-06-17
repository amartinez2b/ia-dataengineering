# Teoría - Módulo 14

## 1. El problema de trabajar con varios agentes

Cuando una persona o un equipo trabaja con un solo agente, el flujo puede parecer simple:

- se abre una sesión
- se da una instrucción
- se revisa el resultado

Pero en la práctica real eso cambia muy rápido.

Según Databricks, al trabajar con agentes en equipos grandes es normal tener varios agentes abiertos al mismo tiempo, por ejemplo:

- un agente de código
- un agente de búsqueda
- un agente de investigación
- documentación, chat y herramientas de colaboración aparte

Eso crea varios problemas:

- copiar y pegar contexto entre agentes
- mover resultados manualmente entre sesiones
- perder trazabilidad de qué hizo cada agente
- tener controles distintos según el harness
- dificultad para combinar agentes o reemplazarlos
- colaboración incómoda con otras personas sobre sesiones vivas

El problema no es solo que existan muchos modelos. El problema es que cada **harness** de agentes suele ser un silo propio.

## 2. Qué problemas existen al trabajar con varios agentes

Tomando como base el artículo de Databricks, los principales problemas son estos:

### 2.1 Interfaces incompatibles

Cada harness encapsula al LLM con su propia interfaz, su propia manera de manejar contexto, permisos, archivos y herramientas.

Eso hace difícil:

- mezclar agentes distintos
- cambiar de harness sin reescribir parte del flujo
- reutilizar políticas o sesiones entre herramientas

### 2.2 Composición limitada

Un solo harness normalmente entiende solo sus propias sesiones.

Eso complica patrones como:

- un agente líder que delega a subagentes
- combinar distintos modelos según el tipo de tarea
- mezclar agentes CLI, SDKs y agentes custom en un mismo sistema

### 2.3 Controles débiles o demasiado locales

Muchos controles viven dentro del prompt o dentro del propio harness.

Eso es insuficiente cuando se necesita:

- control de costos
- aprobación humana contextual
- políticas de permisos dinámicas
- gobierno transversal a varias sesiones

### 2.4 Colaboración pobre

Si una sesión vive encerrada dentro de un agente específico, colaborar se vuelve torpe:

- compartir contexto cuesta
- revisar archivos juntos cuesta
- otras personas no pueden entrar fácilmente a la sesión viva

## 3. Cómo Omnigent soluciona estos problemas

Databricks presenta **Omnigent** como un **meta-harness** que se ubica por encima de los agentes existentes.

La idea central es esta:

- no reemplazar necesariamente Claude Code, Codex u otros agentes
- sino envolverlos en una capa común que permita combinarlos, controlarlos y compartirlos

Según el artículo, Omnigent apunta a tres grandes necesidades:

- **Composition**
- **Control**
- **Collaboration**

### 3.1 Composition

Omnigent permite combinar múltiples modelos, harnesses y técnicas sin reescribir todo el sistema.

Eso significa que una organización puede:

- cambiar entre Claude Code, Codex, Pi u otros agentes
- mezclar agentes distintos en una misma solución
- usar un agente para planificación y otro para ejecución

### 3.2 Control

Omnigent agrega políticas con estado y contexto en la capa meta-harness, no solo dentro del prompt.

El artículo destaca ejemplos como:

- presupuestos de costo por sesión
- permisos condicionados por acciones previas
- aprobaciones humanas más inteligentes

La idea importante es que el control ya no depende únicamente de lo que el agente “quiera obedecer” desde el prompt.

### 3.3 Collaboration

Omnigent permite compartir sesiones vivas por URL y colaborar sobre archivos del workspace.

Eso hace posible:

- revisar juntos una sesión
- comentar archivos
- guiar un agente entre varias personas
- convertir la sesión del agente en un espacio de trabajo compartido

## 4. Qué es y por qué es importante construir un meta-harness

Un **meta-harness** es una capa superior que organiza y gobierna varios harnesses de agentes.

No se enfoca solo en:

- ejecutar un modelo
- abrir una sesión
- enviar un prompt

Se enfoca en problemas que aparecen por encima de eso:

- interoperabilidad
- seguridad
- costos
- colaboración
- portabilidad entre agentes

### Por qué importa

Databricks argumenta que la frontera ya no está en usar un solo modelo dentro de un solo harness.

Los mejores resultados empiezan a aparecer cuando:

- se combinan varios modelos
- se combinan varios agentes
- se crean loops y equipos de agentes
- se controla todo eso desde una capa común

La analogía del artículo es útil: así como antes se administraban procesos individuales y luego aparecieron capas superiores como Kubernetes o Terraform para gestionar conjuntos más complejos, con agentes podría estar ocurriendo algo parecido.

## 5. Cómo trabaja Omnigent

El artículo describe un funcionamiento basado en una interfaz común por encima de agentes CLI y SDKs.

La intuición es que, aunque cada harness sea distinto internamente, hacia el usuario comparten una forma parecida de interacción:

- mensajes y archivos de entrada
- texto, streaming y tool calls de salida

Sobre esa idea, Omnigent construye una API común.

### Capacidades principales mencionadas por Databricks

- colaboración en tiempo real
- múltiples interfaces para el mismo agente
- ejecución en nube o local
- políticas de seguridad contextuales
- políticas de costo
- sandbox fuerte a nivel de sistema operativo
- authoring multi-harness

### Flujo conceptual de trabajo con Omnigent

Una forma simple de entenderlo es así:

1. eliges uno o varios agentes existentes
2. cada agente se envuelve en un runner con una interfaz uniforme
3. Omnigent Server administra políticas, colaboración y acceso
4. la misma sesión puede exponerse por terminal, app, web o API
5. puedes combinar agentes distintos sin quedar atado a un solo harness

## 6. Qué aporta Omnigent más allá del harness individual

La propuesta de Databricks no es solo técnica. También cambia el modo de trabajo.

En vez de pensar:

- “abrir un agente y usarlo”

se empieza a pensar en:

- sesiones compartidas
- políticas transversales
- orquestación multiagente
- colaboración viva sobre el workspace

Eso es importante porque muchas tareas reales del curso y del trabajo profesional ya no son de un solo paso. Son secuencias donde:

- un agente investiga
- otro implementa
- otro revisa
- una persona supervisa

## 7. En qué se diferencia Omnigent de n8n

Aunque ambos pueden participar en flujos con IA, no resuelven exactamente el mismo problema.

### Qué es n8n

Según la documentación y el sitio oficial de n8n, n8n es una plataforma de automatización visual orientada a construir workflows con:

- nodos
- conexiones
- integraciones
- lógica de negocio
- pasos con IA
- human-in-the-loop

Además, n8n enfatiza:

- construcción visual
- integraciones con muchas aplicaciones
- despliegue on-prem o cloud
- control y gobernanza para workflows

### Diferencia principal de abstracción

La diferencia más importante es el nivel en el que trabajan.

**Omnigent** trabaja como una capa por encima de múltiples harnesses de agentes.

Su foco es:

- combinar agentes ya existentes
- controlar sesiones de agentes
- compartir sesiones y políticas
- desacoplar el trabajo del harness específico

**n8n** trabaja como plataforma de workflows y automatización visual.

Su foco es:

- encadenar pasos
- integrar aplicaciones y APIs
- automatizar procesos
- mezclar lógica determinística con pasos de IA

### Diferencia práctica

Omnigent encaja mejor cuando el problema principal es:

- orquestar varios agentes
- compartir sesiones vivas
- imponer políticas de costo y seguridad a nivel meta
- cambiar de harness sin rehacer todo

n8n encaja mejor cuando el problema principal es:

- construir workflows de negocio o integración
- mover datos entre servicios
- automatizar secuencias visuales y repetibles
- combinar nodos, reglas y aprobaciones humanas

### No son necesariamente rivales directos

De hecho, pueden convivir.

Por ejemplo:

- n8n puede orquestar procesos de integración y negocio
- Omnigent puede coordinar el trabajo de varios agentes especializados

Uno se parece más a una plataforma de automatización visual.

El otro se parece más a una capa operativa superior para trabajar con agentes de distintos tipos.

## 8. Qué sigue siendo responsabilidad del equipo

Aunque Omnigent prometa una capa superior más potente, el equipo sigue siendo responsable de:

- decidir qué agentes conviene combinar
- definir políticas útiles y no arbitrarias
- validar la calidad del trabajo multiagente
- controlar costos
- asegurar que la colaboración no comprometa datos o secretos

## 9. Qué se aprende realmente en este módulo

Más allá de conocer una herramienta nueva, este módulo enseña:

- que el problema de los agentes ya no es solo prompting
- que el trabajo multiagente necesita otra capa de abstracción
- que composición, control y colaboración se vuelven centrales
- que no toda orquestación de IA es igual: una cosa es automatizar workflows y otra gobernar agentes

## 10. Ideas clave para llevarse

- trabajar con varios agentes crea fricción real
- Omnigent propone un meta-harness para reducir esa fricción
- un meta-harness importa cuando hay que combinar, controlar y compartir agentes
- Omnigent no es lo mismo que n8n
- n8n automatiza workflows; Omnigent organiza el trabajo por encima de varios agentes
