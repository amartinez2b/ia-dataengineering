# Módulo 13 - Skills y automatización del desarrollo

## Objetivo del módulo

Entender qué son las skills, cómo amplían las capacidades de un agente y cómo pueden usarse para automatizar tareas repetitivas o especializadas dentro de un flujo de ingeniería de datos.

## Enfoque del módulo

Este módulo es principalmente práctico. La teoría introduce el concepto de skills, su valor operativo y repositorios de referencia como [openai/skills](https://github.com/openai/skills). La práctica se centra en usar la skill `docx` para generar un documento Word con la documentación técnica del proyecto desarrollado hasta el tema 12, e incluye además ejercicios complementarios para instalar y usar el plugin `Chrome` en Codex, la skill `prompt-master` en Claude Code y Codex, y la skill `architecture-diagram-generator` para producir diagramas técnicos en HTML.

El alcance del curso no es construir skills desde cero, sino entender su papel general y trabajar con una skill ya existente dentro de un caso aplicado.

## Resultados de aprendizaje

Al finalizar este módulo, el estudiante podrá:

- explicar qué es una skill y para qué sirve
- instalar skills en Claude Code desde un marketplace
- instalar un plugin en Codex y usarlo desde un prompt
- instalar una skill pública y reutilizarla en distintos agentes
- usar una skill especializada para generar entregables profesionales
- usar una skill para generar diagramas técnicos en HTML
- usar una skill para mejorar prompts antes de ejecutar tareas
- automatizar la documentación técnica de un proyecto de datos
- convertir conocimiento técnico en un documento Word estructurado

## Estructura

- [Teoría](./theory/README.md)
- [Práctica](./practice/README.md)

## Agenda sugerida para 1.5 horas

Esta agenda cubre el flujo principal del módulo. Los ejercicios de `Chrome`, `prompt-master` y `architecture-diagram-generator` pueden asignarse como extensión práctica adicional.

- 15 min: qué son las skills y por qué importan
- 10 min: cómo instalar y activar skills
- 20 min: preparar el contenido técnico del proyecto
- 25 min: generar el documento Word con la skill `docx`
- 10 min: instalar y probar el plugin `Chrome` en Codex
- 10 min: revisión final de resultados

## Mensaje clave

Una skill no reemplaza al agente: lo especializa. En un proyecto real, eso permite transformar tareas repetitivas y costosas, como documentar un pipeline, en procesos más rápidos, consistentes y reutilizables.
