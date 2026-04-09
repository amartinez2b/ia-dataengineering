# IA-Data Engineering

Repositorio del curso **IA-Data Engineering**, orientado a enseñar cómo incorporar asistentes de IA y agentes de programación en flujos reales de ingeniería de datos.

## Objetivo del curso

Desarrollar las capacidades necesarias para usar modelos fundacionales, asistentes de código y agentes de programación en la construcción de soluciones de data engineering. Al finalizar el curso, los participantes podrán diseñar prompts efectivos, trabajar con repositorios asistidos por IA, generar código en Python y PySpark, construir pipelines con Airflow y extender agentes mediante skills y MCP.

## Público objetivo

Este curso está pensado para:

- Ingenieros de datos que quieran incorporar IA a su flujo de desarrollo.
- Desarrolladores que trabajen con Python, PySpark y automatización de pipelines.
- Equipos técnicos interesados en agentes de programación y herramientas modernas de desarrollo asistido por IA.

## Prerrequisitos

Para seguir el curso de forma práctica se recomienda contar con el siguiente entorno instalado:

- Python `3.10+`
- Git `2.53+`
- Visual Studio Code `1.112`
- Node.js `v24.14.0`
- DBeaver `26.0.0`
- Docker Desktop `4.65.0`
- Claude Code (Anthropic) `2.1.80`
- OpenCode `1.2.27`
- Codex `0.116.0` (según disponibilidad para el sistema operativo)
- Cursor `Mar 19, 2026`

## Temario general

| Módulo | Tema | Contenido | Objetivo práctico | Horas |
| ------ | ---- | --------- | ----------------- | ----- |
| 1 | Introducción a la IA para ingenieros de datos | Qué es IA, ML y LLMs. Cómo funcionan los LLMs. Limitaciones y riesgos. IA como asistente de desarrollo. | Comprender cómo los LLM pueden asistir en el desarrollo de pipelines. | 1.5 |
| 2 | Ecosistema actual de LLMs | LLMs propietarios (OpenAI, Anthropic, Gemini). LLMs open source (Llama, Mistral, DeepSeek). Cuándo usar cada uno. | Elegir el modelo adecuado para tareas de ingeniería de datos. | 1.5 |
| 3 | Introducción a Git y GitHub para trabajo con IA | Fundamentos de Git. Repositorios, commits, ramas. Flujo de trabajo con IA. Buenas prácticas para repositorios asistidos por LLM. | Crear y gestionar repositorios preparados para trabajar con agentes de IA. | 1.5 |
| 4 | Ingeniería de prompts para desarrollo de software | Cómo estructurar prompts. Contexto, rol, restricciones. Iteración de prompts. Técnicas para generación de código confiable. | Escribir prompts que generen código Python y PySpark de calidad. | 1.5 |
| 5 | Programación asistida por IA vs programación tradicional | Diferencias entre copiar código vs desarrollar con agentes. Estrategias de colaboración humano-IA. | Adoptar una metodología moderna de desarrollo asistido por IA. | 1.5 |
| 6 | Introducción a agentes de programación | Qué es un agente de código. Arquitectura básica. Principales herramientas: Claude Code, OpenCode, OpenDevin/OpenCalw, Codex Agents. | Comprender cómo funcionan los agentes autónomos de programación. | 1.5 |
| 7 | Instalación y configuración de Claude Code | Instalación. Configuración del entorno. Integración con repositorios. Flujo básico de trabajo. | Configurar Claude Code en un entorno real de desarrollo. | 1.5 |
| 8 | Archivos de contexto para agentes | Uso de archivos como `CLAUDE.md`, `MEMORY.md`, instrucciones de proyecto. Context engineering. | Crear contexto persistente para mejorar la calidad del código generado. | 1.5 |
| 9 | Desarrollo práctico con Claude Code | Flujo de trabajo con agentes. Cómo pedir tareas complejas. Refactorización asistida. Debugging con IA. | Utilizar Claude Code para desarrollar software real. | 1.5 |
| 10 | Proyecto práctico 1 - Desarrollo web simple | Crear una página web básica usando Claude Code. Estructura del proyecto. Iteración con IA. | Aprender a coordinar múltiples archivos con agentes. | 1.5 |
| 11 | Proyecto práctico 2 - Desarrollo PySpark | Generar scripts PySpark con Claude Code. Lectura de datos. Transformaciones. Escritura en Delta/Parquet. | Construir código de ingeniería de datos con IA. | 1.5 |
| 12 | Desarrollo de pipelines con IA | Uso de IA para generar DAGs de Airflow. Orquestación de pipelines. Testing de pipelines con IA. | Crear un pipeline Spark + Airflow asistido por agentes. | 1.5 |
| 13 | Skills y automatización del desarrollo | Qué son los Skills. Cómo crear skills reutilizables para pipelines de datos. Automatización de tareas repetitivas. | Crear skills para generar pipelines Spark + Airflow automáticamente. | 1.5 |
| 14 | Introducción a MCP (Model Context Protocol) | Qué es MCP. Arquitectura cliente-servidor. Herramientas MCP. Casos de uso en ingeniería de datos. | Entender cómo conectar LLMs con herramientas externas. | 1.5 |
| 15 | Integración de herramientas mediante MCP | Conectar MCP con repositorios, bases de datos o documentación. Automatización del contexto. | Integrar herramientas reales con agentes de programación. | 1.5 |
| 16 | Arquitectura on premise segura para IA | Componentes de infraestructura, segmentación, identidad, secretos, control de acceso a bases, observabilidad, auditoría y prevención de fuga de información. | Diseñar una arquitectura on premise segura para incorporar IA en procesos internos. | 1.5 |
| 17 | Proyecto final | Construcción de un pipeline completo: ingestión -> transformación PySpark -> orquestación Airflow -> desarrollo asistido con agentes. | Aplicar todos los conceptos del curso en un proyecto real. | 1.5 |

## Duración estimada

El curso está compuesto por **17 sesiones**, cada una con una duración de **1.5 horas**, para una duración total estimada de **25.5 horas**.

## Costo

El costo por participante es de **$250**.

## Resultados esperados

Al finalizar el curso, los participantes deberían poder:

- Entender el rol de la IA en el ciclo de vida de desarrollo de soluciones de datos.
- Elegir herramientas y modelos adecuados para cada tarea.
- Colaborar con agentes de programación de forma estructurada y segura.
- Generar y refinar código en Python, PySpark y Airflow con apoyo de IA.
- Crear contexto reusable mediante archivos de instrucciones, skills y herramientas MCP.
- Desarrollar un proyecto integral de ingeniería de datos asistido por IA.
