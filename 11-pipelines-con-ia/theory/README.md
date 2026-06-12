# Teoría - Módulo 12

## 1. ¿Qué resuelve Airflow en un proyecto de datos?

Cuando un proyecto de ingeniería de datos crece, ya no basta con tener scripts sueltos. Hace falta una herramienta que permita:

- definir el orden de ejecución
- controlar dependencias
- reintentar tareas fallidas
- monitorear corridas
- separar etapas del pipeline

Airflow resuelve justamente ese problema de orquestación.

## 2. ¿Qué es un DAG?

Un **DAG** es un grafo acíclico dirigido que representa tareas y sus dependencias.

En términos simples:

- cada nodo es una tarea
- las flechas indican el orden de ejecución
- no puede haber ciclos

Para este módulo, el DAG representará el flujo del proyecto del tema 11:

- ingestión a `bronze`
- limpieza a `silver`
- consolidación a `gold`

## 3. Cómo pensar un DAG a partir de un pipeline por capas

Una forma simple de modelarlo es:

1. una tarea o grupo de tareas para `raw -> bronze`
2. una tarea o grupo de tareas para `bronze -> silver`
3. una tarea final para `silver -> gold`

En proyectos reales, muchas veces conviene separar por tabla:

- `bronze_products`
- `bronze_sales`
- `bronze_shops`
- `silver_products`
- `silver_sales`
- `silver_shops`
- `gold_comercial`

## 4. Qué debe definir un DAG bien diseñado

Un DAG claro suele definir:

- identificador del DAG
- frecuencia o modo manual
- fecha de inicio
- tareas
- dependencias
- reintentos
- documentación mínima

## 5. Qué operadores pueden ser útiles

Para un laboratorio inicial no hace falta usar demasiada complejidad. Dependiendo del entorno, suelen bastar operadores como:

- `PythonOperator`
- `BashOperator`
- `EmptyOperator`

Lo importante en este módulo no es memorizar todos los operadores, sino aprender a representar correctamente el flujo del pipeline.

## 6. Qué pueden aportar los agentes de IA

Los agentes de IA pueden ayudar a:

- proponer la estructura base del DAG
- convertir scripts existentes en tareas orquestadas
- sugerir nombres claros para las tareas
- revisar dependencias
- detectar errores comunes en el código de Airflow
- explicar por qué una tarea debería depender de otra

## 7. Qué sigue siendo responsabilidad del estudiante

Aunque el DAG se construya con agentes de IA, el estudiante debe validar:

- si el orden de ejecución es correcto
- si las dependencias tienen sentido
- si no hay tareas innecesarias
- si la capa `gold` depende realmente de todas las tablas requeridas
- si el DAG refleja el pipeline real del proyecto

## 8. Flujo recomendado para trabajar con agentes

Un flujo útil para este módulo es:

1. resumir al agente el pipeline implementado en el tema 11
2. pedir una propuesta de DAG
3. validar tareas y dependencias
4. pedir el archivo Python del DAG
5. revisar el resultado
6. ajustar nombres, orden y estructura

## 9. Qué hace bueno a un prompt para construir un DAG

Conviene indicar:

- qué scripts o notebooks existen
- qué tareas deben orquestarse
- cuáles son las dependencias entre capas
- qué nombre debe tener el DAG
- si el flujo será manual o programado
- dónde debe guardarse el archivo

## 10. Qué se aprende realmente en este módulo

Más allá de escribir un archivo de Airflow, este módulo enseña:

- cómo traducir una lógica técnica a una secuencia operativa
- cómo separar tareas con criterio
- cómo validar dependencias antes de ejecutar
- cómo apoyarse en agentes para acelerar diseño y mantenimiento del pipeline

## 11. Ideas clave para llevarse

- Airflow no reemplaza la lógica de datos, la coordina
- un DAG bien diseñado hace visible el flujo real del pipeline
- la IA ayuda a generar estructura, pero el juicio humano define la correcta orquestación
- una buena orquestación vuelve el proyecto más reproducible y mantenible
