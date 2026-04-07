# Teoría - Módulo 11

## 1. ¿Por qué un proyecto PySpark asistido por agentes?

Un proyecto de ingeniería de datos tiene varias piezas que deben coordinarse:

- estructura de carpetas
- datasets de entrada
- notebooks exploratorios
- scripts de transformación
- capas de almacenamiento
- validaciones funcionales

Los agentes de IA ayudan a acelerar ese trabajo, especialmente cuando hay que leer un repositorio existente, entender su lógica y extenderlo de forma consistente.

## 2. Arquitectura por capas

En este módulo se usará una arquitectura tipo medallion:

- `raw`: datos tal como llegan desde la fuente
- `bronze`: datos ingeridos con estructura base y trazabilidad
- `silver`: datos limpiados, tipados y estandarizados
- `gold`: datos curados para consumo analítico o de negocio

Esta separación ayuda a:

- mantener trazabilidad
- aislar errores por etapa
- rehacer procesos sin perder la fuente original
- crear productos de datos más fáciles de consumir

## 3. Qué suele pasar en cada capa

### Raw a Bronze

En esta etapa normalmente se hace:

- lectura de archivos fuente
- copia a una zona controlada
- normalización mínima de nombres o rutas
- incorporación de metadatos de carga

### Bronze a Silver

En esta etapa normalmente se hace:

- limpieza de nulos
- tipado de columnas
- eliminación de duplicados
- estandarización de formatos
- validación de reglas básicas de calidad

### Silver a Gold

En esta etapa normalmente se hace:

- joins entre tablas
- enriquecimiento de datos
- cálculos de negocio
- generación de tablas finales orientadas a análisis

## 4. Scripts y notebooks no cumplen exactamente el mismo rol

En un proyecto de datos conviene diferenciar:

- **notebooks** para explorar, probar hipótesis y validar resultados rápidamente
- **scripts Python/PySpark** para consolidar la lógica que debe poder repetirse

Una buena práctica es:

1. explorar en notebook
2. estabilizar la lógica
3. mover la transformación principal a un script reutilizable
4. usar el notebook como evidencia, prueba o documentación del proceso

## 5. Qué pueden aportar los agentes de IA en este flujo

Los agentes pueden ayudar a:

- analizar la estructura del repositorio
- detectar dónde conviene crear nuevos archivos
- proponer código PySpark base
- refactorizar notebooks a scripts
- sugerir validaciones de calidad
- explicar errores de ejecución
- documentar pasos del pipeline

## 6. Qué sigue siendo responsabilidad del estudiante

Aunque todo el trabajo del laboratorio se hará con agentes de IA, el estudiante debe seguir validando:

- si los paths tienen sentido
- si los nombres de tablas son consistentes
- si la lógica de limpieza no rompe datos válidos
- si los joins son correctos
- si la capa `gold` responde a un objetivo de negocio claro

## 7. Flujo recomendado para trabajar con agentes

Un flujo útil para este módulo es:

1. pedir al agente que analice el repositorio
2. identificar datasets, notebooks y scripts ya existentes
3. diseñar el flujo por capas antes de escribir código
4. implementar una tabla a la vez
5. validar resultados parciales
6. consolidar la tabla final `comercial`

## 8. Qué hace bueno a un prompt para PySpark

Conviene indicar:

- objetivo de la transformación
- tabla de origen
- tabla destino
- reglas de limpieza
- formato esperado
- restricciones del proyecto
- archivo donde debe quedar el resultado

## 9. Qué se aprende realmente en este módulo

Más allá de escribir PySpark, este módulo enseña:

- cómo extender un repositorio de datos real
- cómo trabajar con ramas en un flujo de desarrollo asistido
- cómo combinar notebooks y scripts sin desorden
- cómo usar agentes para acelerar, sin delegar el juicio técnico

## 10. Ideas clave para llevarse

- una arquitectura por capas simplifica el razonamiento del pipeline
- los agentes ayudan más cuando el objetivo y las restricciones están claras
- notebooks y scripts deben complementarse, no competir
- la capa `gold` debe expresar valor de negocio, no solo transformación técnica
