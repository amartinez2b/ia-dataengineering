# Módulo 12 - Desarrollo de pipelines con IA

## Objetivo del módulo

Desarrollar un DAG de Airflow que orqueste el flujo de datos construido en el módulo 11, coordinando la ejecución de las capas `raw -> bronze -> silver -> gold` con ayuda de agentes de IA.

## Enfoque del módulo

Este módulo es principalmente práctico. La teoría introduce solo los conceptos mínimos de orquestación, dependencias, tareas y validación. El foco principal está en usar agentes de IA para diseñar, generar y ajustar un DAG real sobre un proyecto de ingeniería de datos.

## Resultados de aprendizaje

Al finalizar este módulo, el estudiante podrá:

- entender el rol de Airflow en un pipeline de datos
- modelar dependencias entre etapas técnicas
- usar agentes de IA para construir un DAG mantenible
- orquestar la ejecución de `bronze`, `silver` y `gold`
- validar el flujo del DAG antes de ejecutarlo en un entorno real

## Estructura

- [Teoría](./theory/README.md)
- [Práctica](./practice/README.md)

## Agenda sugerida para 1.5 horas

- 15 min: conceptos básicos de Airflow y DAGs
- 15 min: traducir el pipeline del módulo 11 a tareas orquestadas
- 20 min: diseño del DAG con agentes de IA
- 30 min: implementación y ajuste del DAG
- 10 min: validación del flujo y cierre

## Mensaje clave

Un pipeline no queda completo solo porque existan scripts PySpark. La orquestación permite controlar orden, dependencias, reintentos y consistencia operativa. La IA puede acelerar mucho la construcción del DAG, pero el diseño correcto de tareas y relaciones sigue siendo responsabilidad del ingeniero de datos.
