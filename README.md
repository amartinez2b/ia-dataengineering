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
| 7 | Agentes Top | Instalación y comparación de Codex, Gemini CLI y OpenCode. Autenticación con API keys. Uso básico desde terminal. | Instalar y probar agentes reales de programación. | 1.5 |
| 8 | Archivos de contexto para agentes | Uso de archivos como `CLAUDE.md`, `MEMORY.md`, `AGENTS.md` e instrucciones de proyecto. Context engineering. | Crear contexto persistente para mejorar la calidad del trabajo del agente. | 1.5 |
| 9 | Desarrollo práctico agentico | Flujo de trabajo con agentes. Cómo pedir tareas complejas. Refactorización asistida. Debugging con IA usando Claude Code y Codex. | Utilizar agentes para desarrollar software real. | 1.5 |
| 10 | Proyecto práctico 2 - Desarrollo PySpark | Extender un proyecto real con procesos `raw -> bronze -> silver -> gold` usando Python, PySpark y notebooks. | Construir un flujo de ingeniería de datos con IA. | 1.5 |
| 11 | Desarrollo de pipelines con IA | Uso de IA para generar DAGs de Airflow. Orquestación de pipelines. Validación de dependencias. | Crear un pipeline Spark + Airflow asistido por agentes. | 1.5 |
| 12 | Skills y automatización del desarrollo | Qué son las skills. Instalación y reutilización de skills. Automatización de entregables técnicos. | Usar skills para generar documentos, diagramas y otros entregables técnicos. | 1.5 |
| 13 | MCP para diagramación y modelado de datos | Qué es MCP. Arquitectura cliente-servidor. Uso de draw.io MCP, MySQL MCP y combinación con skills. | Diseñar una arquitectura y generar un modelo de datos asistidos por agentes. | 1.5 |
| 14 | Orquestación de agentes con Omnigent | Problemas de trabajar con varios agentes. Meta-harnesses. Composición, control y colaboración multiagente. Diferencias frente a plataformas de workflows como n8n. | Entender cómo coordinar múltiples agentes desde una capa superior. | 1.5 |
| 15 | Arquitectura on premise segura para IA | Componentes de infraestructura, segmentación, identidad, secretos, control de acceso a bases, observabilidad, auditoría y prevención de fuga de información. | Diseñar una arquitectura on premise segura para incorporar IA en procesos internos. | 1.5 |
| 16 | Proyecto final | Construcción de un pipeline completo: acceso a datos, transformación, modelado, visualización y documentación asistida por agentes. | Aplicar todos los conceptos del curso en un proyecto real. | 1.5 |

## Duración estimada

El curso está compuesto por **16 sesiones**, cada una con una duración de **1.5 horas**, para una duración total estimada de **24 horas**.

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
