# Módulo 13 - MCP para diagramación y modelado de datos

## Objetivo del módulo

Entender qué es MCP, cómo conecta agentes con herramientas externas y cómo aprovecharlo para resolver dos tareas muy útiles en ingeniería de datos:

- diseñar y diagramar arquitecturas técnicas
- leer tablas reales y proponer un modelo de datos

## Enfoque del módulo

Este módulo es principalmente práctico. La teoría introduce la arquitectura básica de MCP y su valor operativo. La práctica se centra en dos integraciones concretas:

- el MCP oficial de draw.io combinado con la skill `architecture-diagram-generator`
- el MCP de MySQL para inspeccionar tablas y generar un modelo de datos

Los ejercicios se trabajan tanto con **Codex** como con **Claude Code**.

## Resultados de aprendizaje

Al finalizar este módulo, el estudiante podrá:

- explicar qué es MCP y para qué sirve
- distinguir entre agente, cliente MCP y servidor MCP
- instalar un servidor MCP en Codex
- instalar un servidor MCP en Claude Code
- combinar una skill con una herramienta MCP en un mismo flujo
- usar draw.io MCP para diagramar una arquitectura técnica
- usar MySQL MCP para inspeccionar tablas reales
- generar un modelo de datos a partir de metadatos observados por el agente

## Estructura

- [Teoría](./theory/README.md)
- [Práctica](./practice/README.md)

## Agenda sugerida para 1.5 horas

Esta agenda cubre el flujo principal del módulo. Los cuatro ejercicios pueden distribuirse entre laboratorio guiado y trabajo complementario.

- 15 min: introducción conceptual a MCP
- 15 min: cómo se instala MCP en Codex y Claude Code
- 20 min: diseño de arquitectura con skill + draw.io MCP
- 20 min: inspección de tablas con MySQL MCP
- 20 min: revisión de entregables y comparación de resultados

## Mensaje clave

MCP vuelve al agente mucho más útil porque le permite operar con herramientas reales en lugar de limitarse a generar texto. Cuando además se combina con una skill especializada, el resultado puede pasar de una idea vaga a un diagrama técnico o a un modelo de datos mucho más sólido y reutilizable.
